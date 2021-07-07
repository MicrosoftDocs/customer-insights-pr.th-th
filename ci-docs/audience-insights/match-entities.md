---
title: จับคู่เอนทิตีสำหรับการรวมข้อมูล
description: จับคู่เอนทิตีเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50b11e7d6f62d7a25eb25a0f2b1c4ad7d859def1
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306051"
---
# <a name="match-entities"></a><span data-ttu-id="ffa01-103">จับคู่เอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-103">Match entities</span></span>

<span data-ttu-id="ffa01-104">เฟสการจับคู่ระบุวิธีการรวมชุดข้อมูลของคุณเข้ากับชุดข้อมูลโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="ffa01-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="ffa01-105">หลังจากทำ [ขั้นตอนการแม็ป](map-entities.md) ในกระบวนการรวมข้อมูลจนเสร็จสมบูรณ์ คุณก็พร้อมที่จะจับคู่เอนทิตีของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="ffa01-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="ffa01-106">เฟสการจับคู่ต้องมี เอนทิตีที่แม็ปสองรายการ เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="ffa01-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="ffa01-107">เพจการจับคู่ประกอบด้วยสามส่วน:</span><span class="sxs-lookup"><span data-stu-id="ffa01-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="ffa01-108">เมตริกหลักที่สรุปจำนวนเรกคอร์ดที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="ffa01-109">จับคู่ลำดับและกฎสำหรับการจับคู่ข้ามเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="ffa01-110">กฎสำหรับการขจัดข้อมูลซ้ำซ้อนของเอนทิตีการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="ffa01-111">ระบุลำดับการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-111">Specify the match order</span></span>

<span data-ttu-id="ffa01-112">ไปที่ **ข้อมูล** > **รวมกัน** > **การจับคู่** และเลือก **กำหนดลำดับ** เพื่อเริ่มเฟสการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="ffa01-113">การจับคู่แต่ละรายการจะรวมสองเอนทิตีขึ้นไปให้เป็นเอนทิตีเดียวที่รวมเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="ffa01-114">ขณะเดียวกัน ก็จะเก็บเรกคอร์ดลูกค้าที่ไม่ซ้ำกันด้วย</span><span class="sxs-lookup"><span data-stu-id="ffa01-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="ffa01-115">ตัวอย่างเช่น เราเลือกสองเอนทิตี: **eCommerce:eCommerceContacts** เป็นเอนทิตีหลัก และ **LoyaltyScheme:loyCustomers** เป็นเอนทิตีรอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="ffa01-116">ลำดับของเอนทิตีจะระบุลำดับที่ระบบจะพยายามจับคู่เรกคอร์ด</span><span class="sxs-lookup"><span data-stu-id="ffa01-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="ภาพหน้าจอของเพจการจับคู่ในพื้นที่รวมของกระบวนการรวมข้อมูล":::
  
<span data-ttu-id="ffa01-118">เอนทิตีหลัก *eCommerce:eCommerceContacts* จับคู่กับเอนทิตี *LoyaltyScheme:loyCustomers* ถัดไป</span><span class="sxs-lookup"><span data-stu-id="ffa01-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="ffa01-119">ชุดข้อมูลที่เป็นผลลัพธ์จากขั้นตอนการจับคู่แรกจะจับคู่กับเอนทิตีต่อไปนี้ หากคุณมีมากกว่าสองเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffa01-120">เอนทิตีที่คุณเลือกเป็นเอนทิตีหลักจะทำหน้าที่เป็นพื้นฐานสำหรับชุดข้อมูลโปรไฟล์แบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="ffa01-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="ffa01-121">เอนทิตีเพิ่มเติมที่เลือกในระหว่างเฟสการจับคู่จะถูกเพิ่มลงในเอนทิตีนี้</span><span class="sxs-lookup"><span data-stu-id="ffa01-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="ffa01-122">แต่ไม่ได้หมายความว่าเอนทิตีรวมกันจะมีข้อมูล *ทั้งหมด* ที่รวมอยู่ในเอนทิตีนี้</span><span class="sxs-lookup"><span data-stu-id="ffa01-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="ffa01-123">มีข้อควรพิจารณาสองประการที่สามารถช่วยให้คุณเลือกลำดับชั้นของเอนทิตีของคุณได้ดังนี้:</span><span class="sxs-lookup"><span data-stu-id="ffa01-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="ffa01-124">เลือกเอนทิตีที่มีข้อมูลโปรไฟล์ที่สมบูรณ์และน่าเชื่อถือที่สุดเกี่ยวกับลูกค้าของคุณเป็นเอนทิตีหลัก</span><span class="sxs-lookup"><span data-stu-id="ffa01-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="ffa01-125">เลือกเอนทิตีที่มีหลายแอตทริบิวต์เหมือนกันกับเอนทิตีอื่น (เช่น ชื่อ หมายเลขโทรศัพท์ หรือที่อยู่อีเมล) เป็นเอนทิตีหลัก</span><span class="sxs-lookup"><span data-stu-id="ffa01-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="ffa01-126">หลังจากระบุลำดับการจับคู่แล้ว คุณจะเห็นคู่การจับคู่ที่กำหนดไว้ในส่วน **รายละเอียดเรกคอร์ดที่จับคู่** ใน **ข้อมูล** > **รวม** > **จับคู่**</span><span class="sxs-lookup"><span data-stu-id="ffa01-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="ffa01-127">เมตริกหลักจะว่างเปล่าจนกว่ากระบวนการจับคู่จะเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="ffa01-128">กำหนดกฎสำหรับคู่การจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-128">Define rules for match pairs</span></span>

