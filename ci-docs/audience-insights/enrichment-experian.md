---
title: การเพิ่มข้อมูลด้วยการเพิ่มข้อมูลของบุคคลที่สาม Experian
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลของบุคคลที่สาม Experian
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309843"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e5a63-103">เพิ่มโปรไฟล์ลูกค้าด้วยข้อมูลประชากรจาก Experian (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="e5a63-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e5a63-104">Experian เป็นผู้นำระดับโลกในด้านการรายงานสินเชื่อของผู้บริโภคและธุรกิจและบริการด้านการตลาด</span><span class="sxs-lookup"><span data-stu-id="e5a63-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e5a63-105">ด้วยบริการการเพิ่มข้อมูลของ Experian คุณสามารถสร้างความเข้าใจที่ลึกซึ้งยิ่งขึ้นเกี่ยวกับลูกค้าของคุณ โดยการเพิ่มโปรไฟล์ลูกค้าของคุณด้วยข้อมูลประชากร เช่น ขนาดครัวเรือน รายได้ และอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="e5a63-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e5a63-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="e5a63-106">Prerequisites</span></span>

<span data-ttu-id="e5a63-107">เพื่อตั้งค่าคอนฟิก Experian คุณต้องทำตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="e5a63-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e5a63-108">คุณต้องมีการสมัครใช้งานของ Experian ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="e5a63-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e5a63-109">หากต้องการสมัครใช้งาน [ติดต่อ Experian](https://www.experian.com/marketing-services/contact) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="e5a63-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e5a63-110">[เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูล Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)</span><span class="sxs-lookup"><span data-stu-id="e5a63-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="e5a63-111">การเชื่อมต่อ Experian ได้รับการตั้งค่าคอนฟิกแล้วโดยผู้ดูแลระบบ *หรือ* คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)</span><span class="sxs-lookup"><span data-stu-id="e5a63-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e5a63-112">นอกจากนี้ คุณยังต้องมีรหัสผู้ใช้ รหัสผู้เข้าร่วม และหมายเลขรุ่นสำหรับบัญชี Secure Transport (ST) ที่เปิดใช้งาน SSH ของคุณที่ Experian สร้างขึ้นเพื่อคุณ</span><span class="sxs-lookup"><span data-stu-id="e5a63-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e5a63-113">ประเทศ/ภูมิภาคที่รองรับ</span><span class="sxs-lookup"><span data-stu-id="e5a63-113">Supported countries/regions</span></span>

<span data-ttu-id="e5a63-114">ขณะนี้เราสนับสนุนการเพิ่มข้อมูลโปรไฟล์ลูกค้าในสหรัฐอเมริกาเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="e5a63-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e5a63-115">กำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e5a63-115">Configure the enrichment</span></span>

1. <span data-ttu-id="e5a63-116">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**</span><span class="sxs-lookup"><span data-stu-id="e5a63-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e5a63-117">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5a63-118">![Experian อื่นๆ](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="e5a63-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="e5a63-119">เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="e5a63-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="e5a63-120">ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e5a63-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e5a63-121">หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อโดยเลือก **เพิ่มการเชื่อมต่อ** และเลือก Experian จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="e5a63-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="e5a63-122">เลือก **เชื่อมต่อกับ Experian** เพื่อยืนยันการเลือกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e5a63-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="e5a63-123">เลือก **ต่อไป** และเลือก **ชุดข้อมูลลูกค้า** ที่คุณต้องการเพิ่มด้วยข้อมูลประชากรจาก Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e5a63-124">คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="e5a63-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. <span data-ttu-id="e5a63-126">เลือก **ต่อไป** และกำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลประชากรที่ตรงกันจาก Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e5a63-127">อย่างน้อยหนึ่งในฟิลด์ **ชื่อและที่อยู่** **โทรศัพท์** หรือ **อีเมล์** ต้องระบุ</span><span class="sxs-lookup"><span data-stu-id="e5a63-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="e5a63-128">เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถเพิ่มฟิลด์อื่น ๆ ได้ถึงสองฟิลด์</span><span class="sxs-lookup"><span data-stu-id="e5a63-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="e5a63-129">การเลือกนี้จะส่งผลต่ฟิลด์การทำแม็ปที่คุณสามารถเข้าถึงได้ในขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="e5a63-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="e5a63-130">แอตทริบิวต์ตัวระบุคีย์ที่เพิ่มขึ้นที่ถูกส่งไปที่ Experian มีแนวโน้มที่จะให้อัตราการจับคู่ที่สูงขึ้น</span><span class="sxs-lookup"><span data-stu-id="e5a63-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e5a63-131">ให้เลือก **ถัดไป** เพื่อเริ่มการแม็ปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="e5a63-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="e5a63-132">กำหนดฟิลด์จากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลประชากรที่ตรงกันจาก Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e5a63-133">ทําเครื่องหมายฟิลด์ที่จำเป็นแล้ว</span><span class="sxs-lookup"><span data-stu-id="e5a63-133">Required fields are marked.</span></span>

1. <span data-ttu-id="e5a63-134">ระบุชื่อสำหรับการเพิ่มข้อมูลและชื่อสำหรับเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="e5a63-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="e5a63-135">เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="e5a63-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="e5a63-136">ตั้งค่าคอนฟิกการเชื่อมต่อสำหรับ Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="e5a63-137">คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e5a63-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e5a63-138">เลือก **เพิ่มการเชื่อมต่อ** เมื่อตั้งค่าคอนฟิกการเพิ่มความสมบูรณ์ *หรือ* ไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="e5a63-139">เลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="e5a63-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="e5a63-140">ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="e5a63-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e5a63-141">ป้อนรหัสผู้ใช้ รหัสผู้เข้าร่วม และหมายเลขรุ่นที่ถูกต้องสำหรับบัญชี Experian Secure Transport ของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5a63-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="e5a63-142">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** โดยการเลือก **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="e5a63-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="e5a63-143">เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="e5a63-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e5a63-144">หลังจากเสร็จสิ้นการตรวจสอบแล้ว ให้เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="e5a63-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="บานหน้าต่างการตั้งค่าคอนฟิกการเชื่อมต่อ Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="e5a63-146">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e5a63-146">Enrichment results</span></span>

<span data-ttu-id="e5a63-147">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="e5a63-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e5a63-148">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="e5a63-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e5a63-149">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและกระบวนการเพิ่มความสมบูรณ์ที่ตั้งค่าไว้สำหรับบัญชีของคุณโดย Experian</span><span class="sxs-lookup"><span data-stu-id="e5a63-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e5a63-150">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="e5a63-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e5a63-151">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="e5a63-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e5a63-152">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="e5a63-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5a63-153">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="e5a63-153">Next steps</span></span>

<span data-ttu-id="e5a63-154">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5a63-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e5a63-155">สร้าง [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) และแม้แต่ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่ปรับให้เป็นแบบส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="e5a63-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e5a63-156">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="e5a63-156">Data privacy and compliance</span></span>

<span data-ttu-id="e5a63-157">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Experian คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามสำหรับ Dynamics 365 Customer Insights ซึ่งรวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="e5a63-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e5a63-158">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบให้แน่ใจว่า Experian เป็นไปตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="e5a63-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e5a63-159">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="e5a63-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e5a63-160">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="e5a63-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
