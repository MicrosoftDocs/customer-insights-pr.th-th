---
title: กิจกรรมของลูกค้า
description: กำหนดกิจกรรมของลูกค้าและดูในไทม์ไลน์ของลูกค้า
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866430"
---
# <a name="customer-activities"></a><span data-ttu-id="e9a60-103">กิจกรรมของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="e9a60-103">Customer activities</span></span>

<span data-ttu-id="e9a60-104">รวมกิจกรรมของลูกค้าจาก [แหล่งข้อมูลต่าง ๆ](data-sources.md) ใน Dynamics 365 Customer Insights เพื่อสร้างเส้นเวลาที่แสดงรายการกิจกรรมตามลำดับเวลา</span><span class="sxs-lookup"><span data-stu-id="e9a60-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="e9a60-105">รวมเส้นเวลาในแอป Dynamics 365 ด้วยโซลูชัน [Add-in บัตรลูกค้า](customer-card-add-in.md) หรือในแดชบอร์ด Power BI</span><span class="sxs-lookup"><span data-stu-id="e9a60-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e9a60-106">กำหนดกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="e9a60-106">Define an activity</span></span>

<span data-ttu-id="e9a60-107">แหล่งข้อมูลของคุณสามารถประกอบด้วยเอนทิตีที่มีข้อมูลธุรกรรมและกิจกรรมจากแหล่งข้อมูลหลายแห่ง</span><span class="sxs-lookup"><span data-stu-id="e9a60-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e9a60-108">ระบุเอนทิตีเหล่านี้ และเลือกกิจกรรมที่คุณต้องการดูบนเส้นเวลาของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="e9a60-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e9a60-109">เลือกเอนทิตีที่มีกิจกรรมหรือกิจกรรมเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="e9a60-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="e9a60-110">เอนทิตีต้องมีแอตทริบิวต์อย่างน้อยหนึ่งประเภท **วันที่** ที่จะรวมอยู่ในเส้นเวลาของลูกค้าและคุณไม่สามารถเพิ่มเอนทิตีโดยปราศจากฟิลด์ **วันที่** ได้</span><span class="sxs-lookup"><span data-stu-id="e9a60-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e9a60-111">การควบคุม **เพิ่มกิจกรรม** ถูกปิดใช้งานหากไม่พบเอนทิตีดังกล่าว</span><span class="sxs-lookup"><span data-stu-id="e9a60-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e9a60-112">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **กิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="e9a60-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e9a60-113">เลือก **เพิ่มกิจกรรม** เพื่อเริ่มประสบการณ์ที่แนะนำสำหรับขั้นตอนการตั้งค่ากิจกรรม</span><span class="sxs-lookup"><span data-stu-id="e9a60-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="e9a60-114">ในขั้นตอน **ข้อมูลกิจกรรม** ตั้งค่าสำหรับฟิลด์ต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="e9a60-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="e9a60-115">**ชื่อกิจกรรม**: เลือกชื่อสำหรับกิจกรรมของคุณ</span><span class="sxs-lookup"><span data-stu-id="e9a60-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="e9a60-116">**เอนทิตี**: เลือกเอนทิตีที่มีข้อมูลธุรกรรมหรือกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="e9a60-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e9a60-117">**คีย์หลัก**: เลือกฟิลด์ที่ระบุเรกคอร์ดโดยไม่ซ้ำกัน</span><span class="sxs-lookup"><span data-stu-id="e9a60-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e9a60-118">ไม่ควรมีค่าที่ซ้ำกัน ค่าว่างเปล่า หรือค่าที่หายไป</span><span class="sxs-lookup"><span data-stu-id="e9a60-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="ตั้งค่าข้อมูลกิจกรรมด้วยชื่อ เอนทิตี และคีย์หลัก":::

