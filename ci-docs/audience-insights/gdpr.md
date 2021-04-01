---
title: คำขอสิทธิ์เรื่องข้อมูล (DSR) ภายใต้ GDPR | Microsoft Docs
description: ตอบสนองต่อคำขอของเจ้าของข้อมูลสำหรับความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597534"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="22063-103">คำขอสิทธิ์เรื่องข้อมูล (DSR) ภายใต้ GDPR</span><span class="sxs-lookup"><span data-stu-id="22063-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="22063-104">การตอบสนองต่อคำขอลบของเจ้าของข้อมูล GDPR สำหรับความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="22063-105">“สิทธิในการลบ” โดยการลบของข้อมูลส่วนบุคคลออกจากข้อมูลลูกค้าขององค์กร เป็นการป้องกันที่สำคัญในข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR)</span><span class="sxs-lookup"><span data-stu-id="22063-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="22063-106">การลบข้อมูลส่วนบุคคลรวมถึงการลบข้อมูลส่วนบุคคลทั้งหมดและบันทึกที่ระบบที่สร้างขึ้น ยกเว้นข้อมูลบันทึกการตรวจสอบ</span><span class="sxs-lookup"><span data-stu-id="22063-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="22063-107">จัดการคำขอลบสิทธิ์เรื่องข้อมูล</span><span class="sxs-lookup"><span data-stu-id="22063-107">Manage data subject delete requests</span></span>

<span data-ttu-id="22063-108">ข้อมูลเชิงลึกกลุ่มเป้าหมายนำเสนอประสบการณ์ในผลิตภัณฑ์ต่อไปนี้เพื่อลบข้อมูลส่วนบุคคลสำหรับลูกค้าหรือผู้ใช้เฉพาะ:</span><span class="sxs-lookup"><span data-stu-id="22063-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="22063-109">**จัดการคำขอลบสำหรับข้อมูลลูกค้า**: ข้อมูลลูกค้าใน Customer Insights ถูกนำมาใช้จากแหล่งข้อมูลดั้งเดิมภายนอกไปยัง Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="22063-110">คำขอลบ GDPR ทั้งหมดจะต้องดำเนินการในแหล่งข้อมูลดั้งเดิม</span><span class="sxs-lookup"><span data-stu-id="22063-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="22063-111">**จัดการคำขอลบข้อมูลผู้ใช้ Customer Insights**: ข้อมูลสำหรับผู้ใช้สร้างขึ้นโดย Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="22063-112">คำขอลบ GDPR ทั้งหมดจะต้องดำเนินการใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="22063-113">จัดการคำขอลบสำหรับข้อมูลลูกค้า</span><span class="sxs-lookup"><span data-stu-id="22063-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="22063-114">ผู้ดูแลระบบ Customer Insights สามารถทำตามขั้นตอนเหล่านี้เพื่อลบข้อมูลลูกค้าที่ถูกลบในแหล่งข้อมูล:</span><span class="sxs-lookup"><span data-stu-id="22063-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="22063-115">เข้าสู่ระบบ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="22063-116">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="22063-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="22063-117">สำหรับแหล่งข้อมูลแต่ละรายการในรายการที่มีข้อมูลลูกค้าที่ถูกลบ:</span><span class="sxs-lookup"><span data-stu-id="22063-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="22063-118">เลือก (...) และจากนั้นเลือก **รีเฟรช**</span><span class="sxs-lookup"><span data-stu-id="22063-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="22063-119">ตรวจสอบสถานะของแหล่งข้อมูลภายใต้ **สถานะ**</span><span class="sxs-lookup"><span data-stu-id="22063-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="22063-120">เครื่องหมายถูกหมายถึง การรีเฟรชสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="22063-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="22063-121">สามเหลี่ยมคำเตือนหมายถึง มีบางสิ่งผิดปกติ</span><span class="sxs-lookup"><span data-stu-id="22063-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="22063-122">หากสามเหลี่ยมคำเตือนปรากฏขึ้น ให้ติดต่อ D365CI@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="22063-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="22063-123">![การจัดการคำขอลบ GDPR สำหรับข้อมูลลูกค้า](media/gdpr-data-sources.png "การจัดการคำขอลบ GDPR สำหรับข้อมูลลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="22063-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="22063-124">จัดการคำขอลบสำหรับข้อมูลผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="22063-124">Manage delete requests for user data</span></span>

