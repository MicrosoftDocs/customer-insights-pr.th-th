---
title: สร้างและจัดการเซ็กเมนต์
description: สร้างเซ็กเมนต์ของลูกค้าเพื่อจัดกลุ่มตามแอตทริบิวต์ต่างๆ
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597084"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="cb975-103">สร้างและจัดการเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-103">Create and manage segments</span></span>

<span data-ttu-id="cb975-104">เซ็กเมนต์ช่วยให้คุณสามารถจัดกลุ่มลูกค้าของคุณตามแอตทริบิวต์ข้อมูลพื้นฐาน ธุรกรรมหรือพฤติกรรม</span><span class="sxs-lookup"><span data-stu-id="cb975-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="cb975-105">คุณสามารถใช้เซ็กเมนต์เพื่อกำหนดเป้าหมายแคมเปญส่งเสริมการขาย กิจกรรมการขาย และการสนับสนุนลูกค้า เพื่อให้บรรลุเป้าหมายทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="cb975-106">คุณสามารถกำหนดตัวกรองที่ซับซ้อนรอบเอนทิตีโปรไฟล์ลูกค้าและเอนทิตีที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="cb975-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="cb975-107">แต่ละเซกเมนต์จะสร้างชุดเรกคอร์ดลูกค้าที่คุณสามารถส่งออกและดำเนินการต่อหลังจากประมวลผล</span><span class="sxs-lookup"><span data-stu-id="cb975-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="cb975-108">อาจมีการใช้ [ขีดจำกัดบริการ](service-limits.md) บางอย่าง</span><span class="sxs-lookup"><span data-stu-id="cb975-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="cb975-109">ยกเว้นที่ระบุไว้เป็นอย่างอื่น ทุกเซ็กเมนต์คือ **เซ็กเมนต์ไดนามิก** ซึ่งจะรีเฟรชตามกำหนดการที่เกิดซ้ำ</span><span class="sxs-lookup"><span data-stu-id="cb975-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="cb975-110">ตัวอย่างต่อไปนี้แสดงให้เห็นความสามารถในการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="cb975-111">เราได้กำหนดเซ็กเมนต์สำหรับลูกค้าที่สั่งสินค้าอย่างน้อย $500 ใน 90 วันที่ผ่านมา *และ* ผู้มีส่วนร่วมในการโทรของส่วนบริการลูกค้าที่เพิ่มขึ้น</span><span class="sxs-lookup"><span data-stu-id="cb975-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb975-112">![หลายกลุ่ม](media/segmentation-group1-2.png "หลายกลุ่ม")</span><span class="sxs-lookup"><span data-stu-id="cb975-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="cb975-113">การสร้างเซ็กเมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="cb975-113">Create a new segment</span></span>

