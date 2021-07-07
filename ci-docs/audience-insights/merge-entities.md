---
title: ผสานเอนทิตีในการรวมข้อมูล
description: ผสานเอนทิตีเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305678"
---
# <a name="merge-entities"></a><span data-ttu-id="e5ab9-103">ผสานเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="e5ab9-103">Merge entities</span></span>

<span data-ttu-id="e5ab9-104">เฟสการผสานคือเฟสสุดท้ายในกระบวนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e5ab9-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e5ab9-105">โดยมีวัตถุประสงค์คือการกระทบยอดข้อมูลที่ขัดแย้งกัน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e5ab9-106">ตัวอย่างของข้อมูลที่ขัดแย้งกันอาจรวมถึงชื่อลูกค้าที่พบในชุดข้อมูลสองชุดของคุณ แต่จะแสดงแตกต่างกันเล็กน้อยในแต่ละชุด ("Grant Marshall" เทียบกับ "Grant Marshal") หรือหมายเลขโทรศัพท์ที่แตกต่างกันในรูปแบบ (617-803-091X เทียบกับ 617803091X)</span><span class="sxs-lookup"><span data-stu-id="e5ab9-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e5ab9-107">การผสานจุดข้อมูลที่ขัดแย้งกันเหล่านั้นทำได้บนพื้นฐานแอตทริบิวต์ต่อแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="e5ab9-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="ผสานหน้าในกระบวนการรวมข้อมูลที่แสดงตารางที่มีฟิลด์ที่ผสาน ซึ่งกำหนดโปรไฟล์ลูกค้าแบบรวม":::

<span data-ttu-id="e5ab9-109">หลังจากเสร็จสิ้น [เฟสการจับคู่](match-entities.md) คุณเริ่มขั้นตอนการผสานเฟสได้โดยเลือกไทล์ **ผสาน** บนหน้า **รวม**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e5ab9-110">ตรวจทานคำแนะนำของระบบ        </span><span class="sxs-lookup"><span data-stu-id="e5ab9-110">Review system recommendations</span></span>

<span data-ttu-id="e5ab9-111">บน **ข้อมูล** > **รวมกัน** > **ผสาน** คุณเลือกและไม่รวมแอตทริบิวต์ที่จะผสานภายในเอนทิตีโปรไฟล์ลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="e5ab9-112">โปรไฟล์ลูกค้าแบบรวมเป็นผลมาจากกระบวนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e5ab9-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="e5ab9-113">แอตทริบิวต์บางอย่างถูกรวมเข้ากับระบบโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="e5ab9-114">หากต้องการดูแอตทริบิวต์ที่รวมอยู่ในหนึ่งในแอตทริบิวต์ที่ผสานโดยอัตโนมัติของคุณ ให้เลือกแอตทริบิวต์ที่ผสานในแท็บ **ฟิลด์ลูกค้า** ของตาราง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="e5ab9-115">แอตทริบิวต์ที่ประกอบด้วยแอตทริบิวต์ที่ผสานจะแสดงเป็นแถวใหม่สองแถวใต้แอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="e5ab9-116">แยก เปลี่ยนชื่อ ไม่รวม และแก้ไขฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="e5ab9-117">คุณสามารถเปลี่ยนวิธีที่ระบบประมวลผลแอตทริบิวต์ที่ผสานเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="e5ab9-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="e5ab9-118">เลือก **แสดงเพิ่มเติม** และเลือกสิ่งที่คุณต้องการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="ตัวเลือกในเมนูแบบหล่นลงแสดงเพิ่มเติมเพื่อจัดการแอตทริบิวต์ที่ผสาน":::

<span data-ttu-id="e5ab9-120">สำหรับข้อมูลเพิ่มเติม ดูส่วนต่อไปนี้</span><span class="sxs-lookup"><span data-stu-id="e5ab9-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="e5ab9-121">แยกฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-121">Separate merged fields</span></span>

