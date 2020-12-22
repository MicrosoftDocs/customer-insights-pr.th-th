---
title: สร้างและจัดการเซ็กเมนต์
description: สร้างเซ็กเมนต์ของลูกค้าเพื่อจัดกลุ่มตามแอตทริบิวต์ต่างๆ
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407170"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c87ee-103">สร้างและจัดการเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-103">Create and manage segments</span></span>

<span data-ttu-id="c87ee-104">เซ็กเมนต์ช่วยให้คุณสามารถจัดกลุ่มลูกค้าของคุณตามแอตทริบิวต์ข้อมูลพื้นฐาน ธุรกรรมหรือพฤติกรรม</span><span class="sxs-lookup"><span data-stu-id="c87ee-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c87ee-105">คุณสามารถใช้เซ็กเมนต์เพื่อกำหนดเป้าหมายแคมเปญส่งเสริมการขาย กิจกรรมการขาย และการสนับสนุนลูกค้า เพื่อให้บรรลุเป้าหมายทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c87ee-106">คุณสามารถกำหนดตัวกรองที่ซับซ้อนรอบเอนทิตีโปรไฟล์ลูกค้าและเอนทิตีที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="c87ee-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c87ee-107">แต่ละเซกเมนต์จะสร้างชุดเรกคอร์ดลูกค้าที่คุณสามารถส่งออกและดำเนินการต่อหลังจากประมวลผล</span><span class="sxs-lookup"><span data-stu-id="c87ee-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c87ee-108">อาจมีการใช้ [ขีดจำกัดบริการ](service-limits.md) บางอย่าง</span><span class="sxs-lookup"><span data-stu-id="c87ee-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c87ee-109">ยกเว้นที่ระบุไว้เป็นอย่างอื่น ทุกเซ็กเมนต์คือ **เซ็กเมนต์ไดนามิก** ซึ่งจะรีเฟรชตามกำหนดการที่เกิดซ้ำ</span><span class="sxs-lookup"><span data-stu-id="c87ee-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c87ee-110">ตัวอย่างต่อไปนี้แสดงให้เห็นความสามารถในการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c87ee-111">เราได้กำหนดเซ็กเมนต์สำหรับลูกค้าที่สั่งสินค้าอย่างน้อย $500 ใน 90 วันที่ผ่านมา *และ* ผู้มีส่วนร่วมในการโทรของส่วนบริการลูกค้าที่เพิ่มขึ้น</span><span class="sxs-lookup"><span data-stu-id="c87ee-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c87ee-112">![หลายกลุ่ม](media/segmentation-group1-2.png "หลายกลุ่ม")</span><span class="sxs-lookup"><span data-stu-id="c87ee-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c87ee-113">การสร้างเซ็กเมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="c87ee-113">Create a new segment</span></span>

<span data-ttu-id="c87ee-114">เซ็กเมนต์ได้รับการจัดการบนเพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c87ee-115">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c87ee-116">เลือก **สร้าง** > **เซ็กเมนต์ว่าง**</span><span class="sxs-lookup"><span data-stu-id="c87ee-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="c87ee-117">ในบานหน้าต่าง **เซ็กเมนต์ใหม่** เลือกชนิดเซ็กเมนต์และตั้ง **ชื่อ**.</span><span class="sxs-lookup"><span data-stu-id="c87ee-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c87ee-118">หรือให้ระบุ ชื่อที่แสดง และคำอธิบายที่ช่วยในการระบุเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="c87ee-119">เลือก **ต่อไป** เพื่อไปที่หน้า **ตัวสร้างเซ็กเมนต์** ที่คุณกำหนดกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="c87ee-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c87ee-120">กลุ่มคือกลุ่มลูกค้า</span><span class="sxs-lookup"><span data-stu-id="c87ee-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="c87ee-121">เลือกเอนทิตีที่รวมแอตทริบิวต์ที่คุณต้องการแบ่งตามเซกเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="c87ee-122">เลือกแอตทริบิวต์ที่ใช้แบ่งกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="c87ee-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c87ee-123">แอ็ตทริบิวต์นี้สามารถมีหนึ่งในสี่ประเภทของค่า: ตัวเลข, สตริง, วันที่ หรือบูลีน</span><span class="sxs-lookup"><span data-stu-id="c87ee-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="c87ee-124">เลือกตัวดำเนินการและค่าสำหรับแอตทริบิวต์ที่เลือกไว้</span><span class="sxs-lookup"><span data-stu-id="c87ee-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c87ee-125">![ตัวกรองกลุ่มแบบกำหนดเอง](media/customer-group-numbers.png "ตัวกรองกลุ่มลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="c87ee-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c87ee-126">ตัวเลข</span><span class="sxs-lookup"><span data-stu-id="c87ee-126">Number</span></span> |<span data-ttu-id="c87ee-127">ข้อกำหนด</span><span class="sxs-lookup"><span data-stu-id="c87ee-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c87ee-128">1</span><span class="sxs-lookup"><span data-stu-id="c87ee-128">1</span></span>     |<span data-ttu-id="c87ee-129">เอนทิตี้</span><span class="sxs-lookup"><span data-stu-id="c87ee-129">Entity</span></span>          |
   |<span data-ttu-id="c87ee-130">2</span><span class="sxs-lookup"><span data-stu-id="c87ee-130">2</span></span>     |<span data-ttu-id="c87ee-131">แอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-131">Attribute</span></span>          |
   |<span data-ttu-id="c87ee-132">3</span><span class="sxs-lookup"><span data-stu-id="c87ee-132">3</span></span>    |<span data-ttu-id="c87ee-133">ตัวดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="c87ee-133">Operator</span></span>         |
   |<span data-ttu-id="c87ee-134">4</span><span class="sxs-lookup"><span data-stu-id="c87ee-134">4</span></span>    |<span data-ttu-id="c87ee-135">มูลค่า</span><span class="sxs-lookup"><span data-stu-id="c87ee-135">Value</span></span>         |

