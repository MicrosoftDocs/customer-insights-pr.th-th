---
title: จับคู่เอนทิตีสำหรับการรวมข้อมูล
description: จับคู่เอนทิตีเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407159"
---
# <a name="match-entities"></a><span data-ttu-id="11347-103">จับคู่เอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-103">Match entities</span></span>

<span data-ttu-id="11347-104">หลังจากเสร็จสิ้นเฟสการแม็ปแล้ว คุณก็พร้อมที่จะจับคู่เอนทิตีของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="11347-105">เฟสการจับคู่ระบุวิธีการรวมชุดข้อมูลของคุณเข้ากับชุดข้อมูลโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="11347-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="11347-106">เฟสการจับคู่ต้องมี [เอนทิตีที่แม็ปสองรายการ](map-entities.md) เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="11347-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="11347-107">ระบุลำดับการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-107">Specify the match order</span></span>

<span data-ttu-id="11347-108">ไปที่ **รวม** > **จับคู่** และเลือก **ตั้งค่าลำดับ** เพื่อเริ่มเฟสการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="11347-109">การจับคู่แต่ละครั้งจะรวมเอนทิตีสองรายการหรือมากกว่านั้นลงในเอนทิตีเดียว ในขณะที่จะรักษาเรกคอร์ดลูกค้าที่ไม่ซ้ำกันแต่ละรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="11347-110">ในตัวอย่างต่อไปนี้ เราเลือกเอนทิตีสามรายการ **ContactCSV: TestData** เป็นเอนทิตี **หลัก** **WebAccountCSV: TestData** เป็น **เอนทิตี 2** และ **CallRecordSmall: TestData** เป็น **เอนทิตี 3**</span><span class="sxs-lookup"><span data-stu-id="11347-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="11347-111">แผนภาพด้านบนการเลือกแสดงให้เห็นว่าจะดำเนินการลำดับการจับคู่อย่างไร</span><span class="sxs-lookup"><span data-stu-id="11347-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11347-112">![แก้ไขลำดับการจับคู่ข้อมูล](media/configure-data-match-order-edit-page.png "แก้ไขลำดับการจับคู่ข้อมูล")</span><span class="sxs-lookup"><span data-stu-id="11347-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="11347-113">เอนทิตี **หลัก** จะถูกจับคู่กับ **เอนทิตี 2**</span><span class="sxs-lookup"><span data-stu-id="11347-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="11347-114">ชุดข้อมูลที่เป็นผลลัพธ์จากการจับคู่แรกจะถูกจับคู่กับ **เอนทิตี 3**</span><span class="sxs-lookup"><span data-stu-id="11347-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="11347-115">ในตัวอย่างนี้ เราจะเลือกเฉพาะการจับคู่สองรายการที่เลือก แต่ระบบสามารถรองรับได้มากกว่านั้น</span><span class="sxs-lookup"><span data-stu-id="11347-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11347-116">เอนทิตีที่คุณเลือกเป็นเอนทิตี **หลัก** จะทำหน้าที่เป็นพื้นฐานสำหรับชุดข้อมูลหลักแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="11347-117">เอนทิตีเพิ่มเติมที่เลือกในระหว่างเฟสการจับคู่จะถูกเพิ่มลงในเอนทิตีนี้</span><span class="sxs-lookup"><span data-stu-id="11347-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="11347-118">ในขณะเดียวกัน นี่ไม่ได้หมายความว่าเอนทิตีแบบรวมจะรวมข้อมูล *ทั้งหมด* ที่รวมอยู่ในเอนทิตีนี้</span><span class="sxs-lookup"><span data-stu-id="11347-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="11347-119">มีข้อควรพิจารณาสองประการที่สามารถช่วยให้คุณเลือกลำดับชั้นของเอนทิตีของคุณได้ดังนี้:</span><span class="sxs-lookup"><span data-stu-id="11347-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="11347-120">เอนทิตีใดที่คุณพิจารณาว่ามีข้อมูลที่สมบูรณ์และน่าเชื่อถือมากที่สุดเกี่ยวกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="11347-121">เอนทิตีที่คุณเพิ่งระบุมีแอตทริบิวต์ที่ใช้ร่วมกันโดยเอนทิตีอื่นด้วย (ตัวอย่างเช่น ชื่อ หมายเลขโทรศัพท์ หรือที่อยู่อีเมล) หรือไม่</span><span class="sxs-lookup"><span data-stu-id="11347-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="11347-122">หากไม่มี ให้เลือกเอนทิตีที่น่าเชื่อถือที่สุดอันดับสองของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="11347-123">เลือก **เสร็จสิ้น** เพื่อบันทึกลำดับการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="11347-124">กำหนดกฎสำหรับคู่ที่ตรงกันคู่แรกของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-124">Define rules for your first match pair</span></span>

