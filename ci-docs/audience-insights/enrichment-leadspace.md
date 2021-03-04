---
title: การเพิ่มข้อมูลโปรไฟล์ของบริษัทด้วยการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269445"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="2dadf-103">การเพิ่มข้อมูลของโปรไฟล์บริษัทด้วย Leadspace (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="2dadf-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="2dadf-104">Leadspace เป็นบริษัทด้านวิทยาศาสตร์ข้อมูลที่ให้แพลตฟอร์มข้อมูลลูกค้า B2B</span><span class="sxs-lookup"><span data-stu-id="2dadf-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="2dadf-105">ซึ่งช่วยให้ลูกค้าที่มีโปรไฟล์ลูกค้าแบบรวมสำหรับบริษัทสามารถเพิ่มข้อมูลของพวกเขาได้</span><span class="sxs-lookup"><span data-stu-id="2dadf-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="2dadf-106">การเพิ่มข้อมูลรวมถึงคุณลักษณะเพิ่มเติม เช่น ขนาดบริษัท สถานที่ตั้ง อุตสาหกรรม และอีกมากมาย</span><span class="sxs-lookup"><span data-stu-id="2dadf-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2dadf-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="2dadf-107">Prerequisites</span></span>

<span data-ttu-id="2dadf-108">เมื่อต้องการตั้งค่าคอนฟิก Leadspace คุณต้องทำตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="2dadf-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2dadf-109">คุณมีสิทธิ์การใช้งาน Leadspace ที่ใช้งานอยู่และ "คีย์ถาวร" (เรียกว่า **โทเค็น Leadspace**)</span><span class="sxs-lookup"><span data-stu-id="2dadf-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="2dadf-110">ติดต่อโดยตรง [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) สำหรับรายละเอียดเกี่ยวกับผลิตภัณฑ์ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="2dadf-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="2dadf-111">คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)</span><span class="sxs-lookup"><span data-stu-id="2dadf-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="2dadf-112">คุณมี [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md) สำหรับบริษัท</span><span class="sxs-lookup"><span data-stu-id="2dadf-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="2dadf-113">การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="2dadf-113">Configuration</span></span>

1. <span data-ttu-id="2dadf-114">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="2dadf-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2dadf-115">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ Leadspace</span><span class="sxs-lookup"><span data-stu-id="2dadf-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="ภาพหน้าจอของไทล์ Leadspace":::

1. <span data-ttu-id="2dadf-117">เลือก **เริ่มต้นใช้งาน** จากนั้นป้อน **โทเค็น Leadspace** (คีย์ถาวร) ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="2dadf-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="2dadf-118">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="2dadf-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="2dadf-119">ยืนยันการป้อนข้อมูลทั้งคู่โดยการเลือก **เชื่อมต่อกับ Leadspace**</span><span class="sxs-lookup"><span data-stu-id="2dadf-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="2dadf-120">เลือก **แม็ปข้อมูล** และเลือกชุดข้อมูลที่คุณต้องการเพิ่มข้อมูลบริษัทจาก Leadspace</span><span class="sxs-lookup"><span data-stu-id="2dadf-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="2dadf-121">คุณสามารถเลือกเอนทิตี *ลูกค้า* เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="2dadf-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="เลือกระหว่างโปรไฟล์ลูกค้าและการเพิ่มเซ็กเมนต์":::

1. <span data-ttu-id="2dadf-123">คลิก **ถัดไป** และกำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ควรถูกใช้เพื่อค้นหาข้อมูลบริษัทที่ตรงกันจาก Leadspace</span><span class="sxs-lookup"><span data-stu-id="2dadf-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="2dadf-124">ต้องระบุฟิลด์ **ชื่อของบริษัท**</span><span class="sxs-lookup"><span data-stu-id="2dadf-124">The **Name of company** field is required.</span></span> <span data-ttu-id="2dadf-125">เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถได้อีกสองฟิลด์ **เว็บไซต์ของบริษัท** และ **ตำแหน่งที่ตั้งบริษัท**</span><span class="sxs-lookup"><span data-stu-id="2dadf-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="บานหน้าต่างการแมปฟิลด์ Leadspace":::
   
1. <span data-ttu-id="2dadf-127">เลือก **นำไปใช้** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="2dadf-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="2dadf-128">เลือก **รัน** เพื่อเพิ่มข้อมูลโปรไฟล์บริษัท</span><span class="sxs-lookup"><span data-stu-id="2dadf-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="2dadf-129">การเพิ่มข้อมูลจะใช้เวลานานแค่ไหนขึ้นอยู่กับจำนวนของโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="2dadf-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2dadf-130">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2dadf-130">Enrichment results</span></span>

<span data-ttu-id="2dadf-131">หลังจากรีเฟรชการเพิ่มข้อมูล คุณสามารถตรวจสอบข้อมูลบริษัทที่ปรับปรุงใหม่ได้ภายใต้ [การเพิ่มข้อมูลของฉัน](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="2dadf-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="2dadf-132">คุณสามารถค้นหาเวลาของการปรับปรุงครั้งล่าสุดและจำนวนของโปรไฟล์ที่มีการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2dadf-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2dadf-133">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="2dadf-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="2dadf-134">สำหรับข้อมูลเพิ่มเติม ดูที่ [APIs ของ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API)</span><span class="sxs-lookup"><span data-stu-id="2dadf-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2dadf-135">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="2dadf-135">Next steps</span></span>

<span data-ttu-id="2dadf-136">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="2dadf-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2dadf-137">สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="2dadf-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2dadf-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="2dadf-138">Data privacy and compliance</span></span>

<span data-ttu-id="2dadf-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Leadspace คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="2dadf-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2dadf-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Leadspace ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="2dadf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2dadf-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="2dadf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2dadf-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="2dadf-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]