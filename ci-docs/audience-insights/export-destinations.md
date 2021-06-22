---
title: ส่งออกข้อมูลจาก Customer Insights
description: จัดการการส่งออกเพื่อแบ่งปันข้อมูล
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253063"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="200e9-103">ภาพรวมการส่งออก (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="200e9-103">Exports (preview) overview</span></span>

<span data-ttu-id="200e9-104">หน้า **การส่งออก** แสดงการส่งออกที่กำหนดค่าไว้ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="200e9-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="200e9-105">การส่งออกจะแบ่งปันข้อมูลเฉพาะกับโปรแกรมประยุกต์ต่าง ๆ</span><span class="sxs-lookup"><span data-stu-id="200e9-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="200e9-106">ซึ่งอาจรวมถึงโปรไฟล์ของลูกค้าหรือเอนทิตี สคีมา และรายละเอียดการแมป</span><span class="sxs-lookup"><span data-stu-id="200e9-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="200e9-107">การส่งออกแต่ละครั้งต้องใช้ [การเชื่อมต่อ ตั้งค่าโดยผู้ดูแลระบบ เพื่อจัดการการรับรองความถูกต้องและการเข้าถึง](connections.md)</span><span class="sxs-lookup"><span data-stu-id="200e9-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="200e9-108">ไปที่ **ข้อมูล** > **การส่งออก** เพื่อดูหน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="200e9-109">บทบาทของผู้ใช้ทั้งหมดมีสิทธิ์เข้าถึงเพื่อดูการส่งออกที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="200e9-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="200e9-110">ใช้ฟิลด์ค้นหาในแถบคำสั่งเพื่อค้นหาการส่งออกตามชื่อ ชื่อการเชื่อมต่อ หรือชนิดการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="200e9-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="200e9-111">ตั้งค่าการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="200e9-111">Set up a new export</span></span>

<span data-ttu-id="200e9-112">ในการตั้งค่าหรือแก้ไขการส่งออก คุณต้องมีการเชื่อมต่อที่พร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="200e9-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="200e9-113">การเชื่อมต่อขึ้นอยู่กับ [บทบาทของผู้ใช้](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="200e9-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="200e9-114">ผู้ดูแลระบบสามารถเข้าถึงการเชื่อมต่อทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="200e9-114">Administrators have access to all connections.</span></span> <span data-ttu-id="200e9-115">นอกจากนี้ยังสามารถสร้างการเชื่อมต่อใหม่เมื่อตั้งค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="200e9-116">ผู้สนับสนุนสามารถเข้าถึงการเชื่อมต่อเฉพาะได้</span><span class="sxs-lookup"><span data-stu-id="200e9-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="200e9-117">ขึ้นอยู่กับผู้ดูแลระบบในการกำหนดค่าและแบ่งปันการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="200e9-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="200e9-118">รายการส่งออกจะแสดงผู้สนับสนุนว่าพวกเขาสามารถแก้ไข หรือดูเฉพาะการส่งออกในคอลัมน์ **สิทธิ์ของคุณ**</span><span class="sxs-lookup"><span data-stu-id="200e9-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="200e9-119">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="200e9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="200e9-120">ผู้ชมสามารถดูเฉพาะการส่งออกที่มีอยู่ แต่ไม่สามารถสร้างได้</span><span class="sxs-lookup"><span data-stu-id="200e9-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="200e9-121">กำหนดการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="200e9-121">Define a new export</span></span>

