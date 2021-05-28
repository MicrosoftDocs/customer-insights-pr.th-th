---
title: เซ็กเมนต์ในข้อมูลเชิงลึกของผู้ชม
description: ภาพรวมเกี่ยวกับเซ็กเมนต์และวิธีสร้างและจัดการ
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034035"
---
# <a name="segments-overview"></a><span data-ttu-id="0b87d-103">ภาพรวมของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-103">Segments overview</span></span>

<span data-ttu-id="0b87d-104">เซ็กเมนต์ช่วยให้คุณสามารถจัดกลุ่มลูกค้าของคุณตามแอตทริบิวต์ข้อมูลพื้นฐาน ธุรกรรมหรือพฤติกรรม</span><span class="sxs-lookup"><span data-stu-id="0b87d-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="0b87d-105">คุณสามารถใช้เซ็กเมนต์เพื่อกำหนดเป้าหมายแคมเปญส่งเสริมการขาย กิจกรรมการขาย และการสนับสนุนลูกค้า เพื่อให้บรรลุเป้าหมายทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="0b87d-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="0b87d-106">โปรไฟล์ลูกค้าที่ตรงกับตัวกรองของคำจำกัดความเซ็กเมนต์จะเรียกว่า *สมาชิก* ของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="0b87d-107">อาจมีการใช้ [ขีดจำกัดบริการ](service-limits.md) บางอย่าง</span><span class="sxs-lookup"><span data-stu-id="0b87d-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="0b87d-108">การสร้างเซ็กเมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="0b87d-108">Create a new segment</span></span>