<span data-ttu-id="11347-125">หลังจากระบุลำดับการจับคู่แล้ว คุณจะเห็นการจับคู่ที่กำหนดไว้ในหน้า **การจับคู่**</span><span class="sxs-lookup"><span data-stu-id="11347-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="11347-126">ไทล์ที่ด้านบนของหน้าจอจะว่างเปล่า จนกว่าคุณจะเรียกใช้ลำดับการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11347-127">![กำหนดกฎ](media/configure-data-match-need-rules.png "กำหนดกฎ")</span><span class="sxs-lookup"><span data-stu-id="11347-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="11347-128">คำเตือน **กฎความต้องการ** แนะนำให้ไม่มีการกำหนดกฎการจับคู่สำหรับคู่ที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="11347-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="11347-129">กฎการจับคู่ระบุตรรกะที่คู่ของเอนทิตีที่ระบุจะถูกจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="11347-130">เมื่อต้องการกำหนดกฎแรกของคุณ ให้เปิดบานหน้าต่าง **ข้อกำหนดของกฎ** โดยเลือกแถวการจับคู่ที่สัมพันธ์กันในตารางที่สัมพันธ์กัน (1) และจากนั้น เลือก **สร้างกฎใหม่** (2)</span><span class="sxs-lookup"><span data-stu-id="11347-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-131">![สร้างกฎใหม่](media/configure-data-match-new-rule2.png "สร้างกฎใหม่")</span><span class="sxs-lookup"><span data-stu-id="11347-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="11347-132">ในบานหน้าต่าง **แก้ไขกฎ** ให้ตั้งค่าคอนฟิกเงื่อนไขสำหรับกฎนั้น</span><span class="sxs-lookup"><span data-stu-id="11347-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="11347-133">แต่ละเงื่อนไขจะแสดงด้วยแถวสองแถวที่มีการเลือกแบบบังคับ</span><span class="sxs-lookup"><span data-stu-id="11347-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-134">![บานหน้าต่างของกฎใหม่](media/configure-data-match-new-rule-condition.png "บานหน้าต่างของกฎใหม่")</span><span class="sxs-lookup"><span data-stu-id="11347-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="11347-135">เอนทิตี/ฟิลด์ (แรก) - แอตทริบิวต์ที่จะใช้สำหรับการจับคู่จากเอนทิตีคู่ที่ตรงกันรายการแรก</span><span class="sxs-lookup"><span data-stu-id="11347-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="11347-136">ตัวอย่างอาจรวมถึงหมายเลขโทรศัพท์หรือที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="11347-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="11347-137">เลือกแอตทริบิวต์ที่มีแนวโน้มที่จะไม่ซ้ำกับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="11347-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="11347-138">หลีกเลี่ยงการจับคู่บนพื้นฐานของแอตทริบิวต์ชนิดกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="11347-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="11347-139">กล่าวอีกนัยหนึ่งคือ ถ้าแอตทริบิวต์น่าจะเป็นกิจกรรม ก็อาจจะเป็นเกณฑ์ที่ไม่ดีที่จะจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="11347-140">เอนทิตี/ฟิลด์ (ที่สอง) - แอตทริบิวต์ที่จะใช้สำหรับการจับคู่จากเอนทิตีคู่ที่ตรงกันรายการที่สอง</span><span class="sxs-lookup"><span data-stu-id="11347-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="11347-141">กำหนดมาตรฐาน - **วิธีการปรับสภาพ**: ตัวเลือกการปรับสภาพที่หลากหลายจะพร้อมใช้งานสำหรับแอตทริบิวต์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="11347-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="11347-142">ตัวอย่างเช่น เอาเครื่องหมายวรรคตอนหรือเอาช่องว่างออก</span><span class="sxs-lookup"><span data-stu-id="11347-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="11347-143">สำหรับการปรับสภาพชื่อองค์กร (การแสดงตัวอย่าง) คุณยังสามารถเลือก **ชนิด (โทรศัพท์ ชื่อ องค์กร)** ได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="11347-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-144">![การปรับสภาพ-B2B](media/match-normalization-b2b.png "การปรับสภาพ-B2B")</span><span class="sxs-lookup"><span data-stu-id="11347-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="11347-145">ระดับความแม่นยำ - ระดับของความแม่นยำที่จะใช้สำหรับเงื่อนไขนี้</span><span class="sxs-lookup"><span data-stu-id="11347-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="11347-146">การตั้งค่าระดับความแม่นยำสำหรับเงื่อนไขการจับคู่สามารถมีได้สองชนิด: **พื้นฐาน** และ **กำหนดเอง**</span><span class="sxs-lookup"><span data-stu-id="11347-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="11347-147">พื้นฐาน: ให้คุณมีตัวเลือกสี่รายการให้เลือกจาก: ต่ำ ปานกลาง สูง และพอดี</span><span class="sxs-lookup"><span data-stu-id="11347-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="11347-148">เลือก **พอดี** เพื่อจับคู่เรกคอร์ดที่ตรงกัน 100 เปอร์เซ็นต์เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="11347-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="11347-149">เลือกหนึ่งในระดับอื่นๆ เพื่อให้จับคู่เรกคอร์ดที่ไม่เหมือนกัน 100 เปอร์เซ็นต์</span><span class="sxs-lookup"><span data-stu-id="11347-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="11347-150">กำหนดเอง: ใช้ตัวเลื่อนเพื่อกำหนดเปอร์เซ็นต์ที่กำหนดเองที่เรกคอร์ดจำเป็นต้องจับคู่ หรือป้อนค่าในฟิลด์ **กำหนดเอง**</span><span class="sxs-lookup"><span data-stu-id="11347-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="11347-151">ระบบจะจับคู่เฉพาะเรกคอร์ดที่ผ่านเกณฑ์นี้เป็นคู่ที่ตรงกันแบบรวม</span><span class="sxs-lookup"><span data-stu-id="11347-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="11347-152">ค่าบนตัวเลื่อนอยู่ระหว่าง 0 และ 1</span><span class="sxs-lookup"><span data-stu-id="11347-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="11347-153">ดังนั้น 0.64 แสดงถึง 64 เปอร์เซ็นต์.</span><span class="sxs-lookup"><span data-stu-id="11347-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="11347-154">เลือก **เสร็จสิ้น** เมื่อต้องการบันทึกกฎ</span><span class="sxs-lookup"><span data-stu-id="11347-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="11347-155">เพิ่มเงื่อนไขหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-155">Add multiple conditions</span></span>