<span data-ttu-id="ffa01-129">กฎการจับคู่ระบุตรรกะที่คู่ของเอนทิตีที่ระบุจะถูกจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="ffa01-130">คำเตือน **ต้องมีกฎ** ที่อยู่ถัดจากชื่อเอนทิตีแนะนำว่าไม่มีกฎการจับคู่กำหนดไว้สำหรับคู่การจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="ภาพหน้าจอของส่วนรายละเอียดเรกคอร์ดที่จับคู่พร้อมตัวควบคุมเพื่อเพิ่มกฎที่ไฮไลต์":::

1. <span data-ttu-id="ffa01-132">เลือก **เพิ่มกฎ** ภายใต้เอนทิตีใน **รายละเอียดเรกคอร์ดที่จับคู่** เพื่อกำหนดกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="ffa01-133">ในบานหน้าต่าง **สร้างกฎ** ให้กำหนดค่าเงื่อนไขสำหรับกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="ภาพหน้าจอของกฎการจับคู่แบบเปิดพร้อมเงื่อนไขที่เพิ่มเข้ามา":::

   - <span data-ttu-id="ffa01-135">**เอนทิตี/ฟิลด์ (แถวแรก)**: เลือกเอนทิตีที่เกี่ยวข้องและแอตทริบิวต์เพื่อระบุคุณสมบัติของเรกคอร์ดที่มีแนวโน้มไม่ซ้ำกันสำหรับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="ffa01-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="ffa01-136">ตัวอย่างเช่น หมายเลขโทรศัพท์หรือที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="ffa01-136">For example, a phone number or email address.</span></span> <span data-ttu-id="ffa01-137">หลีกเลี่ยงการจับคู่ตามแอตทริบิวต์ชนิดกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="ffa01-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="ffa01-138">ตัวอย่างเช่น รหัสการซื้อมีแนวโน้มที่จะไม่พบการจับคู่ในชนิดของเรกคอร์ดอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="ffa01-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="ffa01-139">**เอนทิตี/ฟิลด์ (แถวที่สอง)**: เลือกแอตทริบิวต์ที่เกี่ยวข้องกับแอตทริบิวต์ของเอนทิตีที่ระบุในแถวแรก</span><span class="sxs-lookup"><span data-stu-id="ffa01-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="ffa01-140">**ปรับมาตรฐาน**: เลือกจากตัวเลือกการทำให้เป็นมาตรฐานต่อไปนี้สำหรับแอตทริบิวต์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="ffa01-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="ffa01-141">ช่องว่าง: ลบช่องว่างทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="ffa01-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="ffa01-142">*Hello   World* กลายเป็น *HelloWorld*</span><span class="sxs-lookup"><span data-stu-id="ffa01-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="ffa01-143">สัญลักษณ์: ลบสัญลักษณ์และอักขระพิเศษทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="ffa01-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="ffa01-144">*Head&Shoulder* กลายเป็น *HeadShoulder*</span><span class="sxs-lookup"><span data-stu-id="ffa01-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="ffa01-145">ข้อความเป็นตัวพิมพ์เล็ก: แปลงอักขระทั้งหมดเป็นตัวพิมพ์เล็ก</span><span class="sxs-lookup"><span data-stu-id="ffa01-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="ffa01-146">*ตัวพิมพ์ใหญ่และชื่อตัวพิมพ์ใหญ่ทั้งหมด* กลายเป็น *ตัวพิมพ์ใหญ่และชื่อตัวพิมพ์ใหญ่ทั้งหมด*</span><span class="sxs-lookup"><span data-stu-id="ffa01-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="ffa01-147">Unicode เป็น ASCII: แปลงสัญกรณ์ Unicode เป็นอักขระ ASCII</span><span class="sxs-lookup"><span data-stu-id="ffa01-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="ffa01-148">*/u00B2* กลายเป็น *2*</span><span class="sxs-lookup"><span data-stu-id="ffa01-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="ffa01-149">ตัวเลข: แปลงระบบตัวเลขอื่นๆ เช่น เลขโรมัน เป็นเลขอารบิก</span><span class="sxs-lookup"><span data-stu-id="ffa01-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="ffa01-150">*VIII* กลายเป็น *8*</span><span class="sxs-lookup"><span data-stu-id="ffa01-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="ffa01-151">ชนิดของความหมาย: กำหนดมาตรฐานของชื่อ ชื่อเรื่อง หมายเลขโทรศัพท์ ที่อยู่ ฯลฯ</span><span class="sxs-lookup"><span data-stu-id="ffa01-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="ffa01-152">**ความแม่นยำ**: ตั้งค่าระดับความแม่นยำที่จะใช้สำหรับเงื่อนไขนี้</span><span class="sxs-lookup"><span data-stu-id="ffa01-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="ffa01-153">**พื้นฐาน**: เลือกจาก *ต่ำ*, *ปานกลาง*, *สูง* และ *แน่นอน*</span><span class="sxs-lookup"><span data-stu-id="ffa01-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="ffa01-154">เลือก **พอดี** เพื่อจับคู่เรกคอร์ดที่ตรงกัน 100 เปอร์เซ็นต์เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="ffa01-155">เลือกหนึ่งในระดับอื่นๆ เพื่อให้จับคู่เรกคอร์ดที่ไม่เหมือนกัน 100 เปอร์เซ็นต์</span><span class="sxs-lookup"><span data-stu-id="ffa01-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="ffa01-156">**กำหนดเอง**: กำหนดเปอร์เซ็นต์ที่เรกคอร์ดต้องตรงกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="ffa01-157">ระบบจะจับคู่เรกคอร์ดที่ผ่านเกณฑ์นี้เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="ffa01-158">ระบุ **ชื่อ** สำหรับกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="ffa01-159">[เพิ่มเงื่อนไขเพิ่มเติม](#add-conditions-to-a-rule) หรือเลือก **เสร็จ** เพื่อสรุปกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="ffa01-160">หรือ [เพิ่มกฎเพิ่มเติม](#add-rules-to-a-match-pair)</span><span class="sxs-lookup"><span data-stu-id="ffa01-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="ffa01-161">เลือก **บันทึก** เพื่อนำการเปลี่ยนแปลงของคุณมาใช้</span><span class="sxs-lookup"><span data-stu-id="ffa01-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="ffa01-162">เพิ่มเงื่อนไขลงในกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-162">Add conditions to a rule</span></span>

