---
title: ส่งออกข้อมูล Customer Insights ไปยัง DotDigital
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง DotDigital
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759982"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="7d6ca-103">ส่งออกรายการเซ็กเมนต์ไปยัง DotDigital (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="7d6ca-104">ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยังสมุดที่อยู่ DotDigital และใช้สำหรับการส่งเสริมการขาย การตลาดทางอีเมล และเพื่อสร้างกลุ่มลูกค้าด้วย DotDigital</span><span class="sxs-lookup"><span data-stu-id="7d6ca-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7d6ca-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7d6ca-106">คุณมี [บัญชี DotDigital](https://dotdigital.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="7d6ca-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7d6ca-107">มีสมุดรายชื่อที่มีอยู่ใน DotDigital และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="7d6ca-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="7d6ca-108">คุณสามารถดูรหัสได้ใน URL เมื่อเลือกและเปิดสมุดรายชื่อ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="7d6ca-109">สำหรับข้อมูลเพิ่มเติม โปรดดู [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="7d6ca-110">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="7d6ca-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7d6ca-111">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="7d6ca-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7d6ca-112">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-112">Known limitations</span></span>

- <span data-ttu-id="7d6ca-113">โปรไฟล์ต่อการส่งออกไปยัง DotDigital สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="7d6ca-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="7d6ca-114">การส่งออกไปยัง DotDigital จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="7d6ca-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="7d6ca-115">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมงเนื่องจากข้อจำกัดของผู้ให้บริการ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="7d6ca-116">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง DotDigital นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ DotDigital</span><span class="sxs-lookup"><span data-stu-id="7d6ca-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="7d6ca-117">ตั้งค่าการเชื่อมต่อไปยัง DotDigital</span><span class="sxs-lookup"><span data-stu-id="7d6ca-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="7d6ca-118">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7d6ca-119">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **DotDigital** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="7d6ca-120">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7d6ca-121">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="7d6ca-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7d6ca-122">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7d6ca-123">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="7d6ca-123">Choose who can use this connection.</span></span> <span data-ttu-id="7d6ca-124">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7d6ca-125">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7d6ca-126">ป้อน **ชื่อผู้ใช้และรหัสผ่าน DotDigital** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="7d6ca-127">ป้อน **[รหัสสมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="7d6ca-128">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7d6ca-129">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ DotDigital</span><span class="sxs-lookup"><span data-stu-id="7d6ca-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="7d6ca-130">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7d6ca-131">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="7d6ca-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7d6ca-132">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="7d6ca-132">Configure an export</span></span>

<span data-ttu-id="7d6ca-133">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="7d6ca-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7d6ca-134">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7d6ca-135">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7d6ca-136">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7d6ca-137">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน DotDigital</span><span class="sxs-lookup"><span data-stu-id="7d6ca-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="7d6ca-138">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="7d6ca-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="7d6ca-139">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="7d6ca-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7d6ca-140">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่น ๆ เช่น **ชื่อ**, **นามสกุล**, **ชื่อเต็ม**, **เพศ** และ **รหัสไปรษณีย์**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="7d6ca-141">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="7d6ca-141">Select the segments you want to export.</span></span> <span data-ttu-id="7d6ca-142">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง DotDigital ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="7d6ca-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="7d6ca-143">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="7d6ca-143">Select **Save**.</span></span>

<span data-ttu-id="7d6ca-144">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="7d6ca-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7d6ca-145">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7d6ca-146">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="7d6ca-147">ใน DotDigital คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ใน [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7d6ca-148">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="7d6ca-148">Data privacy and compliance</span></span>

<span data-ttu-id="7d6ca-149">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง DotDigital คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="7d6ca-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7d6ca-150">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า DotDigital ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="7d6ca-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7d6ca-151">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="7d6ca-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7d6ca-152">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="7d6ca-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
