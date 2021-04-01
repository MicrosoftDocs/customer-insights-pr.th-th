---
title: แมปเอนทิตีสำหรับการรวมข้อมูล
description: แมปข้อมูลเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596016"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="91292-103">แม็ปเอนทิตีและแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="91292-103">Map entities and attributes</span></span>

<span data-ttu-id="91292-104">**แมป** เป็นขั้นตอนแรกในกระบวนการรวมข้อมูลของข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="91292-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="91292-105">การแม็ปประกอบด้วยสามระยะ:</span><span class="sxs-lookup"><span data-stu-id="91292-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="91292-106">*การเลือกเอนทิตี*: ระบุเอนทิตีที่สามารถรวมได้ซึ่งนำไปสู่ชุดข้อมูลที่มีข้อมูลที่สมบูรณ์มากขึ้นเกี่ยวกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="91292-107">*การเลือกแอตทริบิวต์*: สำหรับเอนทิตีแต่ละรายการ ให้ระบุคอลัมน์ที่คุณต้องการรวมและกระทบยอดในเฟส *การจับคู่* และ *การผสาน*</span><span class="sxs-lookup"><span data-stu-id="91292-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="91292-108">คอลัมน์เหล่านี้เรียกว่า *แอตทริบิวต์*</span><span class="sxs-lookup"><span data-stu-id="91292-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="91292-109">*คีย์หลักและการเลือกประเภทความหมาย*: สำหรับแต่ละเอนทิตี ให้ระบุแอตทริบิวต์ที่คุณต้องการกำหนดเป็นคีย์หลักสำหรับเอนทิตีนั้น และสำหรับแต่ละแอตทริบิวต์ ให้ระบุประเภทความหมายที่อธิบายแอตทริบิวต์นั้นได้ดีที่สุด</span><span class="sxs-lookup"><span data-stu-id="91292-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="91292-110">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับโฟลว์ทั่วไปของการรวมตัวของข้อมูล ดู [รวม](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="91292-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="91292-111">เลือกเอนทิตีแรก</span><span class="sxs-lookup"><span data-stu-id="91292-111">Select the first entities</span></span>

