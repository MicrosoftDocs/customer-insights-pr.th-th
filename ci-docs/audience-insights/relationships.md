---
title: ความสัมพันธ์ระหว่างเอนทิตีและพาธของเอนทิตี
description: สร้างและจัดการความสัมพันธ์ระหว่างเอนทิตีจากแหล่งข้อมูลหลายแหล่ง
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171187"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="2083f-103">ความสัมพันธ์ระหว่างเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="2083f-103">Relationships between entities</span></span>

<span data-ttu-id="2083f-104">ความสัมพันธ์เชื่อมต่อเอนทิตี และกำหนดกราฟของข้อมูลของคุณ เมื่อเอนทิตีแชร์ตัวระบุร่วมซึ่งเป็นคีย์นอก</span><span class="sxs-lookup"><span data-stu-id="2083f-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="2083f-105">คีย์นอกนี้สามารถอ้างอิงจากเอนทิตีหนึ่งไปยังอีกเอนทิตีหนึ่งได้</span><span class="sxs-lookup"><span data-stu-id="2083f-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="2083f-106">เอนทิตีที่เชื่อมต่อเปิดใช้งานข้อกำหนดของเซ็กเมนต์และการวัดตามแหล่งข้อมูลหลายแหล่ง</span><span class="sxs-lookup"><span data-stu-id="2083f-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="2083f-107">ความสัมพันธ์มีสามชนิด:</span><span class="sxs-lookup"><span data-stu-id="2083f-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="2083f-108">ความสัมพันธ์ของระบบที่ไม่สามารถแก้ไขได้ ซึ่งสร้างขึ้นโดยระบบโดยเป็นส่วนหนึ่งของกระบวนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2083f-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="2083f-109">ความสัมพันธ์ที่มีการสืบทอดที่ไม่สามารถแก้ไขได้ ซึ่งสร้างขึ้นโดยอัตโนมัติจากการนำเข้าแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2083f-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="2083f-110">ความสัมพันธ์แบบกำหนดเองที่แก้ไขได้ ซึ่งสร้างและตั้งค่าคอนฟิกโดยผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="2083f-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="2083f-111">ความสัมพันธ์ของระบบที่ไม่สามารถแก้ไขได้</span><span class="sxs-lookup"><span data-stu-id="2083f-111">Non-editable system relationships</span></span>

<span data-ttu-id="2083f-112">ในระหว่างการรวมข้อมูล จะมีการสร้างความสัมพันธ์ของระบบโดยอัตโนมัติตามการจับคู่อัจฉริยะ</span><span class="sxs-lookup"><span data-stu-id="2083f-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="2083f-113">ความสัมพันธ์เหล่านี้ช่วยเชื่อมโยงเรกคอร์ดโปรไฟล์ลูกค้ากับเรกคอร์ดที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2083f-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="2083f-114">ไดอะแกรมต่อไปนี้แสดงการสร้างความสัมพันธ์แบบอิงระบบสามรายการ</span><span class="sxs-lookup"><span data-stu-id="2083f-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="2083f-115">เอนทิตีลูกค้าถูกจับคู่กับเอนทิตีอื่นเพื่อสร้างเอนทิตี *ลูกค้า* แบบรวม</span><span class="sxs-lookup"><span data-stu-id="2083f-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="ไดอะแกรมที่มีพาธความสัมพันธ์สำหรับเอนทิตีลูกค้าที่มีความสัมพันธ์แบบ 1-n สามรายการ":::

