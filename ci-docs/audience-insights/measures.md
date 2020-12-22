---
title: สร้างและแก้ไขการวัด
description: กำหนดการวัดที่เกี่ยวข้องกับลูกค้าเพื่อวิเคราะห์และสะท้อนถึงประสิทธิภาพของพื้นที่ธุรกิจบางแห่ง
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407161"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="b1570-103">กำหนดและจัดการการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-103">Define and manage measures</span></span>

<span data-ttu-id="b1570-104">**การวัด** แสดงตัวบ่งชี้ประสิทธิภาพหลัก (KPIs) ที่สะท้อนให้เห็นถึงประสิทธิภาพและสุขภาพของพื้นที่ธุรกิจเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="b1570-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="b1570-105">ข้อมูลเชิงลึกกลุ่มเป้าหมายมอบประสบการณ์ที่ใช้งานง่ายสำหรับการสร้างการวัดประเภทต่างๆ โดยใช้ตัวสร้างการสอบถามที่ไม่ต้องการให้คุณเขียนโค้ดหรือตรวจสอบความถูกต้องของการวัดของคุณด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="b1570-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="b1570-106">คุณสามารถติดตามการวัดผลทางธุรกิจของคุณในหน้า **หน้าแรก** ให้ดูที่การวัดสำหรับลูกค้าเฉพาะบน **การ์ดลูกค้า** และใช้หน่วยวัดเพื่อกำหนดส่วนของลูกค้าในหน้า **เซ็กเมนต์** .</span><span class="sxs-lookup"><span data-stu-id="b1570-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="b1570-107">สร้างการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-107">Create a measure</span></span>

<span data-ttu-id="b1570-108">ส่วนนี้จะนำคุณผ่านไปยังการสร้างการวัดใหม่ตั้งแต่ต้น</span><span class="sxs-lookup"><span data-stu-id="b1570-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="b1570-109">คุณสามารถสร้างการวัดที่มีข้อมูลจากแหล่งข้อมูลหลาย ๆ แหล่งที่เชื่อมต่อผ่านเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="b1570-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="b1570-110">อาจมีการใช้ [ขีดจำกัดบริการ](service-limits.md) บางอย่าง</span><span class="sxs-lookup"><span data-stu-id="b1570-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="b1570-111">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **การวัด**</span><span class="sxs-lookup"><span data-stu-id="b1570-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="b1570-112">เลือก **การวัดใหม่**.</span><span class="sxs-lookup"><span data-stu-id="b1570-112">Select **New measure**.</span></span>