1. <span data-ttu-id="e9a60-120">เลือก **ต่อไป** เพื่อไปยังขั้นตอนต่อไป</span><span class="sxs-lookup"><span data-stu-id="e9a60-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="e9a60-121">ในขั้นตอน **ความสัมพันธ์** กำหนดค่ารายละเอียดเพื่อเชื่อมต่อข้อมูลกิจกรรมของคุณกับลูกค้าที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="e9a60-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="e9a60-122">ขั้นตอนนี้จะแสดงภาพการเชื่อมต่อระหว่างเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="e9a60-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="e9a60-123">**อันดับแรก**: ฟิลด์นอกในเอนทิตีกิจกรรมของคุณที่จะใช้เพื่อสร้างความสัมพันธ์กับเอนทิตีอื่น</span><span class="sxs-lookup"><span data-stu-id="e9a60-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="e9a60-124">**ประการที่สอง**: เอนทิตีลูกค้าต้นทางที่ตรงกันซึ่งเอนทิตีกิจกรรมของคุณจะอยู่ในความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="e9a60-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e9a60-125">คุณสามารถเชื่อมโยงกับเอนทิตีลูกค้าต้นทางที่ใช้ในกระบวนการรวมข้อมูลเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="e9a60-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="e9a60-126">**ประการที่สาม**: ถ้าความสัมพันธ์ระหว่างเอนทิตีกิจกรรมนี้กับเอนทิตีลูกค้าต้นทางที่เลือกมีอยู่แล้ว ชื่อความสัมพันธ์จะอยู่ในโหมดอ่านอย่างเดียว</span><span class="sxs-lookup"><span data-stu-id="e9a60-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e9a60-127">หากไม่มีความสัมพันธ์ดังกล่าว ความสัมพันธ์ใหม่จะถูกสร้างขึ้นโดยใช้ชื่อที่คุณระบุในกล่องนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="กำหนดความสัมพันธ์ของเอนทิตี":::

1. <span data-ttu-id="e9a60-129">เลือก **ต่อไป** เพื่อไปยังขั้นตอนต่อไป</span><span class="sxs-lookup"><span data-stu-id="e9a60-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="e9a60-130">ในขั้นตอน **การรวมกิจกรรม** เลือกเหตุการณ์ของกิจกรรมและเวลาเริ่มต้นของกิจกรรมของคุณ</span><span class="sxs-lookup"><span data-stu-id="e9a60-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="e9a60-131">**เขตข้อมูลที่จำเป็น**</span><span class="sxs-lookup"><span data-stu-id="e9a60-131">**Required fields**</span></span>
      1. <span data-ttu-id="e9a60-132">**กิจกรรมเหตุการณ์**: ฟิลด์ที่เป็นเหตุการณ์ของกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="e9a60-133">**การประทับเวลา**: ฟิลด์ที่แสดงเวลาเริ่มต้นของกิจกรรมของคุณ</span><span class="sxs-lookup"><span data-stu-id="e9a60-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="e9a60-134">**ฟิลด์ที่ไม่จำเป็นต้องระบุ**</span><span class="sxs-lookup"><span data-stu-id="e9a60-134">**Optional fields**</span></span>
      1. <span data-ttu-id="e9a60-135">**รายละเอียดเพิ่มเติม**: ฟิลด์ที่มีข้อมูลที่เกี่ยวข้องสำหรับกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="e9a60-136">**ไอคอน**: ไอคอนที่แสดงถึงชนิดกิจกรรมนี้ได้ดีที่สุด</span><span class="sxs-lookup"><span data-stu-id="e9a60-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="e9a60-137">**ที่อยู่เว็บ**: ฟิลด์ที่มี URL พร้อมข้อมูลเกี่ยวกับกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="e9a60-138">ตัวอย่างเช่น ระบบธุรกรรมที่เป็นแหล่งของกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e9a60-139">URL นี้สามารถเป็นฟิลด์ใดๆ จากแหล่งข้อมูล หรือสามารถถูกสร้างเป็นฟิลด์ใหม่โดยใช้การแปลง Power Query</span><span class="sxs-lookup"><span data-stu-id="e9a60-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e9a60-140">ข้อมูล URL จะถูกเก็บไว้ในเอนทิตี *กิจกรรมแบบรวม* ซึ่งสามารถใช้ต่อเนื่องโดยใช้ [API](apis.md)</span><span class="sxs-lookup"><span data-stu-id="e9a60-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="ระบุข้อมูลกิจกรรมของลูกค้าในเอนทิตีกิจกรรมแบบรวม":::