- <span data-ttu-id="2083f-117">**ความสัมพันธ์ *CustomerToContact*** ถูกสร้างขึ้นระหว่างเอนทิตี *ลูกค้า* และเอนทิตี *ผู้ติดต่อ*</span><span class="sxs-lookup"><span data-stu-id="2083f-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="2083f-118">เอนทิตี *ลูกค้า* ได้รับฟิลด์คีย์ **Contact_contactID** เพื่อเชื่อมโยงกับฟิลด์คีย์เอนทิตี *ผู้ติดต่อ* **contactID**</span><span class="sxs-lookup"><span data-stu-id="2083f-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="2083f-119">**ความสัมพันธ์ *CustomerToAccount*** ถูกสร้างขึ้นระหว่างเอนทิตี *ลูกค้า* และ เอนทิตี *ลูกค้าองค์กร*</span><span class="sxs-lookup"><span data-stu-id="2083f-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="2083f-120">เอนทิตี *ลูกค้า* ได้รับฟิลด์คีย์ **Account_accountID** เพื่อเชื่อมโยงกับฟิลด์คีย์เอนทิตี *ลูกค้าองค์กร* **accountID**</span><span class="sxs-lookup"><span data-stu-id="2083f-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="2083f-121">**ความสัมพันธ์ *CustomerToWebAccount*** ถูกสร้างขึ้นระหว่างเอนทิตี *ลูกค้า* และเอนทิตี *WebAccount*</span><span class="sxs-lookup"><span data-stu-id="2083f-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="2083f-122">เอนทิตี *ลูกค้า* ได้รับฟิลด์คีย์ **WebAccount_webaccountID** เพื่อเชื่อมโยงกับฟิลด์คีย์เอนทิตี *WebAccount* **webaccountID**</span><span class="sxs-lookup"><span data-stu-id="2083f-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="2083f-123">ความสัมพันธ์ที่มีการสืบทอดซึ่งไม่สามารถแก้ไขได้</span><span class="sxs-lookup"><span data-stu-id="2083f-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="2083f-124">ในระหว่างกระบวนการนำเข้าข้อมูล ระบบจะตรวจสอบแหล่งข้อมูลสำหรับความสัมพันธ์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="2083f-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="2083f-125">หากไม่มีความสัมพันธ์อยู่ ระบบจะสร้างความสัมพันธ์โดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="2083f-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="2083f-126">นอกจากนี้ ความสัมพันธ์เหล่านี้ยังใช้ในกระบวนการดาวน์สตรีมอีกด้วย</span><span class="sxs-lookup"><span data-stu-id="2083f-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="2083f-127">สร้างความสัมพันธ์แบบกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="2083f-127">Create a custom relationship</span></span>

