---
title: กิจกรรมของลูกค้า
description: กำหนดกิจกรรมของลูกค้าและดูในไทม์ไลน์ของลูกค้า
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267455"
---
# <a name="customer-activities"></a><span data-ttu-id="74e4c-103">กิจกรรมของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="74e4c-103">Customer activities</span></span>

<span data-ttu-id="74e4c-104">รวมกิจกรรมของลูกค้าจาก [แหล่งข้อมูลต่างๆ](data-sources.md) ใน Dynamics 365 Customer Insights เพื่อสร้างไทม์ไลน์ของลูกค้าที่แสดงรายการกิจกรรมตามลำดับเวลา</span><span class="sxs-lookup"><span data-stu-id="74e4c-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="74e4c-105">คุณสามารถรวมไทม์ไลน์ในแอปการมีส่วนร่วมกับลูกค้าใน Dynamics 365 ผ่านทาง [Add-in การ์ดลูกค้า](customer-card-add-in.md) หรือในแดชบอร์ด Power BI</span><span class="sxs-lookup"><span data-stu-id="74e4c-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="74e4c-106">กำหนดกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-106">Define an activity</span></span>

<span data-ttu-id="74e4c-107">แหล่งข้อมูลของคุณประกอบด้วยเอนทิตีที่มีข้อมูลธุรกรรมและกิจกรรมจากแหล่งข้อมูลหลายแห่ง</span><span class="sxs-lookup"><span data-stu-id="74e4c-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="74e4c-108">ระบุเอนทิตีเหล่านี้ และเลือกกิจกรรมที่คุณต้องการดูบนเส้นเวลาของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="74e4c-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="74e4c-109">เลือกเอนทิตีที่มีกิจกรรมหรือกิจกรรมเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="74e4c-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="74e4c-110">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **กิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="74e4c-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="74e4c-111">เลือก **เพิ่มกิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="74e4c-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="74e4c-112">เอนทิตีต้องมีแอตทริบิวต์อย่างน้อยหนึ่งประเภท **วันที่** ที่จะรวมอยู่ในเส้นเวลาของลูกค้าและคุณไม่สามารถเพิ่มเอนทิตีโดยปราศจากฟิลด์ **วันที่** ได้</span><span class="sxs-lookup"><span data-stu-id="74e4c-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="74e4c-113">การควบคุม **เพิ่มกิจกรรม** ถูกปิดใช้งานหากไม่พบเอนทิตีดังกล่าว</span><span class="sxs-lookup"><span data-stu-id="74e4c-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="74e4c-114">ในบานหน้าต่าง **เพิ่มกิจกรรม** ตั้งค่าสำหรับฟิลด์ต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="74e4c-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="74e4c-115">**เอนทิตี**: เลือกเอนทิตีที่มีข้อมูลธุรกรรมหรือกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="74e4c-116">**คีย์หลัก**: เลือกฟิลด์ที่ระบุเรกคอร์ดโดยไม่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="74e4c-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="74e4c-117">ไม่ควรมีค่าที่ซ้ำกัน ค่าว่างเปล่า หรือค่าที่หายไป</span><span class="sxs-lookup"><span data-stu-id="74e4c-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="74e4c-118">**การประทับเวลา**: เลือกฟิลด์ที่แสดงเวลาเริ่มต้นของกิจกรรมของคุณ</span><span class="sxs-lookup"><span data-stu-id="74e4c-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="74e4c-119">**เหตุการณ์**: เลือกฟิลด์ที่เป็นเหตุการณ์สำหรับกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="74e4c-120">**ที่อยู่เว็บ**: เลือกฟิลด์ที่แสดงถึง URL ซึ่งให้ข้อมูลเพิ่มเติมเกี่ยวกับกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="74e4c-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="74e4c-121">ตัวอย่างเช่น ระบบธุรกรรมที่เป็นแหล่งของกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="74e4c-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="74e4c-122">URL นี้สามารถเป็นฟิลด์ใดๆ จากแหล่งข้อมูล หรือสามารถถูกสร้างเป็นฟิลด์ใหม่โดยใช้การแปลง Power Query</span><span class="sxs-lookup"><span data-stu-id="74e4c-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="74e4c-123">ข้อมูล URL นี้จะถูกเก็บไว้ในเอนทิตีกิจกรรมแบบรวม ซึ่งสามารถถูกใช้แบบดาวน์สตรีมโดยใช้ API</span><span class="sxs-lookup"><span data-stu-id="74e4c-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="74e4c-124">**รายละเอียด**: อีกทางเลือกหนึ่ง ให้เลือกฟิลด์ที่เพิ่มเข้ามาเพื่อดูรายละเอียดเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="74e4c-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="74e4c-125">**ไอคอน**: อีกทางเลือกหนึ่ง ให้เลือกไอคอนที่แสดงถึงกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="74e4c-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="74e4c-126">**ชนิดกิจกรรม**: กำหนดการอ้างอิงชนิดกิจกรรมไปยัง Common Data Model ที่อธิบายนิยามความหมายของกิจกรรมได้ดีที่สุด</span><span class="sxs-lookup"><span data-stu-id="74e4c-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="74e4c-127">ในส่วน **ตั้งค่าความสัมพันธ์** กำหนดค่ารายละเอียดเพื่อเชื่อมต่อข้อมูลกิจกรรมของคุณกับลูกค้าที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="74e4c-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="74e4c-128">**ฟิลด์เอนทิตีกิจกรรม**: เลือกฟิลด์ในเอนทิตีกิจกรรมของคุณที่จะใช้เพื่อสร้างความสัมพันธ์กับเอนทิตีอื่น</span><span class="sxs-lookup"><span data-stu-id="74e4c-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="74e4c-129">**เอนทิตีลูกค้า**: เลือกเอนทิตีลูกค้าที่สอดคล้องกันซึ่งจะสัมพันธ์กันกับเอนทิตีกิจกรรมของคุณ</span><span class="sxs-lookup"><span data-stu-id="74e4c-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="74e4c-130">คุณสามารถเกี่ยวข้องกับเอนทิตีลูกค้าต้นทางที่ใช้ในกระบวนการการรวมข้อมูลเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="74e4c-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="74e4c-131">**ฟิลด์เอนทิตีของลูกค้า**: ฟิลด์นี้แสดงคีย์หลักของเอนทิตีลูกค้าต้นทางตามที่เลือกในกระบวนการแมป</span><span class="sxs-lookup"><span data-stu-id="74e4c-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="74e4c-132">ฟิลด์คีย์หลักนี้ในเอนทิตีลูกค้าต้นทางใช้เพื่อสร้างความสัมพันธ์กับเอนทิตีกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="74e4c-133">**ชื่อ**: หากความสัมพันธ์ระหว่างเอนทิตีกิจกรรมนี้และเอนทิตีลูกค้าต้นทางที่เลือกมีอยู่แล้ว ชื่อความสัมพันธ์จะอยู่ในโหมดอ่านอย่างเดียว</span><span class="sxs-lookup"><span data-stu-id="74e4c-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="74e4c-134">หากไม่มีความสัมพันธ์ดังกล่าว ความสัมพันธ์ใหม่จะถูกสร้างขึ้นด้วยชื่อที่ให้ไว้ที่นี่</span><span class="sxs-lookup"><span data-stu-id="74e4c-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="74e4c-135">![กำหนดความสัมพันธ์ของเอนทิตี](media/activities-entities-define.png "กำหนดความสัมพันธ์ของเอนทิตี")</span><span class="sxs-lookup"><span data-stu-id="74e4c-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="74e4c-136">เลือก **บันทึก** เพื่อนำการเปลี่ยนแปลงของคุณมาใช้</span><span class="sxs-lookup"><span data-stu-id="74e4c-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="74e4c-137">บนหน้า **กิจกรรม** ให้เลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="74e4c-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="74e4c-138">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="74e4c-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="74e4c-139">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="74e4c-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="74e4c-140">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="74e4c-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="74e4c-141">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="74e4c-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="74e4c-142">แก้ไขกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-142">Edit an activity</span></span>

