---
title: โมเดล Machine Learning แบบกำหนดเอง | Microsoft Docs
description: ทำงานกับโมเดลที่กำหนดเองจาก Azure Machine Learning ใน Dynamics 365 Customer Insights
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267257"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="4ffbb-103">โมเดล Machine Learning แบบกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="4ffbb-103">Custom machine learning models</span></span>

<span data-ttu-id="4ffbb-104">**ระบบอัจฉริยะ** > **โมเดลที่กำหนดเอง** ช่วยให้คุณสามารถจัดการเวิร์กโฟลว์โดยยึดตามโมเดล Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4ffbb-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="4ffbb-105">เวิร์กโฟลว์ช่วยให้คุณสามารถเลือกข้อมูลที่คุณต้องการสร้างข้อมูลเชิงลึกและจับคู่ผลลัพธ์กับข้อมูลลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="4ffbb-106">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการสร้างโมเดล ML ที่กำหนดเอง โปรดดู [ใช้โมเดล Azure Machine Learning](azure-machine-learning-experiments.md)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="4ffbb-107">AI ที่มีความรับผิดชอบ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-107">Responsible AI</span></span>

<span data-ttu-id="4ffbb-108">การคาดคะเนนำเสนอความสามารถในการสร้างประสบการณ์ของลูกค้าที่ดียิ่งขึ้น ปรับปรุงความสามารถทางธุรกิจและกระแสรายได้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="4ffbb-109">เราขอแนะนำงให้คุณสร้างสมดุลระหว่างมูลค่าการคาดคะเนของคุณกับผลกระทบที่มีและอคติที่อาจนำมาใช้ในลักษณะที่ถูกต้องตามหลักจริยธรรม</span><span class="sxs-lookup"><span data-stu-id="4ffbb-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="4ffbb-110">เรียนรู้เพิ่มเติมว่า Microsoft [จัดการ AI ที่มีความรับผิดชอบ](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) อย่างไร</span><span class="sxs-lookup"><span data-stu-id="4ffbb-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="4ffbb-111">คุณยังสามารถเรียนรู้เกี่ยวกับ [เทคนิคและกระบวนการสำหรับการเรียนรู้เกี่ยวกับเครื่องที่รับผิดชอบ](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) เฉพาะสำหรับ Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4ffbb-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ffbb-112">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="4ffbb-112">Prerequisites</span></span>

