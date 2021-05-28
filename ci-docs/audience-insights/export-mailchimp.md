---
title: ส่งออกข้อมูล Customer Insights ไปยัง Mailchimp
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Mailchimp
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976178"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="49c4b-103">ส่งออกรายการเซ็กเมนต์ไปยัง Mailchimp (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="49c4b-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="49c4b-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Mailchimp เพื่อสร้างจดหมายข่าวและการส่งเสริมการขายทางอีเมล</span><span class="sxs-lookup"><span data-stu-id="49c4b-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="49c4b-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="49c4b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="49c4b-106">คุณมี [บัญชี Mailchimp](https://mailchimp.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="49c4b-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="49c4b-107">มีผู้ชมที่มีอยู่ใน Mailchimp และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="49c4b-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="49c4b-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Mailchimp](https://mailchimp.com/help/create-audience/)</span><span class="sxs-lookup"><span data-stu-id="49c4b-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="49c4b-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="49c4b-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="49c4b-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="49c4b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="49c4b-111">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="49c4b-111">Known limitations</span></span>

- <span data-ttu-id="49c4b-112">โปรไฟล์ต่อการส่งออกไปยัง Mailchimp สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="49c4b-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="49c4b-113">การส่งออกไปยัง Mailchimp จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="49c4b-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="49c4b-114">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ 1 ล้านโปรไฟล์อาจใช้เวลาถึงสามชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="49c4b-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="49c4b-115">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Mailchimp นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="49c4b-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="49c4b-116">ตั้งค่าการเชื่อมต่อไปยัง Mailchimp</span><span class="sxs-lookup"><span data-stu-id="49c4b-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="49c4b-117">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="49c4b-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="49c4b-118">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Autopilot** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="49c4b-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="49c4b-119">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="49c4b-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="49c4b-120">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="49c4b-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="49c4b-121">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="49c4b-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="49c4b-122">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="49c4b-122">Choose who can use this connection.</span></span> <span data-ttu-id="49c4b-123">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="49c4b-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="49c4b-124">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="49c4b-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="49c4b-125">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="49c4b-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="49c4b-126">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="49c4b-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="49c4b-127">เลือก **รับรองความถูกต้องกับ Mailchimp** และให้ข้อมูลประจำตัวของ Mailchimp ของคุณ</span><span class="sxs-lookup"><span data-stu-id="49c4b-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="49c4b-128">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="49c4b-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="49c4b-129">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="49c4b-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="49c4b-130">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="49c4b-130">Configure the connector</span></span>

<span data-ttu-id="49c4b-131">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="49c4b-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="49c4b-132">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="49c4b-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="49c4b-133">ไปที่ **ข้อมูล**> **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="49c4b-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="49c4b-134">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="49c4b-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="49c4b-135">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Mailchimp</span><span class="sxs-lookup"><span data-stu-id="49c4b-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="49c4b-136">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="49c4b-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="49c4b-137">ป้อน **[รหัสผู้ชม Mailchimp](https://mailchimp.com/help/find-audience-id/)** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="49c4b-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="49c4b-138">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="49c4b-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="49c4b-139">คุณสามารถส่งออก **ชื่อ** และ **นามสกุล** เพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="49c4b-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="49c4b-140">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="49c4b-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="49c4b-141">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="49c4b-141">Select the segments you want to export.</span></span> <span data-ttu-id="49c4b-142">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Mailchimp ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="49c4b-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="49c4b-143">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="49c4b-143">Select **Save**.</span></span>

<span data-ttu-id="49c4b-144">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="49c4b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="49c4b-145">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="49c4b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49c4b-146">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="49c4b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49c4b-147">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="49c4b-147">Data privacy and compliance</span></span>

<span data-ttu-id="49c4b-148">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Mailchimp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="49c4b-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49c4b-149">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Mailchimp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="49c4b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="49c4b-150">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="49c4b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="49c4b-151">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="49c4b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
