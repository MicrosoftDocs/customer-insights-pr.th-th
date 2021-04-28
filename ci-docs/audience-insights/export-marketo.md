---
title: ส่งออกข้อมูล Customer Insights ไปยัง Marketo
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Marketo
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759844"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="c9b35-103">ส่งออกเซ็กเมนต์ไปยัง Marketo (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="c9b35-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="c9b35-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมเพื่อสร้างการส่งเสริมการขาย จัดทำการตลาดทางอีเมล และใช้กลุ่มลูกค้าเฉพาะกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="c9b35-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c9b35-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="c9b35-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c9b35-106">คุณมี [บัญชี Marketo](https://login.marketo.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="c9b35-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c9b35-107">มีรายการที่มีอยู่ใน Marketo และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="c9b35-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="c9b35-108">สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [รายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)</span><span class="sxs-lookup"><span data-stu-id="c9b35-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="c9b35-109">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c9b35-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="c9b35-110">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="c9b35-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c9b35-111">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="c9b35-111">Known limitations</span></span>

- <span data-ttu-id="c9b35-112">โปรไฟล์ต่อการส่งออกไปยัง Marketo สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="c9b35-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="c9b35-113">การส่งออกไปยัง Marketo จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="c9b35-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="c9b35-114">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="c9b35-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="c9b35-115">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Marketo นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="c9b35-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="c9b35-116">ตั้งค่าการเชื่อมต่อไปยัง Marketo</span><span class="sxs-lookup"><span data-stu-id="c9b35-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="c9b35-117">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="c9b35-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c9b35-118">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Marketo** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="c9b35-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="c9b35-119">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="c9b35-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c9b35-120">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="c9b35-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c9b35-121">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="c9b35-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c9b35-122">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="c9b35-122">Choose who can use this connection.</span></span> <span data-ttu-id="c9b35-123">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="c9b35-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c9b35-124">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="c9b35-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c9b35-125">ป้อน **[รหัสไคลเอ็นต์ Marketo ข้อมูลลับของไคลเอ็นต์และชื่อโฮสต์จุดสิ้นสุด REST](https://developers.marketo.com/rest-api/authentication/)**</span><span class="sxs-lookup"><span data-stu-id="c9b35-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="c9b35-126">เลือก **ฉันตกลง** เพื่อยืนยัน **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** และเลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Marketo</span><span class="sxs-lookup"><span data-stu-id="c9b35-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="c9b35-127">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="c9b35-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c9b35-128">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="c9b35-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c9b35-129">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="c9b35-129">Configure an export</span></span>

<span data-ttu-id="c9b35-130">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="c9b35-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c9b35-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="c9b35-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c9b35-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="c9b35-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c9b35-133">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="c9b35-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c9b35-134">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Marketo</span><span class="sxs-lookup"><span data-stu-id="c9b35-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="c9b35-135">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="c9b35-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c9b35-136">ป้อน **[รหัสรายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="c9b35-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="c9b35-137">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="c9b35-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c9b35-138">คุณสามารถส่งออก **ชื่อ** **นามสกุล** **เมือง** **รัฐ** และ **ประเทศ/ภูมิภาค**  เพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="c9b35-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="c9b35-139">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="c9b35-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c9b35-140">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="c9b35-140">Select the segments you want to export.</span></span> <span data-ttu-id="c9b35-141">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Marketo ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="c9b35-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="c9b35-142">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="c9b35-142">Select **Save**.</span></span>

<span data-ttu-id="c9b35-143">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="c9b35-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c9b35-144">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="c9b35-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c9b35-145">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="c9b35-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c9b35-146">ใน Marketo ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [รายชื่อ Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)</span><span class="sxs-lookup"><span data-stu-id="c9b35-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c9b35-147">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="c9b35-147">Data privacy and compliance</span></span>

<span data-ttu-id="c9b35-148">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Marketo คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="c9b35-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c9b35-149">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Marketo ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="c9b35-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c9b35-150">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="c9b35-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c9b35-151">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="c9b35-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]