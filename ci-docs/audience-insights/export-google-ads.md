---
title: ส่งออกข้อมูล Customer Insights ไปยัง Google Ads
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Google Ads
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759798"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="26f3c-103">ส่งออกกลุ่มไปยัง Google Ads (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="26f3c-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="26f3c-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายการผู้ชมของ Google Ads และใช้เพื่อโฆษณาบน Google Search, Gmail, YouTube และ Google Display Network</span><span class="sxs-lookup"><span data-stu-id="26f3c-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="26f3c-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="26f3c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="26f3c-106">คุณมี [บัญชี Google Ads](https://ads.google.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="26f3c-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="26f3c-107">คุณมี [โทเค็นนักพัฒนา Google Ads ที่ได้รับการอนุมัติ](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="26f3c-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="26f3c-108">คุณปฏิบัติตามข้อกำหนดของ [นโยบายการจับคู่ข้อมูลลูกค้า](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="26f3c-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="26f3c-109">คุณปฏิบัติตามข้อกำหนดของ [ขนาดรายชื่อเพื่อทำการตลาดใหม่](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="26f3c-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="26f3c-110">มีผู้ชมที่มีอยู่ใน Google Ads และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="26f3c-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="26f3c-111">สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)</span><span class="sxs-lookup"><span data-stu-id="26f3c-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="26f3c-112">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="26f3c-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="26f3c-113">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล ชื่อ และ นามสกุล</span><span class="sxs-lookup"><span data-stu-id="26f3c-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="26f3c-114">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="26f3c-114">Known limitations</span></span>

- <span data-ttu-id="26f3c-115">โปรไฟล์ต่อการส่งออกไปยัง Google Ads สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="26f3c-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="26f3c-116">การส่งออกไปยัง Google Ads จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="26f3c-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="26f3c-117">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 5 นาทีเนื่องจากข้อจำกัดของผู้ให้บริการ</span><span class="sxs-lookup"><span data-stu-id="26f3c-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="26f3c-118">การจับคู่ใน Google Ads อาจใช้เวลาถึง 48 ชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="26f3c-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="26f3c-119">ตั้งค่าการเชื่อมต่อไปยัง Google Ads</span><span class="sxs-lookup"><span data-stu-id="26f3c-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="26f3c-120">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="26f3c-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="26f3c-121">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Google Ads** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="26f3c-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="26f3c-122">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="26f3c-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="26f3c-123">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="26f3c-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="26f3c-124">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="26f3c-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="26f3c-125">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="26f3c-125">Choose who can use this connection.</span></span> <span data-ttu-id="26f3c-126">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="26f3c-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="26f3c-127">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="26f3c-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="26f3c-128">ป้อน **[รหัสลูกค้า Google Ads](https://support.google.com/google-ads/answer/1704344)**</span><span class="sxs-lookup"><span data-stu-id="26f3c-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="26f3c-129">ป้อน **[โทเค็นนักพัฒนาที่อนุมัติของ Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**</span><span class="sxs-lookup"><span data-stu-id="26f3c-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="26f3c-130">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="26f3c-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="26f3c-131">เลือก **รับรองความถูกต้องกับ Google Ads** และให้ข้อมูลประจำตัวของ Google Ads ของคุณ</span><span class="sxs-lookup"><span data-stu-id="26f3c-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="26f3c-132">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="26f3c-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="26f3c-133">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="26f3c-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="26f3c-134">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="26f3c-134">Configure an export</span></span>

<span data-ttu-id="26f3c-135">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="26f3c-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="26f3c-136">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="26f3c-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="26f3c-137">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="26f3c-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="26f3c-138">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="26f3c-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="26f3c-139">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Google Ads</span><span class="sxs-lookup"><span data-stu-id="26f3c-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="26f3c-140">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="26f3c-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="26f3c-141">ป้อน **[รหัสผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Google Ads</span><span class="sxs-lookup"><span data-stu-id="26f3c-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="26f3c-142">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="26f3c-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="26f3c-143">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ **ชื่อ** และ **นามสกุล**</span><span class="sxs-lookup"><span data-stu-id="26f3c-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="26f3c-144">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="26f3c-144">Select the segments you want to export.</span></span> <span data-ttu-id="26f3c-145">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Google Ads ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="26f3c-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="26f3c-146">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="26f3c-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="26f3c-147">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="26f3c-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="26f3c-148">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="26f3c-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="26f3c-149">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="26f3c-149">Data privacy and compliance</span></span>

<span data-ttu-id="26f3c-150">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Google Ads คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="26f3c-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="26f3c-151">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Google Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="26f3c-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="26f3c-152">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="26f3c-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="26f3c-153">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="26f3c-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
