---
title: ส่งออกข้อมูล Customer Insights ไปยัง Autopilot
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ Autopilot
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596154"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="a35cd-103">ตัวเชื่อมต่อสำหรับ Autopilot (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="a35cd-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="a35cd-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Autopilot และใช้สำหรับการตลาดทางอีเมลใน Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a35cd-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="a35cd-105">Prerequisites</span></span>

-   <span data-ttu-id="a35cd-106">คุณมี [บัญชี Autopilot](https://www.autopilothq.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="a35cd-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a35cd-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="a35cd-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a35cd-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="a35cd-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="a35cd-109">เชื่อมต่อกับ Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="a35cd-110">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="a35cd-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a35cd-111">ภายใต้ **Autopilot** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="a35cd-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="a35cd-112">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="a35cd-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="บานหน้าต่างการตั้งค่าคอนฟิกสำหรับการเชื่อมต่อ Autopilot":::

1. <span data-ttu-id="a35cd-114">ป้อน **คีย์ Autopilot API** [คีย์ Autopilot API](https://autopilot.docs.apiary.io/#)</span><span class="sxs-lookup"><span data-stu-id="a35cd-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="a35cd-115">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="a35cd-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a35cd-116">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="a35cd-117">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="a35cd-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a35cd-118">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="a35cd-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a35cd-119">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="a35cd-119">Configure the connector</span></span>

1. <span data-ttu-id="a35cd-120">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a35cd-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a35cd-121">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ เช่น **ชื่อ,**, **นามสกุล**</span><span class="sxs-lookup"><span data-stu-id="a35cd-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="a35cd-122">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="a35cd-122">Select the segments you want to export.</span></span> <span data-ttu-id="a35cd-123">เรา **แนะนำอย่างยิ่งว่า อย่าส่งออกโปรไฟล์ลูกค้าทั้งหมดมากกว่า 100'000 โปรไฟล์** ไปยัง Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="a35cd-124">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="a35cd-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a35cd-125">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="a35cd-125">Export the data</span></span>

<span data-ttu-id="a35cd-126">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="a35cd-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a35cd-127">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="a35cd-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a35cd-128">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="a35cd-128">Known limitations</span></span>

- <span data-ttu-id="a35cd-129">คุณสามารถส่งออกโปรไฟล์ทั้งหมดได้มากถึง 100'000 โปรไฟล์ไปยัง Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="a35cd-130">การส่งออกไปยัง Autopilot ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="a35cd-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="a35cd-131">การส่งออกโปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง Autopilot อาจใช้เวลาสองสามชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="a35cd-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="a35cd-132">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Autopilot นั้น ขึ้นอยู่และถูกจำกัดตามสัญญาของคุณกับ Autopilot</span><span class="sxs-lookup"><span data-stu-id="a35cd-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a35cd-133">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="a35cd-133">Data privacy and compliance</span></span>

<span data-ttu-id="a35cd-134">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Autopilot คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="a35cd-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a35cd-135">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Autopilot ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="a35cd-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a35cd-136">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="a35cd-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a35cd-137">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="a35cd-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]