<span data-ttu-id="11347-156">เมื่อต้องการจับคู่เอนทิตีของคุณเฉพาะต่อเมื่อตรงตามเงื่อนไขหลายรายการ ให้เพิ่มเงื่อนไขเพิ่มเติมที่เชื่อมโยงผ่านตัวดำเนินการ AND</span><span class="sxs-lookup"><span data-stu-id="11347-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="11347-157">ในบานหน้าต่าง **แก้ไขกฎ** ให้เลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="11347-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="11347-158">นอกจากนี้ คุณยังสามารถลบเงื่อนไขได้ด้วยการเลือกปุ่มเอาออกที่อยู่ถัดจากเงื่อนไขที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="11347-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="11347-159">เลือก **เสร็จสิ้น** เพื่อบันทึกกฎ</span><span class="sxs-lookup"><span data-stu-id="11347-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="11347-160">เพิ่มกฎหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-160">Add multiple rules</span></span>

<span data-ttu-id="11347-161">แต่ละเงื่อนไขจะใช้กับแอตทริบิวต์คู่เดียว ในขณะที่กฎแสดงชุดของเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="11347-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="11347-162">เมื่อต้องการให้เอนทิตีของคุณจับคู่กับชุดของแอตทริบิวต์ต่างๆ คุณสามารถเพิ่มกฎเพิ่มเติมได้</span><span class="sxs-lookup"><span data-stu-id="11347-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="11347-163">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **รวม** > **จับคู่**</span><span class="sxs-lookup"><span data-stu-id="11347-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="11347-164">เลือกเอนทิตีที่คุณต้องการปรับปรุง และเลือก **เพิ่มกฎ**</span><span class="sxs-lookup"><span data-stu-id="11347-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="11347-165">ทำตามกระบวนงานตามที่สรุปไว้ใน [กำหนดกฎสำหรับคู่ที่ตรงกันรายการแรกของคุณ](#define-rules-for-your-first-match-pair)</span><span class="sxs-lookup"><span data-stu-id="11347-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="11347-166">คำสั่งของกฎสำคัญ</span><span class="sxs-lookup"><span data-stu-id="11347-166">The rule order matters.</span></span> <span data-ttu-id="11347-167">อัลกอริทึมการจับคู่พยายามที่จะจับคู่บนพื้นฐานของกฎแรกของคุณ และต่อเนื่องไปยังกฎที่สอง เฉพาะเมื่อไม่มีการระบุการจับคู่ภายใต้กฎแรก</span><span class="sxs-lookup"><span data-stu-id="11347-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="11347-168">กำหนดการขจัดข้อมูลซ้ำซ้อนในเอนทิตีที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="11347-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="11347-169">นอกจากการระบุกฎการจับคู่ข้ามเอนทิตีตามที่อธิบายไว้ในส่วนข้างต้นแล้ว คุณยังสามารถระบุกฎการขจัดข้อมูลซ้ำซ้อนได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="11347-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="11347-170">*การขจัดข้อมูลซ้ำซ้อน* เป็นกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="11347-170">*Deduplication* is a process.</span></span> <span data-ttu-id="11347-171">โดยจะระบุเรกคอร์ดที่ซ้ำกัน ผสานเข้าเป็นเรกคอร์ดเดียวและเชื่อมโยงเรกคอร์ดต้นทางทั้งหมดกับเรกคอร์ดที่ผสานนี้ด้วยรหัสอื่นกับเรกคอร์ดที่ผสาน</span><span class="sxs-lookup"><span data-stu-id="11347-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="11347-172">หลังจากระบุเรกคอร์ดที่ไม่ซ้ำกันแล้ว เรกคอร์ดนั้นจะมีการใช้ในกระบวนการจับคู่ข้ามเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="11347-173">การขจัดข้อมูลซ้ำซ้อนนำไปใช้ที่ระดับเอนทิตีและสามารถนำไปใช้กับทุกเอนทิตีที่ใช้ในกระบวนการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="11347-174">เพิ่มกฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="11347-174">Add deduplication rules</span></span>

1. <span data-ttu-id="11347-175">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **รวม** > **จับคู่**</span><span class="sxs-lookup"><span data-stu-id="11347-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="11347-176">ในส่วน **ข้อมูลซ้ำที่ผสานกัน** ให้เลือก **ตั้งค่าเอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="11347-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="11347-177">ในส่วน **ผสานค่ากำหนด** เลือกเอนทิตีที่คุณต้องการใช้การขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="11347-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="11347-178">ระบุวิธีการผสานเรกคอร์ดที่ซ้ำกันและเลือกหนึ่งในสามตัวเลือกการผสาน:</span><span class="sxs-lookup"><span data-stu-id="11347-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="11347-179">*ที่กรอกข้อมูลมากที่สุด* : ระบุเรกคอร์ดที่มีแอตทริบิวต์ที่ที่กรอกข้อมูลมากที่สุดเป็นเรกคอร์ดผู้ชนะ</span><span class="sxs-lookup"><span data-stu-id="11347-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="11347-180">นี่คือตัวเลือกการผสานเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="11347-180">This is the default merge option.</span></span>
   - <span data-ttu-id="11347-181">*ล่าสุด*: ระบุเรกคอร์ดผู้ชนะโดยพิจารณาจากความใหม่ที่สุด</span><span class="sxs-lookup"><span data-stu-id="11347-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="11347-182">ต้องมีวันที่หรือฟิลด์ตัวเลขเพื่อกำหนดความใหม่</span><span class="sxs-lookup"><span data-stu-id="11347-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="11347-183">*รายการที่เก่าที่สุด*: ระบุเรกคอร์ดผู้ชนะโดยพิจารณาจากความใหม่น้อยที่สุด</span><span class="sxs-lookup"><span data-stu-id="11347-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="11347-184">ต้องมีวันที่หรือฟิลด์ตัวเลขเพื่อกำหนดความใหม่</span><span class="sxs-lookup"><span data-stu-id="11347-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-185">![กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 1](media/match-selfconflation.png "กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 1")</span><span class="sxs-lookup"><span data-stu-id="11347-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="11347-186">เมื่อเลือกเอนทิตีและตั้งค่าการกำหนดลักษณะการผสานแล้ว ให้เลือก **สร้างกฎใหม่** เพื่อกำหนดกฎการขจัดข้อมูลซ้ำซ้อนในระดับเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="11347-187">**เลือกฟิลด์** แสดงรายการฟิลด์ที่มีอยู่ทั้งหมดจากเอนทิตีที่คุณต้องการขจัดข้อมูลต้นทางซ้ำซ้อนออก</span><span class="sxs-lookup"><span data-stu-id="11347-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="11347-188">ระบุการตั้งค่าการปรับมาตรฐานและความแม่นยำในลักษณะเดียวกันตามที่ระบุในการจับคู่ข้ามเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="11347-189">คุณสามารถกำหนดเงื่อนไขเพิ่มเติมได้โดยเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="11347-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-190">![กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 2](media/match-selfconflation-rules.png "กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 2")</span><span class="sxs-lookup"><span data-stu-id="11347-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="11347-191">คุณสามารถสร้างกฎการขจัดข้อมูลซ้ำซ้อนหลายรายการสำหรับเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="11347-192">การเรียกใช้กระบวนการจับคู่ตอนนี้จะจัดกลุ่มเรกคอร์ดตามเงื่อนไขที่กำหนดไว้ในกฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="11347-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="11347-193">หลังจากจัดกลุ่มเรกคอร์ดแล้ว นโยบายการผสานจะมีการนำไปใช้เพื่อระบุเรกคอร์ดผู้ชนะ</span><span class="sxs-lookup"><span data-stu-id="11347-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="11347-194">จากนั้นเรกคอร์ดผู้ชนะนี้จะมีการส่งต่อไปยังการจับคู่ข้ามเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="11347-195">กฎการจับคู่ที่กำหนดเองใดๆ ที่กำหนดไว้สำหรับการจับคู่เสมอและไม่ตรงกันจะยกเลิกกฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="11347-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="11347-196">หากกฎการขจัดข้อมูลซ้ำซ้อนระบุเรกคอร์ดที่ตรงกัน และกฎการจับคู่แบบกำหนดเองมีการตั้งค่าเป็นไม่ตรงกับเรกคอร์ดเหล่านั้น จะไม่มีการจับคู่เรกคอร์ดทั้งสองนี้</span><span class="sxs-lookup"><span data-stu-id="11347-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="11347-197">หลังจากดำเนินกระบวนการจับคู่ คุณจะเห็นสถิติการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="11347-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="11347-198">การระบุกฎการขจัดข้อมูลซ้ำซ้อนไม่บังคับ</span><span class="sxs-lookup"><span data-stu-id="11347-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="11347-199">หากไม่มีการกำหนดค่ากฎดังกล่าว ระบบจะใช้กฎที่กำหนดโดยระบบ</span><span class="sxs-lookup"><span data-stu-id="11347-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="11347-200">โดยจะยุบเรกคอร์ดทั้งหมดที่ใช้ชุดค่าผสมเดียวกัน (การจับคู่แบบตรงทั้งหมด) จากคีย์หลักและฟิลด์ในกฎการจับคู่ลงในเรกคอร์ดเดียวก่อนที่จะส่งข้อมูลเอนทิตีไปยังการจับคู่ข้ามเอนทิตีเพื่อเพิ่มประสิทธิภาพและความสมบูรณ์ของระบบ</span><span class="sxs-lookup"><span data-stu-id="11347-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="11347-201">เรียกใช้ลำดับการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-201">Run your match order</span></span>

<span data-ttu-id="11347-202">หลังจากกำหนดกฎการจับคู่ รวมถึงกฎการจับคู่ข้ามเอนทิตีและการขจัดข้อมูลซ้ำซ้อนคุณสามารถเรียกใช้ลำดับการจับคู่ได้</span><span class="sxs-lookup"><span data-stu-id="11347-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="11347-203">บนหน้า **จับคู่** เลือก **เรียกใช้** เพื่อเริ่มกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="11347-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="11347-204">อัลกอริทึมการจับคู่อาจใช้เวลาสักครู่เพื่อให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="11347-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="11347-205">คุณไม่สามารถเปลี่ยนแปลงคุณสมบัติบนหน้า **การจับคู่** ได้จนกว่ากระบวนการจับคู่จะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="11347-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="11347-206">ลูกค้าคุณจะพบเอนทิตีโปรไฟล์ลูกค้าแบบรวมที่สร้างขึ้นบนหน้า **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="11347-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="11347-207">เอนทิตีของลูกค้าแบบรวมของคุณเรียกว่า **ConflationMatchPairs : CustomerInsights**</span><span class="sxs-lookup"><span data-stu-id="11347-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="11347-208">หากต้องการเปลี่ยนแปลงเพิ่มเติมและดำเนินการขั้นตอนอีกครั้ง คุณสามารถยกเลิกการจับคู่ที่กำลังดำเนินอยู่</span><span class="sxs-lookup"><span data-stu-id="11347-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="11347-209">เลือกข้อความ **กำลังรีเฟรช ...** และเลือก **ยกเลิกงาน** ในบานหน้าต่างด้านล่างที่ปรากฏขึ้น</span><span class="sxs-lookup"><span data-stu-id="11347-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="11347-210">เมื่อกระบวนการจับคู่เสร็จสมบูรณ์ ข้อความ **กำลังรีเฟรช ...** จะเปลี่ยนเป็น **ที่ประสบความสำเร็จ** และคุณสามารถใช้ฟังก์ชันทั้งหมดของหน้าอีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="11347-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="11347-211">กระบวนการการจับคู่แรกส่งผลลัพธ์ในการสร้างเอนทิตีหลักแบบรวม</span><span class="sxs-lookup"><span data-stu-id="11347-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="11347-212">การเรียกใช้การจับคู่ที่เกิดขึ้นตามมาทั้งหมดจะส่งผลลัพธ์ในส่วนขยายของเอนทิตีนั้น</span><span class="sxs-lookup"><span data-stu-id="11347-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="11347-213">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="11347-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="11347-214">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="11347-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="11347-215">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="11347-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="11347-216">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="11347-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="11347-217">ตรวจทานและตรวจสอบการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-217">Review and validate your matches</span></span>

<span data-ttu-id="11347-218">ประเมินคุณภาพของคู่ที่ตรงกันของคุณและปรับแต่ง:</span><span class="sxs-lookup"><span data-stu-id="11347-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="11347-219">บนหน้า **การจับคู่** คุณจะพบไทล์สองรายการที่แสดงข้อมูลเชิงลึกเริ่มต้นเกี่ยวกับข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="11347-220">**ลูกค้าที่ไม่ซ้ำกัน**: แสดงจำนวนของโปรไฟล์ที่ไม่ซ้ำกันที่ระบบระบุ</span><span class="sxs-lookup"><span data-stu-id="11347-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="11347-221">**เรกคอร์ดที่ตรงกัน**: แสดงจำนวนการจับคู่ในคู่ที่ตรงกันทั้งหมดของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="11347-222">ในตาราง **ลำดับการจับคู่** คุณสามารถประเมินผลลัพธ์ของคู่ที่ตรงกันแต่ละคู่ได้โดยการเปรียบเทียบจำนวนของเรกคอร์ดที่มาจากเอนทิตีคู่ที่ตรงกันนี้กับเปอร์เซ็นต์ของเรกคอร์ดที่จับคู่เสร็จเรียบร้อยแล้ว</span><span class="sxs-lookup"><span data-stu-id="11347-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="11347-223">ในส่วน **กฎ** ของเอนทิตีในตาราง **ลำดับการจับคู่** คุณจะพบเปอร์เซ็นต์ของเรกคอร์ดที่จับคู่สำเร็จในระดับกฎ</span><span class="sxs-lookup"><span data-stu-id="11347-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="11347-224">โดยการเลือกสัญลักษณ์ตารางที่อยู่ถัดจากกฎ คุณจะสามารถดูเรกคอร์ดเหล่านี้ทั้งหมดในระดับกฎได้</span><span class="sxs-lookup"><span data-stu-id="11347-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="11347-225">เราขอแนะนำให้คุณตรวจสอบชุดย่อยของเรกคอร์ดเพื่อตรวจสอบว่ามีการจับคู่อย่างถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="11347-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="11347-226">การทดลองด้วยเกณฑ์ความแม่นยำที่แตกต่างกันรอบๆ เงื่อนไขของคุณเพื่อระบุค่าที่ดีที่สุด</span><span class="sxs-lookup"><span data-stu-id="11347-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="11347-227">เลือกจุดไข่ปลา (...) สำหรับกฎการจับคู่ที่คุณต้องการทดลองด้วย และเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="11347-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="11347-228">เลือกเงื่อนไขที่คุณต้องการทดลอง</span><span class="sxs-lookup"><span data-stu-id="11347-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="11347-229">แต่ละเงื่อนไขจะแสดงโดยแถวหนึ่งแถวในบานหน้าต่าง **กฎการจับคู่**</span><span class="sxs-lookup"><span data-stu-id="11347-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="11347-230">สิ่งที่คุณจะเห็นในหน้า **การแสดงตัวอย่างของเกณฑ์** จะขึ้นอยู่กับระดับความแม่นยำที่คุณเลือกสำหรับเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="11347-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="11347-231">ค้นหาจำนวนของเรกคอร์ดที่จับคู่แล้วและที่ไม่ได้จับคู่สำหรับเงื่อนไขที่เลือก</span><span class="sxs-lookup"><span data-stu-id="11347-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="11347-232">รับความเข้าใจทั้งหมดในผลกระทบของระดับเกณฑ์ที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="11347-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="11347-233">คุณสามารถเปรียบเทียบจำนวนเรกคอร์ดที่จะถูกจับคู่ได้ภายใต้ระดับเกณฑ์แต่ละระดับ และดูเรกคอร์ดภายใต้ตัวเลือกแต่ละรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="11347-234">เลือกไทล์แต่ละรายการและตรวจสอบข้อมูลในส่วนของตาราง</span><span class="sxs-lookup"><span data-stu-id="11347-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="11347-235">เพิ่มประสิทธิภาพการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-235">Optimize your matches</span></span>

<span data-ttu-id="11347-236">เพิ่มคุณภาพโดยการตั้งค่าคอนฟิกใหม่บางส่วนของพารามิเตอร์การจับคู่ของคุณ:</span><span class="sxs-lookup"><span data-stu-id="11347-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="11347-237">**เปลี่ยนลำดับการจับคู่** โดยเลือก **แก้ไข** และเปลี่ยนแปลงฟิลด์ลำดับการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="11347-238">![แก้ไขลำดับการจับคู่ข้อมูล](media/configure-data-match-order-edit.png "แก้ไขลำดับการจับคู่ข้อมูล")</span><span class="sxs-lookup"><span data-stu-id="11347-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="11347-239">**เปลี่ยนลำดับของกฎของคุณ** ถ้าคุณกำหนดกฎหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="11347-240">คุณสามารถเรียงลำดับกฎการจับคู่ใหม่ได้ด้วยการเลือกตัวเลือก **ย้ายขึ้น** และ **ย้ายลง** ในกริดกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="11347-241">![เปลี่ยนลำดับกฎ](media/configure-data-change-rule-order.png "เปลี่ยนลำดับกฎ")</span><span class="sxs-lookup"><span data-stu-id="11347-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="11347-242">**ทำซ้ำกฎของคุณ** ถ้าคุณได้กำหนดกฎการจับคู่และต้องการสร้างกฎที่คล้ายกันพร้อมด้วยการปรับเปลี่ยน</span><span class="sxs-lookup"><span data-stu-id="11347-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="11347-243">ทำเช่นนั้นได้โดยการเลือก **ทำซ้ำ**</span><span class="sxs-lookup"><span data-stu-id="11347-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="11347-244">![ทำซ้ำกฎ](media/configure-data-duplicate-rule.png "ทำซ้ำกฎ")</span><span class="sxs-lookup"><span data-stu-id="11347-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="11347-245">**แก้ไขกฎของคุณ** โดยเลือกสัญลักษณ์ **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="11347-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="11347-246">คุณสามารถนำการเปลี่ยนแปลงต่อไปนี้ไปใช้:</span><span class="sxs-lookup"><span data-stu-id="11347-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="11347-247">เปลี่ยนแอตทริบิวต์สำหรับเงื่อนไข: เลือกแอตทริบิวต์ใหม่ภายในแถวเงื่อนไขที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="11347-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="11347-248">เปลี่ยนแปลงค่าเกณฑ์สำหรับเงื่อนไข: ปรับตัวเลื่อนความแม่นยำ</span><span class="sxs-lookup"><span data-stu-id="11347-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="11347-249">เปลี่ยนแปลงวิธีการปรับสภาพสำหรับเงื่อนไข: ปรับปรุงวิธีการปรับสภาพ</span><span class="sxs-lookup"><span data-stu-id="11347-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="11347-250">ระบุเรกคอร์ดการจับคู่แบบกำหนดเองของคุณ</span><span class="sxs-lookup"><span data-stu-id="11347-250">Specify your custom match records</span></span>

<span data-ttu-id="11347-251">คุณสามารถระบุเงื่อนไขที่เรกคอร์ดบางรายการควรจับคู่เสมอหรือต้องไม่จับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="11347-252">กฎเหล่านี้สามารถอัพโหลดเป็นกลุ่มไปยังกระบวนการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="11347-253">เลือกตัวเลือก **การจับคู่ที่กำหนดเอง** บนหน้าจอ **ลำดับการจับคู่**</span><span class="sxs-lookup"><span data-stu-id="11347-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-254">![สร้างการจับคู่แบบกำหนดเอง](media/custom-match-create.png "สร้างการจับคู่แบบกำหนดเอง")</span><span class="sxs-lookup"><span data-stu-id="11347-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="11347-255">ถ้าคุณไม่มีเอนทิตีที่อัพโหลด คุณจะเห็นกล่องโต้ตอบ **การจับคู่แบบกำหนดเอง** ที่คุณต้องกรอกรายละเอียดบางอย่าง</span><span class="sxs-lookup"><span data-stu-id="11347-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="11347-256">หากคุณได้ให้รายละเอียดเหล่านี้ก่อนหน้านี้ ให้ข้ามไปยังขั้นตอนที่ 8</span><span class="sxs-lookup"><span data-stu-id="11347-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-257">![กล่องโต้ตอบการจับคู่แบบกำหนดเองใหม่](media/custom-match-new-dialog-box.png "กล่องโต้ตอบการจับคู่แบบกำหนดเองใหม่")</span><span class="sxs-lookup"><span data-stu-id="11347-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="11347-258">เลือก **กรอกข้อมูลในแม่แบบ** เพื่อรับไฟล์แม่แบบที่สามารถระบุเรกคอร์ดที่ซึ่งเอนทิตีควรจะจับคู่เสมอหรือต้องไม่จับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="11347-259">คุณจะต้องกรอกข้อมูลลงในเรกคอร์ด "จับคู่เสมอ" และ "ต้องไม่จับคู่" ในแฟ้มที่แตกต่างกันสองรายการ</span><span class="sxs-lookup"><span data-stu-id="11347-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="11347-260">แม่แบบจะมีฟิลด์เพื่อระบุเอนทิตีและค่าคีย์หลักของเอนทิตีที่จะใช้ในการจับคู่ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="11347-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="11347-261">ตัวอย่างเช่น ถ้าคุณต้องการคีย์หลัก 12345 จากเอนทิตีการขายให้จับคู่กับคีย์หลัก 34567 จากเอนทิตีผู้ติดต่อเสมอ คุณจะต้องระบุดังนี้:</span><span class="sxs-lookup"><span data-stu-id="11347-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="11347-262">Entity1: การขาย</span><span class="sxs-lookup"><span data-stu-id="11347-262">Entity1: Sales</span></span>
    - <span data-ttu-id="11347-263">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="11347-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="11347-264">Entity2: ผู้ติดต่อ</span><span class="sxs-lookup"><span data-stu-id="11347-264">Entity2: Contact</span></span>
    - <span data-ttu-id="11347-265">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="11347-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="11347-266">แฟ้มแม่แบบเดียวกันสามารถระบุเรกคอร์ดที่ตรงกันแบบกำหนดเองได้จากหลายเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="11347-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="11347-267">หลังจากเพิ่มการแทนที่ทั้งหมดที่คุณต้องการใช้ บันทึกแฟ้มแม่แบบ</span><span class="sxs-lookup"><span data-stu-id="11347-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="11347-268">6. ไปที่ **ข้อมูล** > **แหล่งข้อมูล** และนำเข้าไฟล์เทมเพลตเป็นเอนทิตีใหม่</span><span class="sxs-lookup"><span data-stu-id="11347-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="11347-269">เมื่อมีการนำไปใช้ คุณสามารถใช้เพื่อระบุการตั้งค่าคอนฟิกการจับคู่</span><span class="sxs-lookup"><span data-stu-id="11347-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="11347-270">หลังจากการอัปโหลดไฟล์ และเอนทิตีพร้อมใช้งานแล้ว ให้เลือกตัวเลือก **การจับคู่ที่กำหนดเอง** อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="11347-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="11347-271">คุณจะเห็นตัวเลือกเพื่อระบุเอนทิตีที่คุณต้องการรวมไว้</span><span class="sxs-lookup"><span data-stu-id="11347-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="11347-272">เลือกเอนทิตีที่ต้องการจากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="11347-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11347-273">![การแทนที่การจับคู่แบบกำหนดเอง](media/custom-match-overrides.png "การแทนที่การจับคู่แบบกำหนดเอง")</span><span class="sxs-lookup"><span data-stu-id="11347-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="11347-274">เลือกเอนทิตีที่คุณต้องการใช้สำหรับ **จับคู่เสมอ** และ **ไม่เคยจับคู่** ให้เลือก **เสร็จสิ้น**</span><span class="sxs-lookup"><span data-stu-id="11347-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="11347-275">เลือก **บันทึก** ในหน้า **การจับคู่** สำหรับการตั้งค่าคอนฟิกการจับคู่ที่กำหนดเองที่คุณเพิ่งตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="11347-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="11347-276">เลือก **เรียกใช้** บนหน้า **การจับคู่** เพื่อเริ่มต้นกระบวนการการจับคู่ และการตั้งค่าคอนฟิกการจับคู่ที่กำหนดเองจะมีผล</span><span class="sxs-lookup"><span data-stu-id="11347-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="11347-277">กฎที่ตรงกันของระบบใดๆ จะถูกแทนที่ด้วยชุดการตั้งค่าคอนฟิก</span><span class="sxs-lookup"><span data-stu-id="11347-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="11347-278">เมื่อการจับคู่เสร็จสมบูรณ์แล้ว คุณสามารถตรวจสอบเอนทิตี **ConflationMatchPair** เพื่อยืนยันว่าการแทนที่ถูกนำไปใช้ในการจับคู่การรวม</span><span class="sxs-lookup"><span data-stu-id="11347-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="11347-279">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="11347-279">Next step</span></span>

<span data-ttu-id="11347-280">หลังจากเสร็จสิ้นกระบวนการจับคู่สำหรับคู่ที่ตรงกันอย่างน้อยหนึ่งรายการ คุณอาจแก้ไขความขัดแย้งที่เป็นไปได้ในข้อมูลของคุณโดยผ่านหัวข้อ [**ผสาน**](merge-entities.md)</span><span class="sxs-lookup"><span data-stu-id="11347-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