<span data-ttu-id="cb975-114">เซ็กเมนต์ได้รับการจัดการบนเพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="cb975-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="cb975-115">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="cb975-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="cb975-116">เลือก **สร้าง** > **เซ็กเมนต์ว่าง**</span><span class="sxs-lookup"><span data-stu-id="cb975-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="cb975-117">ในบานหน้าต่าง **เซ็กเมนต์ใหม่** เลือกชนิดเซ็กเมนต์และตั้ง **ชื่อ**.</span><span class="sxs-lookup"><span data-stu-id="cb975-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="cb975-118">หรือให้ระบุ ชื่อที่แสดง และคำอธิบายที่ช่วยในการระบุเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="cb975-119">เลือก **ต่อไป** เพื่อไปที่หน้า **ตัวสร้างเซ็กเมนต์** ที่คุณกำหนดกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="cb975-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="cb975-120">กลุ่มคือกลุ่มลูกค้า</span><span class="sxs-lookup"><span data-stu-id="cb975-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="cb975-121">เลือกเอนทิตีที่รวมแอตทริบิวต์ที่คุณต้องการแบ่งตามเซกเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="cb975-122">เลือกแอตทริบิวต์ที่ใช้แบ่งกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="cb975-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="cb975-123">แอ็ตทริบิวต์นี้สามารถมีหนึ่งในสี่ประเภทของค่า: ตัวเลข, สตริง, วันที่ หรือบูลีน</span><span class="sxs-lookup"><span data-stu-id="cb975-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="cb975-124">เลือกตัวดำเนินการและค่าสำหรับแอตทริบิวต์ที่เลือกไว้</span><span class="sxs-lookup"><span data-stu-id="cb975-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb975-125">![ตัวกรองกลุ่มแบบกำหนดเอง](media/customer-group-numbers.png "ตัวกรองกลุ่มลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="cb975-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="cb975-126">ตัวเลข</span><span class="sxs-lookup"><span data-stu-id="cb975-126">Number</span></span> |<span data-ttu-id="cb975-127">ข้อกำหนด</span><span class="sxs-lookup"><span data-stu-id="cb975-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="cb975-128">1</span><span class="sxs-lookup"><span data-stu-id="cb975-128">1</span></span>     |<span data-ttu-id="cb975-129">เอนทิตี้</span><span class="sxs-lookup"><span data-stu-id="cb975-129">Entity</span></span>          |
   |<span data-ttu-id="cb975-130">2</span><span class="sxs-lookup"><span data-stu-id="cb975-130">2</span></span>     |<span data-ttu-id="cb975-131">แอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="cb975-131">Attribute</span></span>          |
   |<span data-ttu-id="cb975-132">3</span><span class="sxs-lookup"><span data-stu-id="cb975-132">3</span></span>    |<span data-ttu-id="cb975-133">ตัวดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="cb975-133">Operator</span></span>         |
   |<span data-ttu-id="cb975-134">4</span><span class="sxs-lookup"><span data-stu-id="cb975-134">4</span></span>    |<span data-ttu-id="cb975-135">มูลค่า</span><span class="sxs-lookup"><span data-stu-id="cb975-135">Value</span></span>         |

8. <span data-ttu-id="cb975-136">หากเอนทิตีนั้นเชื่อมต่อกับเอนทิตีลูกค้าแบบครบวงจรผ่าน [ความสัมพันธ์](relationships.md) คุณต้องกำหนดเส้นทางความสัมพันธ์เพื่อสร้างเซ็กเมนต์ที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="cb975-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="cb975-137">เพิ่มเอนทิตีจากเส้นทางความสัมพันธ์จนกว่าคุณจะสามารถเลือกเอนทิตี **ลูกค้า : CustomerInsights** จากเมนูแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="cb975-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="cb975-138">จากนั้นเลือก **เรกคอร์ดทั้งหมด** สำหรับแต่ละเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="cb975-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb975-139">![เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์](media/segments-multiple-relationships.png "เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="cb975-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="cb975-140">ตามค่าเริ่มต้น เซ็กเมนต์จะสร้างเอนทิตีผลลัพธ์ที่มีแอตทริบิวต์ทั้งหมดของโปรไฟล์ลูกค้าซึ่งตรงกับตัวกรองที่กำหนดไว้</span><span class="sxs-lookup"><span data-stu-id="cb975-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="cb975-141">หากเซ็กเมนต์อิงอยู่กับเอนทิตีอื่นที่ไม่ใช่เอนทิตี *ลูกค้า* คุณสามารถเพิ่มแอตทริบิวต์เพิ่มเติมจากเอนทิตีเหล่านี้ไปยังเอนทิตีผลลัพธ์ได้</span><span class="sxs-lookup"><span data-stu-id="cb975-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="cb975-142">เลือก **แอตทริบิวต์ของโครงการ** เพื่อเลือกแอตทริบิวต์ที่จะต่อท้ายเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="cb975-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="cb975-143">ตัวอย่าง: เซ็กเมนต์จะอิงอยู่กับเอนทิตีที่มีข้อมูลกิจกรรมของลูกค้าซึ่งเกี่ยวข้องกับเอนทิตี *ลูกค้า*</span><span class="sxs-lookup"><span data-stu-id="cb975-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="cb975-144">เซ็กเมนต์ดังกล่าวจะค้นหาลูกค้าทั้งหมดที่โทรหาฝ่ายช่วยเหลือในช่วง 60 วันที่ผ่านมา</span><span class="sxs-lookup"><span data-stu-id="cb975-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="cb975-145">คุณสามารถเลือกผนวกระยะเวลาการโทรและจำนวนของการโทรกับเรกคอร์ดลูกค้าที่ตรงกันทั้งหมดในเอนทิตีผลลัพธ์ได้</span><span class="sxs-lookup"><span data-stu-id="cb975-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="cb975-146">ข้อมูลนี้อาจเป็นประโยชน์ในการส่งอีเมลพร้อมลิงก์ไปยังบทความช่วยเหลือทางออนไลน์ที่เป็นประโยชน์และคำถามที่ถามบ่อยให้กับลูกค้าที่โทรหาบ่อยๆ</span><span class="sxs-lookup"><span data-stu-id="cb975-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="cb975-147">เลือก **บันทึก** เพื่อบันทึกเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="cb975-148">เซ็กเมนต์ของคุณจะถูกบันทึกและดำเนินการหากมีการตรวจสอบความถูกต้องของข้อกำหนดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="cb975-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="cb975-149">มิฉะนั้นจะถูกบันทึกเป็นแบบร่าง</span><span class="sxs-lookup"><span data-stu-id="cb975-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="cb975-150">ให้เลือก **กลับไปยังการคาดการณ์** เมื่อต้องการกลับไปยังหน้า **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="cb975-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="cb975-151">จัดการเซ็กเมนต์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="cb975-151">Manage existing segments</span></span>

<span data-ttu-id="cb975-152">บนหน้า **เซ็กเมนต์** คุณสามารถดูเซ็กเมนต์ที่บันทึกไว้ทั้งหมดและจัดการได้</span><span class="sxs-lookup"><span data-stu-id="cb975-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="cb975-153">แต่ละเซ็กเมนต์จะถูกแทนด้วยแถวที่มีข้อมูลเพิ่มเติมเกี่ยวกับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="cb975-154">คุณสามารถจัดเรียงเซ็กเมนต์ในคอลัมน์โดยเลือกส่วนหัวของคอลัมน์</span><span class="sxs-lookup"><span data-stu-id="cb975-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="cb975-155">ใช้กล่อง **ค้นหา** ในมุมขวาบนเพื่อกรองเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb975-156">![ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่](media/segments-selected-segment.png "ตัวเลือกในการจัดการเซ็กเมนต์ที่มีอยู่")</span><span class="sxs-lookup"><span data-stu-id="cb975-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="cb975-157">การดำเนินการต่อไปนี้พร้อมใช้งานเมื่อคุณเลือกเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="cb975-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="cb975-158">**ดู** รายละเอียดเซ็กเมนต์ รวมถึงแนวโน้มการนับสมาชิกแสดงตัวอย่างของสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="cb975-159">**แก้ไข** เซ็กเมนต์ที่จะเปลี่ยนคุณสมบัติ</span><span class="sxs-lookup"><span data-stu-id="cb975-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="cb975-160">**สร้างรายการที่ซ้ำกัน** ของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="cb975-161">คุณสามารถเลือกแก้ไขคุณสมบัติทันทีหรือเพียงแค่บันทึกรายการที่ซ้ำกันก็ได้</span><span class="sxs-lookup"><span data-stu-id="cb975-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="cb975-162">**รีเฟรช** เซ็กเมนต์ที่จะรวมข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="cb975-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="cb975-163">เซ็กเมนต์ **เปิดใช้งาน** หรือ **ปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="cb975-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="cb975-164">เซ็กต์เมนต์มีสองสถานะที่เป็นไปได้ - ใช้งานอยู่หรือไม่ได้ใช้งาน</span><span class="sxs-lookup"><span data-stu-id="cb975-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="cb975-165">สถานะเหล่านี้มีประโยชน์เมื่อแก้ไขเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="cb975-166">สำหรับเซ็กต์เมนต์ที่ไม่ได้ใช้งาน คำจำกัดความของเซ็กต์เมนต์จะมีอยู่ แต่ยังไม่มีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="cb975-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="cb975-167">เมื่อคุณเปิดใช้งานเซ็กต์เมนต์ สถานะจะเปลี่ยนจาก "ไม่ใช้งาน" เป็น "ใช้งานอยู่" และจะเริ่มมองหาลูกค้าที่ตรงกับคำจำกัดความของเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="cb975-168">ถ้า [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ได้รับการกำหนดค่าเซ็กเมนต์ที่ไม่ใช้งาน จะมี **สถานะ** แสดงเป็น **ข้าม** แสดงว่าไม่ได้พยายามรีเฟรชด้วยซ้ำ</span><span class="sxs-lookup"><span data-stu-id="cb975-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="cb975-169">เมื่อเปิดใช้งานเซ็กเมนต์ที่ไม่ได้ใช้งาน จะรีเฟรชและจะรวมอยู่ในการรีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="cb975-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="cb975-170">หรือคุณสามารถใช้ ฟังก์ชั่น **กำหนดการภายหลัง** ในดร็อปดาวน์ **เปิด/ปิด** เพื่อระบุวันที่และเวลาในอนาคต สำหรับการเปิดใช้งานและปิดใช้งานเซ็กเมนต์ใดโดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="cb975-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="cb975-171">**เปลี่ยนชื่อ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-171">**Rename** the segment.</span></span>
- <span data-ttu-id="cb975-172">**ดาวน์โหลด** รายชื่อสมาชิกเป็นไฟล์ .CSV</span><span class="sxs-lookup"><span data-stu-id="cb975-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="cb975-173">ตัวเลือก **เพิ่ม** จะส่งรายการรหัสลูกค้าในเซ็กต์เมนต์เพื่อประมวลผลในแอปพลิเคชันอื่น</span><span class="sxs-lookup"><span data-stu-id="cb975-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="cb975-174">**ลบ** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="cb975-175">รีเฟรชเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-175">Refresh segments</span></span>

<span data-ttu-id="cb975-176">คุณสามารถรีเฟรชเซ็กเมนต์ทั้งหมดในครั้งเดียวโดยเลือก **รีเฟรชทั้งหมด** บนหน้า **เซ็กเมนต์** หรือคุณสามารถรีเฟรชหนึ่งหรือหลายกลุ่มเมื่อคุณเลือกกลุ่มและเลือก **รีเฟรช** จากตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="cb975-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="cb975-177">หรือคุณสามารถกำหนดค่าการรีเฟรชที่เกิดซ้ำได้บน **ผู้ดูแลระบบ** > **ระบบ** > **ตารางเวลา**</span><span class="sxs-lookup"><span data-stu-id="cb975-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="cb975-178">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="cb975-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cb975-179">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="cb975-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cb975-180">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="cb975-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cb975-181">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="cb975-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="cb975-182">ดาวน์โหลดและส่งออกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-182">Download and export segments</span></span>

<span data-ttu-id="cb975-183">คุณสามารถดาวน์โหลดเซ็กเมนต์ของคุณไปยังไฟล์ CSV หรือส่งออกไปยัง Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="cb975-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="cb975-184">ดาวน์โหลดเซ็กเมนต์ไปยังไฟล์ CSV</span><span class="sxs-lookup"><span data-stu-id="cb975-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="cb975-185">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="cb975-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="cb975-186">เลือกจุดไข่ปลาในไทล์ของเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="cb975-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="cb975-187">เลือก **ดาวน์โหลดเป็น CSV** จากรายการดรอปดาวน์การดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="cb975-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="cb975-188">ส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="cb975-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="cb975-189">ก่อนส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Sales ผู้ดูแลระบบจำเป็นต้อง [สร้างปลายทางการส่งออก](export-destinations.md) สำหรับ Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="cb975-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="cb975-190">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="cb975-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="cb975-191">เลือกจุดไข่ปลาในไทล์ของเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="cb975-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="cb975-192">เลือก **เพิ่มไปยัง** จากรายการแบบหล่นลงของการดำเนินการ และเลือกปลายทางการส่งออกที่คุณต้องการส่งข้อมูลไป</span><span class="sxs-lookup"><span data-stu-id="cb975-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="cb975-193">โหมดแบบร่างสำหรับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-193">Draft mode for segments</span></span>

<span data-ttu-id="cb975-194">หากไม่ตรงตามข้อกำหนดทั้งหมดในการประมวลผลเซ็กเมนต์ คุณสามารถบันทึกเซ็กเมนต์เป็นแบบร่างและเข้าถึงได้จากหน้า **เซ็กเมนต์** .</span><span class="sxs-lookup"><span data-stu-id="cb975-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="cb975-195">จะมีการบันทึกเป็นเซ็กเมนต์ที่ไม่ได้ใช้งานและไม่สามารถเปิดใช้งานได้จนกว่าจะถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="cb975-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="cb975-196">เพิ่มเงื่อนไขเพิ่มเติมให้กับกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="cb975-196">Add more conditions to a group</span></span>

<span data-ttu-id="cb975-197">ในการเพิ่มเงื่อนไขเพิ่มเติมให้กับกลุ่ม คุณสามารถใช้ตัวดำเนินการทางตรรกะสองตัว:</span><span class="sxs-lookup"><span data-stu-id="cb975-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="cb975-198">ตัวดำเนินการ **และ**: สองเงื่อนไขต้องตรงตามส่วนหนึ่งของกระบวนการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="cb975-199">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขข้ามเอนทิตีต่าง ๆที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="cb975-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="cb975-200">ตัวดำเนินการ **หรือ**: ต้องตรงตามเงื่อนไขข้อใดข้อหนึ่งโดยเป็นส่วนหนึ่งของกระบวนการแบ่งเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="cb975-201">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขต่าง ๆ สำหรับเอนทิตีเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="cb975-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb975-202">![ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง](media/segmentation-either-condition.png "ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง")</span><span class="sxs-lookup"><span data-stu-id="cb975-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="cb975-203">ปัจจุบันมีความเป็นไปได้ที่จะใส่ตัวดำเนินการ **หรือ** ภายใต้ตัวดำเนินการ **และ** แต่ไม่ใช่วิธีอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="cb975-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="cb975-204">รวมกลุ่มหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="cb975-204">Combine multiple groups</span></span>

<span data-ttu-id="cb975-205">แต่ละกลุ่มผลิตชุดลูกค้าที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="cb975-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="cb975-206">คุณสามารถรวมกลุ่มเหล่านี้เพื่อรวมลูกค้าที่จำเป็นสำหรับกรณีทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="cb975-207">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่เพจ **เซ็กเมนต์** และเลือกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="cb975-208">เลือก **เพิ่มกลุ่ม**.</span><span class="sxs-lookup"><span data-stu-id="cb975-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb975-209">![กลุ่มลูกค้า เพิ่มกลุ่ม](media/customer-group-add-group.png "กลุ่มลูกค้า เพิ่มกลุ่ม")</span><span class="sxs-lookup"><span data-stu-id="cb975-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="cb975-210">เลือกหนึ่งในชุดตัวดำเนินการต่อไปนี้: **กลุ่ม**, **อินเตอร์เซค**, หรือ **ยกเว้น**</span><span class="sxs-lookup"><span data-stu-id="cb975-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb975-211">![กลุ่มลูกค้า เพิ่มยูเนียน](media/customer-group-union.png "กลุ่มลูกค้า เพิ่มยูเนียน")</span><span class="sxs-lookup"><span data-stu-id="cb975-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="cb975-212">เลือกชุดตัวดำเนินการเพื่อกำหนดเซ็กต์เมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="cb975-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="cb975-213">บันทึกเซ็กเมนต์ที่แตกต่างกันเพื่อกำหนดว่าจะเก็บรักษาข้อมูลใด:</span><span class="sxs-lookup"><span data-stu-id="cb975-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="cb975-214">**ยูเนียน** รวมทั้งสองกลุ่มเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="cb975-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="cb975-215">**อินเตอร์เซค** ทับซ้อนทั้งสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="cb975-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="cb975-216">เฉพาะข้อมูลที่ *เหมือนกัน* ในทั้งสองกลุ่มที่จะเก็บรักษาไว้ในกลุ่มที่รวมเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="cb975-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="cb975-217">**ยกเว้น** รวมสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="cb975-217">**Except** combines the two groups.</span></span> <span data-ttu-id="cb975-218">เฉพาะข้อมูลในกลุ่ม A ที่ *ไม่เหมือนกัน* กลับข้อมูลในกลุ่ม B ที่จะเก็บรักษาไว้</span><span class="sxs-lookup"><span data-stu-id="cb975-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="cb975-219">ดูประวัติการประมวลผลและสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-219">View processing history and segment members</span></span>

<span data-ttu-id="cb975-220">คุณสามารถดูข้อมูลรวมเกี่ยวกับเซ็กเมนต์โดยการตรวจสอบรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="cb975-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="cb975-221">บนหน้า **เซ็กเมนต์** ให้เลือกเซ็กเมนต์ที่คุณต้องการตรวจทาน</span><span class="sxs-lookup"><span data-stu-id="cb975-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="cb975-222">ส่วนบนของหน้ามีกราฟแนวโน้มที่แสดงการเปลี่ยนแปลงของจำนวนสมาชิก</span><span class="sxs-lookup"><span data-stu-id="cb975-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="cb975-223">เลื่อนเม้าส์เหนือจุดข้อมูลเพื่อดูจำนวนสมาชิกในวันที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="cb975-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="cb975-224">คุณสามารถปรับปรุงกรอบเวลาของการจัดรูปแบบการแสดง</span><span class="sxs-lookup"><span data-stu-id="cb975-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cb975-225">![ช่วงเวลาของเซ็กเมนต์](media/segment-time-range.png "ช่วงเวลาของเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="cb975-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="cb975-226">ส่วนล่างประกอบด้วยรายชื่อสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="cb975-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="cb975-227">ฟิลด์ที่ปรากฏในรายการนี้ขึ้นอยู่กับแอตทริบิวต์ของเอนทิตีของเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="cb975-228">รายการดังกล่าวเป็นตัวอย่างของสมาชิกเซ็กเมนต์ที่ตรงกันและแสดง 100 เรกคอร์ดแรกของเซ็กเมนต์ของคุณเพื่อให้คุณสามารถประเมินได้อย่างรวดเร็วและตรวจสอบคำจำกัดความของกลุ่มหากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="cb975-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="cb975-229">หากต้องการดูเรกคอร์ดที่ตรงกันทั้งหมด คุณต้อง [ส่งออกเซ็กเมนต์](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cb975-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="cb975-230">เซ็กเมนต์ด่วน</span><span class="sxs-lookup"><span data-stu-id="cb975-230">Quick segments</span></span>

<span data-ttu-id="cb975-231">นอกจากตัวสร้างเซ็กเมนต์แล้ว ยังมีพาธอื่นสำหรับการสร้างเซ็กเมนต์ด้วย</span><span class="sxs-lookup"><span data-stu-id="cb975-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="cb975-232">เซ็กเมนต์แบบด่วน ช่วยให้คุณสร้างเซ็กเมนต์ง่ายๆ (ด้วยผู้ให้บริการรายเดียว) ได้อย่างรวดเร็ว และมีข้อมูลเชิงลึกแบบทันที</span><span class="sxs-lookup"><span data-stu-id="cb975-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="cb975-233">บนหน้า **เซ็กเมนต์** ให้เลือก **สร้าง** > **สร้างอย่างรวดเร็วจาก**</span><span class="sxs-lookup"><span data-stu-id="cb975-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="cb975-234">เลือกตัวเลือก **โปรไฟล์** ในการสร้างเซ็กเมนต์ยึดตามเอนทิตีของลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="cb975-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="cb975-235">เลือกตัวเลือก **การวัด** เพื่อสร้างเซ็กเมนต์รอบ ๆ แต่ละแอตทริบิวต์ลูกค้า ที่คุณสร้างชนิดการวัดไว้ก่อนหน้านี้ในหน้า **การวัด** .</span><span class="sxs-lookup"><span data-stu-id="cb975-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="cb975-236">เลือกตัวเลือก **ระยยอัจฉริยะ** ในการสร้างเซ็กเมนต์สำหรับเอนทิตีผลลัพธ์ที่คุณสร้างขึ้นโดยใช้ความสามารถ **การคาดการณ์** หรือ **โมเดลที่กำหนดเอง** อย่างใดอย่างหนึ่ง</span><span class="sxs-lookup"><span data-stu-id="cb975-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="cb975-237">ในกล่องโต้ตอบ **สร้างใหม่อย่างรวดเร็ว** ให้เลือกแอตทริบิวต์แบบหล่นลง **ฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="cb975-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="cb975-238">ระบบจะให้ข้อมูลเชิงลึกเพิ่มเติมที่จะช่วยให้คุณสร้างเซ็กเมนต์ของลูกค้าที่ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="cb975-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="cb975-239">สำหรับฟิลด์ตามหมวดหมู่ เราจะแสดงจำนวนลูกค้าสูงสุด 10 ราย</span><span class="sxs-lookup"><span data-stu-id="cb975-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="cb975-240">เลือก **ค่า** และเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="cb975-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="cb975-241">สำหรับแอตทริบิวต์ที่เป็นตัวเลข ระบบจะแสดงค่าของแอตทริบิวต์ที่อยู่ภายใต้เปอร์เซ็นไทล์ของลูกค้าแต่ละราย</span><span class="sxs-lookup"><span data-stu-id="cb975-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="cb975-242">เลือก **ตัวดำเนินการ** และ **ค่า** จากนั้นเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="cb975-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="cb975-243">ระบบจะช่วยให้คุณมี **ขนาดเซ็กเมนต์โดยประมาณ**.</span><span class="sxs-lookup"><span data-stu-id="cb975-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="cb975-244">คุณสามารถเลือกได้ว่าจะสร้างเซ็กเมนต์ที่คุณกำหนดไว้หรือก่อนอื่นกลับไปเพื่อให้ได้ขนาดเซ็กเมนต์ที่ต่าง</span><span class="sxs-lookup"><span data-stu-id="cb975-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cb975-245">![ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว](media/quick-segment-name.png "ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว")</span><span class="sxs-lookup"><span data-stu-id="cb975-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="cb975-246">ตั้ง **ชื่อ** ให้เซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="cb975-247">หรือตั้ง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="cb975-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="cb975-248">เลือก **บันทึก** เพื่อสร้างเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="cb975-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="cb975-249">หลังจากประมวลผลเซ็กเมนต์เสร็จแล้ว คุณสามารถดูได้เหมือนเซ็กเมนต์อื่น ๆ ที่คุณสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="cb975-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="cb975-250">สำหรับสถานการณ์ต่อไปนี้ เราแนะนำให้ใช้ตัวสร้างเซกเมนต์มากกว่าความสามารถของเซกเมนต์ที่แนะนำ:</span><span class="sxs-lookup"><span data-stu-id="cb975-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="cb975-251">การสร้างเซ็กเมนต์ที่มีตัวกรองในฟิลด์หมวดหมู่ที่ตัวดำเนินการแตกต่างจากตัวดำเนินการ **Is**</span><span class="sxs-lookup"><span data-stu-id="cb975-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="cb975-252">การสร้างเซ็กเมนต์ที่มีตัวกรองในฟิลด์ตัวเลขที่ตัวดำเนินการแตกต่างจากตัวดำเนินการ **ระหว่าง**, **มากกว่า** และ **น้อยกว่า**</span><span class="sxs-lookup"><span data-stu-id="cb975-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="cb975-253">การสร้างเซ็กเมนต์ด้วยตัวกรองในฟิลด์ประเภทวันที่</span><span class="sxs-lookup"><span data-stu-id="cb975-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb975-254">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="cb975-254">Next steps</span></span>

<span data-ttu-id="cb975-255">[ส่งออกเซ็กเมนต์](export-destinations.md) และสำรวจ [การ์ดลูกค้า](customer-card-add-in.md) และ [ตัวเชื่อมต่อ](export-power-bi.md)เพื่อรับข้อมูลเชิงลึกในระดับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="cb975-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]