<span data-ttu-id="0b87d-109">มีหลายวิธีในการสร้างเซ็กเมนต์ใหม่:</span><span class="sxs-lookup"><span data-stu-id="0b87d-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="0b87d-110">เซ็กเมนต์ที่ซับซ้อนพร้อมตัวสร้างเซ็กเมนต์: [เซ็กเมนต์ว่าง](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="0b87d-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="0b87d-111">เซ็กเมนต์อย่างง่ายพร้อมตัวดำเนินการเดียว: [เซ็กเมนต์ด่วน](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="0b87d-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="0b87d-112">วิธีที่ขับเคลื่อนด้วย AI ในการค้นหาลูกค้าที่คล้ายกัน: [ลูกค้าที่คล้ายกัน](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="0b87d-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="0b87d-113">คำแนะนำที่ขับเคลื่อนด้วย AI ตามการวัดหรือแอตทริบิวต์: [เซ็กเมนต์ที่แนะนำเพื่อปรับปรุงการวัด](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="0b87d-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="0b87d-114">ข้อเสนอแนะตามกิจกรรม: [เซ็กเมนต์ที่แนะนำตามกิจกรรมของลูกค้า](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="0b87d-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="get-insights-on-existing-segments"></a><span data-ttu-id="0b87d-115">รับข้อมูลเชิงลึกเกี่ยวกับเซ็กเมนต์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="0b87d-115">Get insights on existing segments</span></span>

<span data-ttu-id="0b87d-116">ค้นพบข้อมูลเพิ่มเติมเกี่ยวกับเซ็กเมนต์ที่มีอยู่ของคุณด้วย [ข้อมูลเชิงลึกของเซ็กเมนต์](segment-insights.md)</span><span class="sxs-lookup"><span data-stu-id="0b87d-116">Discover additional information around your existing segments with [Segment insights](segment-insights.md).</span></span> <span data-ttu-id="0b87d-117">ค้นหาสิ่งที่แตกต่างสองเซ็กเมนต์ หรือสิ่งที่พวกเขามีเหมือนกัน</span><span class="sxs-lookup"><span data-stu-id="0b87d-117">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="find-similar-customers"></a><span data-ttu-id="0b87d-118">ค้นหาลูกค้าที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="0b87d-118">Find similar customers</span></span>

<span data-ttu-id="0b87d-119">ค้นหาลูกค้าที่คล้ายกับสมาชิกของเซ็กเมนต์ที่เลือก ด้วยความช่วยเหลือของปัญญาประดิษฐ์</span><span class="sxs-lookup"><span data-stu-id="0b87d-119">Find customers that are similar to the members of a selected segment with the help of artificial intelligence.</span></span> <span data-ttu-id="0b87d-120">สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [ลูกค้าที่คล้ายกัน ](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="0b87d-120">For more information, see [similar customers ](find-similar-customer-segments.md).</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="0b87d-121">จัดการเซ็กเมนต์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="0b87d-121">Manage existing segments</span></span>

<span data-ttu-id="0b87d-122">ไปที่หน้า **เซ็กเมนต์** เพื่อดูเซ็กเมนต์ที่บันทึกไว้ทั้งหมดของคุณ และจัดการ</span><span class="sxs-lookup"><span data-stu-id="0b87d-122">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="0b87d-123">แต่ละเซ็กเมนต์จะถูกแทนด้วยแถวที่มีข้อมูลเพิ่มเติมเกี่ยวกับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-123">Each segment is represented by a row that includes additional information about the segment.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b87d-124">![ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่](media/segments-selected-segment.png "ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่")</span><span class="sxs-lookup"><span data-stu-id="0b87d-124">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="0b87d-125">การดำเนินการต่อไปนี้พร้อมใช้งานเมื่อคุณเลือกเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="0b87d-125">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="0b87d-126">**ดู** รายละเอียดเซ็กเมนต์ รวมถึงแนวโน้มการนับสมาชิกแสดงตัวอย่างของสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-126">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="0b87d-127">**แก้ไข** เซ็กเมนต์ที่จะเปลี่ยนคุณสมบัติ</span><span class="sxs-lookup"><span data-stu-id="0b87d-127">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="0b87d-128">**สร้างรายการที่ซ้ำกัน** ของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-128">**Create duplicate** of a segment.</span></span> <span data-ttu-id="0b87d-129">คุณสามารถเลือกแก้ไขคุณสมบัติทันทีหรือเพียงแค่บันทึกรายการที่ซ้ำกันก็ได้</span><span class="sxs-lookup"><span data-stu-id="0b87d-129">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="0b87d-130">**รีเฟรช** เซ็กเมนต์ที่จะรวมข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="0b87d-130">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="0b87d-131">เซ็กเมนต์ **เปิดใช้งาน** หรือ **ปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="0b87d-131">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="0b87d-132">เซ็กต์เมนต์มีสองสถานะที่เป็นไปได้ - ใช้งานอยู่หรือไม่ได้ใช้งาน</span><span class="sxs-lookup"><span data-stu-id="0b87d-132">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="0b87d-133">สถานะเหล่านี้มีประโยชน์เมื่อแก้ไขเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-133">These states come in handy when editing a segment.</span></span> <span data-ttu-id="0b87d-134">สำหรับเซ็กต์เมนต์ที่ไม่ได้ใช้งาน คำจำกัดความของเซ็กต์เมนต์จะมีอยู่ แต่ยังไม่มีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="0b87d-134">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="0b87d-135">เมื่อคุณเปิดใช้งานเซ็กต์เมนต์ สถานะจะเปลี่ยนจาก "ไม่ใช้งาน" เป็น "ใช้งานอยู่" และจะเริ่มมองหาลูกค้าที่ตรงกับคำจำกัดความของเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-135">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="0b87d-136">ถ้า [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ได้รับการกำหนดค่าเซ็กเมนต์ที่ไม่ใช้งาน จะมี **สถานะ** แสดงเป็น **ข้าม** แสดงว่าไม่ได้พยายามรีเฟรชด้วยซ้ำ</span><span class="sxs-lookup"><span data-stu-id="0b87d-136">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="0b87d-137">เมื่อเปิดใช้งานเซ็กเมนต์ที่ไม่ได้ใช้งาน จะรีเฟรชและจะรวมอยู่ในการรีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="0b87d-137">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="0b87d-138">หรือคุณสามารถใช้ ฟังก์ชั่น **กำหนดการภายหลัง** ในดร็อปดาวน์ **เปิด/ปิด** เพื่อระบุวันที่และเวลาในอนาคต สำหรับการเปิดใช้งานและปิดใช้งานเซ็กเมนต์ใดโดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="0b87d-138">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="0b87d-139">**เปลี่ยนชื่อ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-139">**Rename** the segment.</span></span>
- <span data-ttu-id="0b87d-140">**ดาวน์โหลด** รายชื่อสมาชิกเป็นไฟล์ .CSV</span><span class="sxs-lookup"><span data-stu-id="0b87d-140">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="0b87d-141">ตัวเลือก **เพิ่ม** จะส่งรายการรหัสลูกค้าในเซ็กต์เมนต์เพื่อประมวลผลในแอปพลิเคชันอื่น</span><span class="sxs-lookup"><span data-stu-id="0b87d-141">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="0b87d-142">**ลบ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-142">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="0b87d-143">รีเฟรชเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-143">Refresh segments</span></span>

<span data-ttu-id="0b87d-144">คุณสามารถรีเฟรชเซ็กเมนต์ทั้งหมดในครั้งเดียวโดยเลือก **รีเฟรชทั้งหมด** บนหน้า **เซ็กเมนต์** หรือคุณสามารถรีเฟรชหนึ่งหรือหลายกลุ่มเมื่อคุณเลือกกลุ่มและเลือก **รีเฟรช** จากตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="0b87d-144">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="0b87d-145">หรือคุณสามารถกำหนดค่าการรีเฟรชที่เกิดซ้ำได้บน **ผู้ดูแลระบบ** > **ระบบ** > **ตารางเวลา**</span><span class="sxs-lookup"><span data-stu-id="0b87d-145">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="0b87d-146">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="0b87d-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0b87d-147">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="0b87d-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0b87d-148">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="0b87d-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0b87d-149">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="0b87d-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="0b87d-150">ดูประวัติการประมวลผลและสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-150">View processing history and segment members</span></span>

<span data-ttu-id="0b87d-151">คุณสามารถดูข้อมูลรวมเกี่ยวกับเซ็กเมนต์โดยการตรวจสอบรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="0b87d-151">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="0b87d-152">บนหน้า **เซ็กเมนต์** ให้เลือกเซ็กเมนต์ที่คุณต้องการตรวจทาน</span><span class="sxs-lookup"><span data-stu-id="0b87d-152">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="0b87d-153">ส่วนบนของหน้ามีกราฟแนวโน้มที่แสดงการเปลี่ยนแปลงของจำนวนสมาชิก</span><span class="sxs-lookup"><span data-stu-id="0b87d-153">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="0b87d-154">เลื่อนเม้าส์เหนือจุดข้อมูลเพื่อดูจำนวนสมาชิกในวันที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="0b87d-154">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="0b87d-155">คุณสามารถปรับปรุงกรอบเวลาของการจัดรูปแบบการแสดง</span><span class="sxs-lookup"><span data-stu-id="0b87d-155">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b87d-156">![ช่วงเวลาของเซ็กเมนต์](media/segment-time-range.png "ช่วงเวลาของเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="0b87d-156">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="0b87d-157">ส่วนล่างประกอบด้วยรายชื่อสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0b87d-157">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="0b87d-158">ฟิลด์ที่ปรากฏในรายการนี้ขึ้นอยู่กับแอตทริบิวต์ของเอนทิตีของเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="0b87d-158">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="0b87d-159">รายการดังกล่าวเป็นตัวอย่างของสมาชิกเซ็กเมนต์ที่ตรงกันและแสดง 100 เรกคอร์ดแรกของเซ็กเมนต์ของคุณเพื่อให้คุณสามารถประเมินได้อย่างรวดเร็วและตรวจสอบคำจำกัดความของกลุ่มหากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="0b87d-159">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="0b87d-160">หากต้องการดูเรกคอร์ดที่ตรงกันทั้งหมด คุณต้อง [ส่งออกเซ็กเมนต์](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0b87d-160">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
