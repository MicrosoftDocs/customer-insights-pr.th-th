---
title: โมเดล Machine Learning แบบกำหนดเอง | Microsoft Docs
description: ทำงานกับโมเดลที่กำหนดเองจาก Azure Machine Learning ใน Dynamics 365 Customer Insights
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305682"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="bcc53-103">โมเดล Machine Learning แบบกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="bcc53-103">Custom machine learning models</span></span>

<span data-ttu-id="bcc53-104">**ระบบอัจฉริยะ** > **โมเดลที่กำหนดเอง** ช่วยให้คุณสามารถจัดการเวิร์กโฟลว์โดยยึดตามโมเดล Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bcc53-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="bcc53-105">เวิร์กโฟลว์ช่วยให้คุณสามารถเลือกข้อมูลที่คุณต้องการสร้างข้อมูลเชิงลึกและจับคู่ผลลัพธ์กับข้อมูลลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="bcc53-106">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการสร้างโมเดล ML ที่กำหนดเอง โปรดดู [ใช้โมเดล Azure Machine Learning](azure-machine-learning-experiments.md)</span><span class="sxs-lookup"><span data-stu-id="bcc53-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="bcc53-107">AI ที่มีความรับผิดชอบ</span><span class="sxs-lookup"><span data-stu-id="bcc53-107">Responsible AI</span></span>

<span data-ttu-id="bcc53-108">การคาดคะเนนำเสนอความสามารถในการสร้างประสบการณ์ของลูกค้าที่ดียิ่งขึ้น ปรับปรุงความสามารถทางธุรกิจและกระแสรายได้</span><span class="sxs-lookup"><span data-stu-id="bcc53-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="bcc53-109">เราขอแนะนำงให้คุณสร้างสมดุลระหว่างมูลค่าการคาดคะเนของคุณกับผลกระทบที่มีและอคติที่อาจนำมาใช้ในลักษณะที่ถูกต้องตามหลักจริยธรรม</span><span class="sxs-lookup"><span data-stu-id="bcc53-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="bcc53-110">เรียนรู้เพิ่มเติมว่า Microsoft [จัดการ AI ที่มีความรับผิดชอบ](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) อย่างไร</span><span class="sxs-lookup"><span data-stu-id="bcc53-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="bcc53-111">คุณยังสามารถเรียนรู้เกี่ยวกับ [เทคนิคและกระบวนการสำหรับการเรียนรู้เกี่ยวกับเครื่องที่รับผิดชอบ](/azure/machine-learning/concept-responsible-ml) เฉพาะสำหรับ Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bcc53-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bcc53-112">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="bcc53-112">Prerequisites</span></span>

