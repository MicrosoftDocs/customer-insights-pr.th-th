---
title: ส่งออกข้อมูล Customer Insights ไปยัง Sendinblue
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อและส่งออกไปยัง Sendinblue
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314685"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="1e220-103">ส่งออกเซ็กเมนต์ไปยัง Sendinblue (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="1e220-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="1e220-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมเพื่อสร้างแคมเปญ จัดทำการตลาดทางอีเมล และใช้กลุ่มลูกค้าเฉพาะด้วย Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1e220-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1e220-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1e220-106">คุณมี [บัญชี Sendinblue](https://www.sendinblue.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="1e220-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e220-107">มีรายการที่มีอยู่ใน Sendinblue และ ID ที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="1e220-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="1e220-108">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="1e220-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1e220-109">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="1e220-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e220-110">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="1e220-110">Known limitations</span></span>

- <span data-ttu-id="1e220-111">มากถึง 1 ล้านโปรไฟล์ต่อการส่งออกไปยัง Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="1e220-112">การส่งออกไปยัง Sendinblue ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="1e220-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="1e220-113">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลานานถึง 90 นาที</span><span class="sxs-lookup"><span data-stu-id="1e220-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="1e220-114">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Sendinblue นั้นขึ้นอยู่กับและถูกจำกัดในสัญญาของคุณกับ Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="1e220-115">ตั้งค่าการเชื่อมต่อกับ Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="1e220-116">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="1e220-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e220-117">เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Sendinblue** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1e220-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="1e220-118">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="1e220-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e220-119">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="1e220-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e220-120">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1e220-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e220-121">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="1e220-121">Choose who can use this connection.</span></span> <span data-ttu-id="1e220-122">โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="1e220-122">By default it's only administrators.</span></span> <span data-ttu-id="1e220-123">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="1e220-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e220-124">ป้อน **[คีย์ SendinBlue API](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1e220-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="1e220-125">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** และเลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="1e220-126">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1e220-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e220-127">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="1e220-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1e220-128">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="1e220-128">Configure an export</span></span>

<span data-ttu-id="1e220-129">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="1e220-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e220-130">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="1e220-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e220-131">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="1e220-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e220-132">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="1e220-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e220-133">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1e220-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="1e220-134">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="1e220-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1e220-135">ป้อน **รหัสรายการ Sendinblue** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1e220-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="1e220-136">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="1e220-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1e220-137">หรือคุณสามารถส่งออก **ชื่อ**, **นามสกุล** และ **โทรศัพท์** เพื่อสร้างอีเมลที่ปรับให้เป็นแบบส่วนตัวเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="1e220-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="1e220-138">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="1e220-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1e220-139">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="1e220-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="1e220-140">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="1e220-140">Select **Save**.</span></span>

<span data-ttu-id="1e220-141">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="1e220-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e220-142">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="1e220-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e220-143">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="1e220-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e220-144">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="1e220-144">Data privacy and compliance</span></span>

<span data-ttu-id="1e220-145">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Sendinblue คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="1e220-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e220-146">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบให้แน่ใจว่า Sendinblue เป็นไปตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="1e220-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e220-147">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="1e220-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1e220-148">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="1e220-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
