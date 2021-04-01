---
title: นำเข้าข้อมูลผ่านตัวเชื่อมต่อ Power Query
description: ตัวเชื่อมต่อสำหรับแหล่งข้อมูลตาม Power Query
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596936"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="90f60-103">เชื่อมต่อกับแหล่งข้อมูล Power Query</span><span class="sxs-lookup"><span data-stu-id="90f60-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="90f60-104">Power Query มีชุดตัวเชื่อมต่อที่หลากหลายเพื่อนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="90f60-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="90f60-105">ตัวเชื่อมต่อเหล่านี้ส่วนใหญ่รองรับโดย Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="90f60-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="90f60-106">การเพิ่มแหล่งข้อมูลตามตัวเชื่อมต่อ Power Query โดยทั่วไปจะทำตามขั้นตอนที่ระบุไว้ในส่วนถัดไป</span><span class="sxs-lookup"><span data-stu-id="90f60-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="90f60-107">อย่างไรก็ตาม ขึ้นอยู่กับตัวเชื่อมต่อที่คุณใช้ ข้อมูลที่จำเป็นแตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="90f60-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="90f60-108">สำหรับข้อมูลเพิ่มเติม โปรดดูเอกสารเกี่ยวกับตัวเชื่อมต่อแต่ละตัวใน [การอ้างอิงตัวเชื่อมต่อ Power Query](/power-query/connectors/)</span><span class="sxs-lookup"><span data-stu-id="90f60-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="90f60-109">สร้างแหล่งข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="90f60-109">Create a new data source</span></span>

