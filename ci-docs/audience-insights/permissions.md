---
title: จัดการสิทธิ์ผู้ใช้
description: เรียนรู้เกี่ยวกับสิทธิ์และบทบาทผู้ใช้
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595725"
---
# <a name="user-permissions"></a><span data-ttu-id="a71fb-103">สิทธิ์ผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="a71fb-103">User permissions</span></span>

<span data-ttu-id="a71fb-104">เพจ **สิทธิ์** คือตำแหน่งที่คุณจะตั้งค่าบทบาทและสิทธิ์สำหรับการใช้ข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="a71fb-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="a71fb-105">คุณต้องมีสิทธิ์ผู้ดูแลระบบเพื่อดูหน้านี้</span><span class="sxs-lookup"><span data-stu-id="a71fb-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="a71fb-106">หากต้องการเข้าถึงเพจสิทธิ์ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="a71fb-107">มีบทบาทอยู่สามชนิด ดังนี้</span><span class="sxs-lookup"><span data-stu-id="a71fb-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="a71fb-108">ผู้ดู</span><span class="sxs-lookup"><span data-stu-id="a71fb-108">Viewer</span></span>

- <span data-ttu-id="a71fb-109">สำรวจข้อมูลเชิงลึกและเซ็กเมนต์ภายในเพจ **หน้าแรก** และ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="a71fb-110">ค้นหาและกรองโปรไฟล์ลูกค้าโดยใช้เพจ **ลูกค้า** .</span><span class="sxs-lookup"><span data-stu-id="a71fb-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="a71fb-111">ฟิลด์ต้องสามารถค้นหาได้</span><span class="sxs-lookup"><span data-stu-id="a71fb-111">Fields must be searchable.</span></span>
- <span data-ttu-id="a71fb-112">ดูและสำรวจหน้า **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="a71fb-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="a71fb-113">สำรวจและส่งออกเอนทิตีโดยใช้เพจ **เอนทิตี** .</span><span class="sxs-lookup"><span data-stu-id="a71fb-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="a71fb-114">ดูสถานะของกระบวนการของระบบโดยใช้เพจ **ระบบ** .</span><span class="sxs-lookup"><span data-stu-id="a71fb-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="a71fb-115">ส่งออกเซ็กเมนต์จากเพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="a71fb-116">ติดตั้งและใช้แดชบอร์ด **Power BI Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a71fb-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="a71fb-117">ผู้สนับสนุน</span><span class="sxs-lookup"><span data-stu-id="a71fb-117">Contributor</span></span>

- <span data-ttu-id="a71fb-118">สิทธิ์ทั้งหมดที่มีให้กับตัวแสดง</span><span class="sxs-lookup"><span data-stu-id="a71fb-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="a71fb-119">โหลดและแปลงข้อมูลโดยใช้เพจ **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="a71fb-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="a71fb-120">ทำส่วน *การรวมข้อมูล* ให้เสร็จสมบูรณ์ (**แมป**, **จับคู่** และ **ผสาน**) ซึ่งส่งผลให้เกิดเอนทิตีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="a71fb-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="a71fb-121">กำหนด **ความสัมพันธ์** และ **กิจกรรม**.</span><span class="sxs-lookup"><span data-stu-id="a71fb-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="a71fb-122">สร้างเซ็กเมนต์โดยใช้เพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="a71fb-123">สร้างการวัดโดยใช้เพจ **การวัด** .</span><span class="sxs-lookup"><span data-stu-id="a71fb-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="a71fb-124">จัดการการกำหนดค่าและเพิ่มประสิทธิภาพโปรไฟล์ลูกค้าจากหน้า **การเพิ่มข้อมูล** (สำหรับการเพิ่มข้อมูลของบุคคลที่หนึ่งเท่านั้น)</span><span class="sxs-lookup"><span data-stu-id="a71fb-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="a71fb-125">ผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="a71fb-125">Administrator</span></span>

