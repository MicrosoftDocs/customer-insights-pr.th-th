---
title: การเพิ่มความสมบูรณ์ของการปรับปรุงที่อยู่
description: เพิ่มและกำหนดมาตรฐานข้อมูลที่อยู่ของโปรไฟล์ลูกค้าด้วยโมเดลของ Microsoft
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305455"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="216e8-103">การเพิ่มความสมบูรณ์ของโปรไฟล์ลูกค้าด้วยที่อยู่ที่ปรับปรุงแล้ว</span><span class="sxs-lookup"><span data-stu-id="216e8-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="216e8-104">ที่อยู่ในข้อมูลของคุณอาจไม่มีโครงสร้าง ไม่สมบูรณ์ หรือไม่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="216e8-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="216e8-105">ใช้โมเดลของ Microsoft เพื่อกำหนดมาตรฐานและเพิ่มที่อยู่ของคุณลงใน [รูปแบบ Common Data Model](/common-data-model/schema/core/applicationcommon/address) เพื่อความแม่นยำและข้อมูลเชิงลึกที่ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="216e8-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="216e8-106">เราปรับปรุงที่อยู่อย่างไร</span><span class="sxs-lookup"><span data-stu-id="216e8-106">How we enhance addresses</span></span>

<span data-ttu-id="216e8-107">โมเดลของเราผ่านกระบวนการสองขั้นตอนเพื่อปรับปรุงที่อยู่</span><span class="sxs-lookup"><span data-stu-id="216e8-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="216e8-108">ขั้นแรก จะแยกวิเคราะห์ที่อยู่เพื่อระบุส่วนประกอบและทำให้อยู่ในรูปแบบที่มีโครงสร้าง</span><span class="sxs-lookup"><span data-stu-id="216e8-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="216e8-109">จากนั้น เราใช้ AI เพื่อแก้ไข ทำให้สมบูรณ์ และทำให้ค่าในที่อยู่เป็นมาตรฐาน</span><span class="sxs-lookup"><span data-stu-id="216e8-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="216e8-110">ตัว อย่าง เช่น</span><span class="sxs-lookup"><span data-stu-id="216e8-110">Example</span></span>

<span data-ttu-id="216e8-111">ข้อมูลที่อยู่อาจอยู่ในรูปแบบที่ไม่เป็นมาตรฐานและมีข้อผิดพลาดในการสะกดคำ</span><span class="sxs-lookup"><span data-stu-id="216e8-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="216e8-112">โมเดลสามารถแก้ไขปัญหาเหล่านี้และสร้างที่อยู่ที่สอดคล้องกันในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="216e8-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="216e8-113">ข้อจำกัด</span><span class="sxs-lookup"><span data-stu-id="216e8-113">Limitations</span></span>

<span data-ttu-id="216e8-114">ที่อยู่ที่ปรับปรุงแล้วจะใช้ได้เฉพาะกับค่าที่มีอยู่แล้วในข้อมูลที่อยู่ที่นำเข้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="216e8-115">โมเดลจะไม่:</span><span class="sxs-lookup"><span data-stu-id="216e8-115">The model doesn't:</span></span> 

1. <span data-ttu-id="216e8-116">ตรวจสอบว่าที่อยู่เป็นที่อยู่ที่ถูกต้องหรือไม่</span><span class="sxs-lookup"><span data-stu-id="216e8-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="216e8-117">ตรวจสอบว่าค่าใดๆ เช่น รหัสไปรษณี ย์หรือชื่อถนน ถูกต้องหรือไม่</span><span class="sxs-lookup"><span data-stu-id="216e8-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="216e8-118">เปลี่ยนค่าที่ไม่รู้จัก</span><span class="sxs-lookup"><span data-stu-id="216e8-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="216e8-119">โมเดลนี้ใช้เทคนิคที่ใช้การเรียนรู้เกี่ยวกับเครื่องเพื่อปรับปรุงที่อยู่</span><span class="sxs-lookup"><span data-stu-id="216e8-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="216e8-120">แม้ว่าเราจะใช้เกณฑ์ความเชื่อมั่นสูงเมื่อแบบจำลองเปลี่ยนค่าที่ป้อน เช่นเดียวกับโมเดลที่ใช้การเรียนรู้เกี่ยวกับเครื่อง แต่ไม่รับประกันความถูกต้อง 100 เปอร์เซ็นต์</span><span class="sxs-lookup"><span data-stu-id="216e8-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="216e8-121">ประเทศหรือภูมิภาคที่รองรับ</span><span class="sxs-lookup"><span data-stu-id="216e8-121">Supported countries or regions</span></span>