1. <span data-ttu-id="90f60-110">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="90f60-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="90f60-111">เลือก **เพิ่มแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="90f60-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="90f60-112">เลือกวิธีการ **นำเข้าข้อมูล** และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="90f60-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="90f60-113">ระบุ **ชื่อ** สำหรับแหล่งข้อมูล และเลือก **ต่อไป** เพื่อสร้างแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="90f60-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="90f60-114">ตั้งชื่อแนวทาง:</span><span class="sxs-lookup"><span data-stu-id="90f60-114">Name guidelines:</span></span> 
   - <span data-ttu-id="90f60-115">ขึ้นต้นด้วยตัวอักษร</span><span class="sxs-lookup"><span data-stu-id="90f60-115">Start with a letter.</span></span>
   - <span data-ttu-id="90f60-116">ใช้ตัวอักษรและตัวเลขเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="90f60-116">Use letters and numbers only.</span></span> <span data-ttu-id="90f60-117">ไม่อนุญาตให้ใช้อักขระพิเศษและช่องว่าง</span><span class="sxs-lookup"><span data-stu-id="90f60-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="90f60-118">ใช้ระหว่าง 3 ถึง 64 อักขระ</span><span class="sxs-lookup"><span data-stu-id="90f60-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="90f60-119">เลือกหนึ่งใน [ตัวเชื่อมต่อที่พร้อมใช้งาน](#available-power-query-data-sources)</span><span class="sxs-lookup"><span data-stu-id="90f60-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="90f60-120">สำหรับตัวอย่างนี้ เราเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="90f60-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="90f60-121">ป้อนรายละเอียดที่จำเป็นใน **การตั้งค่าการเชื่อมต่อ** สำหรับตัวเชื่อมต่อที่เลือก และเลือก **ต่อไป** เพื่อดูตัวอย่างข้อมูล</span><span class="sxs-lookup"><span data-stu-id="90f60-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="90f60-122">เลือก **แปลงข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="90f60-122">Select **Transform data**.</span></span> <span data-ttu-id="90f60-123">ในขั้นตอนนี้ คุณจะเพิ่มเอนทิตีลงในแหล่งข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="90f60-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="90f60-124">เอนทิตีคือชุดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="90f60-124">Entities are datasets.</span></span> <span data-ttu-id="90f60-125">ถ้าคุณมีฐานข้อมูลที่รวมชุดข้อมูลหลายชุด ชุดข้อมูลแต่ละชุดเป็นเอนทิตีของตนเอง</span><span class="sxs-lookup"><span data-stu-id="90f60-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="90f60-126">กล่องโต้ตอบ **Power Query - แก้ไขการสอบถาม** ช่วยให้คุณตรวจสอบและปรับแต่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="90f60-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="90f60-127">เอนทิตีที่ระบบระบุในแหล่งข้อมูลที่คุณเลือกจะปรากฏในบานหน้าต่างด้านซ้าย</span><span class="sxs-lookup"><span data-stu-id="90f60-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f60-128">![แก้ไขกล่องโต้ตอบการสอบถาม](media/data-manager-configure-edit-queries.png "แก้ไขกล่องโต้ตอบการสอบถาม")</span><span class="sxs-lookup"><span data-stu-id="90f60-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="90f60-129">นอกจากนี้ คุณยังสามารถแปลงข้อมูลของคุณได้</span><span class="sxs-lookup"><span data-stu-id="90f60-129">You can also transform your data.</span></span> <span data-ttu-id="90f60-130">เลือกเอนทิตีที่จะแก้ไขหรือแปลง</span><span class="sxs-lookup"><span data-stu-id="90f60-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="90f60-131">ใช้ตัวเลือกในหน้าต่าง Power Query เพื่อใช้การแปลง</span><span class="sxs-lookup"><span data-stu-id="90f60-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="90f60-132">การแปลงแต่ละรายการจะอยู่ภายใต้ **ขั้นตอนที่ใช้**</span><span class="sxs-lookup"><span data-stu-id="90f60-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="90f60-133">Power Query มีตัวเลือกการแปลงที่สร้างไว้ล่วงหน้ามากมาย</span><span class="sxs-lookup"><span data-stu-id="90f60-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="90f60-134">สำหรับข้อมูลเพิ่มเติม ดูที่ [การแปลง Power Query](/power-query/power-query-what-is-power-query#transformations)</span><span class="sxs-lookup"><span data-stu-id="90f60-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="90f60-135">คุณสามารถเพิ่มเอนทิตีเพิ่มเติมในแหล่งข้อมูลของคุณได้โดยการเลือก **รับข้อมูล** ในกล่องโต้ตอบ **แก้ไขการสอบถาม**</span><span class="sxs-lookup"><span data-stu-id="90f60-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="90f60-136">ขอแนะนำการแปลงเหล่านี้อย่างมาก:</span><span class="sxs-lookup"><span data-stu-id="90f60-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="90f60-137">หากคุณนำเข้าข้อมูลจากไฟล์ CSV แถวแรกมักมีส่วนหัว</span><span class="sxs-lookup"><span data-stu-id="90f60-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="90f60-138">ไปที่ **แปลงตาราง** และเลือก **ใช้ส่วนหัวเป็นแถวแรก**</span><span class="sxs-lookup"><span data-stu-id="90f60-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="90f60-139">ตรวจสอบให้แน่ใจว่าได้ตั้งค่าชนิดข้อมูลอย่างเหมาะสม</span><span class="sxs-lookup"><span data-stu-id="90f60-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="90f60-140">เลือก **บันทึก** ที่มุมขวาล่างของหน้าต่าง Power Query เพื่อบันทึกการแปลงของคุณ</span><span class="sxs-lookup"><span data-stu-id="90f60-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="90f60-141">หลังจากบันทึกแล้ว คุณจะพบแหล่งข้อมูลของคุณบน **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="90f60-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="90f60-142">บนหน้า **แหล่งข้อมูล** คุณจะสังเกตเห็นแหล่งข้อมูลใหม่อยู่ในสถานะ **กำลังรีเฟรช**</span><span class="sxs-lookup"><span data-stu-id="90f60-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="90f60-143">แหล่งข้อมูล Power Query ที่พร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="90f60-143">Available Power Query data sources</span></span>

<span data-ttu-id="90f60-144">ดู [การอ้างอิงตัวเชื่อมต่อ Power Query](/power-query/connectors/) สำหรับรายการตัวเชื่อมต่อล่าสุดที่คุณสามารถเลือกเพื่อนำเข้าข้อมูลไปยัง Customer Insights</span><span class="sxs-lookup"><span data-stu-id="90f60-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="90f60-145">ตัวเชื่อมต่อที่มีเครื่องหมายถูกในคอลัมน์ **Customer Insights (กระแสข้อมูล)** พร้อมใช้งานเพื่อสร้างแหล่งข้อมูลใหม่ตาม Power Query</span><span class="sxs-lookup"><span data-stu-id="90f60-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="90f60-146">ตรวจสอบเอกสารของตัวเชื่อมต่อเฉพาะ เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับข้อกำหนดเบื้องต้น ข้อจำกัด และรายละเอียดอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="90f60-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="90f60-147">แก้ไขแหล่งข้อมูล Power Query</span><span class="sxs-lookup"><span data-stu-id="90f60-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="90f60-148">อาจไม่สามารถทำการเปลี่ยนแปลงแหล่งข้อมูลที่กำลังใช้งานอยู่ในหนึ่งในกระบวนการของแอปได้ (ตัวอย่างเช่น *การแบ่งเซ็กเมนต์* *การจับคู่* หรือ *การผสาน*)</span><span class="sxs-lookup"><span data-stu-id="90f60-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="90f60-149">โดยใช้เพจ **การตั้งค่า** คุณสามารถติดตามความคืบหน้าของแต่ละกระบวนการที่ใช้งานอยู่ได้</span><span class="sxs-lookup"><span data-stu-id="90f60-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="90f60-150">เมื่อกระบวนการเสร็จสมบูรณ์ คุณสามารถกลับไปที่หน้า **แหล่งข้อมูล** และทำการเปลี่ยนแปลงของคุณได้</span><span class="sxs-lookup"><span data-stu-id="90f60-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="90f60-151">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="90f60-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="90f60-152">เลือกจุดไข่ปลาแนวตั้งถัดจาก แหล่งข้อมูล ที่คุณต้องการเปลี่ยนและเลือก **แก้ไข** จากเมนูแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="90f60-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90f60-153">![ตัวเลือก แก้ไข](media/edit-option-data-sources.png "ตัวเลือก แก้ไข")</span><span class="sxs-lookup"><span data-stu-id="90f60-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="90f60-154">ใช้การเปลี่ยนแปลงและการแปลงของคุณในกล่องโต้ตอบ **Power Query - แก้ไขการสอบถาม** ตามที่อธิบายไว้ในส่วน [สร้างแหล่งข้อมูลใหม่](#create-a-new-data-source)</span><span class="sxs-lookup"><span data-stu-id="90f60-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="90f60-155">เลือก **บันทึก** ใน Power Query หลังจากทำการแก้ไขเสร็จสิ้น เพื่อบันทึกการเปลี่ยนแปลงของคุณ</span><span class="sxs-lookup"><span data-stu-id="90f60-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]