- <span data-ttu-id="4ffbb-113">ปัจจุบัน คุณลักษณะนี้รองรับบริการเว็บที่เผยแพร่ผ่าน [Machine Learning Studio (คลาสสิก)](https://studio.azureml.net) และ [ไปป์ไลน์แบบชุดงานของ Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="4ffbb-114">คุณต้องมีบัญชีที่เก็บข้อมูล Azure Data Lake รุ่น2 ที่เชื่อมโยงกับอินสแตนซ์ Azure Studio ของคุณเพื่อใช้คุณลักษณะนี้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="4ffbb-115">สำหรับข้อมูลเพิ่มเติม ดูที่ [สร้างบัญชีที่เก็บข้อมูล Gen2 Azure Data Lake Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="4ffbb-116">เพิ่มเวิร์กโฟลว์ใหม่</span><span class="sxs-lookup"><span data-stu-id="4ffbb-116">Add a new workflow</span></span>

1. <span data-ttu-id="4ffbb-117">ไปที่ **ระบบอัจฉริยะ** > **โมเดลที่กำหนดเอง** และเลือก **เวิร์กโฟลว์ใหม่**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="4ffbb-118">ตั้งชื่อโมเดลที่กำหนดเองที่เป็นที่รู้จักของคุณในฟิลด์ **ชื่อ**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ffbb-119">![ภาพหน้าจอของบานหน้าต่างเวิร์กโฟลว์ใหม่](media/new-workflowv2.png "ภาพหน้าจอของบานหน้าต่างเวิร์กโฟลว์ใหม่")</span><span class="sxs-lookup"><span data-stu-id="4ffbb-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="4ffbb-120">เลือกองค์กรที่มี Web Service ใน **ผู้เช่าที่มี Web Service ของคุณ**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="4ffbb-121">หากการสมัครใช้งาน Azure Machine Learning ของคุณอยู่ในผู้เช่ารายอื่นที่ไม่ใช่ Customer Insights ให้เลือก **ลงชื่อเข้าใช้** ด้วยข้อมูลประจำตัวของคุณสำหรับองค์กรที่เลือก</span><span class="sxs-lookup"><span data-stu-id="4ffbb-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="4ffbb-122">เลือก **พื้นที่ทำงาน** ที่เชื่อมโยงกับบริการเว็บของคุณ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="4ffbb-123">มีสองส่วนในรายการ ส่วนหนึ่งสำหรับ Azure Machine Learning v1 (Machine Learning Studio (คลาสสิก)) และ Azure Machine Learning v2 (Azure Machine Learning)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="4ffbb-124">หากคุณไม่แน่ใจว่าพื้นที่ทำงานใดเหมาะกับบริการเว็บ Machine Learning Studio (คลาสสิก) ของคุณให้เลือก **ใดๆ**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="4ffbb-125">เลือกบริการเว็บ Machine Learning Studio (คลาสสิก) หรือไปป์ไลน์ Azure Machine Learning ในรายการแบบหล่นลง **บริการเว็บที่มีโมเดลของคุณ**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="4ffbb-126">จากนั้นเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="4ffbb-127">เรียนรู้เพิ่มเติมเกี่ยวกับ [การเผยแพร่บริการเว็บใน Machine Learning Studio (คลาสสิก)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="4ffbb-128">เรียนรู้เพิ่มเติมเกี่ยวกับ [การเผยแพร่ไปป์ไลน์ใน Azure Machine Learning โดยใช้ตัวออกแบบ](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) หรือ [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="4ffbb-129">ไปป์ไลน์ของคุณต้องเผยแพร่ภายใต้ [จุดสิ้นสุดไปป์ไลน์](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="4ffbb-130">สำหรับ **การป้อนข้อมูลบริการเว็บ** แต่ละรายการ ให้เลือก **เอนทิตี** ที่ตรงกันจากข้อมูลเชิงลึกกลุ่มเป้าหมาย และเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4ffbb-131">เวิร์กโฟลว์ของโมเดลแบบกำหนดเองจะใช้วิทยาการศึกษาสำนึกเพื่อแม็ปฟิลด์ข้อมูลป้อนเข้าของ Web Service กับแอตทริบิวต์เอนทิตีตามชื่อและชนิดข้อมูลของฟิลด์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="4ffbb-132">คุณจะเห็นข้อผิดพลาด หากไม่สามารถแม็ปฟิลด์ Web Service กับเอนทิตีได้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ffbb-133">![กำหนดค่าเวิร์กโฟลว์](media/intelligence-screen2-updated.png "กำหนดค่าเวิร์กโฟลว์")</span><span class="sxs-lookup"><span data-stu-id="4ffbb-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="4ffbb-134">ในขั้นตอน **พารามิเตอร์ผลลัพธ์ของโมเดล** ให้ตั้งค่าคุณสมบัติต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="4ffbb-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="4ffbb-135">Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="4ffbb-136">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของบริการเว็บเข้ามา</span><span class="sxs-lookup"><span data-stu-id="4ffbb-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="4ffbb-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4ffbb-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="4ffbb-138">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของไปป์ไลน์เข้ามา</span><span class="sxs-lookup"><span data-stu-id="4ffbb-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="4ffbb-139">เลือก **ชื่อพารามิเตอร์ที่เก็บข้อมูลผลลัพธ์** ของไปป์ไลน์แบบชุดงานของคุณจากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="4ffbb-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="4ffbb-140">เลือก **ชื่อพารามิเตอร์พาธผลลัพธ์** ของไปป์ไลน์แบบชุดงานของคุณจากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="4ffbb-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="4ffbb-141">![บานหน้าต่างพารามิเตอร์ผลลัพธ์ของโมเดล](media/intelligence-screen3-outputparameters.png "บานหน้าต่างพารามิเตอร์ผลลัพธ์ของโมเดล")</span><span class="sxs-lookup"><span data-stu-id="4ffbb-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="4ffbb-142">เลือกแอตทริบิวต์ที่ตรงกันจากรายการแบบหล่นลง **รหัสลูกค้าในผลลัพธ์** ที่ระบุลูกค้าและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ffbb-143">![บานหน้าต่างเชื่อมโยงผลลัพธ์กับข้อมูลลูกค้า](media/intelligence-screen4-relatetocustomer.png "บานหน้าต่างเชื่อมโยงผลลัพธ์กับข้อมูลลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="4ffbb-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="4ffbb-144">คุณจะเห็นหน้าจอ **เวิร์กโฟลว์ที่บันทึกไว้** พร้อมรายละเอียดเกี่ยวกับเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="4ffbb-145">ถ้าคุณกำหนดค่าเวิร์กโฟลว์สำหรับไปป์ไลน์ Azure Machine Learning, ข้อมูลเชิงลึกกลุ่มเป้าหมายจะแนบไปกับพื้นที่ทำงานที่มีไปป์ไลน์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="4ffbb-146">ข้อมูลเชิงลึกกลุ่มเป้าหมายจะได้รับบทบาท **ผู้มีส่วนร่วม** ในพื้นที่ทำงาน Azure</span><span class="sxs-lookup"><span data-stu-id="4ffbb-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="4ffbb-147">เลือก **สำเร็จ**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-147">Select **Done**.</span></span>

1. <span data-ttu-id="4ffbb-148">ตอนนี้คุณสามารถเรียกใช้เวิร์กโฟลว์จากเพจ **โมเดลที่กำหนดเอง** ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="4ffbb-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="4ffbb-149">แก้ไขเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-149">Edit a workflow</span></span>

1. <span data-ttu-id="4ffbb-150">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้ และเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="4ffbb-151">คุณสามารถปรับปรุงชื่อที่จำได้ของเวิร์กโฟลว์ของคุณในฟิลด์ **ชื่อที่แสดง** แต่คุณไม่สามารถเปลี่ยนบริการเว็บหรือไปป์ไลน์ที่กำหนดค่าได้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="4ffbb-152">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-152">Select **Next**.</span></span>

1. <span data-ttu-id="4ffbb-153">สำหรับ **การป้อนข้อมูลบริการเว็บ** แต่ละรายการ คุณสามารถปรับปรุง **เอนทิตี** ที่ตรงกันจากข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="4ffbb-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="4ffbb-154">จากนั้นเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="4ffbb-155">ในขั้นตอน **พารามิเตอร์ผลลัพธ์ของโมเดล** ให้ตั้งค่าคุณสมบัติต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="4ffbb-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="4ffbb-156">Machine Learning Studio (คลาสสิก)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="4ffbb-157">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของบริการเว็บเข้ามา</span><span class="sxs-lookup"><span data-stu-id="4ffbb-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="4ffbb-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4ffbb-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="4ffbb-159">ป้อน **ชื่อเอนทิตี** ผลลัพธ์ที่คุณต้องการให้ผลลัพธ์ของไปป์ไลน์เข้ามา</span><span class="sxs-lookup"><span data-stu-id="4ffbb-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="4ffbb-160">เลือก **ชื่อพารามิเตอร์ที่เก็บข้อมูลผลลัพธ์** สำหรับไปป์ไลน์ทดสอบของคุณ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="4ffbb-161">เลือก **ชื่อพารามิเตอร์พาธผลลัพธ์** สำหรับไปป์ไลน์ทดสอบของคุณ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="4ffbb-162">เลือกแอตทริบิวต์ที่ตรงกันจากรายการแบบหล่นลง **รหัสลูกค้าในผลลัพธ์** ที่ระบุลูกค้าและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="4ffbb-163">คุณต้องเลือกแอตทริบิวต์จากผลลัพธ์การอนุมานที่มีค่าเหมือนกับคอลัมน์รหัสลูกค้าของเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="4ffbb-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="4ffbb-164">หากไม่มีคอลัมน์ดังกล่าวในชุดข้อมูลของคุณ ให้เลือกแอตทริบิวต์ที่ระบุแถวโดยไม่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="4ffbb-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="4ffbb-165">เรียกใช้เวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-165">Run a workflow</span></span>

1. <span data-ttu-id="4ffbb-166">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="4ffbb-167">เลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-167">Select **Run**.</span></span>

<span data-ttu-id="4ffbb-168">นอกจากนี้ เวิร์กโฟลว์ของคุณจะทำงานโดยอัตโนมัติพร้อมการรีเฟรชตามกำหนดการทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="4ffbb-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="4ffbb-169">เรียนรู้เพิ่มเติมเกี่ยวกับ [การตั้งค่าการรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="4ffbb-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="4ffbb-170">ลบเวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="4ffbb-170">Delete a workflow</span></span>

1. <span data-ttu-id="4ffbb-171">บนหน้า **โมเดลแบบกำหนดเอง** ให้เลือกจุดไข่ปลาแนวตั้งในคอลัมน์ **การดำเนินการ** ถัดจากเวิร์กโฟลว์ที่คุณสร้างก่อนหน้านี้</span><span class="sxs-lookup"><span data-stu-id="4ffbb-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="4ffbb-172">เลือก **ลบ** และยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="4ffbb-173">เวิร์กโฟลว์ของคุณจะถูกลบ</span><span class="sxs-lookup"><span data-stu-id="4ffbb-173">Your workflow will be deleted.</span></span> <span data-ttu-id="4ffbb-174">[เอนทิตี](entities.md) ที่ถูกสร้างขึ้นเมื่อคุณสร้างเวิร์กโฟลว์ ยังคงอยู่ และสามารถดูได้จากหน้า **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="4ffbb-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]