1. <span data-ttu-id="91292-112">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **รวม** > **แมป**</span><span class="sxs-lookup"><span data-stu-id="91292-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="91292-113">เริ่มระยะการแม็ปโดยการเลือก **เลือกเอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="91292-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="91292-114">เลือกเอนทิตีและแอตทริบิวต์ที่คุณต้องการใช้ในระยะ *การจับคู่* และ *การผสาน*</span><span class="sxs-lookup"><span data-stu-id="91292-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="91292-115">คุณสามารถเลือกแอตทริบิวต์ที่ต้องการทีละรายการจากเอนทิตีหรือรวมแอตทริบิวต์ทั้งหมดจากเอนทิตีโดยการเลือกกล่องกาเครื่องหมาย **รวมทุกฟิลด์** ในระดับเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="91292-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="91292-116">เราขอแนะนำให้เลือกเอนทิตีอย่างน้อยสองรายการเพื่อประโยชน์จากกระบวนการรวมตัวของข้อมูล</span><span class="sxs-lookup"><span data-stu-id="91292-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91292-117">![เพิ่มตัวอย่างเอนทิตี](media/data-manager-configure-map-add-entities-example.png "เพิ่มตัวอย่างเอนทิตี")</span><span class="sxs-lookup"><span data-stu-id="91292-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="91292-118">ในตัวอย่างนี้เรากำลังเพิ่มเอนทิตี **eCommerceContacts** และ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="91292-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="91292-119">เมื่อเลือกเอนทิตีเหล่านี้คุณจะได้รับข้อมูลเชิงลึกว่าลูกค้าธุรกิจออนไลน์รายใดเป็นสมาชิกโปรแกรมความภักดี</span><span class="sxs-lookup"><span data-stu-id="91292-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="91292-120">คุณสามารถค้นหาคำหลักในแอตทริบิวต์และเอนทิตีทั้งหมดเพื่อเลือกแอตทริบิวต์ที่จำเป็นที่คุณต้องการแม็ป</span><span class="sxs-lookup"><span data-stu-id="91292-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91292-121">![ตัวอย่างฟิลด์การค้นหา](media/data-manager-configure-map-search-fields-example.png "ตัวอย่างฟิลด์การค้นหา")</span><span class="sxs-lookup"><span data-stu-id="91292-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="91292-122">เลือก **นำไปใช้** เพื่อยืนยันการเลือกของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="91292-123">เลือกคีย์หลักและประเภทความหมายสำหรับแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="91292-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="91292-124">หลังจากเลือกเอนทิตีของคุณแล้ว หน้า **แม็ป** จะแสดงรายการเอนทิตีที่เลือกสำหรับการตรวจสอบของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="91292-125">กำหนดคีย์หลักสำหรับเอนทิตีและระบุประเภทความหมายสำหรับแอตทริบิวต์ในเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="91292-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="91292-126">**คีย์หลัก**: เลือกแอตทริบิวต์หนึ่งรายการเป็นคีย์หลักสำหรับเอนทิตีแต่ละรายการของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="91292-127">เพื่อให้แอตทริบิวต์เป็นคีย์หลักที่ถูกต้อง ไม่ควรมีค่าที่ซ้ำกัน ค่าที่ขาดหายไป หรือค่า null</span><span class="sxs-lookup"><span data-stu-id="91292-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="91292-128">แอตทริบิวต์ประเภทข้อมูลสตริง จำนวนเต็ม และ GUID ได้รับการสนับสนุนเป็นคีย์หลักและจะแสดงในฟิลด์ให้คุณเลือก</span><span class="sxs-lookup"><span data-stu-id="91292-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="91292-129">**ชนิดความหมายของแอตทริบิวต์**: ประเภทของแอตทริบิวต์ของคุณ เช่น ที่อยู่อีเมล หรือชื่อ</span><span class="sxs-lookup"><span data-stu-id="91292-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="91292-130">ในการใช้โมเดล AI สำหรับการคาดคะเนความหมายที่ชาญฉลาด ช่วยประหยัดเวลาและปรับปรุงความแม่นยำ ให้ตั้งค่า **การแม็ปอัจฉริยะ** เป็น **เปิด**</span><span class="sxs-lookup"><span data-stu-id="91292-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="91292-131">การแม็ปอัจฉริยะเน้นคำแนะนำความหมายที่ใช้ AI ในฟิลด์ **ประเภท**</span><span class="sxs-lookup"><span data-stu-id="91292-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="91292-132">หากคุณตั้งค่าเป็น **ปิด** คุณจะเห็นคำแนะนำการแม็ปปกติของเรา</span><span class="sxs-lookup"><span data-stu-id="91292-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="91292-133">คุณสามารถเลือกประเภทความหมายใดก็ได้จากรายการตัวเลือกที่มีอยู่และแทนที่การเลือกที่แนะนำ</span><span class="sxs-lookup"><span data-stu-id="91292-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91292-134">![ประเภทแอตทริบิวต์และการคาดคะเนความหมาย](media/data-manager-configure-map-add-attributes-semantic-prediction.png "ประเภทแอตทริบิวต์และการคาดคะเนความหมาย")</span><span class="sxs-lookup"><span data-stu-id="91292-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="91292-135">นอกจากนี้ ยังสามารถเพิ่มชนิดความหมายแบบกำหนดเองได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="91292-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="91292-136">เลือกฟิลด์ชนิดสำหรับแอตทริบิวต์นั้น และพิมพ์ชื่อชนิดความหมายที่กำหนดเองของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="91292-137">ด้วยวิธีนี้ คุณยังสามารถเปลี่ยนชนิดของแอตทริบิวต์ที่ถูกระบุโดยระบบ</span><span class="sxs-lookup"><span data-stu-id="91292-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="91292-138">แอตทริบิวต์ทั้งหมดที่ระบุประเภทความหมายโดยอัตโนมัติจะถูกจัดกลุ่มในส่วน **ตรวจสอบฟิลด์ที่แม็ป**</span><span class="sxs-lookup"><span data-stu-id="91292-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="91292-139">ตรวจสอบแอตทริบิวต์เหล่านี้และประเภทความหมายเนื่องจากจะใช้เพื่อรวมเอนทิตีของคุณในขั้นตอนการรวมของการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="91292-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="91292-140">แอตทริบิวต์ที่ไม่ได้แม็ปกับประเภทความหมายโดยอัตโนมัติจะถูกจัดกลุ่มในส่วน **กำหนดข้อมูลในฟิลด์ที่ไม่ได้แม็ป**</span><span class="sxs-lookup"><span data-stu-id="91292-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="91292-141">เลือกฟิลด์ประเภทความหมายสำหรับแอตทริบิวต์ที่ไม่ได้แม็ป หรือป้อนชื่อประเภทแอตทริบิวต์ที่กำหนดเองของคุณ</span><span class="sxs-lookup"><span data-stu-id="91292-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91292-142">![คีย์หลักและชนิดของแอททริบิวต์](media/data-manager-configure-map-add-attributes.png "คีย์หลักและชนิดของแอททริบิวต์")</span><span class="sxs-lookup"><span data-stu-id="91292-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="91292-143">ฟิลด์หนึ่งควรจับคู่กับประเภทความหมาย Person.FullName เพื่อเติมชื่อลูกค้าในบัตรลูกค้า</span><span class="sxs-lookup"><span data-stu-id="91292-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="91292-144">มิเช่นนั้น บัตรลูกค้าจะไม่ปรากฏชื่อ</span><span class="sxs-lookup"><span data-stu-id="91292-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="91292-145">เพิ่มและลบแอตทริบิวต์และเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="91292-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="91292-146">บน **รวม** > **แม็ป** เลือก **แก้ไขฟิลด์**</span><span class="sxs-lookup"><span data-stu-id="91292-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="91292-147">ในบานหน้าต่าง **แก้ไขฟิลด์** ให้เพิ่มหรือลบแอตทริบิวต์และเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="91292-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="91292-148">ใช้การค้นหาหรือเลื่อนเพื่อค้นหาและเลือกแอตทริบิวต์และเอนทิตีที่คุณสนใจ</span><span class="sxs-lookup"><span data-stu-id="91292-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="91292-149">คุณไม่สามารถลบแอตทริบิวต์หรือเอนทิตีได้หากจับคู่แล้ว</span><span class="sxs-lookup"><span data-stu-id="91292-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91292-150">![เพิ่มหรือเอาแอตทริบิวต์ออก](media/configure-data-map-edit.png "เพิ่มหรือเอาแอตทริบิวต์ออก")</span><span class="sxs-lookup"><span data-stu-id="91292-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="91292-151">เลือก **ใช้**</span><span class="sxs-lookup"><span data-stu-id="91292-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="91292-152">เพิ่มภาพในโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="91292-152">Add images to profiles</span></span>

