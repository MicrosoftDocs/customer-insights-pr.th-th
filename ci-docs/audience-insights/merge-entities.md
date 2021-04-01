---
title: ผสานเอนทิตีในการรวมข้อมูล
description: ผสานเอนทิตีเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597856"
---
# <a name="merge-entities"></a><span data-ttu-id="33930-103">ผสานเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="33930-103">Merge entities</span></span>

<span data-ttu-id="33930-104">เฟสการผสานคือเฟสสุดท้ายในกระบวนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="33930-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="33930-105">โดยมีวัตถุประสงค์คือการกระทบยอดข้อมูลที่ขัดแย้งกัน</span><span class="sxs-lookup"><span data-stu-id="33930-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="33930-106">ตัวอย่างของข้อมูลที่ขัดแย้งกันอาจรวมถึงชื่อลูกค้าที่พบในชุดข้อมูลสองชุดของคุณ แต่จะแสดงแตกต่างกันเล็กน้อยในแต่ละชุด ("Grant Marshall" เทียบกับ "Grant Marshal") หรือหมายเลขโทรศัพท์ที่แตกต่างกันในรูปแบบ (617-803-091X เทียบกับ 617803091X)</span><span class="sxs-lookup"><span data-stu-id="33930-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="33930-107">การผสานจุดข้อมูลที่ขัดแย้งกันเหล่านั้นทำได้บนพื้นฐานแอตทริบิวต์ต่อแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="33930-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="33930-108">หลังจากเสร็จสิ้น [เฟสการจับคู่](match-entities.md) คุณเริ่มขั้นตอนการผสานเฟสได้โดยเลือกไทล์ **ผสาน** บนหน้า **รวม**</span><span class="sxs-lookup"><span data-stu-id="33930-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="33930-109">ตรวจทานคำแนะนำของระบบ        </span><span class="sxs-lookup"><span data-stu-id="33930-109">Review system recommendations</span></span>

<span data-ttu-id="33930-110">บนหน้า **ผสาน** คุณสามารถเลือกและยกเว้นแอตทริบิวต์ที่จะผสานภายในเอนทิตีโปรไฟล์ลูกค้าแบบรวมของคุณ (ผลลัพธ์ของกระบวนการกำหนดค่า)</span><span class="sxs-lookup"><span data-stu-id="33930-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="33930-111">แอตทริบิวต์บางอย่างถูกรวมเข้ากับระบบโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="33930-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="33930-112">ดูแอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="33930-112">View merged attributes</span></span>

<span data-ttu-id="33930-113">หากต้องการดูแอททริบิวต์ที่รวมอยู่ในแอตทริบิวต์ที่ผสานโดยอัตโนมัติของคุณ ให้เลือกแอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="33930-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="33930-114">แอตทริบิวต์ทั้งสองที่ประกอบด้วยแอตทริบิวต์ที่ผสานแสดงเป็นสองแถวใหม่ใต้แอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="33930-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33930-115">![เลือกแอตทริบิวต์ที่ผสาน](media/configure-data-merge-profile-attributes.png "เลือกแอตทริบิวต์ที่ผสาน")</span><span class="sxs-lookup"><span data-stu-id="33930-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="33930-116">แยกแอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="33930-116">Separate merged attributes</span></span>

<span data-ttu-id="33930-117">หากต้องการแยกหรือยกเลิกการผสานแอตทริบิวต์ที่ผสานโดยอัตโนมัติใด ๆ ให้ค้นหาแอตทริบิวต์ในตาราง **แอตทริบิวต์โปรไฟล์** .</span><span class="sxs-lookup"><span data-stu-id="33930-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="33930-118">เลือกปุ่มไข่ปลา (...)</span><span class="sxs-lookup"><span data-stu-id="33930-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="33930-119">ในรายการแบบหล่นลง เลือก **แยกฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="33930-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="33930-120">ลบแอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="33930-120">Remove merged attributes</span></span>

<span data-ttu-id="33930-121">หากต้องการยกเว้นแอตทริบิวต์จากเอนทิตีโปรไฟล์ลูกค้าสุดท้ายให้ค้นหาในตาราง **แอตทริบิวต์โปรไฟล์** .</span><span class="sxs-lookup"><span data-stu-id="33930-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="33930-122">เลือกปุ่มไข่ปลา (...)</span><span class="sxs-lookup"><span data-stu-id="33930-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="33930-123">ในรายการแบบหล่นลง เลือก **ไม่ผสาน**</span><span class="sxs-lookup"><span data-stu-id="33930-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="33930-124">แอตทริบิวต์ถูกย้ายไปที่ส่วน **นำออกจากเรกคอร์ดลูกค้า** .</span><span class="sxs-lookup"><span data-stu-id="33930-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="33930-125">เพิ่มแอตทริบิวต์ที่ผสานด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="33930-125">Manually add a merged attribute</span></span>