1. <span data-ttu-id="200e9-122">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-123">เลือก **เพิ่มการส่งออก** เพื่อสร้างการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="200e9-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="200e9-124">ในบานหน้าต่าง **ตั้งค่าการส่งออก** เลือกการเชื่อมต่อที่จะใช้</span><span class="sxs-lookup"><span data-stu-id="200e9-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="200e9-125">[การเชื่อมต่อ](connections.md) ได้รับการจัดการโดยผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="200e9-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="200e9-126">ระบุรายละเอียดที่ต้องการและเลือก **บันทึก** เพื่อสร้างการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="200e9-127">กำหนดการส่งออกใหม่โดยยึดตามการส่งออกที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="200e9-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="200e9-128">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-129">ในรายการของการส่งออก ให้เลือกการส่งออกที่คุณต้องการทำซ้ำ</span><span class="sxs-lookup"><span data-stu-id="200e9-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="200e9-130">เลือก **สร้างรายการซ้ำ** ในแถบคำสั่งเพื่อเปิดบานหน้าต่าง **ตั้งค่าการส่งออก** ที่มีรายละเอียดของการส่งออกที่เลือก</span><span class="sxs-lookup"><span data-stu-id="200e9-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="200e9-131">รีวิวและปรับเปลี่ยนการส่งออกและเลือก **บันทึก** เพื่อสร้างการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="200e9-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="200e9-132">แก้ไขการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-132">Edit an export</span></span>

1. <span data-ttu-id="200e9-133">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-134">ในรายการของการส่งออก ให้เลือกการส่งออกที่คุณต้องการแก้ไข</span><span class="sxs-lookup"><span data-stu-id="200e9-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="200e9-135">เลือก **แก้ไข** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="200e9-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="200e9-136">เปลี่ยนค่าที่คุณต้องการอัปเดตและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="200e9-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="200e9-137">ดูการส่งออกและรายละเอียดการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-137">View exports and export details</span></span>

<span data-ttu-id="200e9-138">หลังจากสร้างปลายทางการส่งออกแล้ว จะถูกแสดงรายการบน **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="200e9-139">ผู้ใช้ทุกคนสามารถดูได้ว่าข้อมูลใดถูกแบ่งปันและสถานะล่าสุด</span><span class="sxs-lookup"><span data-stu-id="200e9-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="200e9-140">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-141">ผู้ใช้ที่ไม่มีสิทธิ์แก้ไขเลือก **ดู** แทน **แก้ไข** เพื่อดูรายละเอียดการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="200e9-142">บานหน้าต่างด้านข้างแสดงการตั้งค่าคอนฟิกของการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="200e9-143">หากไม่มีสิทธิ์แก้ไข คุณจะเปลี่ยนค่าไม่ได้</span><span class="sxs-lookup"><span data-stu-id="200e9-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="200e9-144">เลือก **ปิด** เพื่อกลับไปที่หน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="200e9-145">จัดกำหนดการและรันการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-145">Schedule and run exports</span></span>