<span data-ttu-id="e5ab9-122">หากต้องการแยกฟิลด์ที่ผสาน ให้ค้นหาแอตทริบิวต์ในตาราง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="e5ab9-123">ฟิลด์ที่แยกกันจะแสดงเป็นจุดข้อมูลแต่ละจุดในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="e5ab9-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="e5ab9-124">เลือกฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="e5ab9-125">เลือก **แสดงเพิ่มเติม** และเลือก **แยกฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="e5ab9-126">ยืนยันการแยก</span><span class="sxs-lookup"><span data-stu-id="e5ab9-126">Confirm the separation.</span></span>

1. <span data-ttu-id="e5ab9-127">เลือก **บันทึก** และ **รัน** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="e5ab9-128">เปลี่ยนชื่อฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-128">Rename merged fields</span></span>

<span data-ttu-id="e5ab9-129">เปลี่ยนชื่อที่แสดงของแอตทริบิวต์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="e5ab9-130">คุณไม่สามารถเปลี่ยนชื่อของเอนทิตีผลลัพธ์ได้</span><span class="sxs-lookup"><span data-stu-id="e5ab9-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="e5ab9-131">เลือกฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="e5ab9-132">เลือก **แสดงเพิ่มเติม** และเลือก **เปลี่ยนชื่อ**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="e5ab9-133">ยืนยันชื่อที่แสดงที่เปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="e5ab9-134">เลือก **บันทึก** และ **รัน** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="e5ab9-135">ไม่รวมฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-135">Exclude merged fields</span></span>

<span data-ttu-id="e5ab9-136">ไม่รวมแอตทริบิวต์จากโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="e5ab9-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="e5ab9-137">หากฟิลด์ถูกใช้ในกระบวนการอื่นๆ ตัวอย่างเช่น ในเซ็กเมนต์ ให้ลบฟิลด์ออกจากกระบวนการเหล่านี้ ก่อนที่จะแยกออกจากโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="e5ab9-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="e5ab9-138">เลือกฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="e5ab9-139">เลือก **แสดงเพิ่มเติม** และเลือก **ไม่รวม**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="e5ab9-140">ยืนยันการตัดออก</span><span class="sxs-lookup"><span data-stu-id="e5ab9-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e5ab9-141">เลือก **บันทึก** และ **รัน** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="e5ab9-142">บนหน้า **ผสาน** ให้เลือก **ฟิลด์ที่ตัดออก** เพื่อดูรายการฟิลด์ที่ตัดออกทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="e5ab9-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="e5ab9-143">บานหน้าต่างนี้ช่วยให้คุณสามารถเพิ่มฟิลด์ที่ตัดออกกลับมาได้</span><span class="sxs-lookup"><span data-stu-id="e5ab9-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="e5ab9-144">รวมฟิลด์ด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-144">Manually combine fields</span></span>

<span data-ttu-id="e5ab9-145">ระบุแอตทริบิวต์ที่ผสานด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="e5ab9-146">บนหน้า **ผสาน** ให้เลือก **รวมฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="e5ab9-147">ระบุ **ชื่อ** และ **ชื่อฟิลด์เอาต์พุต**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="e5ab9-148">เลือกฟิลด์ที่จะเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="e5ab9-148">Choose a field to add.</span></span> <span data-ttu-id="e5ab9-149">เลือก **เพิ่มฟิลด์** เพื่อรวมฟิลด์เพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="e5ab9-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="e5ab9-150">ยืนยันการตัดออก</span><span class="sxs-lookup"><span data-stu-id="e5ab9-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e5ab9-151">เลือก **บันทึก** และ **รัน** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="e5ab9-152">เปลี่ยนแปลงลำดับของฟิลด์</span><span class="sxs-lookup"><span data-stu-id="e5ab9-152">Change the order of fields</span></span>

