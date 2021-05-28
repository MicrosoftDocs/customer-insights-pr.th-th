---
title: สร้างและจัดการเซ็กเมนต์
description: สร้างเซ็กเมนต์ของลูกค้าเพื่อจัดกลุ่มตามแอตทริบิวต์ต่างๆ
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064960"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="907df-103">สร้างและจัดการเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-103">Create and manage segments</span></span>

<span data-ttu-id="907df-104">กำหนดตัวกรองที่ซับซ้อนรอบๆ เอนทิตีลูกค้าแบบรวมและเอนทิตีที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="907df-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="907df-105">แต่ละเซกเมนต์จะสร้างชุดเรกคอร์ดลูกค้าที่คุณสามารถส่งออกและดำเนินการต่อหลังจากประมวลผล</span><span class="sxs-lookup"><span data-stu-id="907df-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="907df-106">เซ็กเมนต์ได้รับการจัดการบนเพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="907df-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="907df-107">ตัวอย่างต่อไปนี้แสดงให้เห็นความสามารถในการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="907df-108">เราได้กำหนดเซ็กเมนต์สำหรับลูกค้าที่สั่งสินค้าอย่างน้อย $500 ใน 90 วันที่ผ่านมา *และ* ผู้มีส่วนร่วมในการโทรของส่วนบริการลูกค้าที่เพิ่มขึ้น</span><span class="sxs-lookup"><span data-stu-id="907df-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="ภาพหน้าจอของ UI ตัวสร้างเซ็กเมนต์ที่มีกลุ่มสองกลุ่มที่ระบุเซ็กเมนต์ลูกค้า":::

## <a name="create-a-new-segment"></a><span data-ttu-id="907df-110">การสร้างเซ็กเมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="907df-110">Create a new segment</span></span>

