---
title: ส่งออกข้อมูล Customer Insights ไปยัง AdRoll
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ AdRoll
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697097"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="65e08-103">ตัวเชื่อมต่อสำหรับ AdRoll (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="65e08-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="65e08-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง AdRoll และใช้สำหรับการโฆษณา</span><span class="sxs-lookup"><span data-stu-id="65e08-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="65e08-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="65e08-105">Prerequisites</span></span>

-   <span data-ttu-id="65e08-106">คุณมี [บัญชี AdRoll](https://www.adroll.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="65e08-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="65e08-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="65e08-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="65e08-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="65e08-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="65e08-109">เชื่อมต่อกับ AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="65e08-110">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="65e08-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="65e08-111">ภายใต้ **AdRoll** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="65e08-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="65e08-112">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="65e08-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="บานหน้าต่างการกำหนดค่าสำหรับการเชื่อมต่อ AdRoll":::

1. <span data-ttu-id="65e08-114">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="65e08-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="65e08-115">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="65e08-116">เลือก **รับรองความถูกต้องกับ AdRoll** และให้ข้อมูลประจำตัวผู้ดูแลระบบสำหรับ AdRoll ของคุณ</span><span class="sxs-lookup"><span data-stu-id="65e08-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="65e08-117">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="65e08-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="65e08-118">ป้อน **รหัสผู้ลงโฆษณา AdRoll** [AdRoll ที่สามารถโฆษณาได้](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)</span><span class="sxs-lookup"><span data-stu-id="65e08-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="65e08-119">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="65e08-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="65e08-120">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="65e08-120">Configure the connector</span></span>

1. <span data-ttu-id="65e08-121">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="65e08-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="65e08-122">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="65e08-123">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="65e08-123">Select the segments you want to export.</span></span> <span data-ttu-id="65e08-124">เลือกเซ็กเมนต์ที่มีสมาชิกอย่างน้อย 100 คน</span><span class="sxs-lookup"><span data-stu-id="65e08-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="65e08-125">คุณไม่สามารถส่งออกเซ็กเมนต์ที่เล็กกว่านั้นได้</span><span class="sxs-lookup"><span data-stu-id="65e08-125">You can't export smaller segments.</span></span> <span data-ttu-id="65e08-126">นอกจากนี้ ขนาดสูงสุดของเซ็กเมนต์ที่จะส่งออกคือสมาชิก 250,000 รายต่อการส่งออก</span><span class="sxs-lookup"><span data-stu-id="65e08-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="65e08-127">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="65e08-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="65e08-128">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="65e08-128">Export the data</span></span>

<span data-ttu-id="65e08-129">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="65e08-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="65e08-130">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="65e08-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="65e08-131">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="65e08-131">Known limitations</span></span>

- <span data-ttu-id="65e08-132">คุณสามารถส่งออกโปรไฟล์ทั้งหมดได้มากถึง 250,000 โปรไฟล์ต่อการส่งออกไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="65e08-133">คุณไม่สามารถส่งออกเซ็กเมนต์ที่มีน้อยกว่า 100 โปรไฟล์ไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="65e08-134">การส่งออกไปยัง AdRoll มีการจำกัดเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="65e08-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="65e08-135">การส่งออกโปรไฟล์มากถึง 250,000 โปรไฟล์ไปยัง AdRoll อาจใช้เวลาถึง 10 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="65e08-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="65e08-136">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง AdRoll นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ AdRoll</span><span class="sxs-lookup"><span data-stu-id="65e08-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65e08-137">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="65e08-137">Data privacy and compliance</span></span>

<span data-ttu-id="65e08-138">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง AdRoll คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="65e08-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65e08-139">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า AdRoll ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="65e08-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="65e08-140">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="65e08-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="65e08-141">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="65e08-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
