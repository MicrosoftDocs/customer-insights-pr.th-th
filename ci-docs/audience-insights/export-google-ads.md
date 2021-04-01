---
title: ส่งออกข้อมูล Customer Insights ไปยัง Google Ads
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Google Ads
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598270"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="58cf3-103">ตัวเชื่อมต่อสำหรับ Google Ads (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="58cf3-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="58cf3-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายการผู้ชมของ Google Ads และใช้เพื่อโฆษณาบน Google Search, Gmail, YouTube และ Google Display Network</span><span class="sxs-lookup"><span data-stu-id="58cf3-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="58cf3-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="58cf3-105">Prerequisites</span></span>

-   <span data-ttu-id="58cf3-106">คุณมี [บัญชี Google Ads](https://ads.google.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="58cf3-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="58cf3-107">มีผู้ชมที่มีอยู่ใน Google Ads และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="58cf3-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="58cf3-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)</span><span class="sxs-lookup"><span data-stu-id="58cf3-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="58cf3-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="58cf3-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="58cf3-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล ชื่อ และ นามสกุล</span><span class="sxs-lookup"><span data-stu-id="58cf3-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="58cf3-111">เชื่อมต่อกับ Google Ads</span><span class="sxs-lookup"><span data-stu-id="58cf3-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="58cf3-112">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="58cf3-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="58cf3-113">ภายใต้ **Google Ads** ให้เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="58cf3-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="58cf3-114">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="58cf3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="58cf3-115">ป้อน **[รหัสลูกค้า Google Ads](https://support.google.com/google-ads/answer/1704344)**</span><span class="sxs-lookup"><span data-stu-id="58cf3-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="58cf3-116">ป้อน **[โทเค็นนักพัฒนาที่อนุมัติของ Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**</span><span class="sxs-lookup"><span data-stu-id="58cf3-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="58cf3-117">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="58cf3-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="58cf3-118">ป้อน **[รหัสผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Google Ads</span><span class="sxs-lookup"><span data-stu-id="58cf3-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="58cf3-119">เลือก **รับรองความถูกต้องกับ Google Ads** และให้ข้อมูลประจำตัวของ Google Ads ของคุณ</span><span class="sxs-lookup"><span data-stu-id="58cf3-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="58cf3-120">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="58cf3-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Google Ads":::

1. <span data-ttu-id="58cf3-122">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="58cf3-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="58cf3-123">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="58cf3-123">Configure the connector</span></span>

1. <span data-ttu-id="58cf3-124">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="58cf3-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="58cf3-125">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ **ชื่อ** และ **นามสกุล**</span><span class="sxs-lookup"><span data-stu-id="58cf3-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="58cf3-126">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="58cf3-126">Select the segments you want to export.</span></span> <span data-ttu-id="58cf3-127">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Google Ads ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="58cf3-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="58cf3-128">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="58cf3-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="58cf3-129">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="58cf3-129">Export the data</span></span>

<span data-ttu-id="58cf3-130">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="58cf3-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="58cf3-131">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="58cf3-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="58cf3-132">ใน Google Ads ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/)</span><span class="sxs-lookup"><span data-stu-id="58cf3-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="58cf3-133">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="58cf3-133">Known limitations</span></span>

- <span data-ttu-id="58cf3-134">โปรไฟล์ต่อการส่งออกไปยัง Google Ads สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="58cf3-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="58cf3-135">การส่งออกไปยัง Google Ads จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="58cf3-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="58cf3-136">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 5 นาทีเนื่องจากข้อจำกัดของผู้ให้บริการ</span><span class="sxs-lookup"><span data-stu-id="58cf3-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="58cf3-137">การจับคู่ใน Google Ads อาจใช้เวลาถึง 48 ชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="58cf3-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="58cf3-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="58cf3-138">Data privacy and compliance</span></span>

<span data-ttu-id="58cf3-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Google Ads คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="58cf3-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="58cf3-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Google Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="58cf3-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="58cf3-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="58cf3-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="58cf3-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="58cf3-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]