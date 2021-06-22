---
title: ส่งออกข้อมูล Customer Insights ไปยัง RollWorks
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง RollWorks
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124112"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="33e96-103">ส่งออกเซ็กเมนต์ไปยัง RollWorks (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="33e96-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="33e96-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง RollWorks และใช้สำหรับการโฆษณา</span><span class="sxs-lookup"><span data-stu-id="33e96-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="33e96-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="33e96-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="33e96-106">คุณมี [บัญชี RollWorks](https://www.rollworks.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน</span><span class="sxs-lookup"><span data-stu-id="33e96-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="33e96-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="33e96-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="33e96-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="33e96-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="33e96-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="33e96-109">Known limitations</span></span>

- <span data-ttu-id="33e96-110">คุณสามารถส่งออกโปรไฟล์ได้ถึง 250,000 โปรไฟล์ต่อการส่งออกไปยัง RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="33e96-111">คุณไม่สามารถส่งออกเซ็กเมนต์ที่มีน้อยกว่า 100 โปรไฟล์ไปยัง RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="33e96-112">การส่งออกไปยัง RollWorks นั้นจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="33e96-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="33e96-113">การส่งออกโปรไฟล์มากถึง 250,000 โปรไฟล์ไปยัง RollWorks อาจใช้เวลาถึง 10 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="33e96-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="33e96-114">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง RollWorks นั้นขึ้นอยู่และจำกัดตามสัญญาของคุณกับ RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="33e96-115">ตั้งค่าการเชื่อมต่อไปยัง RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="33e96-116">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="33e96-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33e96-117">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **RollWorks** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="33e96-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="33e96-118">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="33e96-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33e96-119">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="33e96-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33e96-120">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="33e96-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33e96-121">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="33e96-121">Choose who can use this connection.</span></span> <span data-ttu-id="33e96-122">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="33e96-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33e96-123">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="33e96-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="33e96-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="33e96-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="33e96-125">เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="33e96-126">เลือก **รับรองความถูกต้องกับ RollWorks** และให้ข้อมูลรับรองผู้ดูแลระบบของคุณสำหรับ RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="33e96-127">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="33e96-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="33e96-128">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="33e96-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="33e96-129">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="33e96-129">Configure an export</span></span>

<span data-ttu-id="33e96-130">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="33e96-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33e96-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="33e96-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33e96-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="33e96-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33e96-133">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="33e96-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="33e96-134">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="33e96-135">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="33e96-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="33e96-136">ป้อน **รหัสผู้ลงโฆษณา RollWorks** [RollWorks สามารถโฆษณาได้](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)</span><span class="sxs-lookup"><span data-stu-id="33e96-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="33e96-137">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="33e96-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="33e96-138">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง RollWorks</span><span class="sxs-lookup"><span data-stu-id="33e96-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="33e96-139">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="33e96-139">Select the segments you want to export.</span></span> <span data-ttu-id="33e96-140">เลือกเซ็กเมนต์ที่มีสมาชิกอย่างน้อย 100 คน</span><span class="sxs-lookup"><span data-stu-id="33e96-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="33e96-141">คุณไม่สามารถส่งออกเซ็กเมนต์ที่เล็กกว่านั้นได้</span><span class="sxs-lookup"><span data-stu-id="33e96-141">You can't export smaller segments.</span></span> <span data-ttu-id="33e96-142">นอกจากนี้ ขนาดสูงสุดของเซ็กเมนต์ที่จะส่งออกคือสมาชิก 250,000 รายต่อการส่งออก</span><span class="sxs-lookup"><span data-stu-id="33e96-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="33e96-143">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="33e96-143">Select **Save**.</span></span>

<span data-ttu-id="33e96-144">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="33e96-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="33e96-145">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="33e96-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="33e96-146">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="33e96-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="33e96-147">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="33e96-147">Data privacy and compliance</span></span>

<span data-ttu-id="33e96-148">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง RollWorks คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="33e96-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="33e96-149">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำแนะนำของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า RollWorks เป็นไปตามภาระหน้าที่ด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="33e96-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="33e96-150">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="33e96-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="33e96-151">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="33e96-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