- <span data-ttu-id="bcc53-113">ปัจจุบัน คุณลักษณะนี้รองรับบริการเว็บที่เผยแพร่ผ่าน [Machine Learning Studio (คลาสสิก)](https://studio.azureml.net) และ [ไปป์ไลน์แบบชุดงานของ Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines)</span><span class="sxs-lookup"><span data-stu-id="bcc53-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="bcc53-114">คุณต้องมีบัญชีที่เก็บข้อมูล Azure Data Lake รุ่น2 ที่เชื่อมโยงกับอินสแตนซ์ Azure Studio ของคุณเพื่อใช้คุณลักษณะนี้</span><span class="sxs-lookup"><span data-stu-id="bcc53-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="bcc53-115">สำหรับข้อมูลเพิ่มเติม ดูที่ [สร้างบัญชีที่เก็บข้อมูล Gen2 Azure Data Lake Storage](/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="bcc53-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="bcc53-116">สำหรับพื้นที่ทำงาน Azure Machine Learning ที่มีไปป์ไลน์ คุณต้องมีสิทธิ์ของผู้ดูแลระบบแบบผู้ใช้หรือการเข้าถึงของผู้ใช้สำหรับพื้นที่ทำงาน Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bcc53-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcc53-117">ข้อมูลจะถูกถ่ายโอนระหว่างอินสแตนซ์ Customer Insights ของคุณและบริการเว็บ Azure ที่เลือกหรือไปป์ไลน์ในเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="bcc53-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="bcc53-118">เมื่อคุณถ่ายโอนข้อมูลไปยังบริการ Azure โปรดตรวจสอบให้แน่ใจว่าบริการได้รับการกําหนดค่าให้ประมวลผลข้อมูลในลักษณะและตําแหน่งที่ตั้งที่จําเป็นเพื่อให้สอดคล้องกับข้อกําหนดทางกฎหมายหรือข้อบังคับสําหรับข้อมูลนั้นสําหรับองค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="bcc53-119">เพิ่มเวิร์กโฟลว์ใหม่</span><span class="sxs-lookup"><span data-stu-id="bcc53-119">Add a new workflow</span></span>

1. <span data-ttu-id="bcc53-120">ไปที่ **ระบบอัจฉริยะ** > **โมเดลที่กำหนดเอง** และเลือก **เวิร์กโฟลว์ใหม่**</span><span class="sxs-lookup"><span data-stu-id="bcc53-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="bcc53-121">ตั้งชื่อโมเดลที่กำหนดเองที่เป็นที่รู้จักของคุณในฟิลด์ **ชื่อ**</span><span class="sxs-lookup"><span data-stu-id="bcc53-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcc53-122">![ภาพหน้าจอของบานหน้าต่างเวิร์กโฟลว์ใหม่](media/new-workflowv2.png "ภาพหน้าจอของบานหน้าต่างเวิร์กโฟลว์ใหม่")</span><span class="sxs-lookup"><span data-stu-id="bcc53-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="bcc53-123">เลือกองค์กรที่มี Web Service ใน **ผู้เช่าที่มี Web Service ของคุณ**</span><span class="sxs-lookup"><span data-stu-id="bcc53-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="bcc53-124">หากการสมัครใช้งาน Azure Machine Learning ของคุณอยู่ในผู้เช่ารายอื่นที่ไม่ใช่ Customer Insights ให้เลือก **ลงชื่อเข้าใช้** ด้วยข้อมูลประจำตัวของคุณสำหรับองค์กรที่เลือก</span><span class="sxs-lookup"><span data-stu-id="bcc53-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="bcc53-125">เลือก **พื้นที่ทำงาน** ที่เชื่อมโยงกับบริการเว็บของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="bcc53-126">มีสองส่วนในรายการ ส่วนหนึ่งสำหรับ Azure Machine Learning v1 (Machine Learning Studio (คลาสสิก)) และ Azure Machine Learning v2 (Azure Machine Learning)</span><span class="sxs-lookup"><span data-stu-id="bcc53-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="bcc53-127">หากคุณไม่แน่ใจว่าพื้นที่ทำงานใดเหมาะกับบริการเว็บ Machine Learning Studio (คลาสสิก) ของคุณให้เลือก **ใดๆ**</span><span class="sxs-lookup"><span data-stu-id="bcc53-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="bcc53-128">เลือกบริการเว็บ Machine Learning Studio (คลาสสิก) หรือไปป์ไลน์ Azure Machine Learning ในรายการแบบหล่นลง **บริการเว็บที่มีโมเดลของคุณ**</span><span class="sxs-lookup"><span data-stu-id="bcc53-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="bcc53-129">จากนั้นเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="bcc53-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="bcc53-130">เรียนรู้เพิ่มเติมเกี่ยวกับ [การเผยแพร่บริการเว็บใน Machine Learning Studio (คลาสสิก)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="bcc53-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="bcc53-131">เรียนรู้เพิ่มเติมเกี่ยวกับ [การเผยแพร่ไปป์ไลน์ใน Azure Machine Learning โดยใช้ตัวออกแบบ](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) หรือ [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk)</span><span class="sxs-lookup"><span data-stu-id="bcc53-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="bcc53-132">ไปป์ไลน์ของคุณต้องเผยแพร่ภายใต้ [จุดสิ้นสุดไปป์ไลน์](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)</span><span class="sxs-lookup"><span data-stu-id="bcc53-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="bcc53-133">สำหรับ **การป้อนข้อมูลบริการเว็บ** แต่ละรายการ ให้เลือก **เอนทิตี** ที่ตรงกันจากข้อมูลเชิงลึกกลุ่มเป้าหมาย และเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="bcc53-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bcc53-134">เวิร์กโฟลว์ของโมเดลแบบกำหนดเองจะใช้วิทยาการศึกษาสำนึกเพื่อแม็ปฟิลด์ข้อมูลป้อนเข้าของ Web Service กับแอตทริบิวต์เอนทิตีตามชื่อและชนิดข้อมูลของฟิลด์</span><span class="sxs-lookup"><span data-stu-id="bcc53-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="bcc53-135">คุณจะเห็นข้อผิดพลาด หากไม่สามารถแม็ปฟิลด์ Web Service กับเอนทิตีได้</span><span class="sxs-lookup"><span data-stu-id="bcc53-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcc53-136">![กำหนดค่าเวิร์กโฟลว์](media/intelligence-screen2-updated.png "กำหนดค่าเวิร์กโฟลว์")</span><span class="sxs-lookup"><span data-stu-id="bcc53-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="bcc53-137">ในขั้นตอน **พารามิเตอร์ผลลัพธ์ของโมเดล** ให้ตั้งค่าคุณสมบัติต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="bcc53-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bcc53-138">Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="bcc53-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bcc53-139">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของบริการเว็บเข้ามา</span><span class="sxs-lookup"><span data-stu-id="bcc53-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bcc53-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bcc53-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bcc53-141">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของไปป์ไลน์เข้ามา</span><span class="sxs-lookup"><span data-stu-id="bcc53-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bcc53-142">เลือก **ชื่อพารามิเตอร์ที่เก็บข้อมูลผลลัพธ์** ของไปป์ไลน์แบบชุดงานของคุณจากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="bcc53-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="bcc53-143">เลือก **ชื่อพารามิเตอร์พาธผลลัพธ์** ของไปป์ไลน์แบบชุดงานของคุณจากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="bcc53-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bcc53-144">![บานหน้าต่างพารามิเตอร์ผลลัพธ์ของโมเดล](media/intelligence-screen3-outputparameters.png "บานหน้าต่างพารามิเตอร์ผลลัพธ์ของโมเดล")</span><span class="sxs-lookup"><span data-stu-id="bcc53-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="bcc53-145">เลือกแอตทริบิวต์ที่ตรงกันจากรายการแบบหล่นลง **รหัสลูกค้าในผลลัพธ์** ที่ระบุลูกค้า และเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="bcc53-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcc53-146">![บานหน้าต่างเชื่อมโยงผลลัพธ์กับข้อมูลลูกค้า](media/intelligence-screen4-relatetocustomer.png "บานหน้าต่างเชื่อมโยงผลลัพธ์กับข้อมูลลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="bcc53-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="bcc53-147">คุณจะเห็นหน้าจอ **เวิร์กโฟลว์ที่บันทึกไว้** พร้อมรายละเอียดเกี่ยวกับเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="bcc53-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="bcc53-148">ถ้าคุณกำหนดค่าเวิร์กโฟลว์สำหรับไปป์ไลน์ Azure Machine Learning, ข้อมูลเชิงลึกกลุ่มเป้าหมายจะแนบไปกับพื้นที่ทำงานที่มีไปป์ไลน์</span><span class="sxs-lookup"><span data-stu-id="bcc53-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="bcc53-149">ข้อมูลเชิงลึกกลุ่มเป้าหมายจะได้รับบทบาท **ผู้มีส่วนร่วม** ในพื้นที่ทำงาน Azure</span><span class="sxs-lookup"><span data-stu-id="bcc53-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="bcc53-150">เลือก **สำเร็จ**</span><span class="sxs-lookup"><span data-stu-id="bcc53-150">Select **Done**.</span></span>

1. <span data-ttu-id="bcc53-151">ตอนนี้คุณสามารถเรียกใช้เวิร์กโฟลว์จากเพจ **โมเดลที่กำหนดเอง** ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="bcc53-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="bcc53-152">แก้ไขเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="bcc53-152">Edit a workflow</span></span>

1. <span data-ttu-id="bcc53-153">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้ และเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="bcc53-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="bcc53-154">คุณสามารถปรับปรุงชื่อที่จำได้ของเวิร์กโฟลว์ของคุณในฟิลด์ **ชื่อที่แสดง** แต่คุณไม่สามารถเปลี่ยนบริการเว็บหรือไปป์ไลน์ที่กำหนดค่าได้</span><span class="sxs-lookup"><span data-stu-id="bcc53-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="bcc53-155">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="bcc53-155">Select **Next**.</span></span>

1. <span data-ttu-id="bcc53-156">สำหรับ **การป้อนข้อมูลบริการเว็บ** แต่ละรายการ คุณสามารถปรับปรุง **เอนทิตี** ที่ตรงกันจากข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="bcc53-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="bcc53-157">จากนั้นเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="bcc53-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="bcc53-158">ในขั้นตอน **พารามิเตอร์ผลลัพธ์ของโมเดล** ให้ตั้งค่าคุณสมบัติต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="bcc53-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bcc53-159">Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="bcc53-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bcc53-160">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของบริการเว็บเข้ามา</span><span class="sxs-lookup"><span data-stu-id="bcc53-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bcc53-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bcc53-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bcc53-162">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของไปป์ไลน์เข้ามา</span><span class="sxs-lookup"><span data-stu-id="bcc53-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bcc53-163">เลือก **ชื่อพารามิเตอร์ที่เก็บข้อมูลผลลัพธ์** สำหรับไปป์ไลน์ทดสอบของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="bcc53-164">เลือก **ชื่อพารามิเตอร์พาธผลลัพธ์** สำหรับไปป์ไลน์ทดสอบของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="bcc53-165">เลือกแอตทริบิวต์ที่ตรงกันจากรายการแบบหล่นลง **รหัสลูกค้าในผลลัพธ์** ที่ระบุลูกค้า และเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="bcc53-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="bcc53-166">เลือกแอตทริบิวต์จากผลลัพธ์การอนุมานที่มีค่าเหมือนกับคอลัมน์รหัสลูกค้าของเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="bcc53-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="bcc53-167">หากไม่มีคอลัมน์ดังกล่าวในชุดข้อมูลของคุณ ให้เลือกแอตทริบิวต์ที่ระบุแถวโดยไม่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="bcc53-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="bcc53-168">เรียกใช้เวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="bcc53-168">Run a workflow</span></span>

1. <span data-ttu-id="bcc53-169">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้</span><span class="sxs-lookup"><span data-stu-id="bcc53-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bcc53-170">เลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="bcc53-170">Select **Run**.</span></span>

<span data-ttu-id="bcc53-171">นอกจากนี้ เวิร์กโฟลว์ของคุณจะทำงานโดยอัตโนมัติพร้อมการรีเฟรชตามกำหนดการทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="bcc53-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="bcc53-172">เรียนรู้เพิ่มเติมเกี่ยวกับ [การตั้งค่าการรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="bcc53-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="bcc53-173">ลบเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="bcc53-173">Delete a workflow</span></span>

1. <span data-ttu-id="bcc53-174">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้</span><span class="sxs-lookup"><span data-stu-id="bcc53-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bcc53-175">เลือก **ลบ** และยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="bcc53-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="bcc53-176">เวิร์กโฟลว์ของคุณจะถูกลบ</span><span class="sxs-lookup"><span data-stu-id="bcc53-176">Your workflow will be deleted.</span></span> <span data-ttu-id="bcc53-177">[เอนทิตี](entities.md) ที่ถูกสร้างขึ้นเมื่อคุณสร้างเวิร์กโฟลว์ ยังคงอยู่ และสามารถดูได้จากหน้า **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="bcc53-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="bcc53-178">ผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="bcc53-178">Results</span></span>

<span data-ttu-id="bcc53-179">ผลลัพธ์ที่ได้จากเวิร์กโฟลว์จะเก็บไว้ในเอนทิตีที่กำหนดค่าไว้ในระยะพารามิเตอร์ผลลัพธ์ของโมเดล</span><span class="sxs-lookup"><span data-stu-id="bcc53-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="bcc53-180">คุณสามารถเข้าถึงข้อมูลนี้ได้จาก [เพจเอนทิตี](entities.md) หรือด้วย [การเข้าถึง API](apis.md)</span><span class="sxs-lookup"><span data-stu-id="bcc53-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="bcc53-181">การเข้าถึง API</span><span class="sxs-lookup"><span data-stu-id="bcc53-181">API Access</span></span>

<span data-ttu-id="bcc53-182">สำหรับการสอบถาม OData เฉพาะเพื่อรับข้อมูลจากเอนทิตีโมเดลที่กำหนดเอง ให้ใช้รูปแบบต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="bcc53-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="bcc53-183">แทนที่ `<your instance id>` ด้วยรหัสของสภาพแวดล้อม Customer Insights ซึ่งคุณพบในแถบที่อยู่ของเบราว์เซอร์ของคุณเมื่อเข้าถึง Customer Insights</span><span class="sxs-lookup"><span data-stu-id="bcc53-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="bcc53-184">แทนที่ `<custom model output entity>` ด้วยชื่อเอนทิตีที่คุณระบุในขั้นตอนพารามิเตอร์ผลลัพธ์ของโมเดลของการกำหนดค่าโมเดลที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="bcc53-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="bcc53-185">แทนที่ `<guid value>` ด้วยรหัสลูกค้าของลูกค้าที่คุณต้องการเข้าถึงเรกคอร์ด</span><span class="sxs-lookup"><span data-stu-id="bcc53-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="bcc53-186">โดยปกติ คุณจะพบรหัสนี้ใน [เพจโปรไฟล์ลูกค้า](customer-profiles.md) ในฟิลด์ CustomerID</span><span class="sxs-lookup"><span data-stu-id="bcc53-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bcc53-187">คำถามที่ถามบ่อย</span><span class="sxs-lookup"><span data-stu-id="bcc53-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="bcc53-188">เหตุใดฉันจึงไม่เห็นไปป์ไลน์ของฉันเมื่อตั้งค่าเวิร์กโฟลว์โมเดลที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="bcc53-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="bcc53-189">ปัญหานี้มักเกิดจากปัญหาการกำหนดค่าในไปป์ไลน์</span><span class="sxs-lookup"><span data-stu-id="bcc53-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="bcc53-190">ตรวจสอบให้แน่ใจว่า [มีการกำหนดค่าพารามิเตอร์ค่าที่ป้อน](azure-machine-learning-experiments.md#dataset-configuration) และ [พารามิเตอร์ที่เก็บข้อมูลและพาธของผลลัพธ์](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) ได้รับการกำหนดค่าแล้วด้วย</span><span class="sxs-lookup"><span data-stu-id="bcc53-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="bcc53-191">ข้อผิดพลาด "ไม่สามารถบันทึกเวิร์กโฟลว์ระบบอัจฉริยะ" หมายความว่าอย่างไร</span><span class="sxs-lookup"><span data-stu-id="bcc53-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="bcc53-192">ผู้ใช้มักจะเห็นข้อความแสดงข้อผิดพลาดนี้หากไม่มีสิทธิ์การใช้งานของผู้ดูแลระบบแบบเจ้าของหรือการเข้าถึงของผู้ใช้ในพื้นที่ทำงาน</span><span class="sxs-lookup"><span data-stu-id="bcc53-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="bcc53-193">ผู้ใช้ต้องการสิทธิ์ในระดับที่สูงขึ้นเพื่อเปิดใช้งาน Customer Insights ที่จะประมวลผลเวิร์กโฟลว์เป็นบริการ แทนที่จะใช้ข้อมูลประจำตัวของผู้ใช้สำหรับการเรียกใช้เวิร์กโฟลว์ในภายหลัง</span><span class="sxs-lookup"><span data-stu-id="bcc53-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
