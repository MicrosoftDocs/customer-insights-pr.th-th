---
title: การเพิ่มความสมบูรณ์ด้วยการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668701"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="5c90b-103">การเพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="5c90b-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="5c90b-104">HERE Technologies เป็นบริษัทแพลตฟอร์มด้านสถานที่ตั้งที่ให้บริการข้อมูลและสถานที่ตั้งเป็นหลัก</span><span class="sxs-lookup"><span data-stu-id="5c90b-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="5c90b-105">ด้วยบริการเพิ่มข้อมูลจาก HERE Technologies คุณสามารถสร้างความเข้าใจตำแหน่งที่ตั้งที่แม่นยำยิ่งขึ้นสำหรับลูกค้าของคุณด้วยการทำให้ที่อยู่เป็นมาตรฐาน การแยกละติจูดและลองจิจูด และอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="5c90b-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c90b-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="5c90b-106">Prerequisites</span></span>

<span data-ttu-id="5c90b-107">การกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies จะต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="5c90b-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5c90b-108">คุณต้องมีการสมัครใช้งาน HERE Technologies ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="5c90b-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="5c90b-109">หากต้องการสมัครใช้งาน คุณสามารถ [ลงทะเบียนที่นี่](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) หรือ [ติดต่อ HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="5c90b-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="5c90b-110">เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูลตำแหน่งที่ตั้งของ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5c90b-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="5c90b-111">คุณมีคีย์ API ของ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5c90b-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="5c90b-112">คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)</span><span class="sxs-lookup"><span data-stu-id="5c90b-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="5c90b-113">การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="5c90b-113">Configuration</span></span>

1. <span data-ttu-id="5c90b-114">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="5c90b-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5c90b-115">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5c90b-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c90b-116">![ไทล์ HERE Technologies](media/HERE-tile.png "ไทล์ HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="5c90b-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="5c90b-117">ป้อน **คีย์ API ของ HERE Technologies**</span><span class="sxs-lookup"><span data-stu-id="5c90b-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="5c90b-118">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="5c90b-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="5c90b-119">ยืนยันการป้อนข้อมูลทั้งคู่โดยการเลือก **เชื่อมต่อกับ HERE**</span><span class="sxs-lookup"><span data-stu-id="5c90b-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="5c90b-120">เลือก **เพิ่มข้อมูล** และเลือกว่าคุณต้องการแมปฟิลด์กับที่อยู่หลักและ/หรือรอง</span><span class="sxs-lookup"><span data-stu-id="5c90b-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="5c90b-121">คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งคู่ (เช่น ที่อยู่ที่บ้านและที่อยู่ของธุรกิจ) และเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งคู่แยกกัน</span><span class="sxs-lookup"><span data-stu-id="5c90b-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="5c90b-122">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="5c90b-122">Select **Next**.</span></span>

1. <span data-ttu-id="5c90b-123">กำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลตำแหน่งที่ตั้งที่ตรงกันจาก HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5c90b-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="5c90b-124">ต้องระบุฟิลด์ **ถนน 1** และ **รหัสไปรษณีย์** สำหรับที่อยู่หลักและ/หรือรองที่เลือก</span><span class="sxs-lookup"><span data-stu-id="5c90b-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="5c90b-125">เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถเพิ่มฟิลด์มากขึ้นได้</span><span class="sxs-lookup"><span data-stu-id="5c90b-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c90b-126">![เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies](media/enrichment-HERE-configuration.png "เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="5c90b-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="5c90b-127">เลือก **นำไปใช้** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="5c90b-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5c90b-128">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5c90b-128">Enrichment results</span></span>

<span data-ttu-id="5c90b-129">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="5c90b-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5c90b-130">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="5c90b-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c90b-131">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและเวลาตอบสนองของ API จาก HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5c90b-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="5c90b-132">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="5c90b-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="5c90b-133">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="5c90b-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5c90b-134">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="5c90b-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c90b-135">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="5c90b-135">Next steps</span></span>

<span data-ttu-id="5c90b-136">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="5c90b-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5c90b-137">สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="5c90b-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5c90b-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="5c90b-138">Data privacy and compliance</span></span>

<span data-ttu-id="5c90b-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง HERE Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="5c90b-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5c90b-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า HERE Technologies ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="5c90b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5c90b-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="5c90b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5c90b-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="5c90b-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
