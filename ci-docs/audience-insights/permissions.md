---
title: จัดการสิทธิ์ผู้ใช้
description: เรียนรู้เกี่ยวกับสิทธิ์และบทบาทผู้ใช้
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760396"
---
# <a name="user-permissions"></a><span data-ttu-id="7c4a0-103">สิทธิ์ผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="7c4a0-103">User permissions</span></span>

<span data-ttu-id="7c4a0-104">เพจ **สิทธิ์** คือตำแหน่งที่คุณจะตั้งค่าบทบาทและสิทธิ์สำหรับการใช้ข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="7c4a0-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="7c4a0-105">คุณต้องมีสิทธิ์ผู้ดูแลระบบเพื่อดูหน้านี้</span><span class="sxs-lookup"><span data-stu-id="7c4a0-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="7c4a0-106">หากต้องการเข้าถึงเพจสิทธิ์ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="7c4a0-107">มีบทบาทอยู่สามชนิด ดังนี้</span><span class="sxs-lookup"><span data-stu-id="7c4a0-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="7c4a0-108">ผู้ดู</span><span class="sxs-lookup"><span data-stu-id="7c4a0-108">Viewer</span></span>

- <span data-ttu-id="7c4a0-109">สำรวจข้อมูลเชิงลึกและเซ็กเมนต์ภายในเพจ **หน้าแรก** และ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="7c4a0-110">ค้นหาและกรองโปรไฟล์ลูกค้าโดยใช้เพจ **ลูกค้า** .</span><span class="sxs-lookup"><span data-stu-id="7c4a0-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="7c4a0-111">ฟิลด์ต้องสามารถค้นหาได้</span><span class="sxs-lookup"><span data-stu-id="7c4a0-111">Fields must be searchable.</span></span>
- <span data-ttu-id="7c4a0-112">ดูและสำรวจหน้า **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="7c4a0-113">สำรวจและส่งออกเอนทิตีโดยใช้เพจ **เอนทิตี** .</span><span class="sxs-lookup"><span data-stu-id="7c4a0-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="7c4a0-114">ดูสถานะของกระบวนการของระบบโดยใช้เพจ **ระบบ** .</span><span class="sxs-lookup"><span data-stu-id="7c4a0-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="7c4a0-115">ดูการส่งออกในหน้า **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="7c4a0-116">ติดตั้งและใช้แดชบอร์ด **Power BI Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="7c4a0-117">ผู้สนับสนุน</span><span class="sxs-lookup"><span data-stu-id="7c4a0-117">Contributor</span></span>

