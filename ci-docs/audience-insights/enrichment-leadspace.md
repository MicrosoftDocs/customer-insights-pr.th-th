---
title: การเพิ่มข้อมูลโปรไฟล์ของบริษัทด้วยการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305225"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="200e7-103">การเพิ่มข้อมูลของโปรไฟล์บริษัทด้วย Leadspace (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="200e7-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="200e7-104">Leadspace เป็นบริษัทด้านวิทยาศาสตร์ข้อมูลที่ให้แพลตฟอร์มข้อมูลลูกค้า B2B</span><span class="sxs-lookup"><span data-stu-id="200e7-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="200e7-105">ซึ่งช่วยให้ลูกค้าที่มีโปรไฟล์ลูกค้าแบบรวมสำหรับบริษัทสามารถเพิ่มข้อมูลของพวกเขาได้</span><span class="sxs-lookup"><span data-stu-id="200e7-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="200e7-106">การเพิ่มข้อมูลรวมถึงแอตทริบิวต์ต่าง ๆ เช่น ขนาดบริษัท ตำแหน่งที่ตั้ง อุตสาหกรรม และอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="200e7-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="200e7-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="200e7-107">Prerequisites</span></span>

<span data-ttu-id="200e7-108">เมื่อต้องการตั้งค่าคอนฟิก Leadspace คุณต้องทำตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="200e7-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="200e7-109">คุณมีสิทธิ์การใช้งาน Leadspace ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="200e7-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="200e7-110">คุณมี [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md) สำหรับบริษัท</span><span class="sxs-lookup"><span data-stu-id="200e7-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="200e7-111">การเชื่อมต่อ Leadspace ได้รับการกำหนดค่าแล้วโดยผู้ดูแลระบบหรือคุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator) และ "คีย์ถาวร" (เรียกว่า **โทเค็น Leadspace**)</span><span class="sxs-lookup"><span data-stu-id="200e7-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="200e7-112">ติดต่อ [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) โดยตรงสำหรับรายละเอียดเกี่ยวกับผลิตภัณฑ์ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="200e7-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="200e7-113">กำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="200e7-113">Configure the enrichment</span></span>

1. <span data-ttu-id="200e7-114">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="200e7-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="200e7-115">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ Leadspace แล้วเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="200e7-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="ภาพหน้าจอของไทล์ Leadspace":::

1. <span data-ttu-id="200e7-117">เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="200e7-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="200e7-118">ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="200e7-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="200e7-119">หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อโดยเลือก **เพิ่มการเชื่อมต่อ** และการเลือก **Leadspace**</span><span class="sxs-lookup"><span data-stu-id="200e7-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="200e7-120">เลือก **เชื่อมต่อกับ Leadspace** เพื่อยืนยันการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="200e7-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="200e7-121">เลือก **ต่อไป** และเลือก **ชุดข้อมูลลูกค้า** ที่คุณต้องการเพิ่มข้อมูลด้วยข้อมูลบริษัทจาก Leadspace</span><span class="sxs-lookup"><span data-stu-id="200e7-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="200e7-122">คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="200e7-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. <span data-ttu-id="200e7-124">เลือก **ต่อไป** และกำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ใช้เพื่อค้นหาข้อมูลบริษัทที่ตรงกันจาก Leadspace</span><span class="sxs-lookup"><span data-stu-id="200e7-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="200e7-125">ต้องระบุฟิลด์ **ชื่อของบริษัท**</span><span class="sxs-lookup"><span data-stu-id="200e7-125">The **Name of company** field is required.</span></span> <span data-ttu-id="200e7-126">เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถได้อีกสองฟิลด์ **เว็บไซต์ของบริษัท** และ **ตำแหน่งที่ตั้งบริษัท**</span><span class="sxs-lookup"><span data-stu-id="200e7-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="บานหน้าต่างการแมปฟิลด์ Leadspace":::

1. <span data-ttu-id="200e7-128">ให้เลือก **ถัดไป** เพื่อทำการแม็ปฟิลด์ให้เสร็จ</span><span class="sxs-lookup"><span data-stu-id="200e7-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="200e7-129">ระบุชื่อสำหรับการเพิ่มข้อมูลและเลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="200e7-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="200e7-130">กำหนดค่าการเชื่อมต่อสำหรับ Leadspace</span><span class="sxs-lookup"><span data-stu-id="200e7-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="200e7-131">คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="200e7-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="200e7-132">เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มข้อมูล *หรือ* ไปที่ **การจัดการ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Leadspace</span><span class="sxs-lookup"><span data-stu-id="200e7-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="200e7-133">เลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="200e7-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="200e7-134">ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="200e7-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="200e7-135">ระบุโทเค็นของ Leadspace ที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="200e7-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="200e7-136">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** โดยการเลือก **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="200e7-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="200e7-137">เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="200e7-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="200e7-138">หลังจากเสร็จสิ้นการตรวจสอบแล้ว ให้เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="200e7-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อสำหรับ Leadspace":::

## <a name="enrichment-results"></a><span data-ttu-id="200e7-140">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="200e7-140">Enrichment results</span></span>

<span data-ttu-id="200e7-141">หลังจากรีเฟรชการเพิ่มข้อมูล คุณสามารถตรวจสอบข้อมูลบริษัทที่ปรับปรุงใหม่ได้ภายใต้ [การเพิ่มข้อมูลของฉัน](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="200e7-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="200e7-142">คุณสามารถค้นหาเวลาของการปรับปรุงครั้งล่าสุดและจำนวนของโปรไฟล์ที่มีการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="200e7-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="200e7-143">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="200e7-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="200e7-144">สำหรับข้อมูลเพิ่มเติม ดูที่ [APIs ของ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API)</span><span class="sxs-lookup"><span data-stu-id="200e7-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="200e7-145">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="200e7-145">Next steps</span></span>

<span data-ttu-id="200e7-146">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="200e7-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="200e7-147">สร้าง [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) และแม้แต่ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่ปรับให้เป็นแบบส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="200e7-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="200e7-148">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="200e7-148">Data privacy and compliance</span></span>

<span data-ttu-id="200e7-149">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Leadspace คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="200e7-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="200e7-150">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Leadspace ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="200e7-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="200e7-151">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="200e7-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="200e7-152">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="200e7-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
