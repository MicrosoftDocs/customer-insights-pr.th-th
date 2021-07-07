---
title: ส่งออกข้อมูล Customer Insights ไปยัง ActiveCampaign
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อและส่งออกไปยัง ActiveCampaign
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314686"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="b9549-103">ส่งออกเซ็กเมนต์ไปยัง ActiveCampaign (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="b9549-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="b9549-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง ActiveCampaign และใช้สำหรับกิจกรรมทางการตลาด</span><span class="sxs-lookup"><span data-stu-id="b9549-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9549-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="b9549-105">Prerequisites</span></span>

-   <span data-ttu-id="b9549-106">คุณมี [บัญชี ActiveCampaign](https://www.activecampaign.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="b9549-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b9549-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="b9549-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b9549-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออก มีฟิลด์ที่มีที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="b9549-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b9549-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="b9549-109">Known limitations</span></span>

- <span data-ttu-id="b9549-110">คุณสามารถส่งออกโปรไฟล์ได้สูงสุด 1 ล้านโปรไฟล์ต่อการส่งออกไปยัง ActiveCampaign และอาจใช้เวลานานถึง 90 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="b9549-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="b9549-111">การส่งออกไปยัง ActiveCampaign ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="b9549-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="b9549-112">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง ActiveCampaign ขึ้นอยู่กับสัญญาของคุณกับ ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b9549-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="b9549-113">ตั้งค่าการเชื่อมต่อกับ ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b9549-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="b9549-114">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="b9549-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b9549-115">เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **ActiveCampaign** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="b9549-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="b9549-116">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="b9549-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b9549-117">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="b9549-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b9549-118">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="b9549-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b9549-119">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="b9549-119">Choose who can use this connection.</span></span> <span data-ttu-id="b9549-120">โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="b9549-120">By default, it's only administrators.</span></span> <span data-ttu-id="b9549-121">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="b9549-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b9549-122">ป้อน [คีย์ ActiveCampaign API และชื่อโฮสต์จุดสิ้นสุด REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="b9549-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="b9549-123">ชื่อโฮสต์จุดสิ้นสุด REST เป็นชื่อโฮสต์เท่านั้น โดยไม่มี https://</span><span class="sxs-lookup"><span data-stu-id="b9549-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="b9549-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="b9549-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b9549-125">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อไปยัง ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b9549-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="b9549-126">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="b9549-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b9549-127">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="b9549-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b9549-128">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="b9549-128">Configure an export</span></span>

<span data-ttu-id="b9549-129">คุณสามารถตั้งค่าคอนฟิกการส่งออกได้ หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="b9549-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="b9549-130">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="b9549-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b9549-131">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="b9549-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9549-132">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="b9549-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b9549-133">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b9549-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="b9549-134">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="b9549-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b9549-135">ป้อน [**รหัสรายการ ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="b9549-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="b9549-136">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="b9549-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b9549-137">ซึ่งจำเป็นต้องส่งออกเซ็กเมนต์ไปยัง ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b9549-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="b9549-138">หรือคุณสามารถส่งออกชื่อ นามสกุล และโทรศัพท์ เพื่อสร้างอีเมลที่ปรับให้เป็นแบบส่วนตัวเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="b9549-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="b9549-139">เลือก เพิ่มแอตทริบิวต์ เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="b9549-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="b9549-140">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="b9549-140">Select **Save**.</span></span>

<span data-ttu-id="b9549-141">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="b9549-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b9549-142">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="b9549-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b9549-143">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="b9549-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b9549-144">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="b9549-144">Data privacy and compliance</span></span>

<span data-ttu-id="b9549-145">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง ActiveCampaign คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="b9549-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b9549-146">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบให้แน่ใจว่า ActiveCampaign เป็นไปตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="b9549-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b9549-147">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="b9549-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b9549-148">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="b9549-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
