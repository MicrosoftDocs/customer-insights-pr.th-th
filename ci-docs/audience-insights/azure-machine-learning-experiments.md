---
title: การทดลองของ Azure Machine Learning
description: ใช้โมเดลของ Azure Machine Learning ใน Dynamics 365 Customer Insights
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267929"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="12c5b-103">ใช้โมเดลของ Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="12c5b-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="12c5b-104">ข้อมูลที่รวมเข้าด้วยกันใน Dynamics 365 Customer Insights เป็นแหล่งที่มาสำหรับการสร้างโมเดลการเรียนรู้เกี่ยวกับเครื่องที่สามารถสร้างข้อมูลเชิงลึกทางธุรกิจเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="12c5b-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="12c5b-105">Customer Insights ผสานรวมกับ Machine Learning Studio (คลาสสิก) และ Azure Machine Learning เพื่อใช้โมเดลที่คุณกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="12c5b-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="12c5b-106">ดูที่ [การทดลองของ Machine Learning Studio (คลาสสิก)](machine-learning-studio-experiments.md) สำหรับตัวอย่างการทดลองที่สร้างใน Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="12c5b-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="12c5b-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="12c5b-107">Prerequisites</span></span>

- <span data-ttu-id="12c5b-108">เข้าสู่ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="12c5b-108">Access to Customer Insights</span></span>
- <span data-ttu-id="12c5b-109">การสมัครใช้งาน Azure Enterprise ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="12c5b-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="12c5b-110">โปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="12c5b-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="12c5b-111">[การส่งออกเอนทิตีไปยังที่เก็บข้อมูล Azure Blob](export-azure-blob-storage.md) ที่กำหนดค่าแล้ว</span><span class="sxs-lookup"><span data-stu-id="12c5b-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="12c5b-112">ตั้งค่าพื้นที่ทำงานของ Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="12c5b-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="12c5b-113">ดู [สร้างพื้นที่ทำงานของ Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) สำหรับตัวเลือกต่างๆ ในการสร้างพื้นที่ทำงาน</span><span class="sxs-lookup"><span data-stu-id="12c5b-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="12c5b-114">เพื่อประสิทธิภาพที่ดีที่สุด ให้สร้างพื้นที่ทำงานในภูมิภาค Azure ที่ตั้งอยู่ใกล้เคียงกับสภาพแวดล้อม Customer Insights ของคุณมากที่สุด</span><span class="sxs-lookup"><span data-stu-id="12c5b-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="12c5b-115">เข้าถึงพื้นที่ทำงานของคุณผ่าน [Azure Machine Learning Studio](https://ml.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="12c5b-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="12c5b-116">[วิธีการทำงาน](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) กับพื้นที่ทำงานของคุณมีหลายวิธี</span><span class="sxs-lookup"><span data-stu-id="12c5b-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="12c5b-117">ทำงานกับตัวออกแบบ Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="12c5b-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="12c5b-118">ตัวออกแบบ Azure Machine Learning มีพื้นที่ทำงานของภาพที่คุณสามารถลากและวางชุดข้อมูลและโมดูล ซึ่งคล้ายกับ Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="12c5b-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="12c5b-119">ไปป์ไลน์ชุดงานที่สร้างจากตัวออกแบบสามารถรวมเข้ากับ Customer Insights ได้หากมีการกำหนดค่าตามนั้น</span><span class="sxs-lookup"><span data-stu-id="12c5b-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="12c5b-120">การทำงานกับ Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="12c5b-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="12c5b-121">นักวิทยาศาสตร์ข้อมูลและนักพัฒนา AI ใช้ [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) เพื่อสร้างเวิร์กโฟลว์การเรียนรู้เกี่ยวกับเครื่อง</span><span class="sxs-lookup"><span data-stu-id="12c5b-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="12c5b-122">ขณะนี้ โมเดลที่ฝึกโดยใช้ SDK ไม่สามารถรวมเข้ากับ Customer Insights ได้โดยตรง</span><span class="sxs-lookup"><span data-stu-id="12c5b-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="12c5b-123">ไปป์ไลน์การอนุมานแบบชุดงานที่ใช้โมเดลนั้นจำเป็นสำหรับการผสานรวมกับ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="12c5b-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="12c5b-124">ข้อกำหนดไปป์ไลน์แบบชุดงานที่จะรวมเข้ากับ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="12c5b-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="12c5b-125">การกำหนดค่าชุดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="12c5b-125">Dataset Configuration</span></span>

<span data-ttu-id="12c5b-126">คุณต้องสร้างชุดข้อมูลเพื่อใช้ข้อมูลเอนทิตีจาก Customer Insights กับไปป์ไลน์การอนุมานแบบชุดงานของคุณ</span><span class="sxs-lookup"><span data-stu-id="12c5b-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="12c5b-127">ต้องลงทะเบียนชุดข้อมูลเหล่านี้ในพื้นที่ทำงาน</span><span class="sxs-lookup"><span data-stu-id="12c5b-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="12c5b-128">ขณะนี้เรารองรับ [ชุดข้อมูลแบบตาราง](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ในรูปแบบ .csv เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="12c5b-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="12c5b-129">ชุดข้อมูลที่สอดคล้องกับข้อมูลเอนทิตีจำเป็นต้องกำหนดพารามิเตอร์เป็นพารามิเตอร์ไปป์ไลน์</span><span class="sxs-lookup"><span data-stu-id="12c5b-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="12c5b-130">ชุดข้อมูลพารามิเตอร์ในตัวออกแบบ</span><span class="sxs-lookup"><span data-stu-id="12c5b-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="12c5b-131">ในตัวออกแบบ ให้เปิด **เลือกคอลัมน์ในชุดข้อมูล** และเลือก **ตั้งเป็นพารามิเตอร์ไปป์ไลน์** ที่คุณระบุชื่อสำหรับพารามิเตอร์</span><span class="sxs-lookup"><span data-stu-id="12c5b-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="12c5b-132">![การกำหนดพารามิเตอร์ชุดข้อมูลในตัวออกแบบ](media/intelligence-designer-dataset-parameters.png "การกำหนดพารามิเตอร์ชุดข้อมูลในตัวออกแบบ")</span><span class="sxs-lookup"><span data-stu-id="12c5b-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="12c5b-133">พารามิเตอร์ชุดข้อมูลใน SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="12c5b-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="12c5b-134">ไปป์ไลน์การอนุมานแบบชุดงาน</span><span class="sxs-lookup"><span data-stu-id="12c5b-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="12c5b-135">ในตัวออกแบบ สามารถใช้ไปป์ไลน์การฝึกเพื่อสร้างหรือปรับปรุงไปป์ไลน์การอนุมานได้</span><span class="sxs-lookup"><span data-stu-id="12c5b-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="12c5b-136">ขณะนี้รองรับเฉพาะไปป์ไลน์การอนุมานแบบชุดงานเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="12c5b-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="12c5b-137">เมื่อใช้ SDK คุณสามารถเผยแพร่ไปป์ไลน์ไปยังจุดสิ้นสุดได้</span><span class="sxs-lookup"><span data-stu-id="12c5b-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="12c5b-138">ปัจจุบัน Customer Insights รวมเข้ากับไปป์ไลน์เริ่มต้นในจุดสิ้นสุดไปป์ไลน์แบบชุดงานในพื้นที่ทำงาน Machine Learning</span><span class="sxs-lookup"><span data-stu-id="12c5b-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="12c5b-139">นำเข้าข้อมูลไปป์ไลน์ไปยัง Customer Insights</span><span class="sxs-lookup"><span data-stu-id="12c5b-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="12c5b-140">ผู้ออกแบบมี [โมดูลส่งออกข้อมูล](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) ที่อนุญาตให้ส่งออกผลลัพธ์ของไปป์ไลน์ไปยังที่เก็บข้อมูล Azure</span><span class="sxs-lookup"><span data-stu-id="12c5b-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="12c5b-141">ปัจจุบัน โมดูลดังกล่าวต้องใช้ที่เก็บข้อมูลชนิด **ที่เก็บข้อมูล Azure Blob** และกำหนดพารามิเตอร์ **ที่เก็บข้อมูล** และ **พาธ** แบบสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="12c5b-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="12c5b-142">Customer Insights จะแทนที่พารามิเตอร์ทั้งคู่นี้ในระหว่างการดำเนินการไปป์ไลน์กับที่เก็บข้อมูลและพาธที่สามารถเข้าถึงไปยังผลิตภัณฑ์</span><span class="sxs-lookup"><span data-stu-id="12c5b-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12c5b-143">![การกำหนดค่าโมดูลส่งออกข้อมูล](media/intelligence-designer-importdata.png "การกำหนดค่าโมดูลส่งออกข้อมูล")</span><span class="sxs-lookup"><span data-stu-id="12c5b-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="12c5b-144">เมื่อเขียนผลลัพธ์การอนุมานโดยใช้โค้ด คุณสามารถอัปโหลดผลลัพธ์ไปยังพาธภายใน *ที่เก็บข้อมูลที่ลงทะเบียน* ในพื้นที่ทำงาน</span><span class="sxs-lookup"><span data-stu-id="12c5b-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="12c5b-145">หากพาธและที่เก็บข้อมูลมีการกำหนดพารามิเตอร์ในไปป์ไลน์ Customer insights จะสามารถอ่านและนำเข้าเอาต์พุตการอนุมานได้</span><span class="sxs-lookup"><span data-stu-id="12c5b-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="12c5b-146">ปัจจุบันรองรับผลลัพธ์แบบตารางเดียวในรูปแบบ csv เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="12c5b-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="12c5b-147">พาธต้องมีไดเรกทอรีและชื่อไฟล์</span><span class="sxs-lookup"><span data-stu-id="12c5b-147">The path must include the directory and filename.</span></span>

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