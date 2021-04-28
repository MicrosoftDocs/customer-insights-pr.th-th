---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยข้อมูลจาก Microsoft
description: ใช้ข้อมูลที่เป็นกรรมสิทธิ์จาก Microsoft เพื่อเพิ่มข้อมูลลูกค้าของคุณด้วยแบรนด์และความสนใจ
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896625"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="2450a-103">เพิ่มข้อมูลโปรไฟล์ลูกค้าที่มีแบรนด์และความเกี่ยวข้องของความสนใจ (ดูตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="2450a-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="2450a-104">ใช้ข้อมูลที่เป็นกรรมสิทธิ์จาก Microsoft เพื่อเพิ่มข้อมูลลูกค้าของคุณด้วยแบรนด์และความสนใจ</span><span class="sxs-lookup"><span data-stu-id="2450a-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="2450a-105">ความเกี่ยวข้องเหล่านี้ถูกกำหนดตามข้อมูลจากผู้ที่มีข้อมูลประชากรที่คล้ายคลึงไปยังลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="2450a-106">ข้อมูลนี้ช่วยให้คุณเข้าใจและจัดเซ็กเมนต์ลูกค้าของคุณได้ดีขึ้น โดยพิจารณาจากความเกี่ยวข้องของพวกเขากับแบรนด์และความสนใจเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="2450a-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="2450a-107">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** เพื่อ [ตั้งค่าคอนฟิกและดูการเพิ่มข้อมูล](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="2450a-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="2450a-108">หากต้องการตั้งค่าคอนฟิกการเพิ่มข้อมูลความเกี่ยวข้องของแบรนด์ ให้ไปที่แท็บ **ค้นพบ** และเลือก **เพิ่มข้อมูลของฉัน** บนไทล์ **แบรนด์**</span><span class="sxs-lookup"><span data-stu-id="2450a-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="2450a-109">หากต้องการตั้งค่าคอนฟิกการเพิ่มข้อมูลความเกี่ยวข้องของความสนใจ ให้ไปที่แท็บ **ค้นพบ** และเลือก **เพิ่มข้อมูลของฉัน** บนไทล์ **ความสนใจ**</span><span class="sxs-lookup"><span data-stu-id="2450a-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2450a-110">![ไทล์แบรนด์และความสนใจ](media/BrandsInterest-tile-Hub.png "ไทล์แบรนด์และความสนใจ")</span><span class="sxs-lookup"><span data-stu-id="2450a-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="2450a-111">วิธีที่เราพิจารณาความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="2450a-111">How we determine affinities</span></span>

<span data-ttu-id="2450a-112">เราใช้ข้อมูลการค้นหาออนไลน์ของ Microsoft เพื่อค้นหาความสนใจสำหรับแบรนด์และความสนใจในกลุ่มประชากรต่าง ๆ (กำหนดตามอายุ เพศ หรือสถานที่ตั้ง)</span><span class="sxs-lookup"><span data-stu-id="2450a-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="2450a-113">ปริมาณการค้นหาออนไลน์สำหรับแบรนด์หรือความสนใจจะกำหนดว่าเซ็กเมนต์ข้อมูลประชากรสัมพันธ์กันมากน้อยเพียงใดเมื่อเปรียบเทียบกับเซ็กเมนต์อื่นๆ ที่มีต่อแบรนด์หรือความสนใจนั้น</span><span class="sxs-lookup"><span data-stu-id="2450a-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="2450a-114">แบรนด์หรือความสนใจ</span><span class="sxs-lookup"><span data-stu-id="2450a-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="2450a-115">ระดับและคะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-115">Affinity level and score</span></span>

<span data-ttu-id="2450a-116">ในทุกโปรไฟล์ของลูกค้าที่ได้รับการเพิ่มข้อมูล เรามีค่าที่เกี่ยวข้องสองค่า – ระดับความเกี่ยวข้อง และคะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="2450a-117">ค่าเหล่านี้ช่วยคุณในการพิจารณาปริมาณความเกี่ยวข้องที่มีสำหรับเซ็กเมนต์ประชากรของโปรไฟล์นั้น สำหรับแบรนด์หรือความสนใจ เมื่อเทียบกับเซ็กเมนต์ประชากรอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="2450a-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="2450a-118">*ระดับความเกี่ยวข้อง* ประกอบด้วยสี่ระดับและ *คะแนนความสัมพันธ์* ถูกคำนวณในระดับ 100 จุดที่จับคู่กับระดับความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="2450a-119">ระดับความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-119">Affinity level</span></span> |<span data-ttu-id="2450a-120">คะแนนความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="2450a-121">สูงมาก</span><span class="sxs-lookup"><span data-stu-id="2450a-121">Very high</span></span>     | <span data-ttu-id="2450a-122">85-100</span><span class="sxs-lookup"><span data-stu-id="2450a-122">85-100</span></span>       |
|<span data-ttu-id="2450a-123">สูง</span><span class="sxs-lookup"><span data-stu-id="2450a-123">High</span></span>     | <span data-ttu-id="2450a-124">70-84</span><span class="sxs-lookup"><span data-stu-id="2450a-124">70-84</span></span>        |
|<span data-ttu-id="2450a-125">ขนาดปานกลาง</span><span class="sxs-lookup"><span data-stu-id="2450a-125">Medium</span></span>     | <span data-ttu-id="2450a-126">35-69</span><span class="sxs-lookup"><span data-stu-id="2450a-126">35-69</span></span>        |
|<span data-ttu-id="2450a-127">ตํ่า</span><span class="sxs-lookup"><span data-stu-id="2450a-127">Low</span></span>     | <span data-ttu-id="2450a-128">1-34</span><span class="sxs-lookup"><span data-stu-id="2450a-128">1-34</span></span>        |

<span data-ttu-id="2450a-129">โดยขึ้นอยู่กับรายละเอียดที่คุณต้องการสำหรับการวัดความเกี่ยวข้อง คุณสามารถใช้ระดับหรือคะแนนความเกี่ยวข้องก็ได้</span><span class="sxs-lookup"><span data-stu-id="2450a-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="2450a-130">คะแนนความเกี่ยวข้องช่วยให้คุณควบคุมได้แม่นยำยิ่งขึ้น</span><span class="sxs-lookup"><span data-stu-id="2450a-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="2450a-131">ประเทศ/ภูมิภาคที่รองรับ</span><span class="sxs-lookup"><span data-stu-id="2450a-131">Supported countries/regions</span></span>

<span data-ttu-id="2450a-132">ขณะนี้เรารองรับตัวเลือกประเทศ/ภูมิภาคต่อไปนี้: ออสเตรเลีย แคนาดา (อังกฤษ) ฝรั่งเศส เยอรมนี สหราชอาณาจักร หรือสหรัฐอเมริกา (อังกฤษ)</span><span class="sxs-lookup"><span data-stu-id="2450a-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="2450a-133">ในการเลือกประเทศ ให้เปิดไฟล์ **การเพิ่มคุณค่าของแบรนด์** หรือ **การเพิ่มมูลค่าดอกเบี้ย** และเลือก **เปลี่ยนแปลง** ถัดจาก **ประเทศ/ภูมิภาค**</span><span class="sxs-lookup"><span data-stu-id="2450a-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="2450a-134">ในบานหน้าต่าง **การตั้งค่าประเทศ/ภูมิภาค** เลือกตัวเลือก และเลือก **นำไปใช้**</span><span class="sxs-lookup"><span data-stu-id="2450a-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="2450a-135">ผลกระทบที่เกี่ยวข้องกับการเลือกประเทศ</span><span class="sxs-lookup"><span data-stu-id="2450a-135">Implications related to country selection</span></span>

- <span data-ttu-id="2450a-136">เมื่อ [เลือกแบรนด์ของคุณเอง](#define-your-brands-or-interests) ระบบจะให้คำแนะนำตามประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="2450a-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="2450a-137">เมื่อ [เลือกอุตสาหกรรม](#define-your-brands-or-interests) คุณจะได้รับแบรนด์หรือความสนใจที่เกี่ยวข้องมากที่สุดตามประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="2450a-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="2450a-138">เมื่อ [เพิ่มข้อมูลโปรไฟล์](#refresh-enrichment) เราจะเพิ่มโปรไฟล์ลูกค้าทั้งหมดที่เราได้รับข้อมูลสำหรับแบรนด์และความสนใจที่เลือก</span><span class="sxs-lookup"><span data-stu-id="2450a-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="2450a-139">ซึ่งรวมถึงโปรไฟล์ที่ไม่ได้อยู่ในประเทศหรือภูมิภาคที่เลือก</span><span class="sxs-lookup"><span data-stu-id="2450a-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="2450a-140">ตัวอย่างเช่น หากคุณเลือกเยอรมนี เราจะเพิ่มโปรไฟล์ที่ตั้งอยู่ในสหรัฐอเมริกา หากเรามีข้อมูลสำหรับแบรนด์และความสนใจที่เลือกในสหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="2450a-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="2450a-141">ตั้งค่าคอนฟิกการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-141">Configure Enrichment</span></span>

<span data-ttu-id="2450a-142">ประสบการณ์ที่แนะนำจะช่วยคุณในการกำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="2450a-143">กำหนดแบรนด์หรือความสนใจของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-143">Define your brands or interests</span></span>

<span data-ttu-id="2450a-144">เลือกตัวเลือกใดตัวเลือกหนึ่งต่อไปนี้</span><span class="sxs-lookup"><span data-stu-id="2450a-144">Select one of the following options:</span></span>

- <span data-ttu-id="2450a-145">**อุตสาหกรรม**: ระบบจะระบุแบรนด์ชั้นนำหรือความสนใจที่เกี่ยวข้องกับอุตสาหกรรมของคุณ และช่วยเพิ่มข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="2450a-146">**เลือกของคุณเอง**: เลือกได้สูงสุดห้ารายการจากรายการของแบรนด์หรือความสนใจที่เกี่ยวข้องกับองค์กรของคุณมากที่สุด</span><span class="sxs-lookup"><span data-stu-id="2450a-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="2450a-147">หากต้องการเพิ่มแบรนด์หรือความสนใจ ให้ป้อนลงในพื้นที่ป้อนข้อมูลเพื่อรับคำแนะนำตามเงื่อนไขการจับคู่</span><span class="sxs-lookup"><span data-stu-id="2450a-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="2450a-148">หากเราไม่แสดงแบรนด์หรือความสนใจที่คุณต้องการ โปรดส่งข้อเสนอแนะถึงเราโดยใช้ลิงก์ **แนะนำ**</span><span class="sxs-lookup"><span data-stu-id="2450a-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="2450a-149">รีวิวการกำหนดลักษณะการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-149">Review enrichment preferences</span></span>

<span data-ttu-id="2450a-150">รีวิวการกำหนดลักษณะการเพิ่มข้อมูลเริ่มต้นของคุณ และอัปเดตตามต้องการ</span><span class="sxs-lookup"><span data-stu-id="2450a-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="ภาพหน้าจอของหน้าต่างการกำหนดลักษณะการเพิ่มข้อมูล":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="2450a-152">เลือกเอนทิตีเพื่อเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-152">Select entity to enrich</span></span>

<span data-ttu-id="2450a-153">เลือก **เอนทิตีที่เพิ่มข้อมูลแล้ว** และเลือกชุดข้อมูลที่คุณต้องการเพิ่มข้อมูลด้วยข้อมูลบริษัทจาก Microsoft</span><span class="sxs-lookup"><span data-stu-id="2450a-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="2450a-154">คุณสามารถเลือกเอนทิตีลูกค้าเพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="2450a-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="2450a-155">แม็ปฟิลด์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-155">Map your fields</span></span>

<span data-ttu-id="2450a-156">แม็ปฟิลด์จากเอนทิตีลูกค้าแบบรวมของคุณเพื่อกำหนดเซ็กเมนต์ประชากรที่คุณต้องการให้ระบบใช้สำหรับการเพิ่มข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="2450a-157">แม็ปประเทศ/ภูมิภาค และแอตทริบิวต์วันเดือนปีเกิดหรือเพศ เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="2450a-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="2450a-158">นอกจากนี้ คุณต้องแม็ปหนึ่งในเมือง (และรัฐ/จังหวัด) หรือรหัสไปรษณีย์ เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="2450a-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="2450a-159">เลือก **แก้ไข** เพื่อกำหนดการแม็ปของฟิลด์ และเลือก **นำไปใช้** เมื่อคุณทำเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="2450a-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="2450a-160">เลือก **บันทึก** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="2450a-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="2450a-161">รองรับรูปแบบและค่าต่อไปนี้ ค่าไม่คำนึงถึงขนาดตัวพิมพ์:</span><span class="sxs-lookup"><span data-stu-id="2450a-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="2450a-162">**วันเกิด**: เราขอแนะนำให้แปลงวันเกิดเป็นประเภท DateTime ระหว่างการนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="2450a-163">หรืออีกทางเลือกหนึ่ง อาจเป็นสตริงในรูปแบบ [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" หรือ "yyyy-MM-ddTHH: mm: ssZ"</span><span class="sxs-lookup"><span data-stu-id="2450a-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="2450a-164">**เพศ**: ชาย หญิง ไม่ทราบ</span><span class="sxs-lookup"><span data-stu-id="2450a-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="2450a-165">**รหัสไปรษณีย์**: รหัสไปรษณีย์ห้าหลักสำหรับสหรัฐอเมริกา รหัสไปรษณีย์มาตรฐานทุกที่</span><span class="sxs-lookup"><span data-stu-id="2450a-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="2450a-166">**เมือง**: ชื่อเมืองเป็นภาษาอังกฤษ</span><span class="sxs-lookup"><span data-stu-id="2450a-166">**City**: City name in English</span></span>
- <span data-ttu-id="2450a-167">**รัฐ/จังหวัด**: ตัวย่อสองตัวอักษรสำหรับสหรัฐอเมริกาและแคนาดา</span><span class="sxs-lookup"><span data-stu-id="2450a-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="2450a-168">อักษรย่อสองหรือสามตัวสำหรับออสเตรเลีย</span><span class="sxs-lookup"><span data-stu-id="2450a-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="2450a-169">ไม่สามารถใช้ได้กับฝรั่งเศส เยอรมนี หรือสหราชอาณาจักร</span><span class="sxs-lookup"><span data-stu-id="2450a-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="2450a-170">**ประเทศ/ภูมิภาค**:</span><span class="sxs-lookup"><span data-stu-id="2450a-170">**Country/Region**:</span></span>

  - <span data-ttu-id="2450a-171">สหรัฐอเมริกา: United States of America, United States, USA, US, America</span><span class="sxs-lookup"><span data-stu-id="2450a-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="2450a-172">CA: แคนาดา CA</span><span class="sxs-lookup"><span data-stu-id="2450a-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="2450a-173">GB: สหราชอาณาจักร บริเตนใหญ่ GB สหราชอาณาจักรบริเตนใหญ่และไอร์แลนด์เหนือ สหราชอาณาจักรบริเตนใหญ่</span><span class="sxs-lookup"><span data-stu-id="2450a-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="2450a-174">ออสเตรเลีย: ออสเตรเลีย AU</span><span class="sxs-lookup"><span data-stu-id="2450a-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="2450a-175">ฝรั่งเศส: ฝรั่งเศส FR</span><span class="sxs-lookup"><span data-stu-id="2450a-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="2450a-176">DE: เยอรมณี DE สหพันธ์สาธารณรัฐเยอรมนี สาธารณรัฐเยอรมนี</span><span class="sxs-lookup"><span data-stu-id="2450a-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="2450a-177">ตรวจสอบและตั้งชื่อการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-177">Review and name the enrichment</span></span>

<span data-ttu-id="2450a-178">สุดท้าย คุณจะได้รับการตรวจสอบข้อมูลและระบุชื่อสำหรับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="หน้าตรวจสอบความสนใจและการตั้งชื่อ":::

## <a name="refresh-enrichment"></a><span data-ttu-id="2450a-180">รีเฟรชการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-180">Refresh enrichment</span></span>

<span data-ttu-id="2450a-181">เรียกใช้การเพิ่มประสิทธิภาพหลังจากกำหนดค่าแบรนด์ ความสนใจ และการแมปฟิลด์สำหรับข้อมูลด้านประชากร</span><span class="sxs-lookup"><span data-stu-id="2450a-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="2450a-182">ในการเริ่มต้นกระบวนการ เลือก **รัน** บนหน้าการตั้งค่าคอนฟิกแบรนด์หรือความสนใจ</span><span class="sxs-lookup"><span data-stu-id="2450a-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="2450a-183">นอกจากนี้ คุณสามารถให้ระบบรันการเพิ่มข้อมูลได้โดยอัตโนมัติโดยเป็นส่วนหนึ่งของการรีเฟรชที่จัดกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="2450a-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="2450a-184">ขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณ อาจใช้เวลาหลายนาทีในการเพิ่มประสิทธิภาพให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="2450a-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="2450a-185">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="2450a-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2450a-186">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="2450a-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2450a-187">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="2450a-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2450a-188">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="2450a-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2450a-189">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-189">Enrichment results</span></span>

<span data-ttu-id="2450a-190">หลังจากการรันกระบวนการเพิ่มข้อมูล ไปที่ **การเพิ่มข้อมูลของฉัน** เพื่อตรวจสอบจำนวนลูกค้าที่เพิ่มข้อมูลทั้งหมด และการแยกแบรนด์หรือความสนใจในโปรไฟล์ลูกค้าที่ได้รับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="2450a-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="การแสดงตัวอย่างของผลลัพธ์หลังจากเรียกใช้กระบวนการเพิ่มข้อมูล":::

<span data-ttu-id="2450a-192">ตรวจสอบข้อมูลที่เพิ่มโดยการเลือก **ดูข้อมูลที่เพิ่ม** ในแผนภูมิ</span><span class="sxs-lookup"><span data-stu-id="2450a-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="2450a-193">ข้อมูลที่เพิ่มสำหรับแบรนด์ต่างๆ ไปที่เอนทิตี **BrandAffinityFromMicrosoft**</span><span class="sxs-lookup"><span data-stu-id="2450a-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2450a-194">ข้อมูลสำหรับความสนใจอยู่ในเอนทิตี **InterestAffinityFromMicrosoft**</span><span class="sxs-lookup"><span data-stu-id="2450a-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2450a-195">นอกจากนี้ คุณยังจะพบเอนทิตีเหล่านี้แสดงรายการอยู่ในกลุ่ม **การเพิ่มข้อมูล** ใน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="2450a-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="2450a-196">ดูข้อมูลในการเพิ่มข้อมูลบนการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="2450a-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="2450a-197">นอกจากนี้ ยังสามารถดูความเกี่ยวข้องของแบรนด์และความสนใจได้บนการ์ดลูกค้ารายบุคคล</span><span class="sxs-lookup"><span data-stu-id="2450a-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="2450a-198">ไปที่ **ลูกค้า** และเลือกโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="2450a-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="2450a-199">ในการ์ดลูกค้า คุณจะพบแผนภูมิสำหรับแบรนด์หรือความสนใจที่ผู้คนในโปรไฟล์ประชากรของลูกค้านั้นมีความเกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="2450a-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="การ์ดลูกค้าที่มีข้อมูลที่สมบูรณ์":::

## <a name="next-steps"></a><span data-ttu-id="2450a-201">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="2450a-201">Next steps</span></span>

<span data-ttu-id="2450a-202">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2450a-203">สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="2450a-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