<span data-ttu-id="91292-153">หากเอนทิตีมี URL ที่เผยแพร่สู่สาธารณะไปยังภาพโปรไฟล์หรือโลโก้ คุณสามารถเพิ่มเอนทิตีไปยังโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="91292-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="91292-154">เลือกเอนทิตีและค้นหาฟิลด์ที่มี URL ไปยังภาพโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="91292-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="91292-155">ในฟิลด์การนำเข้า **ประเภท** ให้ป้อนค่าต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="91292-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="91292-156">สำหรับบุคคล: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="91292-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="91292-157">สำหรับองค์กร: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="91292-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="91292-158">ดำเนินการต่อด้วยขั้นตอนการรวมและตรวจสอบให้แน่ใจว่ามีการเพิ่มแอตทริบิวต์ที่มี URL รูปภาพในขั้นตอน [ผสาน](merge-entities.md)</span><span class="sxs-lookup"><span data-stu-id="91292-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="91292-159">ตั้งค่าแอตทริบิวต์สำหรับองค์กร</span><span class="sxs-lookup"><span data-stu-id="91292-159">Set attributes for organizations</span></span>

<span data-ttu-id="91292-160">สำหรับองค์กร (แสดงตัวอย่าง) ควรแม็ปชนิดแอตทริบิวต์ไปยัง "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="91292-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="91292-161">![คีย์หลักและชนิดของแอททริบิวต์ B2B](media/configure-data-map-edit-b2b.png "คีย์หลักและชนิดของแอททริบิวต์ B2B")</span><span class="sxs-lookup"><span data-stu-id="91292-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="91292-162">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="91292-162">Next step</span></span>

<span data-ttu-id="91292-163">ในฐานะที่เป็นส่วนหนึ่งของกระบวนการรวมตัวของข้อมูล ไปที่หน้า **การจับคู่**</span><span class="sxs-lookup"><span data-stu-id="91292-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="91292-164">เยี่ยมชม [**การจับคู่**](match-entities.md) เพื่อเรียนรู้เกี่ยวกับเฟสนี้</span><span class="sxs-lookup"><span data-stu-id="91292-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="91292-165">ตรวจสอบวิดีโอต่อไปนี้: [การเริ่มต้นใช้งาน: สร้างโปรไฟล์ลูกค้าแบบรวม](https://youtu.be/oBfGEhucAxs)</span><span class="sxs-lookup"><span data-stu-id="91292-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]