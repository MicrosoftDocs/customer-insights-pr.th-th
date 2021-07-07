---
title: ข้อมูลเชิงลึกเซ็กเมนต์สำหรับเซ็กเมนต์ที่มีอยู่
description: รับข้อมูลเชิงลึกเกี่ยวกับเซ็กเมนต์ที่มีอยู่เพื่อดูความแตกต่างและความเหมือนกัน
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306097"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="7413f-103">ข้อมูลเชิงลึกของเซ็กเมนต์ (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="7413f-103">Segment insights (preview)</span></span>

<span data-ttu-id="7413f-104">ค้นหาข้อมูลเพิ่มเติมและข้อมูลเชิงลึกรอบเซ็กเมนต์ที่มีอยู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="7413f-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="7413f-105">ค้นหาสิ่งที่แตกต่างสองเซ็กเมนต์ หรือสิ่งที่พวกเขามีเหมือนกัน</span><span class="sxs-lookup"><span data-stu-id="7413f-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="7413f-106">การทับซ้อนของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7413f-106">Segment overlap</span></span>

<span data-ttu-id="7413f-107">การวิเคราะห์การทับซ้อนของเซ็กเมนต์ แสดงจำนวนและลูกค้าที่มีร่วมกันตั้งแต่สองเซ็กเมนต์ขึ้นไป</span><span class="sxs-lookup"><span data-stu-id="7413f-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="7413f-108">ตัวอย่างเช่น วิธีที่เซ็กเมนต์ของลูกค้าที่ใช้บ่อยซ้อนทับกับเซ็กเมนต์ที่มีลูกค้าที่พอใจกับบริการหรือผลิตภัณฑ์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="7413f-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="7413f-109">นอกจากนี้คุณยังสามารถวิเคราะห์การเปลี่ยนแปลงที่ทับซ้อนกันสำหรับแอตทริบิวต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="7413f-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="7413f-110">ทำการวิเคราะห์การซ้อนทับกัน</span><span class="sxs-lookup"><span data-stu-id="7413f-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="7413f-111">ไปที่ **เซ็กเมนต์** และเลือกแท็บ **ข้อมูลเชิงลึก (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="7413f-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="7413f-112">เลือก **ใหม่** และเลือกตัวเลือก **ซ้อนทับกัน** ในบานหน้าต่าง **เลือกชนิดข้อมูลเชิงลึก**</span><span class="sxs-lookup"><span data-stu-id="7413f-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="7413f-113">เลือกเซ็กเมนต์ที่สนใจ และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="7413f-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="7413f-114">ทางเลือก ให้เลือกอย่างน้อยหนึ่งฟิลด์ที่น่าสนใจเพื่อวิเคราะห์การทับซ้อนกันสำหรับทุกค่าของฟิลด์ที่เป็นไปได้และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="7413f-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="7413f-115">ระบุชื่อสำหรับการวิเคราะห์ที่ทับซ้อนกันของคุณ ชื่อที่แสดงที่ไม่บังคับ และคำอธิบาย</span><span class="sxs-lookup"><span data-stu-id="7413f-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="7413f-116">เลือก **บันทึก** เพื่อเริ่มการวิเเคราะห์</span><span class="sxs-lookup"><span data-stu-id="7413f-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="7413f-117">การวิเคราะห์การทับซ้อกันพร้อมเมื่อสถานะเปลี่ยนจากการรีเฟรชเป็นสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="7413f-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="7413f-118">ดูและเพิ่มประสิทธิภาพการวิเคราะห์การซ้อนทับกัน</span><span class="sxs-lookup"><span data-stu-id="7413f-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="7413f-119">หลังจากเสร็จสิ้นการวิเคราะห์ ค้นหารายละเอียดเกี่ยวกับข้อมูลเชิงลึกนี้ ใน **เซ็กเมนต์** > **ข้อมูลเชิงลึก (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="7413f-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="รายละเอียดข้อมูลเชิงลึกทับซ้อนของเซ็กเมนต์":::

<span data-ttu-id="7413f-121">เลือกข้อมูลเชิงลึกเพื่อดูผลการวิเคราะห์:</span><span class="sxs-lookup"><span data-stu-id="7413f-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="7413f-122">จำนวนสมาชิกที่ทับซ็อนเซ็กเมนต์ที่เลือกสำหรับการวิเคราะห์</span><span class="sxs-lookup"><span data-stu-id="7413f-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="7413f-123">จำนวนสมาชิกที่รวมอยู่ในเซ็กเมนต์ใดเซ็กเมนต์หนึ่ง แต่ไม่ได้อยู่ในเซ็กเมนต์ที่เหลือ</span><span class="sxs-lookup"><span data-stu-id="7413f-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="7413f-124">หากคุณเลือกฟิลด์ในขณะกำหนดค่าการวิเคราะห์การซ้อนทับกัน คุณจะพบฟิลด์เหล่านั้นในแท็บที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="7413f-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="7413f-125">คุณสามารถใช้รายการแบบหล่นลงของตัวกรองเพื่อเลือกระดับแอตทริบิวต์ที่สนใจ และตารางด้านล่างจะแสดงข้อมูลที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="7413f-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="7413f-126">ตัวจำแนกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7413f-126">Segment differentiators</span></span>

<span data-ttu-id="7413f-127">ความแตกต่างของเซ็กเมนต์ช่วยให้คุณค้นหาความแตกต่างของเซ็กเมนต์จากลูกค้าที่เหลือของคุณหรือจากเซ็กเมนต์อื่น</span><span class="sxs-lookup"><span data-stu-id="7413f-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="7413f-128">คุณเพียงแค่ต้องเลือกเซ็กเมนต์และระบบจะระบุแอตทริบิวต์โปรไฟล์และการวัดที่แยกความแตกต่างของเซ็กเมนต์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="7413f-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="7413f-129">ทำการวิเคราะห์ความแตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="7413f-130">ไปที่ **เซ็กเมนต์** และเลือกแท็บ **ข้อมูลเชิงลึก (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="7413f-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="7413f-131">เลือก **ใหม่** และเลือกตัวเลือก **ซ้อนทับกัน** ในบานหน้าต่าง **เลือกชนิดข้อมูลเชิงลึก**</span><span class="sxs-lookup"><span data-stu-id="7413f-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="7413f-132">เลือกเซ็กเมนต์ที่คุณต้องการวิเคราะห์ เป็น **เซ็กเมนต์หลัก** และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="7413f-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="7413f-133">เลือก **ลูกค้าทุกคน** หรือ **เซ็กเมนต์รอ** เพื่อเปรียบเทียบเซ็กเมนต์หลักของคุณด้วย และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="7413f-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="7413f-134">เลือกหนึ่งหรือหลายฟิลด์ที่น่าสนใจเพื่อมุ่งเน้นการวิเคราะห์เกี่ยวกับแอตทริบิวต์ที่เฉพาะเจาะจง และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="7413f-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="7413f-135">ระบุชื่อสำหรับการวิเคราะห์ที่ทับซ้อนกันของคุณ ชื่อที่แสดงที่ไม่บังคับ และคำอธิบาย</span><span class="sxs-lookup"><span data-stu-id="7413f-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="7413f-136">เลือก **บันทึก** เพื่อเริ่มการวิเเคราะห์</span><span class="sxs-lookup"><span data-stu-id="7413f-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="7413f-137">การวิเคราะห์การทับซ้อกันพร้อมเมื่อสถานะเปลี่ยนจากการรีเฟรชเป็นสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="7413f-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="7413f-138">ดูและเพิ่มประสิทธิภาพการวิเคราะห์ความแตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="7413f-139">หลังจากเสร็จสิ้นการวิเคราะห์ ค้นหารายละเอียดเกี่ยวกับข้อมูลเชิงลึกนี้ ใน **เซ็กเมนต์** > **ข้อมูลเชิงลึก (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="7413f-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="รายละเอียดข้อมูลเชิงลึกความแตกต่างของเซ็กเมนต์":::

<span data-ttu-id="7413f-141">เลือกข้อมูลเชิงลึกเพื่อดูผลการวิเคราะห์:</span><span class="sxs-lookup"><span data-stu-id="7413f-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="7413f-142">การวิเคราะห์ความแตกต่างรวมถึงสองแท็บ</span><span class="sxs-lookup"><span data-stu-id="7413f-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="7413f-143">แท็บ **แอตทริบิวต์** แสดงรายการแอตทริบิวต์โปรไฟล์ที่ถือว่าเป็นตัวแยกความแตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="7413f-144">แท็บ **การวัด** แสดงรายการตัวแยกความแตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="7413f-145">แต่ละแท็บประกอบด้วยรายละเอียดต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="7413f-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="7413f-146">จัดอันดับรายการความแตกต่าง เรียงตามคะแนนที่แตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="7413f-147">**คะแนนความแตกต่าง** สำหรับแต่ละความแตกต่าง</span><span class="sxs-lookup"><span data-stu-id="7413f-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="7413f-148">คะแนนแตกต่างแสดงถึงระดับความแตกต่างของแอตทริบิวต์ระหว่างสองเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7413f-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="7413f-149">ยิ่งคะแนนความแตกต่างสูงเท่าไหร่แอตทริบิวต์ก็จะยิ่งแตกต่างกันมากขึ้นระหว่างสองเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7413f-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="7413f-150">เลือกคะแนนเพื่อเปิดบานหน้าต่าง **คะแนนความแตกต่าง** ที่มีการแจกแจงค่าสำหรับแอตทริบิวต์นั้น</span><span class="sxs-lookup"><span data-stu-id="7413f-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="7413f-151">จัดการข้อมูลเชิงลึกของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7413f-151">Manage segment insights</span></span>

<span data-ttu-id="7413f-152">คุณสามารถใช้ตัวเลือกต่อไปนี้ในข้อมูลเชิงลึกของคุณจากแถบคำสั่ง:</span><span class="sxs-lookup"><span data-stu-id="7413f-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="7413f-153">**กลับ** เพื่อส่งคืนรายการข้อมูลเชิงลึก</span><span class="sxs-lookup"><span data-stu-id="7413f-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="7413f-154">**รีเฟรช** เพื่อรันการวิเคราะห์อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="7413f-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="7413f-155">**ลบ** เพื่อลบข้อมูลเชิงลึกนี้</span><span class="sxs-lookup"><span data-stu-id="7413f-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]