1. <span data-ttu-id="74e4c-143">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **กิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="74e4c-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="74e4c-144">เลือกเอนทิตีกิจกรรมที่คุณต้องการแก้ไขและเลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="74e4c-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="74e4c-145">หรือคุณสามารถวางเมาส์เหนือแถวเอนทิตีและเลือกไอคอน **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="74e4c-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="74e4c-146">คลิกที่ไอคอน **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="74e4c-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="74e4c-147">ในบานหน้าต่าง **แก้ไขกิจกรรม** อัปเดตค่าและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="74e4c-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="74e4c-148">บนหน้า **กิจกรรม** ให้เลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="74e4c-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="74e4c-149">ลบกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="74e4c-149">Delete an activity</span></span>

1. <span data-ttu-id="74e4c-150">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **กิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="74e4c-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="74e4c-151">เลือกเอนทิตีกิจกรรมที่คุณต้องการลบและเลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="74e4c-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="74e4c-152">หรือคุณสามารถวางเมาส์เหนือแถวเอนทิตีและเลือกไอคอน **ลบ**</span><span class="sxs-lookup"><span data-stu-id="74e4c-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="74e4c-153">นอกจากนี้คุณสามารถเลือกเอนทิตีกิจกรรมหลายรายการที่จะลบในครั้งเดียว</span><span class="sxs-lookup"><span data-stu-id="74e4c-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="74e4c-154">![แก้ไขหรือลบความสัมพันธ์ของเอนทิตี](media/activities-entities-edit-delete.png "แก้ไขหรือลบความสัมพันธ์ของเอนทิตี")</span><span class="sxs-lookup"><span data-stu-id="74e4c-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="74e4c-155">เลือกไอคอน **ลบ**</span><span class="sxs-lookup"><span data-stu-id="74e4c-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="74e4c-156">ยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="74e4c-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]