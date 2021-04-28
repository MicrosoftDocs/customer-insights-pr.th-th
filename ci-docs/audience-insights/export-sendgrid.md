---
title: ส่งออกข้อมูล Customer Insights ไปยัง SendGrid
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง SendGrid
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759788"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="4e545-103">ส่งออกเซ็กเมนต์ไปยัง SendGrid (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="4e545-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="4e545-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายชื่อผู้ติดต่อของ SendGrid และใช้สำหรับการส่งเสริมการขายและการตลาดทางอีเมลใน SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4e545-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="4e545-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4e545-106">คุณมี [บัญชี SendGrid](https://sendgrid.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="4e545-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4e545-107">มีรายการผู้ติดต่อที่มีอยู่ใน SendGrid และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="4e545-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="4e545-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [SendGrid - จัดการผู้ติดต่อ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)</span><span class="sxs-lookup"><span data-stu-id="4e545-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="4e545-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="4e545-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4e545-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="4e545-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4e545-111">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="4e545-111">Known limitations</span></span>

- <span data-ttu-id="4e545-112">โปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="4e545-113">การส่งออกไปยัง SendGrid ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="4e545-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="4e545-114">การส่งออกโปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid อาจใช้เวลาสองสามชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="4e545-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4e545-115">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง SendGrid นั้น ขึ้นอยู่และถูกจำกัดตามสัญญาของคุณกับ SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="4e545-116">ตั้งค่าการเชื่อมต่อไปยัง SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="4e545-117">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="4e545-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4e545-118">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **SendGrid** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="4e545-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="4e545-119">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="4e545-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4e545-120">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="4e545-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4e545-121">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="4e545-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4e545-122">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="4e545-122">Choose who can use this connection.</span></span> <span data-ttu-id="4e545-123">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="4e545-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4e545-124">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="4e545-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4e545-125">ป้อน **คีย์ SendGrid API** [คีย์ SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)</span><span class="sxs-lookup"><span data-stu-id="4e545-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="4e545-126">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="4e545-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4e545-127">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="4e545-128">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="4e545-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4e545-129">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="4e545-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4e545-130">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4e545-130">Configure an export</span></span>

<span data-ttu-id="4e545-131">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="4e545-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4e545-132">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="4e545-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4e545-133">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4e545-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4e545-134">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="4e545-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4e545-135">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="4e545-136">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="4e545-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4e545-137">ป้อน **[รหัสรายชื่อ SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="4e545-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="4e545-138">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="4e545-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4e545-139">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ เช่น **ชื่อ**, **นามสกุล**, **ประเทศ/ภูมิภาค**, **รัฐ**, **เมือง** และ **รหัสไปรษณีย์**</span><span class="sxs-lookup"><span data-stu-id="4e545-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="4e545-140">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="4e545-140">Select the segments you want to export.</span></span> <span data-ttu-id="4e545-141">เรา **แนะนำอย่างยิ่งว่า อย่าส่งออกโปรไฟล์ลูกค้าทั้งหมดมากกว่า 100'000 โปรไฟล์** ไปยัง SendGrid</span><span class="sxs-lookup"><span data-stu-id="4e545-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="4e545-142">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="4e545-142">Select **Save**.</span></span>

<span data-ttu-id="4e545-143">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="4e545-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4e545-144">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="4e545-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4e545-145">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="4e545-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4e545-146">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="4e545-146">Data privacy and compliance</span></span>

<span data-ttu-id="4e545-147">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง SendGrid คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="4e545-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4e545-148">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า SendGrid ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="4e545-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4e545-149">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="4e545-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4e545-150">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="4e545-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]