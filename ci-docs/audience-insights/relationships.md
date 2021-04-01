---
title: ความสัมพันธ์ระหว่างเอนทิตีและพาธของเอนทิตี
description: สร้างและจัดการความสัมพันธ์ระหว่างเอนทิตีจากแหล่งข้อมูลหลายแหล่ง
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595235"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c21ef-103">ความสัมพันธ์ระหว่างเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="c21ef-103">Relationships between entities</span></span>

<span data-ttu-id="c21ef-104">ความสัมพันธ์ช่วยให้คุณเชื่อมต่อเอนทิตีและสร้างกราฟของข้อมูลของคุณเมื่อเอนทิตีแบ่งปันตัวระบุร่วมกัน (คีย์นอก) ที่สามารถอ้างอิงได้จากเอนทิตี้หนึ่งไปยังอีกเอนทิตีได้</span><span class="sxs-lookup"><span data-stu-id="c21ef-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="c21ef-105">เอนทิตีที่เชื่อมต่อช่วยให้คุณสามารถกำหนดเซ็กเมนต์และการวัดตามแหล่งข้อมูลหลายแหล่ง</span><span class="sxs-lookup"><span data-stu-id="c21ef-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c21ef-106">ความสัมพันธ์มีอยู่สองชนิด</span><span class="sxs-lookup"><span data-stu-id="c21ef-106">There are two types of relationships.</span></span> <span data-ttu-id="c21ef-107">ระบบความสัมพันธ์ที่ไม่สามารถแก้ไขได้ ซึ่งสร้างขึ้นโดยอัตโนมัติและความสัมพันธ์ที่สร้างเองและกำหนดค่าโดยผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="c21ef-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="c21ef-108">ในระหว่างกระบวนการจับคู่และผสาน ความสัมพันธ์ของระบบถูกสร้างขึ้นเบื้องหลังตามการจับคู่แบบอัจฉริยะ</span><span class="sxs-lookup"><span data-stu-id="c21ef-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="c21ef-109">ความสัมพันธ์เหล่านี้ช่วยเชื่อมโยงเรกคอร์ดโปรไฟล์ลูกค้ากับบันทึกเอนทิตีอื่น ๆ ที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="c21ef-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="c21ef-110">ไดอะแกรมต่อไปนี้แสดงให้เห็นถึงการสร้างความสัมพันธ์ระบบสามระบบ เมื่อเอนทิตีลูกค้าถูกจับคู่กับเอนทิตีเพิ่มเติมเพื่อสร้างเอนทิตีโปรไฟล์ลูกค้าสุดท้าย</span><span class="sxs-lookup"><span data-stu-id="c21ef-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c21ef-111">![การสร้างความสัมพันธ์](media/relationships-entities-merge.png "การสร้างความสัมพันธ์")</span><span class="sxs-lookup"><span data-stu-id="c21ef-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="c21ef-112">**ความสัมพันธ์ *CustomerToContact*** ถูกสร้างขึ้นระหว่างเอนทิตีลูกค้าและเอนทิตีผู้ติดต่อ</span><span class="sxs-lookup"><span data-stu-id="c21ef-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="c21ef-113">เอนทิตีลูกค้าได้รับฟิลด์คีย์หลัก **Contact_contactId** เพื่อเชื่อมโยงกับฟิลด์คีย์หลักของเอนทิตีผู้ติดต่อ **ContactId**.</span><span class="sxs-lookup"><span data-stu-id="c21ef-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="c21ef-114">***CustomerToAccount* ความสัมพันธ์** ถูกสร้างขึ้นระหว่างเอนทิตีลูกค้าและเอนทิตีลูกค้าองค์กร</span><span class="sxs-lookup"><span data-stu-id="c21ef-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="c21ef-115">เอนทิตีลูกค้าได้รับฟิลด์คีย์หลัก **Account_contactId** เพื่อเชื่อมโยงกับฟิลด์คีย์หลักของเอนทิตีลูกค้าองค์กร **accountId**.</span><span class="sxs-lookup"><span data-stu-id="c21ef-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="c21ef-116">***CustomerToWebAccount* ความสัมพันธ์** ถูกสร้างขึ้นระหว่างเอนทิตีลูกค้าและเอนทิตี WebAccount</span><span class="sxs-lookup"><span data-stu-id="c21ef-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="c21ef-117">เอนทิตีลูกค้าได้รับฟิลด์คีย์หลัก **WebAccount_contactId** เพื่อเชื่อมโยงกับฟิลด์คีย์หลักของเอนทิตี WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="c21ef-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="c21ef-118">สร้างความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="c21ef-118">Create a relationship</span></span>

