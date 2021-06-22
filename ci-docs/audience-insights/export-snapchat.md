---
title: ส่งออกข้อมูล Customer Insights ไปยัง Snapchat
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Snapchat
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124066"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="f2886-103">ส่งออกเซ็กเมนต์ไปยัง Snapchat (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="f2886-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="f2886-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Snapchat และใช้สำหรับการโฆษณา</span><span class="sxs-lookup"><span data-stu-id="f2886-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f2886-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f2886-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f2886-106">คุณมี [บัญชี Snapchat Business](https://business.snapchat.com/) [บัญชี Snapchat Ads](https://ads.snapchat.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="f2886-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f2886-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="f2886-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f2886-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="f2886-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f2886-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="f2886-109">Known limitations</span></span>

- <span data-ttu-id="f2886-110">การส่งออกไปยัง Snapchat นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="f2886-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="f2886-111">การส่งออกมากถึง 1 ล้านโปรไฟล์ไปยัง Snapchat อาจใช้เวลาถึง 15 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="f2886-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="f2886-112">ตั้งค่าการเชื่อมต่อไปยัง Snapchat</span><span class="sxs-lookup"><span data-stu-id="f2886-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="f2886-113">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="f2886-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f2886-114">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Snapchat** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f2886-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="f2886-115">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="f2886-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f2886-116">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="f2886-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f2886-117">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f2886-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f2886-118">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="f2886-118">Choose who can use this connection.</span></span> <span data-ttu-id="f2886-119">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="f2886-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f2886-120">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="f2886-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f2886-121">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="f2886-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f2886-122">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ Snapchat</span><span class="sxs-lookup"><span data-stu-id="f2886-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="f2886-123">เลือก **รับรองความถูกต้องกับ Snapchat** และให้ข้อมูลรับรองผู้ดูแลระบบของคุณสำหรับ Snapchat</span><span class="sxs-lookup"><span data-stu-id="f2886-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="f2886-124">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f2886-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f2886-125">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="f2886-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f2886-126">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="f2886-126">Configure an export</span></span>

<span data-ttu-id="f2886-127">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="f2886-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f2886-128">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="f2886-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f2886-129">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="f2886-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2886-130">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="f2886-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f2886-131">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Snapchat</span><span class="sxs-lookup"><span data-stu-id="f2886-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="f2886-132">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="f2886-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f2886-133">ป้อน [**รหัสผู้ชม Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences)</span><span class="sxs-lookup"><span data-stu-id="f2886-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="f2886-134">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="f2886-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f2886-135">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง Snapchat</span><span class="sxs-lookup"><span data-stu-id="f2886-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="f2886-136">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="f2886-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="f2886-137">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="f2886-137">Select **Save**.</span></span>

<span data-ttu-id="f2886-138">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="f2886-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f2886-139">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="f2886-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2886-140">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="f2886-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f2886-141">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="f2886-141">Data privacy and compliance</span></span>

<span data-ttu-id="f2886-142">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Snapchat คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="f2886-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f2886-143">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Snapchat เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="f2886-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f2886-144">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="f2886-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f2886-145">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="f2886-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
