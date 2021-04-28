---
title: ส่งออกข้อมูลจาก Customer Insights
description: จัดการการส่งออกเพื่อแบ่งปันข้อมูล
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896166"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="4c7ea-103">ภาพรวมการส่งออก (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="4c7ea-103">Exports (preview) overview</span></span>

<span data-ttu-id="4c7ea-104">หน้า **การส่งออก** แสดงการส่งออกที่กำหนดค่าไว้ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="4c7ea-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="4c7ea-105">การส่งออกจะแบ่งปันข้อมูลเฉพาะกับโปรแกรมประยุกต์ต่าง ๆ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="4c7ea-106">ซึ่งอาจรวมถึงโปรไฟล์ของลูกค้าหรือเอนทิตี สคีมา และรายละเอียดการแมป</span><span class="sxs-lookup"><span data-stu-id="4c7ea-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="4c7ea-107">การส่งออกแต่ละครั้งต้องใช้ [การเชื่อมต่อ ตั้งค่าโดยผู้ดูแลระบบ เพื่อจัดการการรับรองความถูกต้องและการเข้าถึง](connections.md)</span><span class="sxs-lookup"><span data-stu-id="4c7ea-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c7ea-108">จนถึงเดือนมีนาคม 2021 การส่งออกได้สร้างการเชื่อมต่อกับบริการที่เกี่ยวข้องโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="4c7ea-109">ตอนนี้การส่งออกต้องใช้ [การเชื่อมต่อ สร้างและแบ่งปันโดยผู้ดูแลระบบ](connections.md) ก่อนที่คุณจะสามารถสร้างได้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="4c7ea-110">ไปที่ **ข้อมูล** > **การส่งออก** เพื่อดูหน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="4c7ea-111">บทบาทของผู้ใช้ทั้งหมดมีสิทธิ์เข้าถึงเพื่อดูการส่งออกที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="4c7ea-112">ใช้ฟิลด์ค้นหาในแถบคำสั่งเพื่อค้นหาการส่งออกตามชื่อ ชื่อการเชื่อมต่อ หรือชนิดการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="4c7ea-113">ตั้งค่าการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="4c7ea-113">Set up a new export</span></span>

<span data-ttu-id="4c7ea-114">ในการตั้งค่าหรือแก้ไขการส่งออก คุณต้องมีการเชื่อมต่อที่พร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="4c7ea-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="4c7ea-115">การเชื่อมต่อขึ้นอยู่กับ [บทบาทของผู้ใช้](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="4c7ea-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="4c7ea-116">ผู้ดูแลระบบสามารถเข้าถึงการเชื่อมต่อทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="4c7ea-116">Administrators have access to all connections.</span></span> <span data-ttu-id="4c7ea-117">นอกจากนี้ยังสามารถสร้างการเชื่อมต่อใหม่เมื่อตั้งค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="4c7ea-118">ผู้สนับสนุนสามารถเข้าถึงการเชื่อมต่อเฉพาะได้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="4c7ea-119">ขึ้นอยู่กับผู้ดูแลระบบในการกำหนดค่าและแบ่งปันการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="4c7ea-120">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="4c7ea-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="4c7ea-121">ผู้ชมสามารถดูเฉพาะการส่งออกที่มีอยู่ แต่ไม่สามารถสร้างได้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="4c7ea-122">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4c7ea-123">เลือก **เพิ่มการส่งออก** เพื่อสร้างปลายทางการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="4c7ea-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="4c7ea-124">ในบานหน้าต่าง **ตั้งค่าการส่งออก** เลือกการเชื่อมต่อที่จะใช้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="4c7ea-125">[การเชื่อมต่อ](connections.md) ได้รับการจัดการโดยผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="4c7ea-126">ระบุรายละเอียดที่ต้องการและเลือก **บันทึก** เพื่อสร้างการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="4c7ea-127">แก้ไขการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-127">Edit an export</span></span>

1. <span data-ttu-id="4c7ea-128">เลือกจุดไข่ปลาแนวตั้งสำหรับปลายทางส่งออกที่คุณต้องการแก้ไข</span><span class="sxs-lookup"><span data-stu-id="4c7ea-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="4c7ea-129">เลือก **แก้ไข** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="4c7ea-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="4c7ea-130">เปลี่ยนค่าที่คุณต้องการอัปเดตและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="4c7ea-131">ดูรายละเอียดการส่งออกและการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-131">View Exports and export details</span></span>

<span data-ttu-id="4c7ea-132">หลังจากสร้างปลายทางการส่งออกแล้ว การส่งออกจะแสดงรายการบน **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="4c7ea-133">ผู้ใช้ทุกคนสามารถดูได้ว่าข้อมูลใดถูกแบ่งปันและสถานะล่าสุด</span><span class="sxs-lookup"><span data-stu-id="4c7ea-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="4c7ea-134">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4c7ea-135">ผู้ใช้ที่ไม่มีสิทธิ์แก้ไขเลือก **ดู** แทน **แก้ไข** เพื่อดูรายละเอียดการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="4c7ea-136">บานหน้าต่างด้านข้างนี้แสดงการตั้งค่าของการส่งออกนี้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="4c7ea-137">หากไม่มีสิทธิ์แก้ไข คุณจะเปลี่ยนค่าไม่ได้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="4c7ea-138">เลือก **ปิด** เพื่อกลับไปที่หน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="4c7ea-139">เรียกใช้ส่งออกตามคำขอ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-139">Run exports on demand</span></span>

<span data-ttu-id="4c7ea-140">หลังจากกำหนดค่าการส่งออกแล้ว ระบบจะทำงานกับทุก [การรีเฟรชตามกำหนด](system.md#schedule-tab) ตราบเท่าที่มีการเชื่อมต่อที่ใช้งานได้</span><span class="sxs-lookup"><span data-stu-id="4c7ea-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="4c7ea-141">หากต้องการส่งออกข้อมูลโดยไม่ต้องรอการรีเฟรชตามกำหนดเวลา ให้ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="4c7ea-142">คุณมีสองตัวเลือก คือ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-142">You have two options:</span></span>

- <span data-ttu-id="4c7ea-143">ในการเรียกใช้การส่งออกทั้งหมด ให้เลือก **เรียกใช้ทั้งหมด** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="4c7ea-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="4c7ea-144">ในการเรียกใช้การส่งออกครั้งเดียว ให้เลือกจุดไข่ปลา (...) บนรายการ จากนั้นเลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="4c7ea-145">ลบการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4c7ea-145">Remove an Export</span></span>

1. <span data-ttu-id="4c7ea-146">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4c7ea-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4c7ea-147">เลือกจุดไข่ปลาแนวตั้งสำหรับการส่งออกที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="4c7ea-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="4c7ea-148">เลือก **ลบ** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="4c7ea-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="4c7ea-149">ยืนยันการลบโดยเลือก **ลบ** บนหน้าจอการยืนยัน</span><span class="sxs-lookup"><span data-stu-id="4c7ea-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