<span data-ttu-id="2083f-128">ความสัมพันธ์ประกอบด้วย *เอนทิตีต้นทาง* ที่มีคีย์นอก และ *เอนทิตีเป้าหมาย* ที่คีย์นอกของเอนทิตีต้นทางชี้ไป</span><span class="sxs-lookup"><span data-stu-id="2083f-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="2083f-129">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **ความสัมพันธ์**</span><span class="sxs-lookup"><span data-stu-id="2083f-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="2083f-130">เลือก **ความสัมพันธ์ใหม่**</span><span class="sxs-lookup"><span data-stu-id="2083f-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="2083f-131">ในบานหน้าต่าง **ความสัมพันธ์ใหม่** ให้ป้อนข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="2083f-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="บานหน้าต่างด้านความสัมพันธ์ใหม่พร้อมฟิลด์ป้อนข้อมูลที่ว่างเปล่า":::

   - <span data-ttu-id="2083f-133">**ชื่อความสัมพันธ์**: ชื่อที่สะท้อนถึงจุดประสงค์ของความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="2083f-134">ตัวอย่าง: CustomerToSupportCase</span><span class="sxs-lookup"><span data-stu-id="2083f-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="2083f-135">**คำอธิบาย**: คำอธิบายของความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="2083f-136">**เอนทิตีต้นทาง**: เอนทิตีที่ใช้เป็นต้นทางในความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="2083f-137">ตัวอย่าง: SupportCase</span><span class="sxs-lookup"><span data-stu-id="2083f-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="2083f-138">**เอนทิตีปลายทาง**: เอนทิตีที่ใช้เป็นเป้าหมายในความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="2083f-139">ตัวอย่าง: ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="2083f-139">Example: Customer.</span></span>
   - <span data-ttu-id="2083f-140">**คาร์ดินัลลิตี้ต้นทาง**: ระบุคาร์ดินาลลิตี้ของเอนทิตีต้นทาง</span><span class="sxs-lookup"><span data-stu-id="2083f-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="2083f-141">คาร์ดินาลิตี้อธิบายจำนวนขององค์ประกอบที่เป็นไปได้ในชุด</span><span class="sxs-lookup"><span data-stu-id="2083f-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="2083f-142">ซึ่งเกี่ยวข้องกับคาร์ดินาลิตี้เป้าหมายเสมอ</span><span class="sxs-lookup"><span data-stu-id="2083f-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="2083f-143">คุณสามารถเลือกระหว่าง **หนึ่ง** และ **หลากหลาย**</span><span class="sxs-lookup"><span data-stu-id="2083f-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="2083f-144">สนับสนุนเฉพาะความสัมพันธ์แบบหลายต่อหนึ่งและแบบหนึ่งต่อหนึ่ง</span><span class="sxs-lookup"><span data-stu-id="2083f-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="2083f-145">กลุ่มต่อหนึ่ง: เรกคอร์ดต้นทางหลายรายการสามารถเชื่อมโยงกับเรกคอร์ดเป้าหมายเดียว</span><span class="sxs-lookup"><span data-stu-id="2083f-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="2083f-146">ตัวอย่าง: กรณีการสนับสนุนหลายรายการจากลูกค้ารายเดียว</span><span class="sxs-lookup"><span data-stu-id="2083f-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="2083f-147">หนึ่งต่อหนึ่ง: เรกคอร์ดต้นทางเดียวเกี่ยวข้องกับเรกคอร์ดเป้าหมายเดียว</span><span class="sxs-lookup"><span data-stu-id="2083f-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="2083f-148">ตัวอย่าง: รหัสความภักดีหนึ่งรหัสสำหรับลูกค้ารายเดียว</span><span class="sxs-lookup"><span data-stu-id="2083f-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="2083f-149">สามารถสร้างความสัมพันธ์แบบกลุ่มต่อกลุ่มได้โดยใช้ความสัมพันธ์แบบกลุ่มต่อหนึ่งสองรายการและเอนทิตีการเชื่อมโยง ซึ่งเชื่อมต่อเอนทิตีต้นทางและเอนทิตีเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="2083f-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="2083f-150">**คาร์ดินาลลิตี้เป้าหมาย**: เลือกคาร์ดินาลลิตี้ของเร็กคอร์ดเอนทิตีเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="2083f-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="2083f-151">**ฟิลด์คีย์ต้นทาง**: ฟิลด์คีย์นอกในเอนทิตีต้นทาง</span><span class="sxs-lookup"><span data-stu-id="2083f-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="2083f-152">ตัวอย่าง: SupportCase สามารถใช้ CaseID เป็นฟิลด์คีย์นอก</span><span class="sxs-lookup"><span data-stu-id="2083f-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="2083f-153">**ฟิลด์คีย์เป้าหมาย**: ฟิลด์คีย์ของเอนทิตีเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="2083f-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="2083f-154">ตัวอย่าง ลูกค้าสามารถใช้ฟิลด์คีย์ **CustomerID**</span><span class="sxs-lookup"><span data-stu-id="2083f-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="2083f-155">เลือก **บันทึก** เพื่อสร้างความสัมพันธ์แบบกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="2083f-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="2083f-156">ดูความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-156">View relationships</span></span>

<span data-ttu-id="2083f-157">หน้าความสัมพันธ์แสดงรายการความสัมพันธ์ทั้งหมดที่ถูกสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="2083f-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="2083f-158">แถวแต่ละแถวแสดงถึงความสัมพันธ์ ซึ่งยังรวมถึงรายละเอียดเกี่ยวกับเอนทิตีต้นทาง เอนทิตีเป้าหมาย และคาร์ดินาลลิตี้</span><span class="sxs-lookup"><span data-stu-id="2083f-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="รายการของความสัมพันธ์และตัวเลือกในแถบการดำเนินการของหน้าความสัมพันธ์":::