<span data-ttu-id="200e9-146">การส่งออกแต่ละรายการที่คุณตั้งค่าคอนฟิก มีกำหนดการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="200e9-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="200e9-147">ในระหว่างการรีเฟรช ระบบจะค้นหาข้อมูลใหม่หรือข้อมูลที่อัปเดตเพื่อรวมไว้ในการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="200e9-148">โดยค่าเริ่มต้น การส่งออกจะดำเนินการเป็นส่วนหนึ่งของทุกๆ [การรีเฟรชระบบตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="200e9-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="200e9-149">คุณสามารถปรับแต่งกำหนดการรีเฟรช หรือปิด เพื่อเรียกใช้การส่งออกด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="200e9-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="200e9-150">กำหนดการรีส่งออกขึ้นอยู่กับสถานะของสภาพแวดล้อมของคุณ</span><span class="sxs-lookup"><span data-stu-id="200e9-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="200e9-151">หากมีการอัปเดตเกี่ยวกับ [การขึ้นต่อกัน](system.md#refresh-policies) ที่กำลังดำเนินการ เมื่อการส่งออกตามกำหนดการควรเริ่มต้น ระบบจะดำเนินการการขึ้นต่อกันให้เสร็จสิ้นก่อน และจากนั้นจึงเรียกใช้การส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="200e9-152">คุณสามารถดูว่าการส่งออกถูกรีเฟรชครั้งล่าสุดเมื่อใดในคอลัมน์ **รีเฟรชแล้ว**</span><span class="sxs-lookup"><span data-stu-id="200e9-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="200e9-153">จัดกําหนดการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-153">Schedule exports</span></span>

<span data-ttu-id="200e9-154">คุณสามารถกำหนดกำหนดการรีเฟรชที่กำหนดเองสำหรับการส่งออกแต่ละรายการ หรือการส่งออกหลายรายการต่อครั้ง</span><span class="sxs-lookup"><span data-stu-id="200e9-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="200e9-155">กำหนดการที่กำหนดไว้ในปัจจุบันมีการระบุไว้ในคอลัมน์ **กำหนดการ** ของรายการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="200e9-156">สิทธิ์ให้เปลี่ยนกำหนดการเหมือนกันสำหรับ [การแก้ไขและการกำหนดการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="200e9-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="200e9-157">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-158">เลือกการส่งออกที่คุณต้องการจัดกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="200e9-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="200e9-159">เลือก **จัดกำหนดการ** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="200e9-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="200e9-160">ในบานหน้าต่าง **จัดกำหนดการส่งออก** ตั้งค่า **จัดกำหนดการเรียกใช้** เป็น **เปิด** เพื่อเรียกใช้การส่งออกโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="200e9-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="200e9-161">ตั้งค่าเป็น **ปิด** เพื่อรีเฟรชด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="200e9-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="200e9-162">สำหรับการส่งออกที่รีเฟรชโดยอัตโนมัติ ให้เลือกค่า **การเกิดซ้ำ** และระบุรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="200e9-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="200e9-163">เวลาที่กำหนดนำไปใช้กับทุกกรณีของการเกิดซ้ำ</span><span class="sxs-lookup"><span data-stu-id="200e9-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="200e9-164">ถึงเวลาที่การส่งออกควรเริ่มการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="200e9-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="200e9-165">นำไปใช้และเปิดใช้งานการเปลี่ยนแปลงของคุณ โดยเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="200e9-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="200e9-166">เมื่อแก้ไขกำหนดการสำหรับการส่งออกหลายรายการ คุณต้องทำการเลือกภายใต้ **เก็บหรือแทนที่กำหนดการ**:</span><span class="sxs-lookup"><span data-stu-id="200e9-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="200e9-167">**เก็บกำหนดการแต่ละรายการ**: คงกำหนดการที่กำหนดไว้ก่อนหน้านี้สำหรับการส่งออกที่เลือก และปิดใช้งานหรือเปิดใช้งานเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="200e9-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="200e9-168">**กำหนดกำหนดการใหม่สำหรับการส่งออกที่เลือกทั้งหมด**: แทนที่กำหนดการที่มีอยู่ของการส่งออกที่เลือก</span><span class="sxs-lookup"><span data-stu-id="200e9-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="200e9-169">เรียกใช้ส่งออกตามคำขอ</span><span class="sxs-lookup"><span data-stu-id="200e9-169">Run exports on demand</span></span>

<span data-ttu-id="200e9-170">หากต้องการส่งออกข้อมูลโดยไม่ต้องรอการรีเฟรชตามกำหนดเวลา ให้ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="200e9-171">ในการเรียกใช้การส่งออกทั้งหมด ให้เลือก **เรียกใช้ทั้งหมด** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="200e9-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="200e9-172">การดำเนินการนี้จะเรียกใช้การส่งออกที่มีกำหนดการที่ใช้งานอยู่เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="200e9-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="200e9-173">หากต้องการเรียกใช้การส่งออกรายการเดียว ให้เลือกในรายการ และเลือก **เรียกใช้** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="200e9-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="200e9-174">นั่นคือวิธีที่คุณเรียกใช้การส่งออกโดยไม่มีกำหนดการที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="200e9-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="200e9-175">ลบการส่งออก</span><span class="sxs-lookup"><span data-stu-id="200e9-175">Remove an Export</span></span>

1. <span data-ttu-id="200e9-176">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="200e9-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="200e9-177">เลือกการส่งออกที่คุณต้องการนำออก</span><span class="sxs-lookup"><span data-stu-id="200e9-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="200e9-178">เลือก **ลบ** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="200e9-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="200e9-179">ยืนยันการลบโดยเลือก **ลบ** บนหน้าจอการยืนยัน</span><span class="sxs-lookup"><span data-stu-id="200e9-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