<span data-ttu-id="c21ef-119">กำหนดความสัมพันธ์ที่กำหนดเองบนหน้า **ความสัมพันธ์** .</span><span class="sxs-lookup"><span data-stu-id="c21ef-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="c21ef-120">แต่ละความสัมพันธ์ประกอบด้วยเอนทิตีของแหล่งที่มา (เอนทิตีที่เก็บคีย์นอก) และเอนทิตีเป้าหมาย (เอนทิตีที่คีย์นอกของเอนทิตีต้นทางชี้ไปถึง)</span><span class="sxs-lookup"><span data-stu-id="c21ef-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="c21ef-121">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **ความสัมพันธ์**</span><span class="sxs-lookup"><span data-stu-id="c21ef-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c21ef-122">เลือก **ความสัมพันธ์ใหม่**</span><span class="sxs-lookup"><span data-stu-id="c21ef-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="c21ef-123">ในบานหน้าต่าง **เพิ่มความสัมพันธ์** ให้ป้อนข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="c21ef-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c21ef-124">![ป้อนรายละเอียดความสัมพันธ์](media/relationships-add.png "ป้อนรายละเอียดความสัมพันธ์")</span><span class="sxs-lookup"><span data-stu-id="c21ef-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="c21ef-125">**ชื่อความสัมพันธ์**: ชื่อที่สะท้อนถึงจุดประสงค์ของความสัมพันธ์ (ตัวอย่างเช่น **AccountWebLogs**)</span><span class="sxs-lookup"><span data-stu-id="c21ef-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="c21ef-126">**คำอธิบาย**: คำอธิบายของความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="c21ef-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c21ef-127">**เอนทิตีต้นทาง**: เลือกเอนทิตีที่ใช้เป็นแหล่งข้อมูลในความสัมพันธ์ (ตัวอย่างเช่น WebLog)</span><span class="sxs-lookup"><span data-stu-id="c21ef-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="c21ef-128">**คาร์ดินาลลิตี้**: เลือกคาร์ดินาลลิตี้ของเร็กคอร์ดเอนทิตีต้นทาง</span><span class="sxs-lookup"><span data-stu-id="c21ef-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="c21ef-129">ตัวอย่างเช่น "มากมาย" หมายความว่าหลายๆ เรกคอร์ดของ WebLog เกี่ยวข้องกับหนึ่ง WebAccount</span><span class="sxs-lookup"><span data-stu-id="c21ef-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c21ef-130">**ฟิลด์คีย์หลักต้นทาง**: สิ่งนี้แสดงถึงฟิลด์คีย์นอกในเอนทิตีต้นทาง</span><span class="sxs-lookup"><span data-stu-id="c21ef-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="c21ef-131">ตัวอย่างเช่น WebLog มีฟิลด์คีย์นอก **accountId**</span><span class="sxs-lookup"><span data-stu-id="c21ef-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="c21ef-132">**เอนทิตีเป้าหมาย** : เลือกเอนทิตีที่ใช้เป็นเป้าหมายในความสัมพันธ์ (ตัวอย่างเช่น WebAccount)</span><span class="sxs-lookup"><span data-stu-id="c21ef-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="c21ef-133">**คาร์ดินาลลิตี้เป้าหมาย**: เลือกคาร์ดินาลลิตี้ของเร็กคอร์ดเอนทิตีเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="c21ef-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="c21ef-134">ตัวอย่างเช่น "หนึ่ง" หมายความว่าหลายๆ เรกคอร์ดของ WebLog เกี่ยวข้องกับหนึ่ง WebAccount</span><span class="sxs-lookup"><span data-stu-id="c21ef-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c21ef-135">**ฟิลด์คีย์เป้าหมาย** : ฟิลด์นี้แสดงถึงฟิลด์คีย์หลักของเอนทิตีเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="c21ef-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="c21ef-136">ตัวอย่างเช่น WebAccount มีฟิลด์คีย์หลัก **accountId** .</span><span class="sxs-lookup"><span data-stu-id="c21ef-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="c21ef-137">สนับสนุนเฉพาะความสัมพันธ์แบบหลายต่อหนึ่งและแบบหนึ่งต่อหนึ่ง</span><span class="sxs-lookup"><span data-stu-id="c21ef-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="c21ef-138">ความสัมพันธ์แบบหลายต่อหลายรายการสามารถสร้างขึ้นได้โดยใช้ สองความสัมพันธ์หลายต่อหนึ่งรายการ และเอนทิตีลิงก์ (เอนทิตีที่ใช้ในการเชื่อมต่อเอนทิตีต้นทางและเอนทิตีเป้าหมาย)</span><span class="sxs-lookup"><span data-stu-id="c21ef-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="c21ef-139">ลบความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="c21ef-139">Delete a relationship</span></span>

1. <span data-ttu-id="c21ef-140">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **ความสัมพันธ์**</span><span class="sxs-lookup"><span data-stu-id="c21ef-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c21ef-141">เลือกกล่องกาเครื่องหมายสำหรับความสัมพันธ์ที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="c21ef-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="c21ef-142">เลือก **ลบ** ที่ด้านบนของตาราง **ความสัมพันธ์** .</span><span class="sxs-lookup"><span data-stu-id="c21ef-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="c21ef-143">ยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="c21ef-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="c21ef-144">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="c21ef-144">Next step</span></span>

<span data-ttu-id="c21ef-145">ระบบและความสัมพันธ์ที่กำหนดเองถูกใช้เพื่อสร้างเซ็กเมนต์ตามแหล่งข้อมูลหลายแหล่งที่ไม่ได้เป็นแบบไซโลอีกต่อไป</span><span class="sxs-lookup"><span data-stu-id="c21ef-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="c21ef-146">สำหรับข้อมูลเพิ่มเติม ดู [เซ็กเมนต์](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c21ef-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]