<span data-ttu-id="33930-126">หากต้องการเพิ่มแอตทริบิวต์ที่ผสาน ไปที่หน้า **ผสาน** .</span><span class="sxs-lookup"><span data-stu-id="33930-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="33930-127">เลือก **เพิ่มแอตทริบิวต์ที่ผสาน**.</span><span class="sxs-lookup"><span data-stu-id="33930-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="33930-128">ให้ **ชื่อ** เพื่อระบุในหน้า **ผสาน** ในภายหลัง</span><span class="sxs-lookup"><span data-stu-id="33930-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="33930-129">อีกทางเลือกหนึ่ง ให้ **ชื่อที่แสดง** ปรากฏในเอนทิตีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="33930-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="33930-130">กำหนดค่า **เลือกแอตทริบิวต์ที่ซ้ำกัน** เพื่อเลือกแอตทริบิวต์ที่คุณต้องการผสานจากเอนทิตีที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="33930-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="33930-131">คุณยังสามารถค้นหาแอตทริบิวต์ได้</span><span class="sxs-lookup"><span data-stu-id="33930-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="33930-132">ตั้งค่า **จัดอันดับตามความสำคัญ** เพื่อจัดลำดับความสำคัญของแอตทริบิวต์หนึ่งเหนือส่วนอื่น</span><span class="sxs-lookup"><span data-stu-id="33930-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="33930-133">ตัวอย่างเช่น หากเอนทิตี *WebAccountCSV* รวมถึงข้อมูลที่ถูกต้องที่สุดเกี่ยวกับแอตทริบิวต์ *ชื่อเต็ม* คุณสามารถจัดลำดับความสำคัญของเอนทิตีนี้ได้ก่อน *ContactCSV* โดยการเลือก *WebAccountCSV*</span><span class="sxs-lookup"><span data-stu-id="33930-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="33930-134">ผลที่ตามมาคือ *WebAccountCSV* จะย้ายไปที่ลำดับความสำคัญอันดับแรก ในขณะที่ *ContactCSV* จะย้ายไปที่ลำดับความสำคัญอันดับที่สองเมื่อดึงค่าสำหรับแอตทริบิวต์ *ชื่อเต็ม*</span><span class="sxs-lookup"><span data-stu-id="33930-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="33930-135">เรียกใช้การผสานของคุณ</span><span class="sxs-lookup"><span data-stu-id="33930-135">Run your merge</span></span>

<span data-ttu-id="33930-136">ไม่ว่าคุณจะรวมแอตทริบิวต์ด้วยตนเองหรือปล่อยให้ระบบทำการผสาน คุณสามารถเรียกใช้การผสานได้เสมอ</span><span class="sxs-lookup"><span data-stu-id="33930-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="33930-137">เลือก **เรียกใช้** บนหน้า **ผสาน** เพื่อเริ่มกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="33930-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33930-138">![การผสานข้อมูล บันทึก และเรียกใช้](media/configure-data-merge-save-run.png "การผสานข้อมูล บันทึก และเรียกใช้")</span><span class="sxs-lookup"><span data-stu-id="33930-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="33930-139">หากต้องการเปลี่ยนแปลงเพิ่มเติมและดำเนินการขั้นตอนอีกครั้ง คุณสามารถยกเลิกการผสานที่กำลังดำเนินอยู่</span><span class="sxs-lookup"><span data-stu-id="33930-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="33930-140">เลือก **กำลังรีเฟรช ...** และเลือก **ยกเลิกงาน** ในบานหน้าต่างด้านข้างที่ปรากฏขึ้น</span><span class="sxs-lookup"><span data-stu-id="33930-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="33930-141">หลังจากข้อความ **กำลังรีเฟรช ...** เปลี่ยนเป็น **ที่ประสบความสำเร็จ** การผสานเสร็จสมบูรณ์และแก้ไขข้อขัดแย้งในข้อมูลของคุณตามนโยบายที่คุณกำหนดไว้แล้ว</span><span class="sxs-lookup"><span data-stu-id="33930-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="33930-142">แอตทริบิวต์ที่ผสานและไม่ผสานจะถูกรวมอยู่ในเอนทิตีโปรไฟล์แบบรวม</span><span class="sxs-lookup"><span data-stu-id="33930-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="33930-143">แอตทริบิวต์ที่ไม่ผสานจะไม่รวมอยู่ในเอนทิตีโปรไฟล์แบบรวม</span><span class="sxs-lookup"><span data-stu-id="33930-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="33930-144">หากไม่ใช่ครั้งแรกที่คุณดำเนินการผสานสำเร็จ กระบวนการดาวน์สตรีมทั้งหมด รวมถึงการเพิ่มประสิทธิภาพ การแบ่งส่วน และการวัด จะรันใหม่โดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="33930-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="33930-145">หลังจากกระบวนการดาวน์สตรีมทั้งหมดได้รับการรันอีกครั้ง โปรไฟล์ลูกค้าจะแสดงถึงการเปลี่ยนแปลงที่คุณทำ</span><span class="sxs-lookup"><span data-stu-id="33930-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="33930-146">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="33930-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="33930-147">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="33930-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="33930-148">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="33930-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="33930-149">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="33930-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="33930-150">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="33930-150">Next Step</span></span>

<span data-ttu-id="33930-151">กำหนดค่า [กิจกรรม](activities.md) [การเพิ่มข้อมูล](enrichment-microsoft-graph.md) หรือ [ความสัมพันธ์](relationships.md) เพื่อรับข้อมูลเชิงลึกเพิ่มเติมเกี่ยวกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="33930-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="33930-152">หากคุณกำหนดค่ากิจกรรม การเพิ่มข้อมูล หรือความสัมพันธ์ หรือหากคุณกำหนดเซ็กเมนต์ จะมีการประมวลผลกิจกรรมโดยอัตโนมัติเพื่อใช้ข้อมูลลูกค้าล่าสุด</span><span class="sxs-lookup"><span data-stu-id="33930-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]