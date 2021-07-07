---
title: ส่งออกข้อมูล Customer Insights ไปยัง AdRoll
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง AdRoll
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304857"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="d7e44-103">ส่งออกเซ็กเมนต์ไปยัง AdRoll (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="d7e44-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="d7e44-104">ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง AdRoll และใช้สำหรับการโฆษณา</span><span class="sxs-lookup"><span data-stu-id="d7e44-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d7e44-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d7e44-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d7e44-106">คุณมี [บัญชี AdRoll](https://www.adroll.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="d7e44-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d7e44-107">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d7e44-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d7e44-108">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="d7e44-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d7e44-109">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="d7e44-109">Known limitations</span></span>

- <span data-ttu-id="d7e44-110">คุณสามารถส่งออกโปรไฟล์ได้ถึงครั้งละ 250,000 โปรไฟล์ไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="d7e44-111">คุณไม่สามารถส่งออกเซ็กเมนต์ที่มีน้อยกว่า 100 โปรไฟล์ไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="d7e44-112">การส่งออกไปยัง AdRoll มีการจำกัดเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="d7e44-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="d7e44-113">การส่งออกโปรไฟล์มากถึง 250,000 โปรไฟล์ไปยัง AdRoll อาจใช้เวลาถึง 10 นาทีจึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="d7e44-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="d7e44-114">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง AdRoll ขึ้นอยู่กับสัญญาของคุณกับ AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="d7e44-115">ตั้งค่าการเชื่อมต่อไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="d7e44-116">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="d7e44-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d7e44-117">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **AdRoll** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d7e44-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="d7e44-118">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="d7e44-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d7e44-119">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d7e44-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d7e44-120">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d7e44-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d7e44-121">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d7e44-121">Choose who can use this connection.</span></span> <span data-ttu-id="d7e44-122">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="d7e44-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d7e44-123">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="d7e44-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d7e44-124">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="d7e44-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d7e44-125">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="d7e44-126">เลือก **รับรองความถูกต้องกับ AdRoll** และให้ข้อมูลประจำตัวผู้ดูแลระบบสำหรับ AdRoll ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d7e44-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="d7e44-127">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d7e44-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d7e44-128">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="d7e44-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d7e44-129">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="d7e44-129">Configure an export</span></span>

<span data-ttu-id="d7e44-130">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="d7e44-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d7e44-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="d7e44-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d7e44-132">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="d7e44-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d7e44-133">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="d7e44-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d7e44-134">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="d7e44-135">หากคุณไม่เห็นชื่อส่วนนี้ การเชื่อมต่อชนิดนี้ไม่พร้อมใช้งานสำหรับคุณ</span><span class="sxs-lookup"><span data-stu-id="d7e44-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="d7e44-136">ป้อน **รหัสผู้ลงโฆษณา AdRoll** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d7e44-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="d7e44-137">สำหรับข้อมูลเพิ่มเติม ดูที่ [โปรไฟล์ผู้ลงโฆษณา AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)</span><span class="sxs-lookup"><span data-stu-id="d7e44-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="d7e44-138">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="d7e44-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d7e44-139">จำเป็นต้องส่งออกเซ็กเมนต์ไปยัง AdRoll</span><span class="sxs-lookup"><span data-stu-id="d7e44-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="d7e44-140">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="d7e44-140">Select the segments you want to export.</span></span> <span data-ttu-id="d7e44-141">เลือกเซ็กเมนต์ที่มีสมาชิกอย่างน้อย 100 คน</span><span class="sxs-lookup"><span data-stu-id="d7e44-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="d7e44-142">คุณไม่สามารถส่งออกเซ็กเมนต์ที่เล็กกว่านั้นได้</span><span class="sxs-lookup"><span data-stu-id="d7e44-142">You can't export smaller segments.</span></span> <span data-ttu-id="d7e44-143">นอกจากนี้ ขนาดสูงสุดของเซ็กเมนต์ที่จะส่งออกคือสมาชิก 250,000 รายต่อการส่งออก</span><span class="sxs-lookup"><span data-stu-id="d7e44-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="d7e44-144">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="d7e44-144">Select **Save**.</span></span>

<span data-ttu-id="d7e44-145">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="d7e44-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d7e44-146">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="d7e44-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="d7e44-147">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="d7e44-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d7e44-148">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="d7e44-148">Data privacy and compliance</span></span>

<span data-ttu-id="d7e44-149">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง AdRoll คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="d7e44-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d7e44-150">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า AdRoll ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="d7e44-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d7e44-151">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="d7e44-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d7e44-152">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="d7e44-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
