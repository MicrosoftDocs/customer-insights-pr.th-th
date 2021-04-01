---
title: ส่งออกข้อมูล Customer Insights ไปยัง Marketo
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Marketo
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597994"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="8c8f0-103">ตัวเชื่อมต่อสำหรับ Marketo (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="8c8f0-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมเพื่อสร้างการส่งเสริมการขาย จัดทำการตลาดทางอีเมล และใช้กลุ่มลูกค้าเฉพาะกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="8c8f0-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c8f0-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="8c8f0-105">Prerequisites</span></span>

-   <span data-ttu-id="8c8f0-106">คุณมี [บัญชี Marketo](https://login.marketo.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="8c8f0-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8c8f0-107">มีรายการที่มีอยู่ใน Marketo และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="8c8f0-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="8c8f0-108">สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [รายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="8c8f0-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="8c8f0-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="8c8f0-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="8c8f0-111">เชื่อมต่อกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="8c8f0-111">Connect to Marketo</span></span>

1. <span data-ttu-id="8c8f0-112">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8c8f0-113">ภายใต้ **Marketo** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="8c8f0-114">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8c8f0-115">ป้อน **[รหัสไคลเอ็นต์ Marketo ข้อมูลลับของไคลเอ็นต์และชื่อโฮสต์จุดสิ้นสุด REST](https://developers.marketo.com/rest-api/authentication/)**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="8c8f0-116">ป้อน **[รหัสรายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="8c8f0-117">เลือก **ฉันตกลง** เพื่อยืนยัน **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** และเลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="8c8f0-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="8c8f0-118">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="8c8f0-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Marketo":::

1. <span data-ttu-id="8c8f0-120">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="8c8f0-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8c8f0-121">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="8c8f0-121">Configure the connector</span></span>

1. <span data-ttu-id="8c8f0-122">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="8c8f0-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8c8f0-123">หรือคุณสามารถส่งออก **ชื่อ**, **นามสกุล**, **เมือง**, **รัฐ** และ **ประเทศ/ภูมิภาค** เป็นฟิลด์เพิ่มเติมเพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="8c8f0-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8c8f0-124">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="8c8f0-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8c8f0-125">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="8c8f0-125">Select the segments you want to export.</span></span> <span data-ttu-id="8c8f0-126">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Marketo ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="8c8f0-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="เลือกฟิลด์และเซ็กเมนต์ที่จะส่งออกไปยัง Marketo":::

1. <span data-ttu-id="8c8f0-128">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="8c8f0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8c8f0-129">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="8c8f0-129">Export the data</span></span>

<span data-ttu-id="8c8f0-130">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8c8f0-131">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="8c8f0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8c8f0-132">ใน Marketo ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [รายชื่อ Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8c8f0-133">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="8c8f0-133">Known limitations</span></span>

- <span data-ttu-id="8c8f0-134">โปรไฟล์ต่อการส่งออกไปยัง Marketo สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="8c8f0-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="8c8f0-135">การส่งออกไปยัง Marketo จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="8c8f0-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="8c8f0-136">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="8c8f0-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="8c8f0-137">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Marketo นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="8c8f0-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8c8f0-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="8c8f0-138">Data privacy and compliance</span></span>

<span data-ttu-id="8c8f0-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Marketo คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="8c8f0-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8c8f0-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Marketo ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="8c8f0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8c8f0-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="8c8f0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8c8f0-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="8c8f0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]