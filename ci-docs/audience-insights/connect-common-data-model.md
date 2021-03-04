---
title: เชื่อมต่อข้อมูล Common Data Model กับบัญชี Azure Data Lake
description: ทำงานกับข้อมูล Common Data Model โดยใช้ Azure Data Lake Storage
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267883"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="acb76-103">เชื่อมต่อกับโฟลเดอร์ Common Data Model โดยใช้บัญชี Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="acb76-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="acb76-104">บทความนี้ให้ข้อมูลเกี่ยวกับวิธีการนำเข้าข้อมูลจากโฟลเดอร์ Common Data Model โดยใช้บัญชี Azure Data Lake Storage รุ่น2</span><span class="sxs-lookup"><span data-stu-id="acb76-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="acb76-105">ข้อควรพิจารณาที่สำคัญ</span><span class="sxs-lookup"><span data-stu-id="acb76-105">Important considerations</span></span>

- <span data-ttu-id="acb76-106">ข้อมูลใน Azure Data Lake ของคุณต้องเป็นไปตามมาตรฐาน Common Data Model</span><span class="sxs-lookup"><span data-stu-id="acb76-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="acb76-107">รูปแบบอื่น ๆ ไม่ได้รับการรองรับในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="acb76-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="acb76-108">การนำเข้าข้อมูลรองรับบัญชีที่เก็บข้อมูล Azure Data Lake *รุ่น2* เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="acb76-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="acb76-109">คุณไม่สามารถใช้บัญชีที่เก็บข้อมูล Azure Data Lake รุ่น1 เพื่อนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="acb76-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="acb76-110">การตรวจสอบสิทธิ์กับบริการหลักของ Azure ตรวจสอบให้แน่ใจว่าได้กำหนดค่าไว้ในผู้เช่าของคุณ</span><span class="sxs-lookup"><span data-stu-id="acb76-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="acb76-111">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="acb76-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="acb76-112">Azure Data Lake ที่คุณต้องการเชื่อมต่อและนำเข้าข้อมูลต้องอยู่ในภูมิภาค Azure เดียวกันกับสภาพแวดล้อม Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="acb76-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="acb76-113">ไม่รองรับการเชื่อมต่อกับโฟลเดอร์ Common Data Model จากที่จัดเก็บข้อมูลดิบในภูมิภาค Azure อื่นๆ</span><span class="sxs-lookup"><span data-stu-id="acb76-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="acb76-114">หากต้องการทราบภูมิภาค Azure ของสภาพแวดล้อม ให้ไปที่ **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ** ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="acb76-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="acb76-115">ข้อมูลที่จัดเก็บในบริการออนไลน์อาจถูกจัดเก็บในตำแหน่งอื่นนอกเหนือจากที่ข้อมูลถูกประมวลผลหรือจัดเก็บใน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="acb76-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="acb76-116">โดยการนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ คุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights  [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="acb76-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="acb76-117">เชื่อมต่อกับโฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="acb76-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="acb76-118">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="acb76-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="acb76-119">เลือก **เพิ่มแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="acb76-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="acb76-120">เลือก **เชื่อมต่อกับโฟลเดอร์ Common Data Model** ป้อน **ชื่อ** สำหรับแหล่งข้อมูล และเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="acb76-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="acb76-121">ตั้งชื่อแนวทาง:</span><span class="sxs-lookup"><span data-stu-id="acb76-121">Name guidelines:</span></span> 
   - <span data-ttu-id="acb76-122">ขึ้นต้นด้วยตัวอักษร</span><span class="sxs-lookup"><span data-stu-id="acb76-122">Start with a letter.</span></span>
   - <span data-ttu-id="acb76-123">ใช้ตัวอักษรและตัวเลขเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="acb76-123">Use letters and numbers only.</span></span> <span data-ttu-id="acb76-124">ไม่อนุญาตให้ใช้อักขระพิเศษและช่องว่าง</span><span class="sxs-lookup"><span data-stu-id="acb76-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="acb76-125">ใช้ระหว่าง 3 ถึง 64 อักขระ</span><span class="sxs-lookup"><span data-stu-id="acb76-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="acb76-126">คุณสามารถเลือกระหว่างการใช้ตัวเลือกตามทรัพยากรและตัวเลือกตามการสมัครใช้งานสำหรับการรับรองความถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="acb76-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="acb76-127">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="acb76-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="acb76-128">ป้อนข้อมูล **คอนเทนเนอร์** และเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="acb76-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acb76-129">![กล่องโต้ตอบเพื่อป้อนรายละเอียดการเชื่อมต่อใหม่สำหรับ Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="acb76-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="acb76-130">คุณต้องมีหนึ่งในบทบาทต่อไปนี้สำหรับคอนเทนเนอร์หรือบัญชีที่เก็บข้อมูลที่อ้างถึงข้างต้น เพื่อให้สามารถเชื่อมต่อและสร้างแหล่งข้อมูล:</span><span class="sxs-lookup"><span data-stu-id="acb76-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="acb76-131">ตัวอ่าน Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="acb76-132">เจ้าของ Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="acb76-133">ผู้สนับสนุน Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="acb76-134">ในกล่องโต้ตอบ **เลือกโฟลเดอร์ Common Data Model** เลือกไฟล์ model.json หรือ manifest.json เพื่อนำเข้าข้อมูลมา แล้วเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="acb76-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="acb76-135">ไฟล์ model.json หรือ manifest.json ใดๆ ที่เชื่อมโยงกับแหล่งข้อมูลอื่นในสภาพแวดล้อม จะไม่แสดงในรายการ</span><span class="sxs-lookup"><span data-stu-id="acb76-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="acb76-136">คุณจะได้รับรายชื่อของเอนทิตีที่มีอยู่ในไฟล์ model.json หรือ manifest.json ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="acb76-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="acb76-137">คุณสามารถรีวิวและเลือกจากรายการของเอนทิตีที่พร้อมใช้งาน และเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="acb76-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="acb76-138">เอนทิตีที่เลือกทั้งหมดจะมีการนำเข้าจากแหล่งข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="acb76-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acb76-139">![กล่องโต้ตอบแสดงรายการของเอนทิตีจากไฟล์ model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="acb76-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="acb76-140">ระบุเอนทิตีข้อมูลที่คุณต้องการเปิดใช้งานการทำโปรไฟล์ข้อมูลและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="acb76-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="acb76-141">การทําโปรไฟล์ข้อมูลช่วยให้มีความสามารถด้านการวิเคราะห์และความสามารถอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="acb76-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="acb76-142">คุณสามารถเลือกเอนทิตีทั้งหมด ซึ่งจะเลือกแอตทริบิวต์ทั้งหมดจากเอนทิตี หรือเลือกแอตทริบิวต์บางอย่างที่คุณต้องการ</span><span class="sxs-lookup"><span data-stu-id="acb76-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="acb76-143">โดยค่าเริ่มต้น ไม่มีการเปิดใช้งานเอนทิตีสำหรับการทำโปรไฟล์ข้อมูล</span><span class="sxs-lookup"><span data-stu-id="acb76-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acb76-144">![กล่องโต้ตอบที่แสดงการทำโปรไฟล์ข้อมูล](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="acb76-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="acb76-145">หลังจากบันทึกการเลือกของคุณแล้ว หน้า **แหล่งข้อมูล** จะเปิดขึ้น</span><span class="sxs-lookup"><span data-stu-id="acb76-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="acb76-146">ในขณะนี้ คุณควรเห็นการเชื่อมต่อโฟลเดอร์ Common Data Model เป็นแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="acb76-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="acb76-147">ไฟล์ model.json หรือ manifest.json สามารถเชื่อมโยงกับแหล่งข้อมูลได้เพียงแห่งเดียวในสภาวะแวดล้อมเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="acb76-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="acb76-148">อย่างไรก็ตาม ไฟล์ model.json หรือ manifest.json เดียวกัน สามารถใช้สำหรับแหล่งข้อมูลในหลายสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="acb76-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="acb76-149">แก้ไขแหล่งข้อมูลโฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="acb76-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="acb76-150">คุณสามารถปรับปรุงคีย์การเข้าถึงสำหรับบัญชีที่เก็บข้อมูลที่มีโฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="acb76-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="acb76-151">นอกจากนี้ คุณยังสามารถเปลี่ยนไฟล์ model.json หรือ manifest.json ได้</span><span class="sxs-lookup"><span data-stu-id="acb76-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="acb76-152">ถ้าคุณต้องการเชื่อมต่อกับคอนเทนเนอร์อื่นจากบัญชีที่เก็บข้อมูลของคุณ หรือเปลี่ยนชื่อบัญชี [สร้างการเชื่อมต่อแหล่งข้อมูลใหม่](#connect-to-a-common-data-model-folder)</span><span class="sxs-lookup"><span data-stu-id="acb76-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="acb76-153">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="acb76-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="acb76-154">ถัดจากแหล่งข้อมูลที่คุณต้องการอปรับปรุง เลือกจุดไข่ปลา</span><span class="sxs-lookup"><span data-stu-id="acb76-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="acb76-155">เลือกตัวเลือก **แก้ไข** จากรายการ</span><span class="sxs-lookup"><span data-stu-id="acb76-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="acb76-156">หรือปรับปรุง **แป้นการเข้าถึง** และเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="acb76-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![กล่องโต้ตอบเพื่อแก้ไข และปรับปรุงแป้นการเข้าถึงสำหรับแหล่งข้อมูลที่มีอยู่](media/edit-access-key.png)

5. <span data-ttu-id="acb76-158">หรือคุณสามารถเลือกปรับปรุงการเชื่อมต่อคีย์บัญชีกับการเชื่อมต่อตามทรัพยากรหรือการเชื่อมต่อตามการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="acb76-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="acb76-159">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="acb76-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="acb76-160">คุณไม่สามารถเปลี่ยนแปลงข้อมูล **คอนเทนเนอร์** เมื่อปรับปรุงการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="acb76-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![กล่องโต้ตอบเพื่อป้อนรายละเอียดการเชื่อมต่อสำหรับ Azure Data Lake ไปยังบัญชีที่เก็บข้อมูลที่มีอยู่](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="acb76-162">คุณต้องมีหนึ่งในบทบาทต่อไปนี้สำหรับคอนเทนเนอร์หรือบัญชีที่เก็บข้อมูลที่อ้างถึงข้างต้น เพื่อให้สามารถเชื่อมต่อและสร้างแหล่งข้อมูล:</span><span class="sxs-lookup"><span data-stu-id="acb76-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="acb76-163">ตัวอ่าน Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="acb76-164">เจ้าของ Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="acb76-165">ผู้สนับสนุน Storage Blob Data</span><span class="sxs-lookup"><span data-stu-id="acb76-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="acb76-166">หรือเลือกไฟล์ model.json หรือ manifest.json อื่นที่มีชุดของเอนทิตีที่แตกต่างกันจากคอนเทนเนอร์</span><span class="sxs-lookup"><span data-stu-id="acb76-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="acb76-167">คุณสามารถเลือกเอนทิตีเพิ่มเติมที่จะนำเข้าได้</span><span class="sxs-lookup"><span data-stu-id="acb76-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="acb76-168">นอกจากนี้ คุณยังสามารถลบเอนทิตีที่เลือกไปแล้วใดๆ หากไม่มีการขึ้นต่อกัน</span><span class="sxs-lookup"><span data-stu-id="acb76-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="acb76-169">หากมีการอ้างอิงในไฟล์ model.json หรือ manifest.json ที่มีอยู่และชุดของเอนทิตี คุณจะเห็นข้อความแสดงข้อผิดพลาดและไม่สามารถเลือกไฟล์ model.json หรือ manifest.json อื่นได้</span><span class="sxs-lookup"><span data-stu-id="acb76-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="acb76-170">ลบการอ้างอิงเหล่านั้นก่อนเปลี่ยนแปลงไฟล์ model.json หรือ manifest.json หรือสร้างแหล่งข้อมูลใหม่ด้วยไฟล์ model.json หรือ manifest.json ที่คุณต้องการใช้ เพื่อหลีกเลี่ยงการลบการอ้างอิง</span><span class="sxs-lookup"><span data-stu-id="acb76-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="acb76-171">หรือคุณสามารถเลือกแอตทริบิวต์หรือเอนทิตีเพิ่มเติมเพื่อเปิดใช้งานการทำโปรไฟล์ข้อมูลหรือปิดใช้งานรายการเลือกไว้แล้วได้</span><span class="sxs-lookup"><span data-stu-id="acb76-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]