<span data-ttu-id="2083f-160">หน้านี้นำเสนอชุดตัวเลือกสำหรับความสัมพันธ์ที่มีอยู่และความสัมพันธ์ใหม่:</span><span class="sxs-lookup"><span data-stu-id="2083f-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="2083f-161">**ความสัมพันธ์ใหม่**: [สร้างความสัมพันธ์แบบกำหนดเอง](#create-a-custom-relationship)</span><span class="sxs-lookup"><span data-stu-id="2083f-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="2083f-162">**ตัวสร้างภาพ**: [สำรวจตัวสร้างภาพความสัมพันธ์](#explore-the-relationship-visualizer) เพื่อดูแผนภาพเครือข่ายของความสัมพันธ์และคาร์ดินาลลิตี้ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="2083f-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="2083f-163">**กรองโดย**: เลือกประเภทของความสัมพันธ์เพื่อแสดงในรายการ</span><span class="sxs-lookup"><span data-stu-id="2083f-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="2083f-164">**ค้นหาความสัมพันธ์**: ใช้การค้นหาตามข้อความเกี่ยวกับคุณสมบัติของความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="2083f-165">สำรวจตัวสร้างภาพความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="2083f-166">ตัวสร้างภาพความสัมพันธ์แสดงแผนภาพเครือข่ายของความสัมพันธ์ที่มีอยู่ระหว่างเอนทิตีที่เชื่อมต่อและคาร์ดินาลลิตี้</span><span class="sxs-lookup"><span data-stu-id="2083f-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="2083f-167">ในการกำหนดมุมมองเอง คุณสามารถเปลี่ยนตำแหน่งของกล่องได้โดยการลากบนพื้นที่ทำงาน</span><span class="sxs-lookup"><span data-stu-id="2083f-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="ภาพหน้าจอของไดอะแกรมเครือข่ายตัวสร้างภาพความสัมพันธ์พร้อมการเชื่อมต่อระหว่างเอนทิตีที่เกี่ยวข้อง":::

<span data-ttu-id="2083f-169">ตัวเลือกที่พร้อมใช้งาน:</span><span class="sxs-lookup"><span data-stu-id="2083f-169">Available options:</span></span> 
- <span data-ttu-id="2083f-170">**ส่งออกเป็นรูปภาพ**: บันทึกมุมมองปัจจุบันเป็นไฟล์รูปภาพ</span><span class="sxs-lookup"><span data-stu-id="2083f-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="2083f-171">**เปลี่ยนเป็นเค้าโครงแนวนอน/แนวตั้ง**: เปลี่ยนการจัดตำแหน่งของเอนทิตีและความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2083f-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="2083f-172">**แก้ไข**: อัปเดตคุณสมบัติของความสัมพันธ์ที่กำหนดเองในบานหน้าต่างแก้ไข และบันทึกการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="2083f-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="2083f-173">จัดการความสัมพันธ์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="2083f-173">Manage existing relationships</span></span> 

<span data-ttu-id="2083f-174">ในหน้าความสัมพันธ์ แต่ละความสัมพันธ์จะถูกแสดงเป็นแถว</span><span class="sxs-lookup"><span data-stu-id="2083f-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="2083f-175">เลือกความสัมพันธ์ และเลือกหนึ่งในตัวเลือกต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="2083f-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="2083f-176">**แก้ไข**: อัปเดตคุณสมบัติของความสัมพันธ์ที่กำหนดเองในบานหน้าต่างแก้ไข และบันทึกการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="2083f-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="2083f-177">**ลบ**: ลบความสัมพันธ์ที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="2083f-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="2083f-178">**ดู**: ดูความสัมพันธ์ที่สร้างและสืบทอดโดยระบบ</span><span class="sxs-lookup"><span data-stu-id="2083f-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="2083f-179">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="2083f-179">Next step</span></span>

<span data-ttu-id="2083f-180">ระบบและความสัมพันธ์ที่กำหนดเองถูกใช้เพื่อ [สร้างเซ็กเมนต์](segments.md) ตามแหล่งข้อมูลหลายแหล่งที่ไม่ได้เป็นแบบไซโลอีกต่อไป</span><span class="sxs-lookup"><span data-stu-id="2083f-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
