---
title: ส่งออกข้อมูล Customer Insights ไปยัง Microsoft Advertising
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อและการส่งออกไปยัง Microsoft Advertising
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124561"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="5ae55-103">ส่งออกเซ็กเมนต์ไปยัง Microsoft Advertising (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="5ae55-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="5ae55-104">ส่งออกเซ็กเมนต์ Customer Insights ไปยัง Microsoft Advertising เพื่อสร้างผู้ชมของ Customer Match</span><span class="sxs-lookup"><span data-stu-id="5ae55-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="5ae55-105">ใช้ผู้ชมเหล่านี้สำหรับแคมเปญโฆษณาของคุณ</span><span class="sxs-lookup"><span data-stu-id="5ae55-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ae55-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="5ae55-106">Prerequisites</span></span>

-   <span data-ttu-id="5ae55-107">[บัญชี Microsoft Advertising](https://ads.microsoft.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="5ae55-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5ae55-108">คุณได้ยอมรับข้อกำหนดในการให้บริการของ Customer Match</span><span class="sxs-lookup"><span data-stu-id="5ae55-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="5ae55-109">[เซ็กเมนต์ที่ตั้งค่าคอนฟิก](segments.md) ในข้อมูลเชิงลึกของผู้ชม</span><span class="sxs-lookup"><span data-stu-id="5ae55-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5ae55-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออก มีฟิลด์ที่มีที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="5ae55-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5ae55-111">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="5ae55-111">Known limitations</span></span>

- <span data-ttu-id="5ae55-112">คุณสามารถส่งออกโปรไฟล์ได้ถึง 500 K โปรไฟล์ต่อการส่งออกหนึ่งรายการไปยัง Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="5ae55-113">การส่งออกไปยัง Microsoft Advertising นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="5ae55-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="5ae55-114">การส่งออกมากถึง 500 K โปรไฟล์ไปยัง Microsoft Advertising อาจใช้เวลาถึง 10 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="5ae55-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="5ae55-115">ตั้งค่าการเชื่อมต่อกับ Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="5ae55-116">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="5ae55-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5ae55-117">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Microsoft Advertising** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5ae55-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="5ae55-118">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="5ae55-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5ae55-119">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5ae55-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5ae55-120">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5ae55-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5ae55-121">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5ae55-121">Choose who can use this connection.</span></span> <span data-ttu-id="5ae55-122">ค่าเริ่มต้นคือ ผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="5ae55-122">The default is administrators.</span></span> <span data-ttu-id="5ae55-123">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="5ae55-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5ae55-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="5ae55-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5ae55-125">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อไปยัง Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5ae55-126">เลือก **รับรองความถูกต้องด้วย Microsoft Advertising** และให้ข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับ Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="5ae55-127">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="5ae55-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5ae55-128">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="5ae55-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5ae55-129">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="5ae55-129">Configure an export</span></span>

<span data-ttu-id="5ae55-130">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5ae55-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5ae55-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="5ae55-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5ae55-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="5ae55-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5ae55-133">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="5ae55-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5ae55-134">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="5ae55-135">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5ae55-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5ae55-136">เลือกเซ็กเมนต์ที่จะส่งออก</span><span class="sxs-lookup"><span data-stu-id="5ae55-136">Select the segments to export.</span></span> <span data-ttu-id="5ae55-137">ผู้ชมของ Customer Match ใน Microsoft Advertising จะถูกสร้างขึ้นโดยอัตโนมัติด้วยชื่อของเซ็กเมนต์ที่เลือกสำหรับการส่งออก</span><span class="sxs-lookup"><span data-stu-id="5ae55-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="5ae55-138">แต่ละเซ็กเมนต์จะส่งผลให้มีผู้ชมของ Customer Match ที่แยกจากกัน</span><span class="sxs-lookup"><span data-stu-id="5ae55-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="5ae55-139">ป้อน **รหัสลูกค้าและรหัสบัญชีของ Microsoft Advertising** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="5ae55-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="5ae55-140">คุณสามารถค้นหารหัสลูกค้า (`cid`) และรหัสบัญชี (`aid`) ในพารามิเตอร์ของ URL เมื่อคุณเข้าสู่ระบบ Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="5ae55-141">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่มีที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="5ae55-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="5ae55-142">ซึ่งจำเป็นต้องส่งออกเซ็กเมนต์ไปยัง Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5ae55-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5ae55-143">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="5ae55-143">Select **Save**.</span></span>

<span data-ttu-id="5ae55-144">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="5ae55-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5ae55-145">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="5ae55-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5ae55-146">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="5ae55-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5ae55-147">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="5ae55-147">Data privacy and compliance</span></span>

<span data-ttu-id="5ae55-148">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Microsoft Advertising คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="5ae55-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5ae55-149">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Microsoft Advertising เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="5ae55-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5ae55-150">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="5ae55-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5ae55-151">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกเมื่อใดก็ได้ เพื่อหยุดการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="5ae55-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