- <span data-ttu-id="a71fb-126">สิทธิ์ทั้งหมดที่พร้อมให้ผู้มีส่วนร่วมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="a71fb-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="a71fb-127">เปลี่ยนการตั้งค่าในเพจ **ระบบ** รวมถึงภาษาที่ใช้งานและการรีเฟรชกำหนดการสำหรับกระบวนการระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="a71fb-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="a71fb-128">ดูและเพิ่มสิทธิ์โดยใช้เพจ **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="a71fb-129">กำหนดคำจำกัดความการค้นหาและตัวกรองสำหรับหน้าลูกค้าโดยใช้เพจ **ค้นหาและกรองดัชนี** (เข้าถึงได้ผ่านทางเพจ **ลูกค้า**)</span><span class="sxs-lookup"><span data-stu-id="a71fb-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="a71fb-130">กำหนดปลายทางเซ็กเมนต์ Dynamics 365 Sales โดยใช้เพจ **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="a71fb-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="a71fb-131">จัดการการกำหนดค่าและเพิ่มข้อมูลโปรไฟล์ลูกค้าในจากหน้า **การเพิ่มข้อมูล** (สำหรับการเพิ่มข้อมูลทั้งหมด)</span><span class="sxs-lookup"><span data-stu-id="a71fb-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="a71fb-132">ติดตั้งและใช้งาน **Add-in การ์ดลูกค้า**.</span><span class="sxs-lookup"><span data-stu-id="a71fb-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="a71fb-133">เพิ่มและใช้ **ตัวเชื่อมต่อ Power Apps**</span><span class="sxs-lookup"><span data-stu-id="a71fb-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="a71fb-134">เปิดใช้งานการใช้ [Customer Insights API](apis.md)</span><span class="sxs-lookup"><span data-stu-id="a71fb-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="a71fb-135">มอบหมายบทบาทและสิทธิ์</span><span class="sxs-lookup"><span data-stu-id="a71fb-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="a71fb-136">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="a71fb-137">เลือก **เพิ่มผู้ใช้** เพื่อเปิดบานหน้าต่าง **เพิ่ม/แก้ไขสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="a71fb-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="a71fb-138">ใช้ฟิลด์ **ค้นหา** เพื่อค้นหาผู้ใช้ Azure Active Directory หรือกลุ่มที่มีสิทธิ์ที่คุณต้องการปรับ</span><span class="sxs-lookup"><span data-stu-id="a71fb-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="a71fb-139">เลือก **บทบาท** เพื่อกำหนดให้กับผู้ใช้หรือกลุ่มนั้น</span><span class="sxs-lookup"><span data-stu-id="a71fb-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="a71fb-140">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="a71fb-140">Select **Save**.</span></span> <span data-ttu-id="a71fb-141">สภาพแวดล้อมปัจจุบันจะมีการแชร์โดยอัตโนมัติกับผู้ใช้หรือสมาชิกของกลุ่มที่คุณได้เปลี่ยนสิทธิ์</span><span class="sxs-lookup"><span data-stu-id="a71fb-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="a71fb-142">ผู้ใช้สามารถเข้าถึงแอป Customer Insights และทำงานตามบทบาทที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="a71fb-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="a71fb-143">ดูสิทธิ์ปัจจุบัน</span><span class="sxs-lookup"><span data-stu-id="a71fb-143">View current permissions</span></span>

<span data-ttu-id="a71fb-144">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์** เพื่อดูว่าการมอบหมายบทบาทใดที่ใช้งานอยู่ในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="a71fb-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="a71fb-145">คอลัมน์ **ชนิด** ระบุผู้ใช้ กลุ่ม หรือแอปพลิเคชันเดียว</span><span class="sxs-lookup"><span data-stu-id="a71fb-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="a71fb-146">ระบบรองรับผู้ใช้และกลุ่มบุคคล</span><span class="sxs-lookup"><span data-stu-id="a71fb-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="a71fb-147">บทบาทมีการระบุไว้ภายใต้คอลัมน์ **บทบาท** .</span><span class="sxs-lookup"><span data-stu-id="a71fb-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="a71fb-148">เลือกชื่อคอลัมน์ใดๆ เพื่อจัดเรียงผลลัพธ์ตามค่าของคอลัมน์นั้น</span><span class="sxs-lookup"><span data-stu-id="a71fb-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="a71fb-149">ใช้ฟิลด์ **ค้นหา** ที่ด้านบนของหน้าเพื่อค้นหาตำแหน่งผู้ใช้เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="a71fb-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]