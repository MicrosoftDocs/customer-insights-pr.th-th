---
title: ส่งออกข้อมูล Customer Insights ไปยัง SendGrid
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ SendGrid
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268755"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="ebed2-103">ตัวเชื่อมต่อสำหรับ SendGrid (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="ebed2-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="ebed2-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายชื่อผู้ติดต่อของ SendGrid และใช้สำหรับการส่งเสริมการขายและการตลาดทางอีเมลใน SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ebed2-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="ebed2-105">Prerequisites</span></span>

-   <span data-ttu-id="ebed2-106">คุณมี [บัญชี SendGrid](https://sendgrid.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="ebed2-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ebed2-107">มีรายการผู้ติดต่อที่มีอยู่ใน SendGrid และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="ebed2-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ebed2-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [SendGrid - จัดการผู้ติดต่อ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)</span><span class="sxs-lookup"><span data-stu-id="ebed2-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ebed2-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="ebed2-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ebed2-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="ebed2-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="ebed2-111">เชื่อมต่อกับ SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="ebed2-112">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="ebed2-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ebed2-113">ภายใต้ **SendGrid** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="ebed2-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="ebed2-114">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="ebed2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="บานหน้าต่างการตั้งค่าคอนฟิกการส่งออก SendGrid":::

1. <span data-ttu-id="ebed2-116">ป้อน **คีย์ SendGrid API** [คีย์ SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)</span><span class="sxs-lookup"><span data-stu-id="ebed2-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ebed2-117">ป้อน **[รหัสรายชื่อ SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="ebed2-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ebed2-118">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="ebed2-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ebed2-119">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ebed2-120">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="ebed2-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ebed2-121">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="ebed2-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ebed2-122">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="ebed2-122">Configure the connector</span></span>

1. <span data-ttu-id="ebed2-123">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="ebed2-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ebed2-124">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ เช่น **ชื่อ**, **นามสกุล**, **ประเทศ/ภูมิภาค**, **รัฐ**, **เมือง** และ **รหัสไปรษณีย์**</span><span class="sxs-lookup"><span data-stu-id="ebed2-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ebed2-125">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="ebed2-125">Select the segments you want to export.</span></span> <span data-ttu-id="ebed2-126">เรา **แนะนำอย่างยิ่งว่า อย่าส่งออกโปรไฟล์ลูกค้าทั้งหมดมากกว่า 100'000 โปรไฟล์** ไปยัง SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ebed2-127">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="ebed2-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ebed2-128">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="ebed2-128">Export the data</span></span>

<span data-ttu-id="ebed2-129">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="ebed2-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ebed2-130">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="ebed2-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ebed2-131">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="ebed2-131">Known limitations</span></span>

- <span data-ttu-id="ebed2-132">โปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ebed2-133">การส่งออกไปยัง SendGrid ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="ebed2-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ebed2-134">การส่งออกโปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid อาจใช้เวลาสองสามชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="ebed2-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ebed2-135">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง SendGrid นั้น ขึ้นอยู่และถูกจำกัดตามสัญญาของคุณกับ SendGrid</span><span class="sxs-lookup"><span data-stu-id="ebed2-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ebed2-136">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="ebed2-136">Data privacy and compliance</span></span>

<span data-ttu-id="ebed2-137">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง SendGrid คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="ebed2-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ebed2-138">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า SendGrid ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="ebed2-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ebed2-139">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="ebed2-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ebed2-140">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="ebed2-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]