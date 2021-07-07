---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยข้อมูลจาก Microsoft
description: ใช้ข้อมูลที่เป็นกรรมสิทธิ์จาก Microsoft เพื่อเพิ่มข้อมูลลูกค้าของคุณด้วยแบรนด์และความสนใจ
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305179"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="3c287-103">เพิ่มข้อมูลโปรไฟล์ลูกค้าที่มีแบรนด์และความเกี่ยวข้องของความสนใจ (ดูตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="3c287-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="3c287-104">ใช้ข้อมูลที่เป็นกรรมสิทธิ์จาก Microsoft เพื่อเพิ่มข้อมูลลูกค้าของคุณด้วยแบรนด์และความสนใจ</span><span class="sxs-lookup"><span data-stu-id="3c287-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="3c287-105">ความเกี่ยวข้องเหล่านี้ยึดตามข้อมูลจากผู้คนที่มีข้อมูลประชากรที่คล้ายคลึงกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="3c287-106">ข้อมูลนี้ช่วยให้คุณเข้าใจและจัดเซ็กเมนต์ลูกค้าของคุณได้ดีขึ้น โดยพิจารณาจากความเกี่ยวข้องของพวกเขากับแบรนด์และความสนใจเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="3c287-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="3c287-107">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** เพื่อ [ตั้งค่าคอนฟิกและดูการเพิ่มข้อมูล](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="3c287-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="3c287-108">หากต้องการตั้งค่าคอนฟิกการเพิ่มข้อมูลความเกี่ยวข้องของแบรนด์ ให้ไปที่แท็บ **ค้นพบ** และเลือก **เพิ่มข้อมูลของฉัน** บนไทล์ **แบรนด์**</span><span class="sxs-lookup"><span data-stu-id="3c287-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="3c287-109">หากต้องการตั้งค่าคอนฟิกการเพิ่มข้อมูลความเกี่ยวข้องของความสนใจ ให้ไปที่แท็บ **ค้นพบ** และเลือก **เพิ่มข้อมูลของฉัน** บนไทล์ **ความสนใจ**</span><span class="sxs-lookup"><span data-stu-id="3c287-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c287-110">![ไทล์แบรนด์และความสนใจ](media/BrandsInterest-tile-Hub.png "ไทล์แบรนด์และความสนใจ")</span><span class="sxs-lookup"><span data-stu-id="3c287-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="3c287-111">วิธีที่เราพิจารณาความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="3c287-111">How we determine affinities</span></span>

<span data-ttu-id="3c287-112">เราใช้ข้อมูลการค้นหาออนไลน์ของ Microsoft เพื่อค้นหาความสนใจสำหรับแบรนด์และความสนใจในกลุ่มประชากรต่าง ๆ (กำหนดตามอายุ เพศ หรือสถานที่ตั้ง)</span><span class="sxs-lookup"><span data-stu-id="3c287-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="3c287-113">ปริมาณการค้นหาออนไลน์สำหรับแบรนด์หรือความสนใจจะกำหนดว่าเซ็กเมนต์ข้อมูลประชากรสัมพันธ์กันมากน้อยเพียงใดเมื่อเปรียบเทียบกับเซ็กเมนต์อื่นๆ ที่มีต่อแบรนด์หรือความสนใจนั้น</span><span class="sxs-lookup"><span data-stu-id="3c287-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="3c287-114">ระดับและคะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-114">Affinity level and score</span></span>

<span data-ttu-id="3c287-115">ในทุกโปรไฟล์ของลูกค้าที่ได้รับการเพิ่มข้อมูล เรามีค่าที่เกี่ยวข้องสองค่า: ระดับความเกี่ยวข้อง และคะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="3c287-116">ค่าเหล่านี้ช่วยคุณในการพิจารณาปริมาณความเกี่ยวข้องที่มีสำหรับเซ็กเมนต์ประชากรของโปรไฟล์นั้น สำหรับแบรนด์หรือความสนใจ เมื่อเทียบกับเซ็กเมนต์ประชากรอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="3c287-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="3c287-117">*ระดับความเกี่ยวข้อง* ประกอบด้วยสี่ระดับและ *คะแนนความสัมพันธ์* ถูกคำนวณในระดับ 100 จุดที่จับคู่กับระดับความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="3c287-118">ระดับความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-118">Affinity level</span></span> |<span data-ttu-id="3c287-119">คะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="3c287-120">สูงมาก</span><span class="sxs-lookup"><span data-stu-id="3c287-120">Very high</span></span>     | <span data-ttu-id="3c287-121">85-100</span><span class="sxs-lookup"><span data-stu-id="3c287-121">85-100</span></span>       |
|<span data-ttu-id="3c287-122">สูง</span><span class="sxs-lookup"><span data-stu-id="3c287-122">High</span></span>     | <span data-ttu-id="3c287-123">70-84</span><span class="sxs-lookup"><span data-stu-id="3c287-123">70-84</span></span>        |
|<span data-ttu-id="3c287-124">ขนาดปานกลาง</span><span class="sxs-lookup"><span data-stu-id="3c287-124">Medium</span></span>     | <span data-ttu-id="3c287-125">35-69</span><span class="sxs-lookup"><span data-stu-id="3c287-125">35-69</span></span>        |
|<span data-ttu-id="3c287-126">ตํ่า</span><span class="sxs-lookup"><span data-stu-id="3c287-126">Low</span></span>     | <span data-ttu-id="3c287-127">1-34</span><span class="sxs-lookup"><span data-stu-id="3c287-127">1-34</span></span>        |

<span data-ttu-id="3c287-128">โดยขึ้นอยู่กับรายละเอียดที่คุณต้องการสำหรับการวัดความเกี่ยวข้อง คุณสามารถใช้ระดับหรือคะแนนความเกี่ยวข้องก็ได้</span><span class="sxs-lookup"><span data-stu-id="3c287-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="3c287-129">คะแนนความเกี่ยวข้องช่วยให้คุณควบคุมได้แม่นยำยิ่งขึ้น</span><span class="sxs-lookup"><span data-stu-id="3c287-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3c287-130">ประเทศ/ภูมิภาคที่รองรับ</span><span class="sxs-lookup"><span data-stu-id="3c287-130">Supported countries/regions</span></span>

<span data-ttu-id="3c287-131">ขณะนี้เรารองรับตัวเลือกประเทศ/ภูมิภาคต่อไปนี้: ออสเตรเลีย แคนาดา (อังกฤษ) ฝรั่งเศส เยอรมนี สหราชอาณาจักร หรือสหรัฐอเมริกา (อังกฤษ)</span><span class="sxs-lookup"><span data-stu-id="3c287-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="3c287-132">ในการเลือกประเทศหรือภูมิภาค ให้เปิด **การเพิ่มข้อมูลแบรนด์** หรือ **การเพิ่มข้อมูลความสนใจ** และเลือก **เปลี่ยน** ถัดจาก **ประเทศ/ภูมิภาค**</span><span class="sxs-lookup"><span data-stu-id="3c287-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="3c287-133">ในบานหน้าต่าง **การตั้งค่าประเทศ/ภูมิภาค** เลือกตัวเลือก และเลือก **นำไปใช้**</span><span class="sxs-lookup"><span data-stu-id="3c287-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="3c287-134">ผลกระทบที่เกี่ยวข้องกับการเลือกประเทศ</span><span class="sxs-lookup"><span data-stu-id="3c287-134">Implications related to country selection</span></span>

- <span data-ttu-id="3c287-135">เมื่อ [เลือกแบรนด์ของคุณเอง](#define-your-brands-or-interests) ระบบจะให้คำแนะนำตามประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="3c287-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="3c287-136">เมื่อ [เลือกอุตสาหกรรม](#define-your-brands-or-interests) คุณจะได้รับแบรนด์หรือความสนใจที่เกี่ยวข้องมากที่สุดตามประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="3c287-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="3c287-137">เมื่อ [เพิ่มข้อมูลโปรไฟล์](#refresh-enrichment) เราจะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดที่เราได้รับข้อมูลสำหรับแบรนด์และความสนใจที่เลือก ซึ่งรวมถึงโปรไฟล์ที่ไม่ได้อยู่ในประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="3c287-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="3c287-138">ตัวอย่างเช่น หากคุณเลือกเยอรมนี เราจะเพิ่มโปรไฟล์ที่ตั้งอยู่ในสหรัฐอเมริกา หากเรามีข้อมูลสำหรับแบรนด์และความสนใจที่เลือกในสหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="3c287-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="3c287-139">ตั้งค่าคอนฟิกการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-139">Configure enrichment</span></span>

<span data-ttu-id="3c287-140">ประสบการณ์ที่แนะนำจะช่วยคุณในการกำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="3c287-141">กำหนดแบรนด์หรือความสนใจของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-141">Define your brands or interests</span></span>

<span data-ttu-id="3c287-142">เลือกแบรนด์หรือความสนใจสูงสุดห้ารายการโดยใช้ตัวเลือกใดตัวเลือกหนึ่งหรือทั้งสองตัวเลือกต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="3c287-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="3c287-143">**อุตสาหกรรม**: เลือกอุตสาหกรรมของคุณจากรายการแบบหล่นลง แล้วจากนั้น เลือกจากแบรนด์หรือความสนใจอันดับต้นๆ สำหรับอุตสาหกรรมนั้น</span><span class="sxs-lookup"><span data-stu-id="3c287-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="3c287-144">**เลือกของคุณเอง**: ป้อนแบรนด์หรือความสนใจที่เกี่ยวข้องกับองค์กรของคุณ และจากนั้น เลือกจากคำแนะนำที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="3c287-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="3c287-145">หากเราไม่แสดงแบรนด์หรือความสนใจที่คุณต้องการ โปรดส่งข้อเสนอแนะถึงเราโดยใช้ลิงก์ **แนะนำ**</span><span class="sxs-lookup"><span data-stu-id="3c287-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="3c287-146">รีวิวการกำหนดลักษณะการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-146">Review enrichment preferences</span></span>

<span data-ttu-id="3c287-147">รีวิวการกำหนดลักษณะการเพิ่มข้อมูลเริ่มต้นของคุณ และอัปเดตตามต้องการ</span><span class="sxs-lookup"><span data-stu-id="3c287-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="ภาพหน้าจอของหน้าต่างการกำหนดลักษณะการเพิ่มข้อมูล":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="3c287-149">เลือกเอนทิตีเพื่อเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-149">Select entity to enrich</span></span>

<span data-ttu-id="3c287-150">เลือก **เอนทิตีที่เพิ่มข้อมูลแล้ว** และเลือกชุดข้อมูลที่คุณต้องการเพิ่มข้อมูลด้วยข้อมูลบริษัทจาก Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c287-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="3c287-151">คุณสามารถเลือกเอนทิตีลูกค้าเพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="3c287-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="3c287-152">แม็ปฟิลด์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-152">Map your fields</span></span>

<span data-ttu-id="3c287-153">แม็ปฟิลด์จากเอนทิตีลูกค้าแบบรวมของคุณเพื่อกำหนดเซ็กเมนต์ประชากรที่คุณต้องการให้ระบบใช้สำหรับการเพิ่มข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="3c287-154">แม็ปประเทศ/ภูมิภาค และแอตทริบิวต์วันเดือนปีเกิดหรือเพศ เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="3c287-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="3c287-155">นอกจากนี้ คุณต้องแม็ปหนึ่งในเมือง (และรัฐ/จังหวัด) หรือรหัสไปรษณีย์ เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="3c287-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="3c287-156">เลือก **แก้ไข** เพื่อกำหนดการแม็ปของฟิลด์ และเลือก **นำไปใช้** เมื่อคุณทำเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="3c287-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="3c287-157">เลือก **บันทึก** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="3c287-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="3c287-158">รองรับรูปแบบและค่าต่อไปนี้ (ค่าไม่ต้องตรงตามตัวพิมพ์ใหญ่-เล็ก):</span><span class="sxs-lookup"><span data-stu-id="3c287-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="3c287-159">**วันเกิด**: เราขอแนะนำให้แปลงวันเกิดเป็นประเภท DateTime ระหว่างการนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="3c287-160">หรืออาจเป็นสตริงในรูปแบบ [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" หรือ "yyyy-MM-ddTHH:mm:ss"</span><span class="sxs-lookup"><span data-stu-id="3c287-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="3c287-161">**เพศ**: ชาย หญิง ไม่ทราบ</span><span class="sxs-lookup"><span data-stu-id="3c287-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="3c287-162">**รหัสไปรษณีย์**: รหัสไปรษณีย์ห้าหลักสำหรับสหรัฐอเมริกา รหัสไปรษณีย์มาตรฐานที่อื่นทุกที่</span><span class="sxs-lookup"><span data-stu-id="3c287-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="3c287-163">**เมือง**: ชื่อเมืองเป็นภาษาอังกฤษ</span><span class="sxs-lookup"><span data-stu-id="3c287-163">**City**: City name in English.</span></span>
- <span data-ttu-id="3c287-164">**รัฐ/จังหวัด**: ตัวย่อสองตัวอักษรสำหรับสหรัฐอเมริกาและแคนาดา</span><span class="sxs-lookup"><span data-stu-id="3c287-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="3c287-165">อักษรย่อสองหรือสามตัวสำหรับออสเตรเลีย</span><span class="sxs-lookup"><span data-stu-id="3c287-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="3c287-166">ไม่สามารถใช้ได้กับฝรั่งเศส เยอรมนี หรือสหราชอาณาจักร</span><span class="sxs-lookup"><span data-stu-id="3c287-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="3c287-167">**ประเทศ/ภูมิภาค**:</span><span class="sxs-lookup"><span data-stu-id="3c287-167">**Country/Region**:</span></span>

  - <span data-ttu-id="3c287-168">สหรัฐอเมริกา: United States of America, United States, USA, US, America</span><span class="sxs-lookup"><span data-stu-id="3c287-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="3c287-169">CA: แคนาดา CA</span><span class="sxs-lookup"><span data-stu-id="3c287-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="3c287-170">GB: สหราชอาณาจักร บริเตนใหญ่ GB สหราชอาณาจักรบริเตนใหญ่และไอร์แลนด์เหนือ สหราชอาณาจักรบริเตนใหญ่</span><span class="sxs-lookup"><span data-stu-id="3c287-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="3c287-171">AU: ออสเตรเลีย, AU, เครือจักรภพออสเตรเลีย</span><span class="sxs-lookup"><span data-stu-id="3c287-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="3c287-172">ฝรั่งเศส: ฝรั่งเศส FR</span><span class="sxs-lookup"><span data-stu-id="3c287-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="3c287-173">DE: เยอรมณี DE สหพันธ์สาธารณรัฐเยอรมนี สาธารณรัฐเยอรมนี</span><span class="sxs-lookup"><span data-stu-id="3c287-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="3c287-174">ตรวจสอบและตั้งชื่อการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-174">Review and name the enrichment</span></span>

<span data-ttu-id="3c287-175">สุดท้าย คุณจะได้รับการตรวจสอบข้อมูลและระบุชื่อสำหรับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="หน้าตรวจสอบความสนใจและการตั้งชื่อ":::

## <a name="refresh-enrichment"></a><span data-ttu-id="3c287-177">รีเฟรชการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-177">Refresh enrichment</span></span>

<span data-ttu-id="3c287-178">เรียกใช้การเพิ่มประสิทธิภาพหลังจากกำหนดค่าแบรนด์ ความสนใจ และการแมปฟิลด์สำหรับข้อมูลด้านประชากร</span><span class="sxs-lookup"><span data-stu-id="3c287-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="3c287-179">ในการเริ่มต้นกระบวนการ เลือก **รัน** บนหน้าการตั้งค่าคอนฟิกแบรนด์หรือความสนใจ</span><span class="sxs-lookup"><span data-stu-id="3c287-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="3c287-180">นอกจากนี้ คุณสามารถให้ระบบรันการเพิ่มข้อมูลได้โดยอัตโนมัติโดยเป็นส่วนหนึ่งของการรีเฟรชที่จัดกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="3c287-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="3c287-181">ขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณ อาจใช้เวลาหลายนาทีในการเพิ่มประสิทธิภาพให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="3c287-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="3c287-182">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="3c287-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3c287-183">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="3c287-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3c287-184">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="3c287-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3c287-185">หลังจากเลือก **ดูรายละเอียด** สำหรับงานใดงานหนึ่ง คุณจะพบข้อมูลเพิ่มเติม: เวลาดำเนินการ วันที่ดำเนินการล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="3c287-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3c287-186">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-186">Enrichment results</span></span>

<span data-ttu-id="3c287-187">หลังจากการรันกระบวนการเพิ่มข้อมูล ไปที่ **การเพิ่มข้อมูลของฉัน** เพื่อตรวจสอบจำนวนลูกค้าที่เพิ่มข้อมูลทั้งหมด และการแยกแบรนด์หรือความสนใจในโปรไฟล์ลูกค้าที่ได้รับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3c287-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="การแสดงตัวอย่างของผลลัพธ์หลังจากเรียกใช้กระบวนการเพิ่มข้อมูล":::

<span data-ttu-id="3c287-189">ตรวจสอบข้อมูลที่เพิ่มโดยการเลือก **ดูข้อมูลที่เพิ่ม** ในแผนภูมิ</span><span class="sxs-lookup"><span data-stu-id="3c287-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="3c287-190">ข้อมูลที่เพิ่มสำหรับแบรนด์ต่างๆ ไปที่เอนทิตี **BrandAffinityFromMicrosoft**</span><span class="sxs-lookup"><span data-stu-id="3c287-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3c287-191">ข้อมูลสำหรับความสนใจอยู่ในเอนทิตี **InterestAffinityFromMicrosoft**</span><span class="sxs-lookup"><span data-stu-id="3c287-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3c287-192">นอกจากนี้ คุณยังจะพบเอนทิตีเหล่านี้แสดงรายการอยู่ในกลุ่ม **การเพิ่มข้อมูล** ใน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="3c287-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="3c287-193">ดูข้อมูลในการเพิ่มข้อมูลบนการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3c287-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="3c287-194">นอกจากนี้ ยังสามารถดูความเกี่ยวข้องของแบรนด์และความสนใจได้บนการ์ดลูกค้ารายบุคคล</span><span class="sxs-lookup"><span data-stu-id="3c287-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="3c287-195">ไปที่ **ลูกค้า** และเลือกโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3c287-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="3c287-196">ในการ์ดลูกค้า คุณจะพบแผนภูมิสำหรับแบรนด์หรือความสนใจที่ผู้คนในโปรไฟล์ประชากรของลูกค้านั้นมีความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="3c287-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="การ์ดลูกค้าที่มีข้อมูลที่สมบูรณ์":::

## <a name="next-steps"></a><span data-ttu-id="3c287-198">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="3c287-198">Next steps</span></span>

<span data-ttu-id="3c287-199">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3c287-200">สร้าง [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) และแม้แต่ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่ปรับให้เป็นแบบส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="3c287-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
