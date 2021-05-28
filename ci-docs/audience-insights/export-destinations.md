---
title: ส่งออกข้อมูลจาก Customer Insights
description: จัดการการส่งออกเพื่อแบ่งปันข้อมูล
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016659"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="3e7f6-103">ภาพรวมการส่งออก (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="3e7f6-103">Exports (preview) overview</span></span>

<span data-ttu-id="3e7f6-104">หน้า **การส่งออก** แสดงการส่งออกที่กำหนดค่าไว้ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="3e7f6-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="3e7f6-105">การส่งออกจะแบ่งปันข้อมูลเฉพาะกับโปรแกรมประยุกต์ต่าง ๆ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="3e7f6-106">ซึ่งอาจรวมถึงโปรไฟล์ของลูกค้าหรือเอนทิตี สคีมา และรายละเอียดการแมป</span><span class="sxs-lookup"><span data-stu-id="3e7f6-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="3e7f6-107">การส่งออกแต่ละครั้งต้องใช้ [การเชื่อมต่อ ตั้งค่าโดยผู้ดูแลระบบ เพื่อจัดการการรับรองความถูกต้องและการเข้าถึง](connections.md)</span><span class="sxs-lookup"><span data-stu-id="3e7f6-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="3e7f6-108">ไปที่ **ข้อมูล** > **การส่งออก** เพื่อดูหน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="3e7f6-109">บทบาทของผู้ใช้ทั้งหมดมีสิทธิ์เข้าถึงเพื่อดูการส่งออกที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="3e7f6-110">ใช้ฟิลด์ค้นหาในแถบคำสั่งเพื่อค้นหาการส่งออกตามชื่อ ชื่อการเชื่อมต่อ หรือชนิดการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="3e7f6-111">ตั้งค่าการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="3e7f6-111">Set up a new export</span></span>

<span data-ttu-id="3e7f6-112">ในการตั้งค่าหรือแก้ไขการส่งออก คุณต้องมีการเชื่อมต่อที่พร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="3e7f6-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="3e7f6-113">การเชื่อมต่อขึ้นอยู่กับ [บทบาทของผู้ใช้](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="3e7f6-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="3e7f6-114">ผู้ดูแลระบบสามารถเข้าถึงการเชื่อมต่อทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="3e7f6-114">Administrators have access to all connections.</span></span> <span data-ttu-id="3e7f6-115">นอกจากนี้ยังสามารถสร้างการเชื่อมต่อใหม่เมื่อตั้งค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="3e7f6-116">ผู้สนับสนุนสามารถเข้าถึงการเชื่อมต่อเฉพาะได้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="3e7f6-117">ขึ้นอยู่กับผู้ดูแลระบบในการกำหนดค่าและแบ่งปันการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="3e7f6-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="3e7f6-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="3e7f6-119">ผู้ชมสามารถดูเฉพาะการส่งออกที่มีอยู่ แต่ไม่สามารถสร้างได้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="3e7f6-120">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e7f6-121">เลือก **เพิ่มการส่งออก** เพื่อสร้างปลายทางการส่งออกใหม่</span><span class="sxs-lookup"><span data-stu-id="3e7f6-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="3e7f6-122">ในบานหน้าต่าง **ตั้งค่าการส่งออก** เลือกการเชื่อมต่อที่จะใช้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="3e7f6-123">[การเชื่อมต่อ](connections.md) ได้รับการจัดการโดยผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="3e7f6-124">ระบุรายละเอียดที่ต้องการและเลือก **บันทึก** เพื่อสร้างการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="3e7f6-125">แก้ไขการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-125">Edit an export</span></span>

1. <span data-ttu-id="3e7f6-126">เลือกจุดไข่ปลาแนวตั้งสำหรับปลายทางส่งออกที่คุณต้องการแก้ไข</span><span class="sxs-lookup"><span data-stu-id="3e7f6-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="3e7f6-127">เลือก **แก้ไข** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3e7f6-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="3e7f6-128">เปลี่ยนค่าที่คุณต้องการอัปเดตและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="3e7f6-129">ดูรายละเอียดการส่งออกและการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-129">View Exports and export details</span></span>

<span data-ttu-id="3e7f6-130">หลังจากสร้างปลายทางการส่งออกแล้ว การส่งออกจะแสดงรายการบน **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="3e7f6-131">ผู้ใช้ทุกคนสามารถดูได้ว่าข้อมูลใดถูกแบ่งปันและสถานะล่าสุด</span><span class="sxs-lookup"><span data-stu-id="3e7f6-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="3e7f6-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e7f6-133">ผู้ใช้ที่ไม่มีสิทธิ์แก้ไขเลือก **ดู** แทน **แก้ไข** เพื่อดูรายละเอียดการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="3e7f6-134">บานหน้าต่างด้านข้างนี้แสดงการตั้งค่าของการส่งออกนี้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="3e7f6-135">หากไม่มีสิทธิ์แก้ไข คุณจะเปลี่ยนค่าไม่ได้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="3e7f6-136">เลือก **ปิด** เพื่อกลับไปที่หน้าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="3e7f6-137">เรียกใช้ส่งออกตามคำขอ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-137">Run exports on demand</span></span>

<span data-ttu-id="3e7f6-138">หลังจากกำหนดค่าการส่งออกแล้ว ระบบจะทำงานกับทุก [การรีเฟรชตามกำหนด](system.md#schedule-tab) ตราบเท่าที่มีการเชื่อมต่อที่ใช้งานได้</span><span class="sxs-lookup"><span data-stu-id="3e7f6-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="3e7f6-139">หากต้องการส่งออกข้อมูลโดยไม่ต้องรอการรีเฟรชตามกำหนดเวลา ให้ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="3e7f6-140">คุณมีสองตัวเลือก คือ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-140">You have two options:</span></span>

- <span data-ttu-id="3e7f6-141">ในการเรียกใช้การส่งออกทั้งหมด ให้เลือก **เรียกใช้ทั้งหมด** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="3e7f6-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="3e7f6-142">ในการเรียกใช้การส่งออกครั้งเดียว ให้เลือกจุดไข่ปลา (...) บนรายการ จากนั้นเลือก **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="3e7f6-143">ลบการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3e7f6-143">Remove an Export</span></span>

1. <span data-ttu-id="3e7f6-144">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3e7f6-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3e7f6-145">เลือกจุดไข่ปลาแนวตั้งสำหรับการส่งออกที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="3e7f6-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="3e7f6-146">เลือก **ลบ** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3e7f6-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="3e7f6-147">ยืนยันการลบโดยเลือก **ลบ** บนหน้าจอการยืนยัน</span><span class="sxs-lookup"><span data-stu-id="3e7f6-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
