---
title: ส่งออกข้อมูล Customer Insights ไปยัง DotDigital
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ DotDigital
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269123"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="20bd2-103">ตัวเชื่อมต่อสำหรับ DotDigital (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="20bd2-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="20bd2-104">ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยังสมุดที่อยู่ DotDigital และใช้สำหรับการส่งเสริมการขาย การตลาดทางอีเมล และเพื่อสร้างกลุ่มลูกค้าด้วย DotDigital</span><span class="sxs-lookup"><span data-stu-id="20bd2-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="20bd2-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="20bd2-105">Prerequisites</span></span>

-   <span data-ttu-id="20bd2-106">คุณมี [บัญชี DotDigital](https://dotdigital.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="20bd2-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="20bd2-107">มีสมุดรายชื่อที่มีอยู่ใน DotDigital และรหัสที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="20bd2-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="20bd2-108">คุณสามารถดูรหัสได้ใน URL เมื่อเลือกและเปิดสมุดรายชื่อ</span><span class="sxs-lookup"><span data-stu-id="20bd2-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="20bd2-109">สำหรับข้อมูลเพิ่มเติม โปรดดู [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)</span><span class="sxs-lookup"><span data-stu-id="20bd2-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="20bd2-110">คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="20bd2-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="20bd2-111">โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล</span><span class="sxs-lookup"><span data-stu-id="20bd2-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="20bd2-112">เชื่อมต่อกับ DotDigital</span><span class="sxs-lookup"><span data-stu-id="20bd2-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="20bd2-113">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="20bd2-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="20bd2-114">ภายใต้ **DotDigital** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="20bd2-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="20bd2-115">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="20bd2-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="บานหน้าต่างการกำหนดค่าสำหรับการส่งออก DotDigital":::

1. <span data-ttu-id="20bd2-117">ป้อน **ชื่อผู้ใช้และรหัสผ่าน DotDigital** ของคุณ</span><span class="sxs-lookup"><span data-stu-id="20bd2-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="20bd2-118">ป้อน **[รหัสสมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**</span><span class="sxs-lookup"><span data-stu-id="20bd2-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="20bd2-119">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="20bd2-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="20bd2-120">เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ DotDigital</span><span class="sxs-lookup"><span data-stu-id="20bd2-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="20bd2-121">เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="20bd2-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="20bd2-122">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="20bd2-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="20bd2-123">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="20bd2-123">Configure the connector</span></span>

1. <span data-ttu-id="20bd2-124">ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="20bd2-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="20bd2-125">ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่น ๆ เช่น **ชื่อ**, **นามสกุล**, **ชื่อเต็ม**, **เพศ** และ **รหัสไปรษณีย์**</span><span class="sxs-lookup"><span data-stu-id="20bd2-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="20bd2-126">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="20bd2-126">Select the segments you want to export.</span></span> <span data-ttu-id="20bd2-127">คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง DotDigital ได้มากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="20bd2-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="20bd2-128">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="20bd2-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="20bd2-129">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="20bd2-129">Export the data</span></span>

<span data-ttu-id="20bd2-130">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="20bd2-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="20bd2-131">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="20bd2-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20bd2-132">ใน DotDigital คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ใน [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)</span><span class="sxs-lookup"><span data-stu-id="20bd2-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="20bd2-133">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="20bd2-133">Known limitations</span></span>

- <span data-ttu-id="20bd2-134">โปรไฟล์ต่อการส่งออกไปยัง DotDigital สูงสุด 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="20bd2-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="20bd2-135">การส่งออกไปยัง DotDigital จำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="20bd2-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="20bd2-136">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมงเนื่องจากข้อจำกัดของผู้ให้บริการ</span><span class="sxs-lookup"><span data-stu-id="20bd2-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="20bd2-137">จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง DotDigital นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ DotDigital</span><span class="sxs-lookup"><span data-stu-id="20bd2-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="20bd2-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="20bd2-138">Data privacy and compliance</span></span>

<span data-ttu-id="20bd2-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง DotDigital คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="20bd2-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="20bd2-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า DotDigital ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="20bd2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="20bd2-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="20bd2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="20bd2-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="20bd2-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]