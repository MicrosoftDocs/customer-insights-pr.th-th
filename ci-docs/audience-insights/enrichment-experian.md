---
title: การเพิ่มความสมบูรณ์ด้วยการเพิ่มข้อมูลจากบุคคลที่สาม Experian
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม Experian
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269583"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f01d3-103">เพิ่มโปรไฟล์ลูกค้าด้วยข้อมูลประชากรจาก Experian (ดูตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="f01d3-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f01d3-104">Experian เป็นผู้นำระดับโลกในด้านการรายงานเครดิตสำหรับผู้บริโภคและธุรกิจ และบริการด้านการตลาด</span><span class="sxs-lookup"><span data-stu-id="f01d3-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f01d3-105">ด้วยบริการการเพิ่มข้อมูลจาก Experian คุณสามารถสร้างความเข้าใจที่ลึกซึ้งยิ่งขึ้นเกี่ยวกับลูกค้าของคุณ โดยการเพิ่มโปรไฟล์ลูกค้าของคุณด้วยข้อมูลประชากร เช่น ขนาดครัวเรือน รายได้ และอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="f01d3-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f01d3-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="f01d3-106">Prerequisites</span></span>

<span data-ttu-id="f01d3-107">เมื่อต้องการกำหนดค่า Experian คุณต้องทำตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="f01d3-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f01d3-108">คุณมีการสมัครใช้งาน Experian ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="f01d3-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f01d3-109">หากต้องการสมัครสมาชิก [ติดต่อ Experian](https://www.experian.com/marketing-services/contact) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="f01d3-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f01d3-110">[เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูล Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)</span><span class="sxs-lookup"><span data-stu-id="f01d3-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f01d3-111">คุณมีรหัสผู้ใช้ รหัสผู้เข้าร่วม และหมายเลขรุ่นสำหรับบัญชี Secure Transport (ST) ที่เปิดใช้งาน SSH ที่ Experian สร้างให้คุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f01d3-112">คุณมีสิทธิ์ของ [ผู้ดูแลระบบ](permissions.md#administrator) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="f01d3-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f01d3-113">การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="f01d3-113">Configuration</span></span>

1. <span data-ttu-id="f01d3-114">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**</span><span class="sxs-lookup"><span data-stu-id="f01d3-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f01d3-115">เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ Experian</span><span class="sxs-lookup"><span data-stu-id="f01d3-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f01d3-116">![ไทล์ Experian](media/experian-tile.png "ไทล์ Experian")</span><span class="sxs-lookup"><span data-stu-id="f01d3-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f01d3-117">เลือก **เริ่มต้นใช้งาน** และป้อนรหัสผู้ใช้ รหัสผู้เข้าร่วม และหมายเลขรุ่นสำหรับบัญชี Experian Secure Transport ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f01d3-118">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="f01d3-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f01d3-119">ยืนยันอินพุตทั้งหมดโดยเลือก **นำไปใช้**</span><span class="sxs-lookup"><span data-stu-id="f01d3-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f01d3-120">แม็ปฟิลด์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-120">Map your fields</span></span>

1.  <span data-ttu-id="f01d3-121">เลือก **เพิ่มข้อมูล** และเลือก **ชุดข้อมูลของลูกค้า** ที่คุณต้องการเพิ่มข้อมูลประชากรจาก Experian</span><span class="sxs-lookup"><span data-stu-id="f01d3-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="f01d3-122">คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="f01d3-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="f01d3-123">เลือกตัวระบุคีย์ของคุณจาก **ชื่อและที่อยู่** **อีเมล** หรือ **โทรศัพท์** เพื่อส่งไปยัง Experian สำหรับการแก้ปัญหาข้อมูลประจำตัว</span><span class="sxs-lookup"><span data-stu-id="f01d3-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f01d3-124">แอตทริบิวต์ตัวระบุคีย์เพิ่มเติมที่ส่งไปยัง Experian น่าจะให้อัตราการจับคู่ที่สูงกว่า</span><span class="sxs-lookup"><span data-stu-id="f01d3-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f01d3-125">เลือก **ต่อไป** และแมปแอตทริบิวต์ที่เกี่ยวข้องจากเอนทิตีลูกค้าแบบรวมของคุณให้ฟิลด์ตัวระบุคีย์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="f01d3-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f01d3-126">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมที่คุณต้องการส่งให้ Experian</span><span class="sxs-lookup"><span data-stu-id="f01d3-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f01d3-127">เลือก **บันทึก** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="f01d3-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f01d3-128">![การแม็ปฟิลด์ Experian](media/experian-field-mapping.png "การแม็ปฟิลด์ Experian")</span><span class="sxs-lookup"><span data-stu-id="f01d3-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f01d3-129">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f01d3-129">Enrichment results</span></span>

<span data-ttu-id="f01d3-130">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="f01d3-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f01d3-131">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="f01d3-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f01d3-132">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและกระบวนการการเพิ่มข้อมูลที่ Experian ตั้งค่าไว้สำหรับบัญชีของคุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f01d3-133">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="f01d3-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f01d3-134">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="f01d3-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f01d3-135">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="f01d3-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f01d3-136">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="f01d3-136">Next steps</span></span>

<span data-ttu-id="f01d3-137">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f01d3-138">สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="f01d3-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f01d3-139">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="f01d3-139">Data privacy and compliance</span></span>

<span data-ttu-id="f01d3-140">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Experian คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="f01d3-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f01d3-141">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Experian ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="f01d3-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f01d3-142">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="f01d3-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f01d3-143">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ</span><span class="sxs-lookup"><span data-stu-id="f01d3-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]