<span data-ttu-id="e5ab9-153">เอนทิตีบางรายการมีรายละเอียดมากกว่ารายการอื่น</span><span class="sxs-lookup"><span data-stu-id="e5ab9-153">Some entities contain more details than others.</span></span> <span data-ttu-id="e5ab9-154">หากเอนทิตีมีข้อมูลล่าสุดเกี่ยวกับฟิลด์ คุณสามารถจัดลำดับความสำคัญเหนือเอนทิตีอื่นๆ เมื่อผสานค่า</span><span class="sxs-lookup"><span data-stu-id="e5ab9-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="e5ab9-155">เลือกฟิลด์ที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="e5ab9-156">เลือก **แสดงเพิ่มเติม** และเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="e5ab9-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="e5ab9-157">ในบานหน้าต่าง **รวมฟิลด์** เลือก **เลื่อนขึ้น/ลง** เพื่อกำหนดลำดับ หรือลากและวางในตำแหน่งที่ต้องการ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="e5ab9-158">ยืนยันการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-158">Confirm the change.</span></span>

1. <span data-ttu-id="e5ab9-159">เลือก **บันทึก** และ **รัน** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e5ab9-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e5ab9-160">เรียกใช้การผสานของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-160">Run your merge</span></span>

<span data-ttu-id="e5ab9-161">ไม่ว่าคุณจะรวมแอตทริบิวต์ด้วยตนเองหรือปล่อยให้ระบบทำการผสาน คุณสามารถเรียกใช้การผสานได้เสมอ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e5ab9-162">เลือก **เรียกใช้** บนหน้า **ผสาน** เพื่อเริ่มกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e5ab9-163">![การผสานข้อมูล บันทึก และเรียกใช้](media/configure-data-merge-save-run.png "การผสานข้อมูล บันทึก และเรียกใช้")</span><span class="sxs-lookup"><span data-stu-id="e5ab9-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e5ab9-164">เลือก **เรียกใช้ ผสาน เท่านั้น** หากคุณต้องการดูผลลัพธ์ที่แสดงในเอนทิตีลูกค้าแบบรวมเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="e5ab9-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="e5ab9-165">กระบวนการดาวน์สตรีมจะได้รับการรีเฟรชเป็น [กำหนดไว้ในกำหนดการรีเฟรช](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="e5ab9-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="e5ab9-166">เลือก **เรียกใช้ ผสาน และกระบวนการดาวน์สตรีม** เพื่อรีเฟรชระบบด้วยการเปลี่ยนแปลงของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="e5ab9-167">กระบวนการทั้งหมด ซึ่งรวมถึงการเพิ่มความสมบูรณ์ เซ็กเมนต์ และการวัด จะดำเนินการอีกครั้งโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="e5ab9-168">หลังจากกระบวนการดาวน์สตรีมทั้งหมดเสร็จสิ้นแล้ว โปรไฟล์ของลูกค้าจะแสดงการเปลี่ยนแปลงใดๆ ที่คุณทำ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="e5ab9-169">หากต้องการทำการเปลี่ยนแปลงเพิ่มเติมและเรียกใช้ขั้นตอนนี้อีกครั้ง คุณสามารถยกเลิกการผสานที่กำลังดำเนินการอยู่</span><span class="sxs-lookup"><span data-stu-id="e5ab9-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e5ab9-170">เลือก **กำลังรีเฟรช ...** และเลือก **ยกเลิกงาน** ในบานหน้าต่างด้านข้างที่ปรากฏขึ้น</span><span class="sxs-lookup"><span data-stu-id="e5ab9-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="e5ab9-171">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e5ab9-172">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="e5ab9-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e5ab9-173">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="e5ab9-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e5ab9-174">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="e5ab9-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e5ab9-175">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="e5ab9-175">Next Step</span></span>

<span data-ttu-id="e5ab9-176">กำหนดค่า [กิจกรรม](activities.md) [การเพิ่มข้อมูล](enrichment-hub.md) หรือ [ความสัมพันธ์](relationships.md) เพื่อรับข้อมูลเชิงลึกเพิ่มเติมเกี่ยวกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5ab9-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e5ab9-177">หากคุณตั้งค่าคอนฟิกกิจกรรม การเพิ่มความสมบูรณ์ หรือเซ็กเมนต์ไว้แล้ว รายการเหล่านี้จะได้รับการประมวลผลโดยอัตโนมัติเพื่อใช้ข้อมูลล่าสุดของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="e5ab9-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