- <span data-ttu-id="7c4a0-118">สิทธิ์ทั้งหมดที่มีให้กับตัวแสดง</span><span class="sxs-lookup"><span data-stu-id="7c4a0-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="7c4a0-119">โหลดและแปลงข้อมูลโดยใช้เพจ **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="7c4a0-120">ทำส่วน *การรวมข้อมูล* ให้เสร็จสมบูรณ์ (**แมป**, **จับคู่** และ **ผสาน**) ซึ่งส่งผลให้เกิดเอนทิตีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="7c4a0-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="7c4a0-121">กำหนด **ความสัมพันธ์** และ **กิจกรรม**.</span><span class="sxs-lookup"><span data-stu-id="7c4a0-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="7c4a0-122">สร้างเซ็กเมนต์โดยใช้เพจ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="7c4a0-123">สร้างการวัดโดยใช้เพจ **การวัด** .</span><span class="sxs-lookup"><span data-stu-id="7c4a0-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="7c4a0-124">จัดการการกำหนดค่าและเพิ่มประสิทธิภาพโปรไฟล์ลูกค้าจากหน้า **การเพิ่มข้อมูล** (สำหรับการเพิ่มข้อมูลของบุคคลที่หนึ่งเท่านั้น)</span><span class="sxs-lookup"><span data-stu-id="7c4a0-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="7c4a0-125">จัดการและสร้างการส่งออกตามการเชื่อมต่อที่แบ่งปันกับผู้สนับสนุน</span><span class="sxs-lookup"><span data-stu-id="7c4a0-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="7c4a0-126">[เรียนรู้เพิ่มเติมเกี่ยวกับวิธีที่ผู้ดูแลระบบอนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="7c4a0-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="7c4a0-127">ผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="7c4a0-127">Administrator</span></span>

- <span data-ttu-id="7c4a0-128">สิทธิ์ทั้งหมดที่พร้อมให้ผู้มีส่วนร่วมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="7c4a0-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="7c4a0-129">เปลี่ยนการตั้งค่าในเพจ **ระบบ** รวมถึงภาษาที่ใช้งานและการรีเฟรชกำหนดการสำหรับกระบวนการระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="7c4a0-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="7c4a0-130">ดูและเพิ่มสิทธิ์โดยใช้เพจ **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="7c4a0-131">กำหนดคำจำกัดความการค้นหาและตัวกรองสำหรับหน้าลูกค้าโดยใช้เพจ **ค้นหาและกรองดัชนี** (เข้าถึงได้ผ่านทางเพจ **ลูกค้า**)</span><span class="sxs-lookup"><span data-stu-id="7c4a0-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="7c4a0-132">จัดการการเชื่อมต่อและอนุญาตสำหรับบทบาทผู้ใช้อื่น ๆ บนหน้า **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="7c4a0-133">จัดการการกำหนดค่าและเพิ่มข้อมูลโปรไฟล์ลูกค้าในจากหน้า **การเพิ่มข้อมูล** (สำหรับการเพิ่มข้อมูลทั้งหมด)</span><span class="sxs-lookup"><span data-stu-id="7c4a0-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="7c4a0-134">จัดการและสร้างการส่งออกบนหน้า **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="7c4a0-135">ติดตั้งและใช้งาน **Add-in การ์ดลูกค้า**.</span><span class="sxs-lookup"><span data-stu-id="7c4a0-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="7c4a0-136">เพิ่มและใช้ **ตัวเชื่อมต่อ Power Apps**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="7c4a0-137">เปิดใช้งานการใช้ [Customer Insights API](apis.md)</span><span class="sxs-lookup"><span data-stu-id="7c4a0-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="7c4a0-138">มอบหมายบทบาทและสิทธิ์</span><span class="sxs-lookup"><span data-stu-id="7c4a0-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="7c4a0-139">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="7c4a0-140">เลือก **เพิ่มผู้ใช้** เพื่อเปิดบานหน้าต่าง **เพิ่ม/แก้ไขสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="7c4a0-141">ใช้ฟิลด์ **ค้นหา** เพื่อค้นหาผู้ใช้ Azure Active Directory หรือกลุ่มที่มีสิทธิ์ที่คุณต้องการปรับ</span><span class="sxs-lookup"><span data-stu-id="7c4a0-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="7c4a0-142">เลือก **บทบาท** เพื่อกำหนดให้กับผู้ใช้หรือกลุ่มนั้น</span><span class="sxs-lookup"><span data-stu-id="7c4a0-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="7c4a0-143">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="7c4a0-143">Select **Save**.</span></span> <span data-ttu-id="7c4a0-144">สภาพแวดล้อมปัจจุบันจะมีการแชร์โดยอัตโนมัติกับผู้ใช้หรือสมาชิกของกลุ่มที่คุณได้เปลี่ยนสิทธิ์</span><span class="sxs-lookup"><span data-stu-id="7c4a0-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="7c4a0-145">ผู้ใช้สามารถเข้าถึงแอป Customer Insights และทำงานตามบทบาทที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="7c4a0-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="7c4a0-146">ดูสิทธิ์ปัจจุบัน</span><span class="sxs-lookup"><span data-stu-id="7c4a0-146">View current permissions</span></span>

<span data-ttu-id="7c4a0-147">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์** เพื่อดูว่าการมอบหมายบทบาทใดที่ใช้งานอยู่ในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="7c4a0-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="7c4a0-148">คอลัมน์ **ชนิด** ระบุผู้ใช้ กลุ่ม หรือแอปพลิเคชันเดียว</span><span class="sxs-lookup"><span data-stu-id="7c4a0-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="7c4a0-149">ระบบรองรับผู้ใช้และกลุ่มบุคคล</span><span class="sxs-lookup"><span data-stu-id="7c4a0-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="7c4a0-150">บทบาทมีการระบุไว้ภายใต้คอลัมน์ **บทบาท** .</span><span class="sxs-lookup"><span data-stu-id="7c4a0-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="7c4a0-151">เลือกชื่อคอลัมน์ใดๆ เพื่อจัดเรียงผลลัพธ์ตามค่าของคอลัมน์นั้น</span><span class="sxs-lookup"><span data-stu-id="7c4a0-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="7c4a0-152">ใช้ฟิลด์ **ค้นหา** ที่ด้านบนของหน้าเพื่อค้นหาตำแหน่งผู้ใช้เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="7c4a0-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
