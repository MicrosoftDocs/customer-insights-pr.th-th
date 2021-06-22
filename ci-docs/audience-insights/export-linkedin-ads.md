---
title: ส่งออกข้อมูล Customer Insights ไปยัง LinkedIn Ads
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อและส่งออกไปยัง LinkedIn Ads
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124563"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="309c7-103">ส่งออกเซ็กเมนต์ไปยัง LinkedIn Ads (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="309c7-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="309c7-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง LinkedIn Ads เพื่อสร้าง Matched Audiences</span><span class="sxs-lookup"><span data-stu-id="309c7-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="309c7-105">ใช้ Matched Audiences สำหรับการกำหนดเป้าหมายบริษัทและการกำหนดเป้าหมายผู้ติดต่อ</span><span class="sxs-lookup"><span data-stu-id="309c7-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="309c7-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="309c7-106">Prerequisites</span></span>

-   <span data-ttu-id="309c7-107">คุณมี [บัญชี LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="309c7-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="309c7-108">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="309c7-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="309c7-109">โปรไฟล์ลูกค้าในเซ็กเมนต์ที่ส่งออก มีฟิลด์ที่มีที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="309c7-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="309c7-110">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="309c7-110">Known limitations</span></span>

- <span data-ttu-id="309c7-111">คุณสามารถส่งออกโปรไฟล์ได้ถึง 100K โปรไฟล์ต่อการส่งออกหนึ่งรายการไปยัง LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="309c7-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="309c7-112">การส่งออกไปยัง LinkedIn Ads นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="309c7-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="309c7-113">การส่งออกมากถึง 100K โปรไฟล์ไปยัง LinkedIn Ads อาจใช้เวลาถึง 10 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="309c7-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="309c7-114">ตั้งค่าการเชื่อมต่อกับ LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="309c7-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="309c7-115">ในข้อมูลเชิงลึกของผู้ชม ให้ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="309c7-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="309c7-116">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **LinkedIn Ads** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="309c7-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="309c7-117">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="309c7-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="309c7-118">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="309c7-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="309c7-119">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="309c7-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="309c7-120">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="309c7-120">Choose who can use this connection.</span></span> <span data-ttu-id="309c7-121">หากคุณไม่ดำเนินการใดๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="309c7-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="309c7-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="309c7-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="309c7-123">ให้ [รหัสบัญชี LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="309c7-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="309c7-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="309c7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="309c7-125">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="309c7-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="309c7-126">เลือก **รับรองความถูกต้องกับ LinkedIn** และให้ข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับ LinkedIn Campaign Manager</span><span class="sxs-lookup"><span data-stu-id="309c7-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="309c7-127">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="309c7-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="309c7-128">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="309c7-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="309c7-129">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="309c7-129">Configure an export</span></span>

<span data-ttu-id="309c7-130">คุณสามารถตั้งค่าคอนฟิกการส่งออกได้ หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="309c7-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="309c7-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="309c7-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="309c7-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="309c7-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="309c7-133">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="309c7-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="309c7-134">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="309c7-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="309c7-135">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="309c7-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="309c7-136">เลือกว่าคุณต้องการส่งออกข้อมูลเพื่อทำ [การกำหนดเป้าหมายการติดต่อ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) หรือ [การกำหนดเป้าหมายบริษัท](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) บน LinkedIn</span><span class="sxs-lookup"><span data-stu-id="309c7-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="309c7-137">ในส่วน **การจับคู่ข้อมูล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงถึงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="309c7-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="309c7-138">ซึ่งจำเป็นต้องส่งออกเซ็กเมนต์ไปยัง LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="309c7-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="309c7-139">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="309c7-139">Select the segments you want to export.</span></span> <span data-ttu-id="309c7-140">Matched Audiences ใน LinkedIn Campaign Manager จะถูกสร้างขึ้นโดยอัตโนมัติด้วยชื่อของเซ็กเมนต์ที่คุณเลือกที่จะส่งออก</span><span class="sxs-lookup"><span data-stu-id="309c7-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="309c7-141">แต่ละเซ็กเมนต์จะส่งผลให้มี Matched Audience ที่แยกจากกัน</span><span class="sxs-lookup"><span data-stu-id="309c7-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="309c7-142">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="309c7-142">Select **Save**.</span></span>

<span data-ttu-id="309c7-143">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="309c7-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="309c7-144">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="309c7-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="309c7-145">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="309c7-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="309c7-146">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="309c7-146">Data privacy and compliance</span></span>

<span data-ttu-id="309c7-147">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง LinkedIn Ads คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="309c7-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="309c7-148">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า LinkedIn Ads เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="309c7-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="309c7-149">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="309c7-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="309c7-150">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถลบปลายทางการส่งออกเมื่อใดก็ได้ เพื่อหยุดการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="309c7-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
