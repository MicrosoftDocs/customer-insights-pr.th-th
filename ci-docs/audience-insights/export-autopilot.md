---
title: ส่งออกข้อมูล Customer Insights ไปยัง Autopilot
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Autopilot
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760166"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="68aee-103">ส่งออกเซ็กเมนต์ไปยัง Autopilot (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="68aee-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="68aee-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Autopilot และใช้สำหรับการตลาดทางอีเมลใน Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="68aee-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="68aee-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="68aee-106">คุณมี [บัญชี Autopilot](https://www.autopilothq.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="68aee-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="68aee-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="68aee-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="68aee-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="68aee-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68aee-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="68aee-109">Known limitations</span></span>

- <span data-ttu-id="68aee-110">คุณสามารถส่งออกโปรไฟล์ทั้งหมดได้มากถึง 100'000 โปรไฟล์ไปยัง Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="68aee-111">การส่งออกไปยัง Autopilot ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="68aee-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="68aee-112">การส่งออกโปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง Autopilot อาจใช้เวลาสองสามชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="68aee-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="68aee-113">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Autopilot นั้น ขึ้นอยู่และถูกจำกัดตามสัญญาของคุณกับ Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="68aee-114">ตั้งค่าการเชื่อมต่อไปยัง Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="68aee-115">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="68aee-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="68aee-116">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Autopilot** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="68aee-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="68aee-117">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="68aee-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="68aee-118">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="68aee-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="68aee-119">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="68aee-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="68aee-120">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="68aee-120">Choose who can use this connection.</span></span> <span data-ttu-id="68aee-121">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="68aee-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="68aee-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="68aee-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="68aee-123">ป้อน [คีย์ API ของ AutoPilot](https://autopilot.docs.apiary.io/#)</span><span class="sxs-lookup"><span data-stu-id="68aee-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="68aee-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="68aee-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68aee-125">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="68aee-126">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="68aee-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="68aee-127">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="68aee-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="68aee-128">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="68aee-128">Configure an export</span></span>

<span data-ttu-id="68aee-129">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="68aee-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="68aee-130">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="68aee-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="68aee-131">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="68aee-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="68aee-132">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="68aee-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="68aee-133">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="68aee-134">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="68aee-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="68aee-135">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="68aee-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="68aee-136">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ เช่น **ชื่อ,**, **นามสกุล**</span><span class="sxs-lookup"><span data-stu-id="68aee-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="68aee-137">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="68aee-137">Select the segments you want to export.</span></span> <span data-ttu-id="68aee-138">เรา **แนะนำอย่างยิ่งว่า อย่าส่งออกโปรไฟล์ลูกค้าทั้งหมดมากกว่า 100'000 โปรไฟล์** ไปยัง Autopilot</span><span class="sxs-lookup"><span data-stu-id="68aee-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="68aee-139">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="68aee-139">Select **Save**.</span></span>

<span data-ttu-id="68aee-140">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="68aee-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="68aee-141">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="68aee-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68aee-142">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="68aee-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68aee-143">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="68aee-143">Data privacy and compliance</span></span>

<span data-ttu-id="68aee-144">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Autopilot คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="68aee-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68aee-145">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Autopilot ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="68aee-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="68aee-146">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="68aee-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68aee-147">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="68aee-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
