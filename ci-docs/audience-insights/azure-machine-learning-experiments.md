---
title: การทดลองของ Azure Machine Learning
description: ใช้โมเดลของ Azure Machine Learning ใน Dynamics 365 Customer Insights
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c3bed3dca40be748140a8b339191e6a42725714
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228911"
---
# <a name="use-azure-machine-learning-based-models"></a>ใช้โมเดลของ Azure Machine Learning

ข้อมูลที่รวมเข้าด้วยกันใน Dynamics 365 Customer Insights เป็นแหล่งที่มาสำหรับการสร้างโมเดลการเรียนรู้เกี่ยวกับเครื่องที่สามารถสร้างข้อมูลเชิงลึกทางธุรกิจเพิ่มเติม Customer Insights ผสานรวมกับ Azure Machine Learning เพื่อใช้โมเดลที่คุณกำหนดเอง

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- เข้าสู่ Customer Insights
- การสมัครใช้งาน Azure Enterprise ที่ใช้งานอยู่
- [โปรไฟล์ลูกค้าแบบรวม](data-unification.md)
- [การส่งออกเอนทิตีไปยังที่เก็บข้อมูล Azure Blob](export-azure-blob-storage.md) ที่กำหนดค่าแล้ว

## <a name="set-up-azure-machine-learning-workspace"></a>ตั้งค่าพื้นที่ทำงานของ Azure Machine Learning

1. ดู [สร้างพื้นที่ทำงานของ Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) สำหรับตัวเลือกต่างๆ ในการสร้างพื้นที่ทำงาน เพื่อประสิทธิภาพที่ดีที่สุด ให้สร้างพื้นที่ทำงานในภูมิภาค Azure ที่ตั้งอยู่ใกล้เคียงกับสภาพแวดล้อม Customer Insights ของคุณมากที่สุด

1. เข้าถึงพื้นที่ทำงานของคุณผ่าน [Azure Machine Learning Studio](https://ml.azure.com/) [วิธีการทำงาน](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) กับพื้นที่ทำงานของคุณมีหลายวิธี

## <a name="work-with-azure-machine-learning-designer"></a>ทำงานกับตัวออกแบบ Azure Machine Learning

ตัวออกแบบ Azure Machine Learning มีพื้นที่ทำงานการแสดงผลด้วยภาพที่คุณสามารถลากและวางชุดข้อมูลและโมดูลต่างๆ ไปป์ไลน์ชุดงานที่สร้างจากตัวออกแบบสามารถรวมเข้ากับ Customer Insights ได้หากมีการกำหนดค่าตามนั้น 
   
## <a name="working-with-azure-machine-learning-sdk"></a>การทำงานกับ Azure Machine Learning SDK

นักวิทยาศาสตร์ข้อมูลและนักพัฒนา AI ใช้ [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) เพื่อสร้างเวิร์กโฟลว์การเรียนรู้เกี่ยวกับเครื่อง ขณะนี้ โมเดลที่ฝึกโดยใช้ SDK ไม่สามารถรวมเข้ากับ Customer Insights ได้โดยตรง ไปป์ไลน์การอนุมานแบบชุดงานที่ใช้โมเดลนั้นจำเป็นสำหรับการผสานรวมกับ Customer Insights

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>ข้อกำหนดไปป์ไลน์แบบชุดงานที่จะรวมเข้ากับ Customer Insights

### <a name="dataset-configuration"></a>การกำหนดค่าชุดข้อมูล

คุณต้องสร้างชุดข้อมูลเพื่อใช้ข้อมูลเอนทิตีจาก Customer Insights กับไปป์ไลน์การอนุมานแบบชุดงานของคุณ ต้องลงทะเบียนชุดข้อมูลเหล่านี้ในพื้นที่ทำงาน ขณะนี้เรารองรับ [ชุดข้อมูลแบบตาราง](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ในรูปแบบ .csv เท่านั้น ชุดข้อมูลที่สอดคล้องกับข้อมูลเอนทิตีจำเป็นต้องกำหนดพารามิเตอร์เป็นพารามิเตอร์ไปป์ไลน์
   
* ชุดข้อมูลพารามิเตอร์ในตัวออกแบบ
   
     ในตัวออกแบบ ให้เปิด **เลือกคอลัมน์ในชุดข้อมูล** และเลือก **ตั้งเป็นพารามิเตอร์ไปป์ไลน์** ที่คุณระบุชื่อสำหรับพารามิเตอร์

     > [!div class="mx-imgBorder"]
     > ![การกำหนดพารามิเตอร์ชุดข้อมูลในตัวออกแบบ](media/intelligence-designer-dataset-parameters.png "การกำหนดพารามิเตอร์ชุดข้อมูลในตัวออกแบบ")
   
* พารามิเตอร์ชุดข้อมูลใน SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>ไปป์ไลน์การอนุมานแบบชุดงาน
  
* ในตัวออกแบบ สามารถใช้ไปป์ไลน์การฝึกเพื่อสร้างหรือปรับปรุงไปป์ไลน์การอนุมานได้ ขณะนี้รองรับเฉพาะไปป์ไลน์การอนุมานแบบชุดงานเท่านั้น

* เมื่อใช้ SDK คุณสามารถเผยแพร่ไปป์ไลน์ไปยังจุดสิ้นสุดได้ ปัจจุบัน Customer Insights รวมเข้ากับไปป์ไลน์เริ่มต้นในจุดสิ้นสุดไปป์ไลน์แบบชุดงานในพื้นที่ทำงาน Machine Learning
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>นำเข้าข้อมูลไปป์ไลน์ไปยัง Customer Insights

* ผู้ออกแบบมี [โมดูลส่งออกข้อมูล](/azure/machine-learning/algorithm-module-reference/export-data) ที่อนุญาตให้ส่งออกผลลัพธ์ของไปป์ไลน์ไปยังที่เก็บข้อมูล Azure ปัจจุบัน โมดูลดังกล่าวต้องใช้ที่เก็บข้อมูลชนิด **ที่เก็บข้อมูล Azure Blob** และกำหนดพารามิเตอร์ **ที่เก็บข้อมูล** และ **พาธ** แบบสัมพันธ์ Customer Insights จะแทนที่พารามิเตอร์ทั้งคู่นี้ในระหว่างการดำเนินการไปป์ไลน์กับที่เก็บข้อมูลและพาธที่สามารถเข้าถึงไปยังผลิตภัณฑ์
   > [!div class="mx-imgBorder"]
   > ![การกำหนดค่าโมดูลส่งออกข้อมูล](media/intelligence-designer-importdata.png "การกำหนดค่าโมดูลส่งออกข้อมูล")
   
* เมื่อเขียนผลลัพธ์การอนุมานโดยใช้โค้ด คุณสามารถอัปโหลดผลลัพธ์ไปยังพาธภายใน *ที่เก็บข้อมูลที่ลงทะเบียน* ในพื้นที่ทำงาน หากพาธและที่เก็บข้อมูลมีการกำหนดพารามิเตอร์ในไปป์ไลน์ Customer insights จะสามารถอ่านและนำเข้าเอาต์พุตการอนุมานได้ ปัจจุบันรองรับผลลัพธ์แบบตารางเดียวในรูปแบบ csv เท่านั้น พาธต้องมีไดเรกทอรีและชื่อไฟล์

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]