<span data-ttu-id="ffa01-163">หากต้องการจับคู่เอนทิตีเฉพาะเมื่อแอตทริบิวต์ตรงตามเงื่อนไขหลายข้อ ให้เพิ่มเงื่อนไขเพิ่มเติมในกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="ffa01-164">เงื่อนไขเชื่อมต่อกับตัวดำเนินการเชิงตรรกะ และจะมีการดำเนินการก็ต่อเมื่อตรงตามเงื่อนไขทั้งหมดเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="ffa01-165">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** และเลือก **แก้ไข** ในกฎที่คุณต้องการเพิ่มเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="ffa01-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="ffa01-166">ในบานหน้าต่าง **แก้ไขกฎ** ให้เลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="ffa01-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="ffa01-167">เลือก **เสร็จสิ้น** เพื่อบันทึกกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="ffa01-168">เพิ่มกฎลงในคู่การจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-168">Add rules to a match pair</span></span>

<span data-ttu-id="ffa01-169">กฎการจับคู่แสดงถึงชุดเงื่อนไข</span><span class="sxs-lookup"><span data-stu-id="ffa01-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="ffa01-170">หากต้องการจับคู่เอนทิตีตามเงื่อนไขที่อิงตามแอตทริบิวต์หลายรายการ ให้เพิ่มกฎเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="ffa01-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="ffa01-171">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** และเลือก **เพิ่มกฎ** ในเอนทิตีที่คุณต้องการเพิ่มกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="ffa01-172">ทำตามขั้นตอนใน [กำหนดกฎสำหรับคู่การจับคู่](#define-rules-for-match-pairs)</span><span class="sxs-lookup"><span data-stu-id="ffa01-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="ffa01-173">ลำดับของกฎมีความสำคัญ</span><span class="sxs-lookup"><span data-stu-id="ffa01-173">The order of rules matters.</span></span> <span data-ttu-id="ffa01-174">อัลกอริทึมการจับคู่จะพยายามจับคู่ตามเกณฑ์ของกฎข้อแรกของคุณและดำเนินการต่อกับกฎข้อที่สองเฉพาะเมื่อไม่มีการระบุการจับคู่กับกฎข้อแรก</span><span class="sxs-lookup"><span data-stu-id="ffa01-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

### <a name="change-the-entity-order-in-match-rules"></a><span data-ttu-id="ffa01-175">เปลี่ยนลำดับเอนทิตีในกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-175">Change the entity order in match rules</span></span>

<span data-ttu-id="ffa01-176">คุณสามารถจัดลำดับเอนทิตีใหม่สำหรับกฎการจับคู่เพื่อเปลี่ยนลำดับในการประมวลผล</span><span class="sxs-lookup"><span data-stu-id="ffa01-176">You can reorder entities for match rules to change the order in which they are processed.</span></span> <span data-ttu-id="ffa01-177">กฎที่ขัดแย้งกันเนื่องจากลำดับที่เปลี่ยนแปลง จะถูกลบออก</span><span class="sxs-lookup"><span data-stu-id="ffa01-177">Rules that are conflicting because of a changed order will be removed.</span></span> <span data-ttu-id="ffa01-178">คุณต้องสร้างกฎที่ถูกลบใหม่ด้วยการตั้งค่าคอนฟิกที่อัปเดต</span><span class="sxs-lookup"><span data-stu-id="ffa01-178">You have to recreate removed rules with an updated configuration.</span></span>

1. <span data-ttu-id="ffa01-179">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** และเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="ffa01-179">Go to **Data** > **Unify** > **Match** and select **Edit**.</span></span>

1. <span data-ttu-id="ffa01-180">ในบานหน้าต่าง **แก้ไขกฎ** เลือกตัวควบคุม **เลื่อนขึ้น/ลง** หรือลากและวางเอนทิตีเพื่อเปลี่ยนลำดับ</span><span class="sxs-lookup"><span data-stu-id="ffa01-180">In the **Edit rule** pane, select the **Move up/down** control or drag and drop entities to change the order.</span></span>

   :::image type="content" source="media/reorder-match-rules.png" alt-text="ตัวเลือกในการเปลี่ยนลำดับในการประมวลผลเอนทิตีในระยะการจับคู่":::

1. <span data-ttu-id="ffa01-182">เลือก **เสร็จสิ้น** เพื่อบันทึกกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-182">Select **Done** so save the rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="ffa01-183">กำหนดการขจัดข้อมูลซ้ำซ้อนในเอนทิตีที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-183">Define deduplication on a match entity</span></span>

<span data-ttu-id="ffa01-184">นอกจาก [กฎการจับคู่ข้ามเอนทิตี](#define-rules-for-match-pairs) คุณยังสามารถระบุกฎการขจัดข้อมูลซ้ำซ้อนได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="ffa01-184">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="ffa01-185">*การขจัดข้อมูลซ้ำซ้อน* เป็นอีกกระบวนการหนึ่งเมื่อมีการจับคู่เรกคอร์ด</span><span class="sxs-lookup"><span data-stu-id="ffa01-185">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="ffa01-186">โดยจะระบุเรกคอร์ดที่ซ้ำกันและรวมเข้าเป็นเรกคอร์ดเดียว</span><span class="sxs-lookup"><span data-stu-id="ffa01-186">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="ffa01-187">เรกคอร์ดต้นทางได้รับการเชื่อมโยงกับเรกคอร์ดที่ผนวกกับรหัสสำรอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-187">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="ffa01-188">เรกคอร์ดที่ไม่ซ้ำกันจะมีการใช้ในกระบวนการจับคู่ข้ามเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-188">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="ffa01-189">การขจัดข้อมูลซ้ำซ้อนจะเกิดขึ้นกับแต่ละเอนทิตีและสามารถกำหนดค่าทุกเอนทิตีที่ใช้ในคู่การจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-189">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="ffa01-190">การระบุกฎการขจัดข้อมูลซ้ำซ้อนไม่บังคับ</span><span class="sxs-lookup"><span data-stu-id="ffa01-190">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="ffa01-191">หากไม่มีการกำหนดค่ากฎดังกล่าว ระบบจะใช้กฎที่กำหนดโดยระบบ</span><span class="sxs-lookup"><span data-stu-id="ffa01-191">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="ffa01-192">กฎดังกล่าวจะรวมเรกคอร์ดทั้งหมดเป็นเรกคอร์ดเดียวก่อนที่จะส่งข้อมูลเอนทิตีไปยังการจับคู่ข้ามเอนทิตีเพื่อเพิ่มประสิทธิภาพ</span><span class="sxs-lookup"><span data-stu-id="ffa01-192">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="ffa01-193">เพิ่มกฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="ffa01-193">Add deduplication rules</span></span>

1. <span data-ttu-id="ffa01-194">ไปที่ **ข้อมูล** > **รวม** > **จับคู่**</span><span class="sxs-lookup"><span data-stu-id="ffa01-194">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="ffa01-195">ในส่วน **ข้อมูลซ้ำที่ผสานกัน** ให้เลือก **ตั้งค่าเอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="ffa01-195">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="ffa01-196">ในกรณีที่สร้างกฎการขจัดข้อมูลซ้ำซ้อนแล้ว ให้เลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="ffa01-196">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="ffa01-197">ในบานหน้าต่าง **รวมการกำหนดลักษณะ** เลือกเอนทิตีที่คุณต้องการเรียกใช้การขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="ffa01-197">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="ffa01-198">ระบุวิธีการรวมเรกคอร์ดที่ซ้ำกันและเลือกหนึ่งในสามตัวเลือก:</span><span class="sxs-lookup"><span data-stu-id="ffa01-198">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="ffa01-199">**ที่กรอกข้อมูลมากที่สุด** : ระบุเรกคอร์ดที่มีฟิลด์แอตทริบิวต์ที่กรอกข้อมูลมากที่สุดเป็นเรกคอร์ดผู้ชนะ</span><span class="sxs-lookup"><span data-stu-id="ffa01-199">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="ffa01-200">ซึ่งเป็นตัวเลือกการผสานเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-200">It's the default merge option.</span></span>
   - <span data-ttu-id="ffa01-201">**ล่าสุด**: ระบุเรกคอร์ดผู้ชนะโดยพิจารณาจากความใหม่ที่สุด</span><span class="sxs-lookup"><span data-stu-id="ffa01-201">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="ffa01-202">ต้องมีวันที่หรือฟิลด์ตัวเลขเพื่อกำหนดความใหม่</span><span class="sxs-lookup"><span data-stu-id="ffa01-202">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="ffa01-203">**รายการที่เก่าที่สุด**: ระบุเรกคอร์ดผู้ชนะโดยพิจารณาจากความใหม่น้อยที่สุด</span><span class="sxs-lookup"><span data-stu-id="ffa01-203">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="ffa01-204">ต้องมีวันที่หรือฟิลด์ตัวเลขเพื่อกำหนดความใหม่</span><span class="sxs-lookup"><span data-stu-id="ffa01-204">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffa01-205">![กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 1](media/match-selfconflation.png "กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 1")</span><span class="sxs-lookup"><span data-stu-id="ffa01-205">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="ffa01-206">เมื่อเลือกเอนทิตีและตั้งค่าการกำหนดลักษณะการผสานแล้ว ให้เลือก **เพิ่มกฎ** เพื่อกำหนดกฎการขจัดข้อมูลซ้ำซ้อนในระดับเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-206">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="ffa01-207">**เลือกฟิลด์** แสดงรายการฟิลด์ที่มีอยู่ทั้งหมดจากเอนทิตีนั้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-207">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="ffa01-208">เลือกฟิลด์ที่คุณต้องการตรวจสอบรายการที่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-208">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="ffa01-209">เลือกฟิลด์ที่มีแนวโน้มไม่ซ้ำกันสำหรับลูกค้าหนึ่งราย</span><span class="sxs-lookup"><span data-stu-id="ffa01-209">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="ffa01-210">ตัวอย่างเช่น ที่อยู่อีเมล หรือชื่อ เมือง และหมายเลขโทรศัพท์รวมกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-210">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="ffa01-211">ระบุการตั้งค่าการปรับมาตรฐานและความแม่นยำ</span><span class="sxs-lookup"><span data-stu-id="ffa01-211">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="ffa01-212">กำหนดเงื่อนไขเพิ่มเติมได้โดยเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="ffa01-212">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffa01-213">![กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 2](media/match-selfconflation-rules.png "กฎการขจัดข้อมูลซ้ำซ้อนขั้นตอนที่ 2")</span><span class="sxs-lookup"><span data-stu-id="ffa01-213">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="ffa01-214">คุณสามารถสร้างกฎการขจัดข้อมูลซ้ำซ้อนหลายรายการสำหรับเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-214">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="ffa01-215">การเรียกใช้กระบวนการจับคู่ตอนนี้จะจัดกลุ่มเรกคอร์ดตามเงื่อนไขที่กำหนดไว้ในกฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="ffa01-215">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="ffa01-216">หลังจากจัดกลุ่มเรกคอร์ดแล้ว นโยบายการผสานจะมีการนำไปใช้เพื่อระบุเรกคอร์ดผู้ชนะ</span><span class="sxs-lookup"><span data-stu-id="ffa01-216">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="ffa01-217">จากนั้นเรกคอร์ดผู้ชนะนี้จะถูกส่งต่อไปยังการจับคู่ข้ามเอนทิตี พร้อมกับเรกคอร์ดที่ไม่ใช่ผู้ชนะ (เช่น รหัสทางเลือก) เพื่อปรับปรุงคุณภาพการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-217">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="ffa01-218">กฎการจับคู่ที่กำหนดเองใดๆ ที่กำหนดไว้จะแทนที่กฎการขจัดข้อมูลซ้ำซ้อน</span><span class="sxs-lookup"><span data-stu-id="ffa01-218">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="ffa01-219">หากกฎการขจัดข้อมูลซ้ำซ้อนระบุเรกคอร์ดที่ตรงกัน และกฎการจับคู่แบบกำหนดเองมีการตั้งค่าเป็นไม่ตรงกับเรกคอร์ดเหล่านั้น จะไม่มีการจับคู่เรกคอร์ดทั้งสองนี้</span><span class="sxs-lookup"><span data-stu-id="ffa01-219">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="ffa01-220">หลังจาก [การดำเนินกระบวนการจับคู่](#run-the-match-process) คุณจะเห็นสถิติการขจัดข้อมูลซ้ำซ้อนในไทล์เมตริกหลัก</span><span class="sxs-lookup"><span data-stu-id="ffa01-220">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="ffa01-221">ผลลัพธ์รายการที่ซ้ำกันเป็นเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-221">Deduplication output as an entity</span></span>

<span data-ttu-id="ffa01-222">กระบวนการขจัดข้อมูลซ้ำซ้อนจะสร้างเอนทิตีใหม่สำหรับทุกเอนทิตีจากคู่การจับคู่เพื่อระบุเรกคอร์ดที่ไม่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-222">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="ffa01-223">เอนทิตีเหล่านี้สามารถพบได้พร้อมกับ **ConflationMatchPairs:CustomerInsights** ในส่วน **ระบบ** ในหน้า **เอนทิตี** พร้อมชื่อ **Deduplication_DataSource_Entity**</span><span class="sxs-lookup"><span data-stu-id="ffa01-223">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="ffa01-224">เอนทิตีผลลัพธ์การยกเลิกการทําซ้ำประกอบด้วยข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="ffa01-224">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="ffa01-225">รหัส / คีย์</span><span class="sxs-lookup"><span data-stu-id="ffa01-225">IDs / Keys</span></span>
  - <span data-ttu-id="ffa01-226">ฟิลด์คีย์หลักและฟิลด์รหัสสำรอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-226">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="ffa01-227">ฟิลด์รหัสสำรองประกอบด้วยรหัสสำรองทั้งหมดที่ระบุสำหรับเรกคอร์ด</span><span class="sxs-lookup"><span data-stu-id="ffa01-227">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="ffa01-228">ฟิลด์ Deduplication_GroupId แสดงกลุ่มหรือคลัสเตอร์ที่ระบุภายในเอนทิตีที่จัดกลุ่มเรกคอร์ดที่คล้ายกันทั้งหมดตามฟิลด์การยกเลิกการทําซ้ำที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="ffa01-228">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="ffa01-229">ซึ่งใช้เพื่อวัตถุประสงค์ในการประมวลผลระบบ</span><span class="sxs-lookup"><span data-stu-id="ffa01-229">It's used for system processing purposes.</span></span> <span data-ttu-id="ffa01-230">หากไม่มีการระบุกฎการยกเลิกการทําซ้ำด้วยตนเอง และใช้กฎการยกเลิกการทําซ้ำที่กำหนดโดยระบบ คุณอาจไม่พบฟิลด์นี้ในเอนทิตีผลลัพธ์การยกเลิกการทําซ้ำ</span><span class="sxs-lookup"><span data-stu-id="ffa01-230">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="ffa01-231">Deduplication_WinnerId: ฟิลด์นี้มีรหัสผู้ชนะจากกลุ่มหรือคลัสเตอร์ที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="ffa01-231">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="ffa01-232">ถ้า Deduplication_WinnerId เหมือนกับค่าคีย์หลักสำหรับเร็กคอร์ด หมายความว่าเร็กคอร์ดนั้นเป็นเรกคอร์ดผู้ชนะ</span><span class="sxs-lookup"><span data-stu-id="ffa01-232">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="ffa01-233">ฟิลด์ที่ใช้เพื่อกำหนดกฎการยกเลิกการทําซ้ำ</span><span class="sxs-lookup"><span data-stu-id="ffa01-233">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="ffa01-234">ฟิลด์กฎและคะแนนเพื่อระบุว่ากฎการยกเลิกการทําซ้ำใดถูกนำไปใช้ และคะแนนที่ส่งคืนโดยอัลกอริทึมการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-234">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="ffa01-235">เรียกใช้กระบวนการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-235">Run the match process</span></span>

<span data-ttu-id="ffa01-236">เมื่อมีการกำหนดค่ากฎการจับคู่ รวมถึงกฎการจับคู่ข้ามเอนทิตีและการขจัดข้อมูลซ้ำซ้อนคุณสามารถเรียกใช้กระบวนการจับคู่ได้</span><span class="sxs-lookup"><span data-stu-id="ffa01-236">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="ffa01-237">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** และเลือก **เรียกใช้** เพื่อเริ่มกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="ffa01-237">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="ffa01-238">อัลกอริทึมการจับคู่ต้องใช้เวลาสักพักจึงจะเสร็จสมบูรณ์ และคุณไม่สามารถเปลี่ยนแปลงการกำหนดค่าได้จนกว่าจะเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-238">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="ffa01-239">เพื่อทำการเปลี่ยนแปลง คุณสามารถยกเลิกการเรียกใช้ได้</span><span class="sxs-lookup"><span data-stu-id="ffa01-239">To make changes, you can cancel the run.</span></span> <span data-ttu-id="ffa01-240">เลือกสถานะของงานและเลือก **ยกเลิกงาน** ในบานหน้าต่าง **รายละเอียดความคืบหน้า**</span><span class="sxs-lookup"><span data-stu-id="ffa01-240">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="ffa01-241">คุณจะพบผลลัพธ์ของการดำเนินการกับเอนทิตีโปรไฟล์ลูกค้าแบบรวมที่ประสบความสำเร็จในเพจ **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="ffa01-241">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="ffa01-242">เอนทิตีลูกค้าแบบรวมมีชื่อว่า **ลูกค้า** ในส่วน **โปรไฟล์**</span><span class="sxs-lookup"><span data-stu-id="ffa01-242">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="ffa01-243">การดำเนินการจับคู่ครั้งแรกที่ประสบความสำเร็จทำให้เกิดเอนทิตี *ลูกค้า* แบบรวม</span><span class="sxs-lookup"><span data-stu-id="ffa01-243">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="ffa01-244">การดำเนินการจับคู่ที่ตามมาทั้งหมดจะขยายเอนทิตีนั้น</span><span class="sxs-lookup"><span data-stu-id="ffa01-244">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="ffa01-245">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="ffa01-245">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ffa01-246">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="ffa01-246">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ffa01-247">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="ffa01-247">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ffa01-248">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="ffa01-248">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="ffa01-249">ตรวจทานและตรวจสอบการจับคู่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="ffa01-249">Review and validate your matches</span></span>

<span data-ttu-id="ffa01-250">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** เพื่อประเมินคุณภาพของคู่การจับคู่ของคุณและปรับปรุง หากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="ffa01-250">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="ffa01-251">ไทล์ที่อยู่ด้านบนของเพจจะแสดงเมตริกหลัก โดยสรุปจำนวนเรกคอร์ดที่ตรงกันและรายการที่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-251">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="ภาพหน้าจอที่ครอบตัดของเมตริกหลักในเพจการจับคู่พร้อมตัวเลขและรายละเอียด":::

- <span data-ttu-id="ffa01-253">**เรกคอร์ดต้นทางที่ไม่ซ้ำกัน** แสดงจำนวนเรกคอร์ดต้นทางแต่ละรายการที่ประมวลผลในการดำเนินการจับคู่ล่าสุด</span><span class="sxs-lookup"><span data-stu-id="ffa01-253">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="ffa01-254">**เรกคอร์ดที่ตรงกันและไม่ตรงกัน** ไฮไลต์จำนวนเรกคอร์ดที่ไม่ซ้ำกันที่เหลืออยู่หลังจากประมวลผลกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-254">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="ffa01-255">**เรกคอร์ดที่ตรงกันเท่านั้น** แสดงจำนวนของการจับคู่ในคู่การจับคู่ทั้งหมดของคุณ</span><span class="sxs-lookup"><span data-stu-id="ffa01-255">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="ffa01-256">คุณสามารถประเมินผลลัพธ์ของคู่การจับคู่แต่ละคู่และกฎของคู่นั้นได้ในตาราง **รายละเอียดเรกคอร์ดที่ตรงกัน**</span><span class="sxs-lookup"><span data-stu-id="ffa01-256">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="ffa01-257">เปรียบเทียบจำนวนของเรกคอร์ดที่มาจากคู่การจับคู่กับเปอร์เซ็นต์ของเรกคอร์ดที่จับคู่สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="ffa01-257">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="ffa01-258">ตรวจสอบกฎของคู่การจับคู่เพื่อดูเปอร์เซ็นต์ของเรกคอร์ดที่จับคู่สำเร็จในระดับกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-258">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="ffa01-259">เลือกจุดไข่ปลา (...) จากนั้นเลือก **ดูตัวอย่างการจับคู่** เพื่อดูเรกคอร์ดเหล่านี้ทั้งหมดในระดับกฎ</span><span class="sxs-lookup"><span data-stu-id="ffa01-259">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="ffa01-260">เราขอแนะนำให้คุณดูที่บางเรกคอร์ดเพื่อตรวจสอบว่ามีการจับคู่อย่างถูกต้องหรือไม่</span><span class="sxs-lookup"><span data-stu-id="ffa01-260">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="ffa01-261">ลองใช้เกณฑ์ความแม่นยำที่แตกต่างกันสำหรับเงื่อนไขเพื่อค้นหาค่าที่เหมาะสมที่สุด</span><span class="sxs-lookup"><span data-stu-id="ffa01-261">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="ffa01-262">เลือกจุดไข่ปลา (...) สำหรับกฎที่คุณต้องการทดลองและเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="ffa01-262">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="ffa01-263">เปลี่ยนค่าความแม่นยำในเงื่อนไขที่คุณต้องการแก้ไข</span><span class="sxs-lookup"><span data-stu-id="ffa01-263">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="ffa01-264">เลือก **ดูตัวอย่าง** เพื่อที่จะดูจำนวนของเรกคอร์ดที่ตรงกันและไม่ตรงกันสำหรับเงื่อนไขที่เลือก</span><span class="sxs-lookup"><span data-stu-id="ffa01-264">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="ffa01-265">จัดการกฎการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-265">Manage match rules</span></span>

<span data-ttu-id="ffa01-266">คุณสามารถกำหนดค่าใหม่และปรับแต่งพารามิเตอร์การจับคู่ส่วนใหญ่</span><span class="sxs-lookup"><span data-stu-id="ffa01-266">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="ภาพหน้าจอของเมนูแบบหล่นลงพร้อมตัวเลือกกฎการจับคู่":::

- <span data-ttu-id="ffa01-268">**เปลี่ยนลำดับของกฎของคุณ** ถ้าคุณกำหนดกฎหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="ffa01-268">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="ffa01-269">คุณสามารถเรียงลำดับกฎการจับคู่ใหม่ได้โดยเลือกตัวเลือก **เลื่อนขึ้น** และ **เลื่อนลง** หรือโดยการลากและวาง</span><span class="sxs-lookup"><span data-stu-id="ffa01-269">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="ffa01-270">**เปลี่ยนเงื่อนไขของกฎ** โดยการเลือก **แก้ไข** และเลือกฟิลด์ต่างๆ</span><span class="sxs-lookup"><span data-stu-id="ffa01-270">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="ffa01-271">**ปิดใช้งานกฎ** เพื่อรักษากฎการจับคู่ในขณะที่ไม่รวมกฎจากกระบวนการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-271">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="ffa01-272">**ทำซ้ำกฎของคุณ** หากคุณได้กำหนดกฎการจับคู่และต้องการสร้างกฎที่คล้ายกันด้วยการปรับเปลี่ยน ให้เลือก **ทำซ้ำ**</span><span class="sxs-lookup"><span data-stu-id="ffa01-272">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="ffa01-273">**ลบกฎ** โดยเลือกสัญลักษณ์ **ลบ**</span><span class="sxs-lookup"><span data-stu-id="ffa01-273">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="ffa01-274">ระบุเงื่อนไขการจับคู่ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-274">Specify custom match conditions</span></span>

<span data-ttu-id="ffa01-275">คุณสามารถระบุเงื่อนไขที่เรกคอร์ดบางรายการควรจับคู่เสมอหรือต้องไม่จับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-275">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="ffa01-276">คุณสามารถอัปโหลดกฎเหล่านี้เพื่อแทนที่กระบวนการจับคู่มาตรฐานได้</span><span class="sxs-lookup"><span data-stu-id="ffa01-276">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="ffa01-277">ตัวอย่างเช่น หากมี John Doe I และ John Doe II ในเรกคอร์ดของเรา ระบบอาจจับคู่พวกเขาเป็นบุคคลเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-277">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="ffa01-278">กฎการจับคู่ที่กำหนดเองช่วยให้คุณสามารถระบุว่าโปรไฟล์ของพวกเขาหมายถึงบุคคลที่ต่างกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-278">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="ffa01-279">ไปที่ **ข้อมูล** > **รวม** > **จับคู่** และเลือก **การจับคู่ที่กำหนดเอง** ในส่วน **รายละเอียดเรกคอร์ดที่ตรงกัน**</span><span class="sxs-lookup"><span data-stu-id="ffa01-279">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="ภาพหน้าจอของส่วนกฎการจับคู่พร้อมตัวควบคุมการจับคู่ที่กำหนดเองที่ไฮไลต์":::

1. <span data-ttu-id="ffa01-281">หากคุณไม่ได้กำหนดกฎการจับคู่ที่กำหนดเองไว้ คุณจะเห็นบานหน้าต่าง **การจับคู่ที่กำหนดเอง** พร้อมรายละเอียดเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="ffa01-281">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="ffa01-282">เลือก **กรอกข้อมูลในแม่แบบ** เพื่อรับไฟล์แม่แบบที่สามารถระบุเรกคอร์ดที่ซึ่งเอนทิตีควรจะจับคู่เสมอหรือต้องไม่จับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-282">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="ffa01-283">คุณจะต้องกรอกข้อมูลลงในเรกคอร์ด "จับคู่เสมอ" และ "ต้องไม่จับคู่" ในแฟ้มที่แตกต่างกันสองรายการ</span><span class="sxs-lookup"><span data-stu-id="ffa01-283">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="ffa01-284">แม่แบบจะมีฟิลด์เพื่อระบุเอนทิตีและค่าคีย์หลักของเอนทิตีที่จะใช้ในการจับคู่ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-284">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="ffa01-285">ตัวอย่างเช่น หากคุณต้องการคีย์หลัก *12345* จากเอนทิตี *การขาย* จับคู่กับคีย์หลัก *34567* จากเอนทิตี *ผู้ติดต่อ* เสมอ ให้กรอกข้อมูลในเทมเพลต:</span><span class="sxs-lookup"><span data-stu-id="ffa01-285">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="ffa01-286">Entity1: การขาย</span><span class="sxs-lookup"><span data-stu-id="ffa01-286">Entity1: Sales</span></span>
    - <span data-ttu-id="ffa01-287">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="ffa01-287">Entity1Key: 12345</span></span>
    - <span data-ttu-id="ffa01-288">Entity2: ผู้ติดต่อ</span><span class="sxs-lookup"><span data-stu-id="ffa01-288">Entity2: Contact</span></span>
    - <span data-ttu-id="ffa01-289">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="ffa01-289">Entity2Key: 34567</span></span>

   <span data-ttu-id="ffa01-290">แฟ้มแม่แบบเดียวกันสามารถระบุเรกคอร์ดที่ตรงกันแบบกำหนดเองได้จากหลายเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="ffa01-290">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="ffa01-291">หากคุณต้องการระบุการจับคู่แบบกำหนดเองสำหรับการยกเลิกการทําซ้ำในเอนทิตี ให้ระบุเอนทิตีเดียวกันกับทั้ง เอนทิตี 1 และ เอนทิตี 2 และตั้งค่าคีย์หลักที่แตกต่างกัน</span><span class="sxs-lookup"><span data-stu-id="ffa01-291">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="ffa01-292">หลังจากเพิ่มการแทนที่ทั้งหมดที่คุณต้องการใช้ บันทึกแฟ้มแม่แบบ</span><span class="sxs-lookup"><span data-stu-id="ffa01-292">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="ffa01-293">ไปที่ **ข้อมูล** > **แหล่งข้อมูล** และนำเข้าไฟล์เทมเพลตเป็นเอนทิตีใหม่</span><span class="sxs-lookup"><span data-stu-id="ffa01-293">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="ffa01-294">เมื่อมีการนำไปใช้ คุณสามารถใช้เพื่อระบุการตั้งค่าคอนฟิกการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-294">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="ffa01-295">หลังจากการอัปโหลดไฟล์ และเอนทิตีพร้อมใช้งานแล้ว ให้เลือกตัวเลือก **การจับคู่ที่กำหนดเอง** อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="ffa01-295">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="ffa01-296">คุณจะเห็นตัวเลือกเพื่อระบุเอนทิตีที่คุณต้องการรวมไว้</span><span class="sxs-lookup"><span data-stu-id="ffa01-296">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="ffa01-297">เลือกเอนทิตีที่จำเป็นจากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="ffa01-297">Select the required entities from the dropdown menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="ภาพหน้าจอของกล่องโต้ตอบเพื่อเลือกแทนที่สำหรับสถานการณ์การจับคู่ที่กำหนดเอง":::

1. <span data-ttu-id="ffa01-299">เลือกเอนทิตีที่คุณต้องการใช้สำหรับ **จับคู่เสมอ** และ **ไม่เคยจับคู่** ให้เลือก **เสร็จสิ้น**</span><span class="sxs-lookup"><span data-stu-id="ffa01-299">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="ffa01-300">เลือก **บันทึก** ในเพจ **จับคู่** เพื่อใช้การกำหนดค่าการจับคู่ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-300">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="ffa01-301">เลือก **เรียกใช้** ในเพจ **จับคู่** เพื่อเริ่มกระบวนการจับคู่</span><span class="sxs-lookup"><span data-stu-id="ffa01-301">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="ffa01-302">กฎการจับคู่ที่ระบุอื่นๆ จะมีการแทนที่โดยการกำหนดค่าการจับคู่ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="ffa01-302">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="ffa01-303">ไปที่ **ข้อมูล** > **เอนทิตี** และตรวจสอบเอนทิตี **ConflationMatchPair** เพื่อยืนยันว่ามีการใช้การแทนที่</span><span class="sxs-lookup"><span data-stu-id="ffa01-303">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="ffa01-304">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="ffa01-304">Next step</span></span>

<span data-ttu-id="ffa01-305">หลังจากเสร็จสิ้นกระบวนการจับคู่สำหรับคู่ที่ตรงกันอย่างน้อยหนึ่งรายการ คุณอาจแก้ไขความขัดแย้งที่เป็นไปได้ในข้อมูลของคุณโดยผ่านหัวข้อ [**ผสาน**](merge-entities.md)</span><span class="sxs-lookup"><span data-stu-id="ffa01-305">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
