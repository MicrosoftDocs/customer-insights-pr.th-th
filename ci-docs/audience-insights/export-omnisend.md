---
title: ส่งออกข้อมูล Customer Insights ไปยัง Omnisend
description: เรียนรู้วิธีตั้งค่าคอนฟิกการเชื่อมต่อและการส่งออกไปยัง Omnisend
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124562"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="5955b-103">ส่งออกเซ็กเมนต์ไปยัง Omnisend (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="5955b-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="5955b-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Omnisend และใช้สำหรับกิจกรรมการตลาด</span><span class="sxs-lookup"><span data-stu-id="5955b-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5955b-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="5955b-105">Prerequisites</span></span>

-   <span data-ttu-id="5955b-106">คุณมี [บัญชี Omnisend](https://www.omnisend.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="5955b-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5955b-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="5955b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5955b-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="5955b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5955b-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="5955b-109">Known limitations</span></span>

- <span data-ttu-id="5955b-110">คุณสามารถส่งออกโปรไฟล์ได้มากถึง 1 ล้านโปรไฟล์ต่อหนึ่งการส่งออกไปยัง Omnisend และอาจใช้เวลาถึง 4 ชั่วโมงจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="5955b-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="5955b-111">การส่งออกไปยัง Omnisend ถูกจำกัดสำหรับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="5955b-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="5955b-112">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Omnisend ได้นั้นขึ้นอยู่กับสัญญาของคุณกับ Omnisend</span><span class="sxs-lookup"><span data-stu-id="5955b-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="5955b-113">ตั้งค่าการเชื่อมต่อไปยัง Omnisend</span><span class="sxs-lookup"><span data-stu-id="5955b-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="5955b-114">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="5955b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5955b-115">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Omnisend** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5955b-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="5955b-116">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="5955b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5955b-117">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5955b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5955b-118">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5955b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5955b-119">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5955b-119">Choose who can use this connection.</span></span> <span data-ttu-id="5955b-120">โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="5955b-120">By default it's only administrators.</span></span> <span data-ttu-id="5955b-121">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="5955b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5955b-122">ป้อน [คีย์ API ของ Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="5955b-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="5955b-123">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="5955b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5955b-124">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อไปยัง Omnisend</span><span class="sxs-lookup"><span data-stu-id="5955b-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="5955b-125">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="5955b-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5955b-126">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="5955b-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5955b-127">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="5955b-127">Configure an export</span></span>

<span data-ttu-id="5955b-128">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5955b-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5955b-129">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="5955b-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5955b-130">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="5955b-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5955b-131">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="5955b-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5955b-132">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Omnisend</span><span class="sxs-lookup"><span data-stu-id="5955b-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="5955b-133">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5955b-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5955b-134">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="5955b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5955b-135">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง Omnisend</span><span class="sxs-lookup"><span data-stu-id="5955b-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="5955b-136">หรือคุณสามารถส่งออกชื่อ, นามสกุล, ที่อยู่, ประเทศ/ภูมิภาค ,รัฐ, เมือง, และรหัสไปรษณีย์ เพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="5955b-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="5955b-137">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้</span><span class="sxs-lookup"><span data-stu-id="5955b-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5955b-138">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="5955b-138">Select **Save**.</span></span>

<span data-ttu-id="5955b-139">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="5955b-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5955b-140">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="5955b-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5955b-141">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="5955b-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5955b-142">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="5955b-142">Data privacy and compliance</span></span>

<span data-ttu-id="5955b-143">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Ommisend คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="5955b-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5955b-144">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Omnisend เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="5955b-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5955b-145">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="5955b-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5955b-146">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="5955b-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
