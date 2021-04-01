---
title: ส่งออกข้อมูล Customer Insights ไปยัง Mailchimp
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Mailchimp
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598224"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="0a01d-103">ตัวเชื่อมต่อสำหรับ Mailchimp (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="0a01d-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="0a01d-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Mailchimp เพื่อสร้างจดหมายข่าวและการส่งเสริมการขายทางอีเมล</span><span class="sxs-lookup"><span data-stu-id="0a01d-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a01d-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="0a01d-105">Prerequisites</span></span>

-   <span data-ttu-id="0a01d-106">คุณมี [บัญชี Mailchimp](https://mailchimp.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="0a01d-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a01d-107">มีผู้ชมที่มีอยู่ใน Mailchimp และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="0a01d-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="0a01d-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Mailchimp](https://mailchimp.com/help/create-audience/)</span><span class="sxs-lookup"><span data-stu-id="0a01d-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="0a01d-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="0a01d-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="0a01d-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="0a01d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="0a01d-111">เชื่อมต่อกับ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0a01d-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="0a01d-112">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="0a01d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0a01d-113">ภายใต้ **Mailchimp** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="0a01d-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="0a01d-114">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="0a01d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0a01d-115">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="0a01d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a01d-116">ป้อน **[รหัสผู้ชม Mailchimp](https://mailchimp.com/help/find-audience-id/)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0a01d-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="0a01d-117">เลือก **รับรองความถูกต้องกับ Mailchimp** และให้ข้อมูลประจำตัวของ Mailchimp ของคุณ</span><span class="sxs-lookup"><span data-stu-id="0a01d-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="0a01d-118">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="0a01d-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Mailchimp":::

1. <span data-ttu-id="0a01d-120">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="0a01d-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0a01d-121">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="0a01d-121">Configure the connector</span></span>

1. <span data-ttu-id="0a01d-122">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="0a01d-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0a01d-123">หรือคุณสามารถส่งออก **ชื่อ** และ **นามสกุล** เป็นฟิลด์เพิ่มเติมเพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="0a01d-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="0a01d-124">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="0a01d-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0a01d-125">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="0a01d-125">Select the segments you want to export.</span></span> <span data-ttu-id="0a01d-126">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Mailchimp ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="0a01d-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="เลือกฟิลด์และเซ็กเมนต์ที่จะส่งออกไปยัง Mailchimp":::

1. <span data-ttu-id="0a01d-128">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="0a01d-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0a01d-129">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="0a01d-129">Export the data</span></span>

<span data-ttu-id="0a01d-130">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="0a01d-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0a01d-131">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="0a01d-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a01d-132">ใน Mailchimp ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [ผู้ชม Mailchimp](https://mailchimp.com/help/create-audience/)</span><span class="sxs-lookup"><span data-stu-id="0a01d-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a01d-133">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="0a01d-133">Known limitations</span></span>

- <span data-ttu-id="0a01d-134">โปรไฟล์ต่อการส่งออกไปยัง Mailchimp สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="0a01d-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="0a01d-135">การส่งออกไปยัง Mailchimp จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0a01d-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="0a01d-136">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึงสามชั่วโมงเนื่องจากข้อจำกัดของผู้ให้บริการ</span><span class="sxs-lookup"><span data-stu-id="0a01d-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="0a01d-137">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Mailchimp นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0a01d-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a01d-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="0a01d-138">Data privacy and compliance</span></span>

<span data-ttu-id="0a01d-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Mailchimp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="0a01d-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a01d-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Mailchimp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="0a01d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a01d-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="0a01d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a01d-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="0a01d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]