<span data-ttu-id="216e8-122">ขณะนี้เราสนับสนุนการเพิ่มความสมบูรณ์ของที่อยู่ในประเทศหรือภูมิภาคเหล่านี้:</span><span class="sxs-lookup"><span data-stu-id="216e8-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="216e8-123">ออสเตรเลีย</span><span class="sxs-lookup"><span data-stu-id="216e8-123">Australia</span></span>
- <span data-ttu-id="216e8-124">แคนาดา</span><span class="sxs-lookup"><span data-stu-id="216e8-124">Canada</span></span>
- <span data-ttu-id="216e8-125">สหราชอาณาจักร</span><span class="sxs-lookup"><span data-stu-id="216e8-125">United Kingdom</span></span>
- <span data-ttu-id="216e8-126">สหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="216e8-126">United States</span></span>

<span data-ttu-id="216e8-127">ที่อยู่ต้องมีค่าประเทศ/ภูมิภาค</span><span class="sxs-lookup"><span data-stu-id="216e8-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="216e8-128">เราไม่ประมวลผลที่อยู่สำหรับประเทศหรือภูมิภาคที่ไม่มีการรองรับ และที่อยู่ที่ไม่มีประเทศหรือภูมิภาคให้</span><span class="sxs-lookup"><span data-stu-id="216e8-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="216e8-129">กำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="216e8-129">Configure the enrichment</span></span>

1. <span data-ttu-id="216e8-130">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="216e8-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="216e8-131">เลือก **เพิ่มความสมบูรณ์ข้อมูลของฉัน** บนไทล์ **ที่อยู่ที่ปรับปรุงแล้ว**</span><span class="sxs-lookup"><span data-stu-id="216e8-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="ภาพหน้าจอของไทล์ที่อยู่ที่ปรับปรุงแล้ว":::

1. <span data-ttu-id="216e8-133">เลือก **ชุดข้อมูลลูกค้า** และเลือกเอนทิตีที่มีที่อยู่ที่คุณต้องการเพิ่มความสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="216e8-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="216e8-134">คุณสามารถเลือกเอนทิตี *ลูกค้า* เพื่อเพิ่มที่อยู่ในโปรไฟล์ลูกค้าทั้งหมดของคุณ หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มความสมบูรณ์ของที่อยู่เฉพาะในโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="216e8-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="216e8-135">เลือกวิธีการจัดรูปแบบที่อยู่ในชุดข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="216e8-136">เลือก **ที่อยู่แบบแอตทริบิวต์เดียว** หากที่อยู่ในข้อมูลของคุณใช้ฟิลด์เดียว</span><span class="sxs-lookup"><span data-stu-id="216e8-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="216e8-137">เลือก **ที่อยู่แบบหลายแอตทริบิวต์** หากที่อยู่ในข้อมูลของคุณใช้ฟิลด์ข้อมูลมากกว่าหนึ่งฟิลดื</span><span class="sxs-lookup"><span data-stu-id="216e8-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="216e8-138">ประเทศ/ภูมิภาคเป็นแบบบังคับทั้งในที่อยู่แบบแอตทริบิวต์เดียวและแบบหลายแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="216e8-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="216e8-139">ที่อยู่ที่ไม่มีค่าประเทศ/ภูมิภาคที่ถูกต้องหรือที่ได้รับการสนับสนุน จะไม่ถูกเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="216e8-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="216e8-140">แม็ปฟิลด์ที่อยู่จากเอนทิตีลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="หน้าการแม็ปฟิลด์ที่อยู่ที่ปรับปรุงแล้ว":::

1. <span data-ttu-id="216e8-142">ให้เลือก **ถัดไป** เพื่อทำการแม็ปฟิลด์ให้เสร็จ</span><span class="sxs-lookup"><span data-stu-id="216e8-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="216e8-143">ระบุชื่อสำหรับการเพิ่มความสมบูรณ์และเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="216e8-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="216e8-144">เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="216e8-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="216e8-145">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="216e8-145">Enrichment results</span></span>

<span data-ttu-id="216e8-146">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="216e8-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="216e8-147">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="216e8-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="216e8-148">เวลาในการประมวลผลขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="216e8-149">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="216e8-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="216e8-150">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="216e8-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="216e8-151">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="216e8-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="216e8-152">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="216e8-152">Next steps</span></span>

<span data-ttu-id="216e8-153">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="216e8-154">สร้าง [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) และแม้แต่ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่ปรับให้เป็นแบบส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="216e8-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
