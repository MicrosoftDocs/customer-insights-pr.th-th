---
title: การเพิ่มความสมบูรณ์ด้วยการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896074"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="d58e5-103">การเพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="d58e5-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="d58e5-104">HERE Technologies เป็นบริษัทแพลตฟอร์มด้านสถานที่ตั้งที่ให้บริการข้อมูลและสถานที่ตั้งเป็นหลัก</span><span class="sxs-lookup"><span data-stu-id="d58e5-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="d58e5-105">ด้วยบริการเพิ่มข้อมูลจาก HERE Technologies คุณสามารถสร้างความเข้าใจตำแหน่งที่ตั้งที่แม่นยำยิ่งขึ้นสำหรับลูกค้าของคุณด้วยการทำให้ที่อยู่เป็นมาตรฐาน การแยกละติจูดและลองจิจูด และอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="d58e5-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d58e5-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="d58e5-106">Prerequisites</span></span>

<span data-ttu-id="d58e5-107">การกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies จะต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="d58e5-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d58e5-108">คุณต้องมีการสมัครใช้งาน HERE Technologies ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="d58e5-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="d58e5-109">หากต้องการสมัครใช้งาน คุณสามารถ [ลงทะเบียนที่นี่](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) หรือ [ติดต่อ HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="d58e5-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="d58e5-110">เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูลตำแหน่งที่ตั้งของ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="d58e5-111">มี [การเชื่อมต่อ](connections.md) HERE ใช้ได้ *หรือ* คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator) และคีย์ API ของ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d58e5-112">กำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d58e5-112">Configure the enrichment</span></span>

1. <span data-ttu-id="d58e5-113">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="d58e5-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="d58e5-114">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ HERE Technologies แล้วเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="d58e5-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d58e5-115">![ไทล์ HERE Technologies](media/HERE-tile.png "ไทล์ HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="d58e5-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="d58e5-116">เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="d58e5-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d58e5-117">ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d58e5-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="d58e5-118">หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อโดยเลือก **เพิ่มการเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="d58e5-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="d58e5-119">เลือก **HERE Technologies** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="d58e5-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="d58e5-120">เลือก **เชื่อมต่อกับ HERE Technologies** เพื่อยืนยันการเลือก</span><span class="sxs-lookup"><span data-stu-id="d58e5-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="d58e5-121">เลือก **ต่อไป** และเลือก **ชุดข้อมูลลูกค้า** ที่คุณต้องการเพิ่มข้อมูลด้วยข้อมูลตำแหน่งที่ตั้งจาก HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="d58e5-122">คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="d58e5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. <span data-ttu-id="d58e5-124">เลือกว่าคุณต้องการแม็ปฟิลด์กับที่อยู่หลักและ/หรือที่อยู่รอง</span><span class="sxs-lookup"><span data-stu-id="d58e5-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="d58e5-125">คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งสองและเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งสองแยกกัน</span><span class="sxs-lookup"><span data-stu-id="d58e5-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="d58e5-126">ตัวอย่างเช่น หากมีที่อยู่บ้านและที่อยู่ของธุรกิจ</span><span class="sxs-lookup"><span data-stu-id="d58e5-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="d58e5-127">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="d58e5-127">Select **Next**.</span></span>

1. <span data-ttu-id="d58e5-128">กำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลตำแหน่งที่ตั้งที่ตรงกันจาก HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="d58e5-129">ต้องระบุฟิลด์ **ถนน 1** และ **รหัสไปรษณีย์** สำหรับที่อยู่หลักและ/หรือรองที่เลือก</span><span class="sxs-lookup"><span data-stu-id="d58e5-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="d58e5-130">เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถเพิ่มฟิลด์มากขึ้นได้</span><span class="sxs-lookup"><span data-stu-id="d58e5-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d58e5-131">![เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies](media/enrichment-HERE-configuration.png "เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="d58e5-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="d58e5-132">ให้เลือก **ถัดไป** เพื่อทำการแม็ปฟิลด์ให้เสร็จ</span><span class="sxs-lookup"><span data-stu-id="d58e5-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d58e5-133">ระบุชื่อสำหรับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d58e5-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="d58e5-134">1. เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="d58e5-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="d58e5-135">กำหนดค่าการเชื่อมต่อสำหรับ HERE technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="d58e5-136">คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d58e5-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d58e5-137">เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มข้อมูล *หรือ* ไปที่ **การจัดการ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="d58e5-138">ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="d58e5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d58e5-139">ระบุคีย์ API ของ HERE Technologies ที่ถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="d58e5-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="d58e5-140">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="d58e5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="d58e5-141">เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="d58e5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d58e5-142">หลังจากเสร็จสิ้นการตรวจสอบแล้ว ให้เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="d58e5-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="d58e5-143">![หน้าการกำหนดค่าการเชื่อมต่อสำหรับ HERE technologies](media/enrichment-HERE-connection.png "หน้าการกำหนดค่าการเชื่อมต่อสำหรับ HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="d58e5-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d58e5-144">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d58e5-144">Enrichment results</span></span>

<span data-ttu-id="d58e5-145">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="d58e5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d58e5-146">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="d58e5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d58e5-147">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและเวลาตอบสนองของ API จาก HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d58e5-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="d58e5-148">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="d58e5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d58e5-149">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="d58e5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d58e5-150">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="d58e5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d58e5-151">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="d58e5-151">Next steps</span></span>

<span data-ttu-id="d58e5-152">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="d58e5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d58e5-153">สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="d58e5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d58e5-154">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="d58e5-154">Data privacy and compliance</span></span>

<span data-ttu-id="d58e5-155">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง HERE Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="d58e5-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d58e5-156">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า HERE Technologies ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="d58e5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d58e5-157">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="d58e5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d58e5-158">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="d58e5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