8. <span data-ttu-id="c87ee-136">หากเอนทิตีนั้นเชื่อมต่อกับเอนทิตีลูกค้าแบบครบวงจรผ่าน [ความสัมพันธ์](relationships.md) คุณต้องกำหนดเส้นทางความสัมพันธ์เพื่อสร้างเซ็กเมนต์ที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="c87ee-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c87ee-137">เพิ่มเอนทิตีจากเส้นทางความสัมพันธ์จนกว่าคุณจะสามารถเลือกเอนทิตี **ลูกค้า : CustomerInsights** จากเมนูแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="c87ee-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c87ee-138">จากนั้นเลือก **เรกคอร์ดทั้งหมด** สำหรับแต่ละเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="c87ee-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c87ee-139">![เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์](media/segments-multiple-relationships.png "เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="c87ee-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="c87ee-140">เลือก **บันทึก** เพื่อบันทึกเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="c87ee-141">เซ็กเมนต์ของคุณจะถูกบันทึกและดำเนินการหากมีการตรวจสอบความถูกต้องของข้อกำหนดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="c87ee-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c87ee-142">มิฉะนั้นจะถูกบันทึกเป็นแบบร่าง</span><span class="sxs-lookup"><span data-stu-id="c87ee-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="c87ee-143">ให้เลือก **กลับไปยังการคาดการณ์** เมื่อต้องการกลับไปยังหน้า **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c87ee-144">จัดการเซ็กเมนต์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="c87ee-144">Manage existing segments</span></span>

<span data-ttu-id="c87ee-145">บนหน้า **เซ็กเมนต์** คุณสามารถดูเซ็กเมนต์ที่บันทึกไว้ทั้งหมดและจัดการได้</span><span class="sxs-lookup"><span data-stu-id="c87ee-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c87ee-146">แต่ละเซ็กเมนต์จะถูกแทนด้วยแถวที่มีข้อมูลเพิ่มเติมเกี่ยวกับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c87ee-147">คุณสามารถจัดเรียงเซ็กเมนต์ในคอลัมน์โดยเลือกส่วนหัวของคอลัมน์</span><span class="sxs-lookup"><span data-stu-id="c87ee-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c87ee-148">ใช้กล่อง **ค้นหา** ในมุมขวาบนเพื่อกรองเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c87ee-149">![ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่](media/segments-selected-segment.png "ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่")</span><span class="sxs-lookup"><span data-stu-id="c87ee-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c87ee-150">การดำเนินการต่อไปนี้พร้อมใช้งานเมื่อคุณเลือกเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="c87ee-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c87ee-151">**ดู** รายละเอียดเซ็กเมนต์ รวมถึงแนวโน้มการนับสมาชิกแสดงตัวอย่างของสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c87ee-152">**แก้ไข** เซ็กเมนต์ที่จะเปลี่ยนคุณสมบัติ</span><span class="sxs-lookup"><span data-stu-id="c87ee-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c87ee-153">**รีเฟรช** เซ็กเมนต์ที่จะรวมข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="c87ee-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c87ee-154">เซ็กเมนต์ **เปิดใช้งาน** หรือ **ปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="c87ee-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c87ee-155">เซ็กต์เมนต์มีสองสถานะที่เป็นไปได้ - ใช้งานอยู่หรือไม่ได้ใช้งาน</span><span class="sxs-lookup"><span data-stu-id="c87ee-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c87ee-156">สถานะเหล่านี้มีประโยชน์เมื่อแก้ไขเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c87ee-157">สำหรับเซ็กต์เมนต์ที่ไม่ได้ใช้งาน คำจำกัดความของเซ็กต์เมนต์จะมีอยู่ แต่ยังไม่มีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="c87ee-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c87ee-158">เมื่อคุณเปิดใช้งานเซ็กต์เมนต์ สถานะจะเปลี่ยนจาก "ไม่ใช้งาน" เป็น "ใช้งานอยู่" และจะเริ่มมองหาลูกค้าที่ตรงกับคำจำกัดความของเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c87ee-159">ถ้า [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ได้รับการกำหนดค่าเซ็กเมนต์ที่ไม่ใช้งาน จะมี **สถานะ** แสดงเป็น **ข้าม** แสดงว่าไม่ได้พยายามรีเฟรชด้วยซ้ำ</span><span class="sxs-lookup"><span data-stu-id="c87ee-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c87ee-160">เมื่อเปิดใช้งานเซ็กเมนต์ที่ไม่ได้ใช้งาน จะรีเฟรชและจะรวมอยู่ในการรีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="c87ee-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c87ee-161">หรือคุณสามารถใช้ ฟังก์ชั่น **กำหนดการภายหลัง** ในดร็อปดาวน์ **เปิด/ปิด** เพื่อระบุวันที่และเวลาในอนาคต สำหรับการเปิดใช้งานและปิดใช้งานเซ็กเมนต์ใดโดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="c87ee-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c87ee-162">**เปลี่ยนชื่อ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-162">**Rename** the segment.</span></span>
- <span data-ttu-id="c87ee-163">**ดาวน์โหลด** รายชื่อสมาชิกเป็นไฟล์ .CSV</span><span class="sxs-lookup"><span data-stu-id="c87ee-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c87ee-164">ตัวเลือก **เพิ่ม** จะส่งรายการรหัสลูกค้าในเซ็กต์เมนต์เพื่อประมวลผลในแอปพลิเคชันอื่น</span><span class="sxs-lookup"><span data-stu-id="c87ee-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c87ee-165">**ลบ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c87ee-166">รีเฟรชเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-166">Refresh segments</span></span>

<span data-ttu-id="c87ee-167">คุณสามารถรีเฟรชเซ็กเมนต์ทั้งหมดในครั้งเดียวโดยเลือก **รีเฟรชทั้งหมด** บนหน้า **เซ็กเมนต์** หรือคุณสามารถรีเฟรชหนึ่งหรือหลายกลุ่มเมื่อคุณเลือกกลุ่มและเลือก **รีเฟรช** จากตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="c87ee-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c87ee-168">หรือคุณสามารถกำหนดค่าการรีเฟรชที่เกิดซ้ำได้บน **ผู้ดูแลระบบ** > **ระบบ** > **ตารางเวลา**</span><span class="sxs-lookup"><span data-stu-id="c87ee-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c87ee-169">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="c87ee-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c87ee-170">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="c87ee-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c87ee-171">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="c87ee-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c87ee-172">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="c87ee-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c87ee-173">ดาวน์โหลดและส่งออกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-173">Download and export segments</span></span>

<span data-ttu-id="c87ee-174">คุณสามารถดาวน์โหลดเซ็กเมนต์ของคุณไปยังไฟล์ CSV หรือส่งออกไปยัง Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c87ee-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c87ee-175">ดาวน์โหลดเซ็กเมนต์ไปยังไฟล์ CSV</span><span class="sxs-lookup"><span data-stu-id="c87ee-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c87ee-176">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c87ee-177">เลือกจุดไข่ปลาในไทล์ของเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="c87ee-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c87ee-178">เลือก **ดาวน์โหลดเป็น CSV** จากรายการดรอปดาวน์การดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="c87ee-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c87ee-179">ส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c87ee-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c87ee-180">ก่อนส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Sales ผู้ดูแลระบบจำเป็นต้อง [สร้างปลายทางการส่งออก](export-destinations.md) สำหรับ Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c87ee-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c87ee-181">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c87ee-182">เลือกจุดไข่ปลาในไทล์ของเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="c87ee-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c87ee-183">เลือก **เพิ่มไปยัง** จากรายการแบบหล่นลงของการดำเนินการ และเลือกปลายทางการส่งออกที่คุณต้องการส่งข้อมูลไป</span><span class="sxs-lookup"><span data-stu-id="c87ee-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c87ee-184">โหมดแบบร่างสำหรับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-184">Draft mode for segments</span></span>

<span data-ttu-id="c87ee-185">หากไม่ตรงตามข้อกำหนดทั้งหมดในการประมวลผลเซ็กเมนต์ คุณสามารถบันทึกเซ็กเมนต์เป็นแบบร่างและเข้าถึงได้จากหน้า **เซ็กเมนต์** .</span><span class="sxs-lookup"><span data-stu-id="c87ee-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c87ee-186">จะมีการบันทึกเป็นเซ็กเมนต์ที่ไม่ได้ใช้งานและไม่สามารถเปิดใช้งานได้จนกว่าจะถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="c87ee-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c87ee-187">เพิ่มเงื่อนไขเพิ่มเติมให้กับกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="c87ee-187">Add more conditions to a group</span></span>

<span data-ttu-id="c87ee-188">ในการเพิ่มเงื่อนไขเพิ่มเติมให้กับกลุ่ม คุณสามารถใช้ตัวดำเนินการทางตรรกะสองตัว:</span><span class="sxs-lookup"><span data-stu-id="c87ee-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c87ee-189">ตัวดำเนินการ **และ**: สองเงื่อนไขต้องตรงตามส่วนหนึ่งของกระบวนการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c87ee-190">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขข้ามเอนทิตีต่าง ๆที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="c87ee-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c87ee-191">ตัวดำเนินการ **หรือ**: ต้องตรงตามเงื่อนไขข้อใดข้อหนึ่งโดยเป็นส่วนหนึ่งของกระบวนการแบ่งเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c87ee-192">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขต่าง ๆ สำหรับเอนทิตีเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="c87ee-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c87ee-193">![ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง](media/segmentation-either-condition.png "ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง")</span><span class="sxs-lookup"><span data-stu-id="c87ee-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c87ee-194">ปัจจุบันมีความเป็นไปได้ที่จะใส่ตัวดำเนินการ **หรือ** ภายใต้ตัวดำเนินการ **และ** แต่ไม่ใช่วิธีอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="c87ee-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c87ee-195">รวมกลุ่มหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="c87ee-195">Combine multiple groups</span></span>

<span data-ttu-id="c87ee-196">แต่ละกลุ่มผลิตชุดลูกค้าที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="c87ee-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c87ee-197">คุณสามารถรวมกลุ่มเหล่านี้เพื่อรวมลูกค้าที่จำเป็นสำหรับกรณีทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c87ee-198">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่เพจ **เซ็กเมนต์** และเลือกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c87ee-199">เลือก **เพิ่มกลุ่ม**.</span><span class="sxs-lookup"><span data-stu-id="c87ee-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c87ee-200">![กลุ่มลูกค้า เพิ่มกลุ่ม](media/customer-group-add-group.png "กลุ่มลูกค้า เพิ่มกลุ่ม")</span><span class="sxs-lookup"><span data-stu-id="c87ee-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c87ee-201">เลือกหนึ่งในชุดตัวดำเนินการต่อไปนี้: **กลุ่ม**, **อินเตอร์เซค**, หรือ **ยกเว้น**</span><span class="sxs-lookup"><span data-stu-id="c87ee-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c87ee-202">![กลุ่มลูกค้า เพิ่มยูเนียน](media/customer-group-union.png "กลุ่มลูกค้า เพิ่มยูเนียน")</span><span class="sxs-lookup"><span data-stu-id="c87ee-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c87ee-203">เลือกชุดตัวดำเนินการเพื่อกำหนดเซ็กต์เมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="c87ee-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="c87ee-204">บันทึกเซ็กเมนต์ที่แตกต่างกันเพื่อกำหนดว่าจะเก็บรักษาข้อมูลใด:</span><span class="sxs-lookup"><span data-stu-id="c87ee-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c87ee-205">**ยูเนียน** รวมทั้งสองกลุ่มเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="c87ee-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c87ee-206">**อินเตอร์เซค** ทับซ้อนทั้งสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="c87ee-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c87ee-207">เฉพาะข้อมูลที่ *เหมือนกัน* ในทั้งสองกลุ่มที่จะเก็บรักษาไว้ในกลุ่มที่รวมเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="c87ee-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c87ee-208">**ยกเว้น** รวมสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="c87ee-208">**Except** combines the two groups.</span></span> <span data-ttu-id="c87ee-209">เฉพาะข้อมูลในกลุ่ม A ที่ *ไม่เหมือนกัน* กลับข้อมูลในกลุ่ม B ที่จะเก็บรักษาไว้</span><span class="sxs-lookup"><span data-stu-id="c87ee-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c87ee-210">ดูประวัติการประมวลผลและสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-210">View processing history and segment members</span></span>

<span data-ttu-id="c87ee-211">คุณสามารถดูข้อมูลรวมเกี่ยวกับเซ็กเมนต์โดยการตรวจสอบรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="c87ee-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c87ee-212">บนหน้า **เซ็กเมนต์** ให้เลือกเซ็กเมนต์ที่คุณต้องการตรวจทาน</span><span class="sxs-lookup"><span data-stu-id="c87ee-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c87ee-213">ส่วนบนของหน้ามีกราฟแนวโน้มที่แสดงการเปลี่ยนแปลงของจำนวนสมาชิก</span><span class="sxs-lookup"><span data-stu-id="c87ee-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c87ee-214">เลื่อนเม้าส์เหนือจุดข้อมูลเพื่อดูจำนวนสมาชิกในวันที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="c87ee-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c87ee-215">คุณสามารถปรับปรุงกรอบเวลาของการจัดรูปแบบการแสดง</span><span class="sxs-lookup"><span data-stu-id="c87ee-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c87ee-216">![ช่วงเวลาของเซ็กเมนต์](media/segment-time-range.png "ช่วงเวลาของเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="c87ee-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c87ee-217">ส่วนล่างประกอบด้วยรายชื่อสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c87ee-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c87ee-218">ฟิลด์ที่ปรากฏในรายการนี้ขึ้นอยู่กับแอตทริบิวต์ของเอนทิตีของเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c87ee-219">รายการดังกล่าวเป็นตัวอย่างของสมาชิกเซ็กเมนต์ที่ตรงกันและแสดง 100 เรกคอร์ดแรกของเซ็กเมนต์ของคุณเพื่อให้คุณสามารถประเมินได้อย่างรวดเร็วและตรวจสอบคำจำกัดความของกลุ่มหากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="c87ee-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c87ee-220">หากต้องการดูเรกคอร์ดที่ตรงกันทั้งหมด คุณต้อง [ส่งออกเซ็กเมนต์](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c87ee-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c87ee-221">เซ็กเมนต์ด่วน</span><span class="sxs-lookup"><span data-stu-id="c87ee-221">Quick segments</span></span>

<span data-ttu-id="c87ee-222">นอกจากตัวสร้างเซ็กเมนต์แล้ว ยังมีพาธอื่นสำหรับการสร้างเซ็กเมนต์ด้วย</span><span class="sxs-lookup"><span data-stu-id="c87ee-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c87ee-223">เซ็กเมนต์แบบด่วน ช่วยให้คุณสร้างเซ็กเมนต์ง่ายๆ (ด้วยผู้ให้บริการรายเดียว) ได้อย่างรวดเร็ว และมีข้อมูลเชิงลึกแบบทันที</span><span class="sxs-lookup"><span data-stu-id="c87ee-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c87ee-224">บนหน้า **เซ็กเมนต์** ให้เลือก **สร้าง** > **สร้างอย่างรวดเร็วจาก**</span><span class="sxs-lookup"><span data-stu-id="c87ee-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c87ee-225">เลือกตัวเลือก **โปรไฟล์** ในการสร้างเซ็กเมนต์ยึดตามเอนทิตีของลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="c87ee-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c87ee-226">เลือกตัวเลือก **การวัด** เพื่อสร้างเซ็กเมนต์รอบ ๆ แต่ละแอตทริบิวต์ลูกค้า ที่คุณสร้างชนิดการวัดไว้ก่อนหน้านี้ในหน้า **การวัด** .</span><span class="sxs-lookup"><span data-stu-id="c87ee-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c87ee-227">เลือกตัวเลือก **ระยยอัจฉริยะ** ในการสร้างเซ็กเมนต์สำหรับเอนทิตีผลลัพธ์ที่คุณสร้างขึ้นโดยใช้ความสามารถ **การคาดการณ์** หรือ **โมเดลที่กำหนดเอง** อย่างใดอย่างหนึ่ง</span><span class="sxs-lookup"><span data-stu-id="c87ee-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c87ee-228">ในกล่องโต้ตอบ **สร้างใหม่อย่างรวดเร็ว** ให้เลือกแอตทริบิวต์แบบหล่นลง **ฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="c87ee-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c87ee-229">ระบบจะให้ข้อมูลเชิงลึกเพิ่มเติมที่จะช่วยให้คุณสร้างเซ็กเมนต์ของลูกค้าที่ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="c87ee-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c87ee-230">สำหรับฟิลด์ตามหมวดหมู่ เราจะแสดงจำนวนลูกค้าสูงสุด 10 ราย</span><span class="sxs-lookup"><span data-stu-id="c87ee-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c87ee-231">เลือก **ค่า** และเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="c87ee-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c87ee-232">สำหรับแอตทริบิวต์ที่เป็นตัวเลข ระบบจะแสดงค่าของแอตทริบิวต์ที่อยู่ภายใต้เปอร์เซ็นไทล์ของลูกค้าแต่ละราย</span><span class="sxs-lookup"><span data-stu-id="c87ee-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c87ee-233">เลือก **ตัวดำเนินการ** และ **ค่า** จากนั้นเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="c87ee-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c87ee-234">ระบบจะช่วยให้คุณมี **ขนาดเซ็กเมนต์โดยประมาณ**.</span><span class="sxs-lookup"><span data-stu-id="c87ee-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c87ee-235">คุณสามารถเลือกได้ว่าจะสร้างเซ็กเมนต์ที่คุณกำหนดไว้หรือก่อนอื่นกลับไปเพื่อให้ได้ขนาดเซ็กเมนต์ที่ต่าง</span><span class="sxs-lookup"><span data-stu-id="c87ee-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c87ee-236">![ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว](media/quick-segment-name.png "ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว")</span><span class="sxs-lookup"><span data-stu-id="c87ee-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c87ee-237">ตั้ง **ชื่อ** ให้เซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c87ee-238">หรือตั้ง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="c87ee-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c87ee-239">เลือก **บันทึก** เพื่อสร้างเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c87ee-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c87ee-240">หลังจากประมวลผลเซ็กเมนต์เสร็จแล้ว คุณสามารถดูได้เหมือนเซ็กเมนต์อื่น ๆ ที่คุณสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="c87ee-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c87ee-241">สำหรับสถานการณ์ต่อไปนี้ เราแนะนำให้ใช้ตัวสร้างเซกเมนต์มากกว่าความสามารถของเซกเมนต์ที่แนะนำ:</span><span class="sxs-lookup"><span data-stu-id="c87ee-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c87ee-242">การสร้างเซ็กเมนต์ที่มีตัวกรองในฟิลด์หมวดหมู่ที่ตัวดำเนินการแตกต่างจากตัวดำเนินการ **Is**</span><span class="sxs-lookup"><span data-stu-id="c87ee-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c87ee-243">การสร้างเซ็กเมนต์ที่มีตัวกรองในฟิลด์ตัวเลขที่ตัวดำเนินการแตกต่างจากตัวดำเนินการ **ระหว่าง**, **มากกว่า** และ **น้อยกว่า**</span><span class="sxs-lookup"><span data-stu-id="c87ee-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c87ee-244">การสร้างเซ็กเมนต์ด้วยตัวกรองในฟิลด์ประเภทวันที่</span><span class="sxs-lookup"><span data-stu-id="c87ee-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c87ee-245">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="c87ee-245">Next steps</span></span>

<span data-ttu-id="c87ee-246">[ส่งออกเซ็กเมนต์](export-destinations.md) และสำรวจ [การ์ดลูกค้า](customer-card-add-in.md) และ [ตัวเชื่อมต่อ](export-power-bi.md)เพื่อรับข้อมูลเชิงลึกในระดับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="c87ee-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
