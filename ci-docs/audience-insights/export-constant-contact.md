---
title: ส่งออกข้อมูล Customer Insights ไปยัง Constant Contact
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Constant Contact
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124296"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="3768a-103">ส่งออกเซ็กเมนต์ไปยัง Constant Contact (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="3768a-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="3768a-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Constant Contact และใช้สำหรับกิจกรรมการตลาด</span><span class="sxs-lookup"><span data-stu-id="3768a-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3768a-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="3768a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3768a-106">คุณมี [บัญชี Constant Contact](https://www.constantcontact.com/account-home) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="3768a-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3768a-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="3768a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3768a-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="3768a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3768a-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="3768a-109">Known limitations</span></span>

- <span data-ttu-id="3768a-110">คุณสามารถส่งออกโปรไฟล์ได้ถึง 1 ล้านโปรไฟล์ต่อการส่งออกไปยัง Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="3768a-111">การส่งออกไปยัง Constant Contact นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="3768a-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="3768a-112">การส่งออกมากถึง 1 ล้านโปรไฟล์ไปยัง Constant Contact อาจใช้เวลาถึง 1 ชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="3768a-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="3768a-113">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Constant Contact นั้นขึ้นอยู่และจำกัดตามสัญญาของคุณกับ Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="3768a-114">ตั้งค่าการเชื่อมต่อกับ Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="3768a-115">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="3768a-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3768a-116">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Constant Contact** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="3768a-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="3768a-117">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="3768a-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3768a-118">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="3768a-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3768a-119">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="3768a-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3768a-120">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="3768a-120">Choose who can use this connection.</span></span> <span data-ttu-id="3768a-121">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="3768a-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3768a-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="3768a-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3768a-123">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="3768a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3768a-124">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="3768a-125">เลือก **รับรองความถูกต้องกับ AdRoll** และให้ข้อมูลรับรองผู้ดูแลระบบของคุณสำหรับ Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="3768a-126">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="3768a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3768a-127">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="3768a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3768a-128">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3768a-128">Configure an export</span></span>

<span data-ttu-id="3768a-129">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="3768a-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3768a-130">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="3768a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3768a-131">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="3768a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3768a-132">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="3768a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3768a-133">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="3768a-134">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="3768a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3768a-135">ป้อน [**รหัสรายการ Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="3768a-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="3768a-136">เปิดรายการใน Constant Contact เพื่อค้นหารหัสรายการใน URL</span><span class="sxs-lookup"><span data-stu-id="3768a-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="3768a-137">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3768a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3768a-138">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง Constant Contact</span><span class="sxs-lookup"><span data-stu-id="3768a-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="3768a-139">หรือคุณสามารถส่งออก ชื่อ และ นามสกุล เป็นฟิลด์เพิ่มเติมเพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="3768a-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="3768a-140">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="3768a-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="3768a-141">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="3768a-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="3768a-142">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="3768a-142">Select **Save**.</span></span>

<span data-ttu-id="3768a-143">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="3768a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3768a-144">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="3768a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3768a-145">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="3768a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3768a-146">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="3768a-146">Data privacy and compliance</span></span>

<span data-ttu-id="3768a-147">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Constant Contact คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="3768a-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3768a-148">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Constant Contact เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="3768a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3768a-149">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="3768a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3768a-150">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="3768a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