<span data-ttu-id="907df-111">มีหลายวิธีในการสร้างเซ็กเมนต์ใหม่</span><span class="sxs-lookup"><span data-stu-id="907df-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="907df-112">ส่วนนี้อธิบายถึงวิธีการสร้าง *เซ็กเมนต์ว่าง* ตั้งแต่เริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="907df-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="907df-113">นอกจากนี้ คุณยังสามารถสร้าง *เซ็กเมนต์ด่วน* ตามเอนทิตีที่มีอยู่ หรือใช้ประโยชน์จากโมเดลการเรียนรู้เกี่ยวกับเครื่องเพื่อรับ *เซ็กเมนต์ที่แนะนำ*</span><span class="sxs-lookup"><span data-stu-id="907df-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="907df-114">ข้อมูลเพิ่มเติม: [ภาพรวมเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="907df-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="907df-115">ในขณะที่สร้างเซ็กเมนต์ คุณสามารถบันทึกแบบร่างได้</span><span class="sxs-lookup"><span data-stu-id="907df-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="907df-116">ซึ่งจะถูกบันทึกเป็นเซ็กเมนต์ที่ไม่ได้ใช้งาน และไม่สามารถเปิดใช้งานได้ หากเสร็จสิ้นการตั้งค่าคอนฟิกที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="907df-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="907df-117">ไปยังหน้า **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="907df-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="907df-118">เลือก **สร้าง** > **เซ็กเมนต์ว่าง**</span><span class="sxs-lookup"><span data-stu-id="907df-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="907df-119">ในบานหน้าต่าง **เซ็กเมนต์ใหม่** เลือกชนิดเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="907df-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="907df-120">**เซ็กเมนต์ไดนามิก** [รีเฟรช](segments.md#refresh-segments) ตามกำหนดการที่เกิดขึ้นประจำ</span><span class="sxs-lookup"><span data-stu-id="907df-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="907df-121">**เซ็กเมนต์คงที่** เรียกใช้ครั้งเดียวเมื่อคุณสร้าง</span><span class="sxs-lookup"><span data-stu-id="907df-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="907df-122">ระบุ **ชื่อเอนทิตีเอาต์พุต** สำหรับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="907df-123">หรือให้ระบุ ชื่อที่แสดง และคำอธิบายที่ช่วยในการระบุเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="907df-124">เลือก **ต่อไป** เพื่อไปที่หน้า **ตัวสร้างเซ็กเมนต์** ที่คุณกำหนดกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="907df-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="907df-125">กลุ่มคือกลุ่มลูกค้า</span><span class="sxs-lookup"><span data-stu-id="907df-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="907df-126">เลือกเอนทิตีที่รวมแอตทริบิวต์ที่คุณต้องการแบ่งตามเซกเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="907df-127">เลือกแอตทริบิวต์ที่ใช้แบ่งกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="907df-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="907df-128">แอ็ตทริบิวต์นี้สามารถมีหนึ่งในสี่ประเภทของค่า: ตัวเลข, สตริง, วันที่ หรือบูลีน</span><span class="sxs-lookup"><span data-stu-id="907df-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="907df-129">เลือกตัวดำเนินการและค่าสำหรับแอตทริบิวต์ที่เลือกไว้</span><span class="sxs-lookup"><span data-stu-id="907df-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="907df-130">![ตัวกรองกลุ่มแบบกำหนดเอง](media/customer-group-numbers.png "ตัวกรองกลุ่มลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="907df-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="907df-131">หมายเลข</span><span class="sxs-lookup"><span data-stu-id="907df-131">Number</span></span> |<span data-ttu-id="907df-132">ข้อกำหนด</span><span class="sxs-lookup"><span data-stu-id="907df-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="907df-133">1</span><span class="sxs-lookup"><span data-stu-id="907df-133">1</span></span>     |<span data-ttu-id="907df-134">Entity</span><span class="sxs-lookup"><span data-stu-id="907df-134">Entity</span></span>          |
   |<span data-ttu-id="907df-135">2</span><span class="sxs-lookup"><span data-stu-id="907df-135">2</span></span>     |<span data-ttu-id="907df-136">แอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="907df-136">Attribute</span></span>          |
   |<span data-ttu-id="907df-137">3</span><span class="sxs-lookup"><span data-stu-id="907df-137">3</span></span>    |<span data-ttu-id="907df-138">ตัวดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="907df-138">Operator</span></span>         |
   |<span data-ttu-id="907df-139">4</span><span class="sxs-lookup"><span data-stu-id="907df-139">4</span></span>    |<span data-ttu-id="907df-140">ค่า</span><span class="sxs-lookup"><span data-stu-id="907df-140">Value</span></span>         |

   1. <span data-ttu-id="907df-141">ในการเพิ่มเงื่อนไขเพิ่มเติมให้กับกลุ่ม คุณสามารถใช้ตัวดำเนินการทางตรรกะสองตัว:</span><span class="sxs-lookup"><span data-stu-id="907df-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="907df-142">ตัวดำเนินการ **และ**: สองเงื่อนไขต้องตรงตามส่วนหนึ่งของกระบวนการแบ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="907df-143">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขข้ามเอนทิตีต่าง ๆที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="907df-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="907df-144">ตัวดำเนินการ **หรือ**: ต้องตรงตามเงื่อนไขข้อใดข้อหนึ่งโดยเป็นส่วนหนึ่งของกระบวนการแบ่งเซ็กต์เมนต์</span><span class="sxs-lookup"><span data-stu-id="907df-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="907df-145">ตัวเลือกนี้มีประโยชน์มากที่สุดเมื่อคุณกำหนดเงื่อนไขต่าง ๆ สำหรับเอนทิตีเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="907df-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="907df-146">![ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง](media/segmentation-either-condition.png "ตัวดำเนินการ OR จะต้องตรงตามเงื่อนไขอย่างใดอย่างหนึ่ง")</span><span class="sxs-lookup"><span data-stu-id="907df-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="907df-147">ปัจจุบันมีความเป็นไปได้ที่จะใส่ตัวดำเนินการ **หรือ** ภายใต้ตัวดำเนินการ **และ** แต่ไม่ใช่วิธีอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="907df-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="907df-148">กลุ่มแต่ละกลุ่มตรงกับชุดของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="907df-148">Each group matches set of customers.</span></span> <span data-ttu-id="907df-149">คุณสามารถรวมกลุ่มเพื่อรวมลูกค้าที่จำเป็นสำหรับกรณีธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="907df-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="907df-150">เลือก **เพิ่มกลุ่ม**.</span><span class="sxs-lookup"><span data-stu-id="907df-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="907df-151">![กลุ่มลูกค้า เพิ่มกลุ่ม](media/customer-group-add-group.png "กลุ่มลูกค้า เพิ่มกลุ่ม")</span><span class="sxs-lookup"><span data-stu-id="907df-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="907df-152">เลือกหนึ่งในตัวดำเนินการตั้งค่า: **ยูเนียน**, **อินเตอร์เซก** หรือ **ยกเว้น**</span><span class="sxs-lookup"><span data-stu-id="907df-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="907df-153">![กลุ่มลูกค้า เพิ่มยูเนียน](media/customer-group-union.png "กลุ่มลูกค้า เพิ่มยูเนียน")</span><span class="sxs-lookup"><span data-stu-id="907df-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="907df-154">**ยูเนียน** รวมทั้งสองกลุ่มเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="907df-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="907df-155">**อินเตอร์เซค** ทับซ้อนทั้งสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="907df-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="907df-156">เฉพาะข้อมูลที่ *เหมือนกัน* ในทั้งสองกลุ่มที่จะเก็บรักษาไว้ในกลุ่มที่รวมเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="907df-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="907df-157">**ยกเว้น** รวมสองกลุ่ม</span><span class="sxs-lookup"><span data-stu-id="907df-157">**Except** combines the two groups.</span></span> <span data-ttu-id="907df-158">เฉพาะข้อมูลในกลุ่ม A ที่ *ไม่เหมือนกัน* กลับข้อมูลในกลุ่ม B ที่จะเก็บรักษาไว้</span><span class="sxs-lookup"><span data-stu-id="907df-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="907df-159">หากเอนทิตีนั้นเชื่อมต่อกับเอนทิตีลูกค้าแบบครบวงจรผ่าน [ความสัมพันธ์](relationships.md) คุณต้องกำหนดเส้นทางความสัมพันธ์เพื่อสร้างเซ็กเมนต์ที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="907df-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="907df-160">เพิ่มเอนทิตีจากเส้นทางความสัมพันธ์จนกว่าคุณจะสามารถเลือกเอนทิตี **ลูกค้า : CustomerInsights** จากเมนูแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="907df-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="907df-161">จากนั้น เลือก **เรกคอร์ดทั้งหมด** สำหรับแต่ละขั้นตอน</span><span class="sxs-lookup"><span data-stu-id="907df-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="907df-162">![เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์](media/segments-multiple-relationships.png "เส้นทางความสัมพันธ์ระหว่างการสร้างเซ็กเมนต์")</span><span class="sxs-lookup"><span data-stu-id="907df-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="907df-163">ตามค่าเริ่มต้น เซ็กเมนต์จะสร้างเอนทิตีผลลัพธ์ที่มีแอตทริบิวต์ทั้งหมดของโปรไฟล์ลูกค้าซึ่งตรงกับตัวกรองที่กำหนดไว้</span><span class="sxs-lookup"><span data-stu-id="907df-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="907df-164">หากเซ็กเมนต์อิงอยู่กับเอนทิตีอื่นที่ไม่ใช่เอนทิตี *ลูกค้า* คุณสามารถเพิ่มแอตทริบิวต์เพิ่มเติมจากเอนทิตีเหล่านี้ไปยังเอนทิตีผลลัพธ์ได้</span><span class="sxs-lookup"><span data-stu-id="907df-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="907df-165">เลือก **แอตทริบิวต์ของโครงการ** เพื่อเลือกแอตทริบิวต์ที่จะต่อท้ายเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="907df-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="907df-166">ตัวอย่าง: เซ็กเมนต์จะอิงอยู่กับเอนทิตีที่มีข้อมูลกิจกรรมของลูกค้าซึ่งเกี่ยวข้องกับเอนทิตี *ลูกค้า*</span><span class="sxs-lookup"><span data-stu-id="907df-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="907df-167">เซ็กเมนต์ดังกล่าวจะค้นหาลูกค้าทั้งหมดที่โทรหาฝ่ายช่วยเหลือในช่วง 60 วันที่ผ่านมา</span><span class="sxs-lookup"><span data-stu-id="907df-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="907df-168">คุณสามารถเลือกผนวกระยะเวลาการโทรและจำนวนของการโทรกับเรกคอร์ดลูกค้าที่ตรงกันทั้งหมดในเอนทิตีผลลัพธ์ได้</span><span class="sxs-lookup"><span data-stu-id="907df-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="907df-169">ข้อมูลนี้อาจเป็นประโยชน์ในการส่งอีเมลพร้อมลิงก์ไปยังบทความช่วยเหลือทางออนไลน์ที่เป็นประโยชน์และคำถามที่ถามบ่อยให้กับลูกค้าที่โทรหาบ่อยๆ</span><span class="sxs-lookup"><span data-stu-id="907df-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="907df-170">แอตทริบิวต์ที่คาดการณ์จะใช้ได้เฉพาะกับเอนทิตีที่มีความสัมพันธ์แบบหนึ่งต่อกลุ่มกับเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="907df-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="907df-171">ตัวอย่างเช่น ลูกค้ารายหนึ่งสามารถมีการสมัครใช้งานหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="907df-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="907df-172">คุณสามารถคาดการณ์แอตทริบิวต์จากเอนทิตีที่ใช้ในกลุ่มทุกกลุ่มของการสอบถามเซ็กเมนต์ที่คุณกำลังสร้าง</span><span class="sxs-lookup"><span data-stu-id="907df-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="907df-173">แอตทริบิวต์ที่คาดการณ์ไว้จะถูกนำมาพิจารณาเมื่อใช้ตัวดำเนินการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="907df-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="907df-174">เลือก **บันทึก** เพื่อบันทึกเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="907df-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="907df-175">เซ็กเมนต์ของคุณจะถูกบันทึกและดำเนินการหากมีการตรวจสอบความถูกต้องของข้อกำหนดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="907df-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="907df-176">มิฉะนั้นจะถูกบันทึกเป็นแบบร่าง</span><span class="sxs-lookup"><span data-stu-id="907df-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="907df-177">ให้เลือก **กลับไปยังการคาดการณ์** เมื่อต้องการกลับไปยังหน้า **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="907df-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="907df-178">เซ็กเมนต์ด่วน</span><span class="sxs-lookup"><span data-stu-id="907df-178">Quick segments</span></span>

<span data-ttu-id="907df-179">เซ็กเมนต์ด่วนช่วยให้คุณสามารถสร้างเซ็กเมนต์อย่าวง่ายด้วยตัวดำเนินการเดียวได้อย่างรวดเร็วเพื่อข้อมูลเชิงลึกที่เร็วขึ้น</span><span class="sxs-lookup"><span data-stu-id="907df-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="907df-180">ในหน้า **เซ็กเมนต์** ให้เลือก **ใหม่** > **สร้างจาก**</span><span class="sxs-lookup"><span data-stu-id="907df-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="907df-181">เลือกตัวเลือก **โปรไฟล์** ในการสร้างเซ็กเมนต์ยึดตามเอนทิตี *ลูกค้าแบบรวม*</span><span class="sxs-lookup"><span data-stu-id="907df-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="907df-182">เลือกตัวเลือก **การวัด** ในการสร้างเซ็กเมนต์ตามการวัดที่คุณสร้างไว้ก่อนหน้านี้</span><span class="sxs-lookup"><span data-stu-id="907df-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="907df-183">เลือกตัวเลือก **ระยยอัจฉริยะ** ในการสร้างเซ็กเมนต์สำหรับเอนทิตีผลลัพธ์ที่คุณสร้างขึ้นโดยใช้ความสามารถ **การคาดการณ์** หรือ **โมเดลที่กำหนดเอง** อย่างใดอย่างหนึ่ง</span><span class="sxs-lookup"><span data-stu-id="907df-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="907df-184">ในกล่องโต้ตอบ **สร้างใหม่อย่างรวดเร็ว** ให้เลือกแอตทริบิวต์แบบหล่นลง **ฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="907df-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="907df-185">ระบบจะให้ข้อมูลเชิงลึกเพิ่มเติมที่จะช่วยให้คุณสร้างเซ็กเมนต์ของลูกค้าที่ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="907df-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="907df-186">สำหรับฟิลด์ตามหมวดหมู่ เราจะแสดงจำนวนลูกค้าสูงสุด 10 ราย</span><span class="sxs-lookup"><span data-stu-id="907df-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="907df-187">เลือก **ค่า** และเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="907df-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="907df-188">สำหรับแอตทริบิวต์ที่เป็นตัวเลข ระบบจะแสดงค่าของแอตทริบิวต์ที่อยู่ภายใต้เปอร์เซ็นไทล์ของลูกค้าแต่ละราย</span><span class="sxs-lookup"><span data-stu-id="907df-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="907df-189">เลือก **ตัวดำเนินการ** และ **ค่า** จากนั้นเลือก **ตรวจทาน**.</span><span class="sxs-lookup"><span data-stu-id="907df-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="907df-190">ระบบจะช่วยให้คุณมี **ขนาดเซ็กเมนต์โดยประมาณ**.</span><span class="sxs-lookup"><span data-stu-id="907df-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="907df-191">คุณสามารถเลือกได้ว่าจะสร้างเซ็กเมนต์ที่คุณกำหนดไว้หรือก่อนอื่นกลับไปเพื่อให้ได้ขนาดเซ็กเมนต์ที่ต่าง</span><span class="sxs-lookup"><span data-stu-id="907df-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="907df-192">![ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว](media/quick-segment-name.png "ชื่อและการประมาณสำหรับเซ็กเมนต์ที่รวดเร็ว")</span><span class="sxs-lookup"><span data-stu-id="907df-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="907df-193">ตั้ง **ชื่อ** ให้เซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="907df-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="907df-194">หรือตั้ง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="907df-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="907df-195">เลือก **บันทึก** เพื่อสร้างเซ็กเมนต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="907df-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="907df-196">หลังจากประมวลผลเซ็กเมนต์เสร็จแล้ว คุณสามารถดูได้เหมือนเซ็กเมนต์อื่น ๆ ที่คุณสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="907df-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="907df-197">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="907df-197">Next steps</span></span>

<span data-ttu-id="907df-198">[ส่งออกเซ็กเมนต์](export-destinations.md) และสำรวจ [การ์ดลูกค้า](customer-card-add-in.md) และ [ตัวเชื่อมต่อ](export-power-bi.md)เพื่อรับข้อมูลเชิงลึกในระดับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="907df-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
