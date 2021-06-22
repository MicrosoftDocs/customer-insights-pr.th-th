---
title: ส่งออกข้อมูล Customer Insights ไปยัง Campaign Monitor
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Campaign Monitor
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124204"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="c0974-103">ส่งออกเซ็กเมนต์ไปยัง Campaign Monitor (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="c0974-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="c0974-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Campaign Monitor และใช้สำหรับกิจกรรมการตลาด</span><span class="sxs-lookup"><span data-stu-id="c0974-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c0974-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="c0974-105">Prerequisites</span></span>

-   <span data-ttu-id="c0974-106">คุณมี [บัญชี Campaign Monitor](https://www.campaignmonitor.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="c0974-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c0974-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="c0974-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c0974-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="c0974-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c0974-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="c0974-109">Known limitations</span></span>

- <span data-ttu-id="c0974-110">คุณสามารถส่งออกโปรไฟล์ได้ถึง 1 ล้านโปรไฟล์ต่อการส่งออกไปยัง Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="c0974-111">การส่งออกไปยัง Campaign Monitor นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c0974-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="c0974-112">การส่งออกมากถึง 1 ล้านโปรไฟล์ไปยัง Campaign Monitor อาจใช้เวลาถึง 20 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="c0974-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="c0974-113">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Campaign Monitor นั้นขึ้นอยู่และจำกัดตามสัญญาของคุณกับ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="c0974-114">ตั้งค่าการเชื่อมต่อกับ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="c0974-115">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="c0974-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c0974-116">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Campaign Monitor** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="c0974-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="c0974-117">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="c0974-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c0974-118">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="c0974-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c0974-119">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="c0974-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c0974-120">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="c0974-120">Choose who can use this connection.</span></span> <span data-ttu-id="c0974-121">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="c0974-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c0974-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="c0974-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c0974-123">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="c0974-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c0974-124">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="c0974-125">เลือก **รับรองความถูกต้องกับ Campaign Monitor** และให้ข้อมูลรับรองผู้ดูแลระบบของคุณสำหรับ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="c0974-126">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c0974-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c0974-127">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="c0974-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c0974-128">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="c0974-128">Configure an export</span></span>

<span data-ttu-id="c0974-129">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="c0974-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c0974-130">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="c0974-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c0974-131">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="c0974-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0974-132">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="c0974-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c0974-133">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="c0974-134">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="c0974-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c0974-135">ป้อน [**รหัสรายการ Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c0974-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="c0974-136">[สร้างคีย์ API](https://www.campaignmonitor.com/api/getting-started/) จาก **การตั้งค่าบัญชี** ใน Campaign Monitor ก่อนเพื่อดูรหัสรายการ API</span><span class="sxs-lookup"><span data-stu-id="c0974-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="c0974-137">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="c0974-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c0974-138">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c0974-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="c0974-139">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="c0974-139">Select **Save**.</span></span>

<span data-ttu-id="c0974-140">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="c0974-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c0974-141">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="c0974-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c0974-142">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="c0974-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c0974-143">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="c0974-143">Data privacy and compliance</span></span>

<span data-ttu-id="c0974-144">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Campaign Monitor คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="c0974-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c0974-145">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Campaign Monitor เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="c0974-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c0974-146">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="c0974-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c0974-147">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="c0974-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