<span data-ttu-id="22063-125">ผู้ดูแลระบบ Customer Insights สามารถทำตามขั้นตอนเหล่านี้เพื่อลบข้อมูลผู้ใช้ Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="22063-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="22063-126">เข้าสู่ระบบ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22063-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="22063-127">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="22063-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="22063-128">เลือกกล่องกาเครื่องหมายสำหรับผู้ใช้ที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="22063-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="22063-129">เลือก **เอาออก**</span><span class="sxs-lookup"><span data-stu-id="22063-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="22063-130">![การจัดการคำขอลบ GDPR สำหรับข้อมูลผู้ใช้](media/gdpr-permissions.png "การจัดการคำขอลบ GDPR สำหรับข้อมูลผู้ใช้")</span><span class="sxs-lookup"><span data-stu-id="22063-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="22063-131">การตอบสนองต่อคำขอส่งออกของเจ้าของข้อมูล GDPR</span><span class="sxs-lookup"><span data-stu-id="22063-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="22063-132">ในฐานะที่เป็นส่วนหนึ่งของข้อผูกพันของเราที่จะร่วมมือกับคุณในการเดินทางไปยังข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR) เราได้พัฒนาเอกสารเพื่อช่วยคุณเตรียมความพร้อม</span><span class="sxs-lookup"><span data-stu-id="22063-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="22063-133">เอกสารนี้อธิบายขั้นตอนที่คุณสามารถทำได้ในปัจจุบันเพื่อสนับสนุนการปฏิบัติตาม GDPR เมื่อใช้ข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="22063-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="22063-134">จัดการการส่งออกและดูคำขอ</span><span class="sxs-lookup"><span data-stu-id="22063-134">Manage export and view requests</span></span>

<span data-ttu-id="22063-135">สิทธิ์ของความสามารถในการเคลื่อนย้ายข้อมูลอนุญาตให้หัวข้อของข้อมูลร้องขอสำเนาข้อมูลส่วนบุคคลของพวกเขาในรูปแบบอิเล็กทรอนิกส์ ("รูปแบบที่มีโครงสร้าง มีการใช้โดยทั่วไป สามารถอ่านได้ด้วยเครื่อง และสามารถทำงานร่วมกันได้") ซึ่งอาจถูกส่งไปยังตัวควบคุมข้อมูลอื่น</span><span class="sxs-lookup"><span data-stu-id="22063-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="22063-136">ส่งออกข้อมูลลูกค้า (ผู้ดูแลระบบผู้เช่า)</span><span class="sxs-lookup"><span data-stu-id="22063-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="22063-137">ผู้ดูแลระบบผู้เช่าสามารถทำตามขั้นตอนเหล่านี้เพื่อส่งออกข้อมูล:</span><span class="sxs-lookup"><span data-stu-id="22063-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="22063-138">ส่งอีเมลไปที่ D365CI@microsoft.com ซึ่งระบุที่อยู่อีเมลของลูกค้าในคำขอ</span><span class="sxs-lookup"><span data-stu-id="22063-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="22063-139">ทีม Customer Insights จะส่งอีเมลไปยังที่อยู่อีเมลผู้ดูแลระบบของผู้เช่าที่ลงทะเบียน โดยขอให้ยืนยันการส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="22063-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="22063-140">รับทราบการยืนยันในการส่งออกข้อมูลสำหรับลูกค้าที่ร้องขอ</span><span class="sxs-lookup"><span data-stu-id="22063-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="22063-141">รับข้อมูลที่ส่งออกผ่านที่อยู่อีเมลผู้ดูแลระบบของผู้เช่า</span><span class="sxs-lookup"><span data-stu-id="22063-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="22063-142">ส่งออกข้อมูลผู้ใช้ (ผู้ดูแลระบบผู้เช่า)</span><span class="sxs-lookup"><span data-stu-id="22063-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="22063-143">ส่งอีเมลไปที่ D365CI@microsoft.com ซึ่งระบุที่อยู่อีเมลของผู้ใช้ในคำขอ</span><span class="sxs-lookup"><span data-stu-id="22063-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="22063-144">ทีม Customer Insights จะส่งอีเมลไปยังที่อยู่อีเมลผู้ดูแลระบบของผู้เช่าที่ลงทะเบียน โดยขอให้ยืนยันการส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="22063-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="22063-145">รับทราบการยืนยันในการส่งออกข้อมูลสำหรับผู้ใช้ที่ร้องขอ</span><span class="sxs-lookup"><span data-stu-id="22063-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="22063-146">รับข้อมูลที่ส่งออกผ่านที่อยู่อีเมลผู้ดูแลระบบของผู้เช่า</span><span class="sxs-lookup"><span data-stu-id="22063-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]