1. <span data-ttu-id="e9a60-142">เลือก **ถัดไป** เพื่อไปยังขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="e9a60-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="e9a60-143">คุณสามารถเลือก **เสร็จสิ้นและตรวจสอบ** เพื่อบันทึกกิจกรรมทันทีโดยตั้งค่าชนิดกิจกรรมเป็น **อื่น ๆ**</span><span class="sxs-lookup"><span data-stu-id="e9a60-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="e9a60-144">ในขั้นตอน **ชนิดกิจกรรม** เลือกชนิดกิจกรรมและเลือกว่าคุณต้องการแมปชนิดกิจกรรมบางอย่างตามความหมายเพื่อใช้ในพื้นที่อื่น ๆ ของ Customer Insights หรือไม่</span><span class="sxs-lookup"><span data-stu-id="e9a60-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="e9a60-145">ปัจจุบัน ชนิดกิจกรรม *การสมัครสมาชิก* & *SalesOrderLine* สามารถแมปตามความหมายได้หลังจากตกลงที่จะแมปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="e9a60-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="e9a60-146">หากชนิดกิจกรรมไม่เกี่ยวข้องกับกิจกรรมใหม่ คุณสามารถเลือก *อื่น ๆ* หรือ *สร้างใหม่* สำหรับชนิดกิจกรรมที่กำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="e9a60-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="e9a60-147">เลือก **ถัดไป** เพื่อไปยังขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="e9a60-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="e9a60-148">ในขั้นตอน **ตรวจทาน** ตรวจสอบการเลือกของคุณ</span><span class="sxs-lookup"><span data-stu-id="e9a60-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="e9a60-149">คุณกลับไปที่ขั้นตอนก่อนหน้านี้และอัปเดตข้อมูลหากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="e9a60-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="ตรวจทานฟิลด์ที่ระบุสำหรับกิจกรรม":::
   
1. <span data-ttu-id="e9a60-151">เลือก **บันทึกกิจกรรม** เพื่อใช้การเปลี่ยนแปลงของคุณและเลือก **เสร็จแล้ว** เพื่อกลับไปที่ **ข้อมูล** > **กิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="e9a60-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="e9a60-152">คุณจะเห็นว่ากิจกรรมใดบ้างที่ตั้งค่าให้แสดงในเส้นเวลา</span><span class="sxs-lookup"><span data-stu-id="e9a60-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="e9a60-153">บนหน้า **กิจกรรม** ให้เลือก **เรียกใช้** เพื่อดำเนินการกับกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="e9a60-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="e9a60-154">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="e9a60-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e9a60-155">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="e9a60-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e9a60-156">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="e9a60-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e9a60-157">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="e9a60-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="e9a60-158">จัดการกิจกรรมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="e9a60-158">Manage existing activities</span></span>

<span data-ttu-id="e9a60-159">บน **ข้อมูล** > **กิจกรรม** คุณสามารถดูกิจกรรมที่บันทึกไว้ทั้งหมดและจัดการได้</span><span class="sxs-lookup"><span data-stu-id="e9a60-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="e9a60-160">แต่ละกิจกรรมจะแสดงด้วยแถวที่มีรายละเอียดเกี่ยวกับแหล่งที่มา เอนทิตี และชนิดกิจกรรมด้วย</span><span class="sxs-lookup"><span data-stu-id="e9a60-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="e9a60-161">การดำเนินการต่อไปนี้พร้อมใช้งานเมื่อคุณเลือกกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="e9a60-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="e9a60-162">**แก้ไข**: เปิดการตั้งค่ากิจกรรมในขั้นตอนการตรวจสอบ</span><span class="sxs-lookup"><span data-stu-id="e9a60-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="e9a60-163">คุณสามารถเปลี่ยนการกำหนดค่าปัจจุบันส่วนใดส่วนหนึ่งหรือทั้งหมดได้จากขั้นตอนนี้</span><span class="sxs-lookup"><span data-stu-id="e9a60-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="e9a60-164">หลังจากเปลี่ยนการกำหนดค่าแล้ว ให้เลือก **บันทึกกิจกรรม** จากนั้นเลือก **เรียกใช้** เพื่อประมวลผลการเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="e9a60-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="e9a60-165">**เปลี่ยนชื่อ**: เปิดกล่องโต้ตอบเพื่อป้อนชื่ออื่นสำหรับกิจกรรมที่เลือก</span><span class="sxs-lookup"><span data-stu-id="e9a60-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="e9a60-166">เลือก **บันทึก** เพื่อนำการเปลี่ยนแปลงของคุณมาใช้</span><span class="sxs-lookup"><span data-stu-id="e9a60-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="e9a60-167">**ลบ**: เปิดกล่องโต้ตอบเพื่อยืนยันการลบกิจกรรมที่เลือก</span><span class="sxs-lookup"><span data-stu-id="e9a60-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="e9a60-168">คุณยังสามารถลบมากกว่าหนึ่งกิจกรรมพร้อมกันได้โดยเลือกกิจกรรม จากนั้นเลือกไอคอนลบ</span><span class="sxs-lookup"><span data-stu-id="e9a60-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="e9a60-169">ให้เลือก **ลบ** เพื่อยืนยันการลบ</span><span class="sxs-lookup"><span data-stu-id="e9a60-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