3. <span data-ttu-id="b1570-113">เลือกการวัด **ชนิด**:</span><span class="sxs-lookup"><span data-stu-id="b1570-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="b1570-114">**แอตทริบิวต์ลูกค้า**: ฟิลด์เดียวต่อลูกค้าที่สะท้อนถึงคะแนน ค่า หรือสถานะสำหรับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="b1570-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="b1570-115">แอตทริบิวต์ลูกค้าจะถูกสร้างขึ้นเป็นแอตทริบิวต์ในเอนทิตีระบบใหม่ที่สร้างขึ้นที่เรียกว่า **การวัดของลูกค้า**. </span><span class="sxs-lookup"><span data-stu-id="b1570-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="b1570-116">**การวัดของลูกค้า**: ข้อมูลเชิงลึกเกี่ยวกับพฤติกรรมลูกค้าที่มีรายละเอียดแยกย่อยตามมิติที่เลือก</span><span class="sxs-lookup"><span data-stu-id="b1570-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="b1570-117">เอนทิตีใหม่จะถูกสร้างขึ้นสำหรับแต่ละการวัดที่อาจมีหลายเรกคอร์ดต่อลูกค้า</span><span class="sxs-lookup"><span data-stu-id="b1570-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="b1570-118">**การวัดทางธุรกิจ**: ติดตามผลการดำเนินงานและสุขภาพของธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="b1570-119">การวัดทางธุรกิจสามารถมีสองผลลัพธ์ที่แตกต่างกัน: การแสดงผลตัวเลขบนหน้า **หน้าแรก** หรือเอนทิตีใหม่ที่คุณพบในหน้า **เอนทิตี** .</span><span class="sxs-lookup"><span data-stu-id="b1570-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="b1570-120">ใส่ **ชื่อ** และตัวเลือกเพิ่มเติม **ชื่อที่แสดง** จากนั้นเลือก **ถัดไป**.</span><span class="sxs-lookup"><span data-stu-id="b1570-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="b1570-121">ในส่วน **เอนทิตี** เลือกเอนทิตีแรกจากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="b1570-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="b1570-122">ณ จุดนี้ คุณควรตัดสินใจว่าจำเป็นต้องมีเอนทิตีเพิ่มเติมเป็นส่วนหนึ่งของข้อกำหนดการวัดของคุณหรือไม่</span><span class="sxs-lookup"><span data-stu-id="b1570-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1570-123">![ข้อกำหนดการวัด](media/measure-definition.png "ข้อกำหนดการวัด")</span><span class="sxs-lookup"><span data-stu-id="b1570-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="b1570-124">เมื่อต้องการเพิ่มเอนทิตี เลือก **เพิ่มเอนทิตี** และเลือกเอนทิตีที่คุณต้องการใช้สำหรับการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1570-125">คุณสามารถเลือกได้เพียงเอนทิตีที่มีความสัมพันธ์กับเอนทิตีเริ่มต้นของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="b1570-126">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับความสัมพันธ์ ดู [ความสัมพันธ์](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="b1570-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="b1570-127">อีกทางหนึ่งคือคุณสามารถกำหนดค่าตัวแปร</span><span class="sxs-lookup"><span data-stu-id="b1570-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="b1570-128">ในส่วน **ตัวแปร** ให้เลือก **ตัวแปรใหม่**.</span><span class="sxs-lookup"><span data-stu-id="b1570-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="b1570-129">ตัวแปรเป็นการคำนวณที่ทำบนแต่ละเรกคอร์ดที่คุณเลือก</span><span class="sxs-lookup"><span data-stu-id="b1570-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="b1570-130">ตัวอย่างเช่น การรวมระบบขายหน้าร้าน (POS) และการขายออนไลน์สำหรับแต่ละเรกคอร์ดของลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="b1570-131">ระบุ **ชื่อ** สำหรับตัวแปร</span><span class="sxs-lookup"><span data-stu-id="b1570-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="b1570-132">ในพื้นที่ **นิพจน์** ให้เลือกฟิลด์เพื่อเริ่มต้นการคำนวณของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="b1570-133">พิมพ์นิพจน์ในพื้นที่ **นิพจน์** ในขณะที่เลือกฟิลด์เพิ่มเติมที่จะรวมไว้ในการคำนวณของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1570-134">ขณะนี้รองรับเฉพาะนิพจน์เลขคณิตเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="b1570-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="b1570-135">นอกจากนี้ การคำนวณตัวแปรไม่ได้รับการสนับสนุนสำหรับเอนทิตีจาก [เส้นทางเอนทิตี](relationships.md)ที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="b1570-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="b1570-136">เลือก **เสร็จสิ้น**</span><span class="sxs-lookup"><span data-stu-id="b1570-136">Select **Done**.</span></span>

11. <span data-ttu-id="b1570-137">ในส่วน **ข้อกำหนดการวัด** คุณจะกำหนดวิธีการรวมเอนทิตีและตัวแปรที่มีการคำนวณของคุณในเอนทิตีการวัดหรือแอตทริบิวต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="b1570-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="b1570-138">เลือก **มิติใหม่**.</span><span class="sxs-lookup"><span data-stu-id="b1570-138">Select **New dimension**.</span></span> <span data-ttu-id="b1570-139">คุณสามารถคิดมิติเป็น *กลุ่มตาม* ฟังก์ชัน</span><span class="sxs-lookup"><span data-stu-id="b1570-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="b1570-140">ผลลัพธ์ข้อมูลของเอนทิตีการวัดหรือแอตทริบิวต์ของคุณจะถูกจัดกลุ่มตามมิติที่กำหนดไว้ทั้งหมดของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b1570-141">![เลือกวงจรการรวม](media/measures-businessreport-measure-definition2.png "เลือกวงจรการรวม")</span><span class="sxs-lookup"><span data-stu-id="b1570-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="b1570-142">เลือกหรือป้อนข้อมูลต่อไปนี้เป็นส่วนหนึ่งของข้อกำหนดมิติของคุณ:</span><span class="sxs-lookup"><span data-stu-id="b1570-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="b1570-143">**เอนทิตี**: ถ้าคุณกำหนดเอนทิตีการวัดควรมีแอตทริบิวต์อย่างน้อยหนึ่งคุณลักษณะ</span><span class="sxs-lookup"><span data-stu-id="b1570-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="b1570-144">ถ้าคุณกำหนดแอตทริบิวต์การวัดจะมีแอตทริบิวต์เดียวเท่านั้นที่เป็นค่าเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="b1570-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="b1570-145">การเลือกนี้จะเกี่ยวกับการเลือกเอนทิตีที่มีแอตทริบิวต์นั้น</span><span class="sxs-lookup"><span data-stu-id="b1570-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="b1570-146">**ฟิลด์**: เลือกแอตทริบิวต์เฉพาะที่จะรวมไว้ในเอนทิตีการวัดของคุณหรือแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="b1570-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="b1570-147">**บักเก็ต**: เลือกว่าคุณต้องการรวมข้อมูลแบบพื้นฐานในรายวัน รายเดือน หรือรายปี</span><span class="sxs-lookup"><span data-stu-id="b1570-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="b1570-148">เป็นการเลือกที่จำเป็นเฉพาะเมื่อคุณเลือกแอตทริบิวต์ประเภทวันที่</span><span class="sxs-lookup"><span data-stu-id="b1570-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="b1570-149">**เป็น**: กำหนดชื่อฟิลด์ใหม่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="b1570-150">**ชื่อที่แสดง**: กำหนดชื่อที่แสดงของฟิลด์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1570-151">การวัดทางธุรกิจของคุณจะถูกบันทึกเป็นเอนทิตีแบบหมายเลขเดียวและจะปรากฏใน **หน้าแรก** เว้นแต่คุณจะเพิ่มมิติเพิ่มเติมในการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="b1570-152">หลังจากที่เพิ่มมิติมากขึ้นแล้ว การวัดจะ *ไม่* แสดงใน **หน้าแรก** .</span><span class="sxs-lookup"><span data-stu-id="b1570-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="b1570-153">อีกวิธีหนึ่งคือเพิ่มฟังก์ชันการรวม</span><span class="sxs-lookup"><span data-stu-id="b1570-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="b1570-154">การรวมใดๆที่คุณสร้างผลลัพธ์ในค่าใหม่ภายในเอนทิตีการวัดหรือแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="b1570-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="b1570-155">ฟังก์ชันการรวมที่ได้รับการสนับสนุน คือ **ค่าต่ำสุด** **ค่าสูงสุด** **ค่าเฉลี่ย** **มัธยฐาน**, **ผลรวม**, **นับรายการที่ไม่ซ้ำกัน** **แรก**  (ใช้เรกคอร์ดแรกของค่ามิติ) และ **สุดท้าย** (ใช้เรกคอร์ดสุดท้ายที่เพิ่มไปยังค่ามิติ)</span><span class="sxs-lookup"><span data-stu-id="b1570-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="b1570-156">เลือก **บันทึก** เพื่อนําไปใช้ในการเปลี่ยนแปลงการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="b1570-157">จัดการการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="b1570-157">Manage your measures</span></span>

<span data-ttu-id="b1570-158">หลังจากสร้างการวัดอย่างน้อยหนึ่งรายการ คุณจะเห็นรายการของการวัดในเพจ **การวัด**</span><span class="sxs-lookup"><span data-stu-id="b1570-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="b1570-159">คุณจะพบข้อมูลเกี่ยวกับชนิดของการวัด ผู้สร้าง วันที่และเวลาที่สร้าง วันที่และเวลาแก้ไขครั้งล่าสุด สถานะ (ไม่ว่าจะเป็นการวัดที่ใช้งานอยู่ ไม่ใช้งาน หรือ ไม่สำเร็จ) และวันที่และเวลาในการรีเฟรชครั้งล่าสุด</span><span class="sxs-lookup"><span data-stu-id="b1570-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="b1570-160">เมื่อคุณเลือกการวัดจากรายการ คุณสามารถดูตัวอย่างของเอาต์พุต</span><span class="sxs-lookup"><span data-stu-id="b1570-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="b1570-161">หากต้องการรีเฟรชมาตรการทั้งหมดของคุณในเวลาเดียวกัน ให้เลือก **รีเฟรชทั้งหมด** โดยไม่ต้องเลือกการวัดที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="b1570-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1570-162">![การดำเนินการเพื่อจัดการมาตรการเดียว](media/measure-actions.png "การดำเนินการเพื่อจัดการมาตรการเดียว")</span><span class="sxs-lookup"><span data-stu-id="b1570-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="b1570-163">หรือเลือกการวัดจากรายการและดำเนินการข้อใดข้อหนึ่งต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="b1570-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="b1570-164">เลือกชื่อการวัดเพื่อดูรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="b1570-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="b1570-165">**แก้ไข** การกำหนดค่าของการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="b1570-166">**เปลี่ยนชื่อ** การวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-166">**Rename** the measure.</span></span>
- <span data-ttu-id="b1570-167">**ลบ** การวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-167">**Delete** the measure.</span></span>
- <span data-ttu-id="b1570-168">เลือกจุดไข่ปลา (...) จากนั้น **รีเฟรช** เพื่อเริ่มกระบวนการรีเฟรชสำหรับการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="b1570-169">เลือกจุดไข่ปลา (...) จากนั้น **ดาวน์โหลด** เพื่อรับไฟล์ .CSV ของการวัด</span><span class="sxs-lookup"><span data-stu-id="b1570-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="b1570-170">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="b1570-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b1570-171">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="b1570-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b1570-172">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="b1570-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b1570-173">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="b1570-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="b1570-174">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="b1570-174">Next step</span></span>

<span data-ttu-id="b1570-175">คุณสามารถใช้การวัดที่มีอยู่เพื่อสร้างเซ็กเมนต์ของลูกค้าแรกของคุณในหน้า **เซ็กเมนต์** .</span><span class="sxs-lookup"><span data-stu-id="b1570-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="b1570-176">สำหรับข้อมูลเพิ่มเติม ดู [เซ็กเมนต์](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b1570-176">For more information, see [Segments](segments.md).</span></span>
