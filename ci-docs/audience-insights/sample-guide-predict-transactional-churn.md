---
title: คู่มือตัวอย่างการคาดคะเนการเลิกทำธุรกรรม
description: ใช้คู่มือตัวอย่างนี้เพื่อทดลองใช้โมเดลการคาดคะเนการเลิกทำธุรกรรมแบบสำเร็จรูป
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306143"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="fce67-103">คู่มือตัวอย่างการคาดคะเนการเลิกทำธุรกรรม (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="fce67-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="fce67-104">คู่มือนี้จะอธิบายตัวอย่างแบบตั้งแต่ต้นจนจบของการคาดคะเนการเลิกทำธุรกรรมใน Customer Insights โดยใช้ข้อมูลตัวอย่างที่ให้ไว้ด้านล่าง</span><span class="sxs-lookup"><span data-stu-id="fce67-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="fce67-105">ข้อมูลทั้งหมดที่ใช้ในคู่มือนี้ไม่ใช่ข้อมูลลูกค้าจริงและเป็นส่วนหนึ่งของชุดข้อมูล Contoso ที่พบในสภาพแวดล้อม *การสาธิต* ภายในการสมัครใช้งาน Customer Insights ของคุณ</span><span class="sxs-lookup"><span data-stu-id="fce67-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="fce67-106">สถานการณ์สมมติ</span><span class="sxs-lookup"><span data-stu-id="fce67-106">Scenario</span></span>

<span data-ttu-id="fce67-107">Contoso เป็นบริษัทที่ผลิตกาแฟและเครื่องชงกาแฟคุณภาพสูง ซึ่งขายผ่านเว็บไซต์กาแฟ Contoso ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="fce67-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="fce67-108">เป้าหมายของพวกเขาคือการรู้ว่าลูกค้ารายใดที่มักซื้อผลิตภัณฑ์ของตนเป็นประจำจะหยุดเป็นลูกค้าที่ใช้งานอยู่ใน 60 วันข้างหน้า</span><span class="sxs-lookup"><span data-stu-id="fce67-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="fce67-109">รู้ว่าลูกค้าของพวกเขารายใด **มีแนวโน้มที่จะเลิกใช้บริการ** สามารถช่วยให้พวกเขาประหยัดความพยายามทางการตลาดโดยมุ่งเน้นที่การรักษาลูกค้าเอาไว้</span><span class="sxs-lookup"><span data-stu-id="fce67-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fce67-110">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="fce67-110">Prerequisites</span></span>

- <span data-ttu-id="fce67-111">อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fce67-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="fce67-112">เราขอแนะนำให้คุณดำเนินการตามขั้นตอนต่อไปนี้ [ในสภาพแวดล้อมใหม่](manage-environments.md)</span><span class="sxs-lookup"><span data-stu-id="fce67-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="fce67-113">งานที่ 1 - นำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="fce67-114">ตรวจสอบบทความ [เกี่ยวกับการนำเข้าข้อมูล](data-sources.md) และ [การนำเข้าแหล่งข้อมูลโดยใช้ตัวเชื่อมต่อ Power Query](connect-power-query.md) โดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="fce67-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="fce67-115">ข้อมูลต่อไปนี้ถือว่าคุณคุ้นเคยกับการนำเข้าข้อมูลโดยทั่วไป</span><span class="sxs-lookup"><span data-stu-id="fce67-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="fce67-116">นำเข้าข้อมูลลูกค้าจากแพลตฟอร์มอีคอมเมิร์ซ</span><span class="sxs-lookup"><span data-stu-id="fce67-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="fce67-117">สร้างแหล่งข้อมูลที่ชื่อ **อีคอมเมิร์ซ** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="fce67-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fce67-118">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscontacts</span><span class="sxs-lookup"><span data-stu-id="fce67-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="fce67-119">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="fce67-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fce67-120">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="fce67-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="fce67-121">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="fce67-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fce67-122">**CreatedOn**: วันที่/เวลา/โซน</span><span class="sxs-lookup"><span data-stu-id="fce67-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="fce67-123">![เปลี่ยน DoB เป็น วันที่](media/ecommerce-dob-date.PNG "เปลี่ยนวันเดือนปีเกิดเป็นวันที่")</span><span class="sxs-lookup"><span data-stu-id="fce67-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="fce67-124">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="fce67-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="fce67-125">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="fce67-126">นำเข้าข้อมูลการซื้อออนไลน์</span><span class="sxs-lookup"><span data-stu-id="fce67-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="fce67-127">เพิ่มชุดข้อมูลอื่นให้เหมือนกันแหล่งข้อมูล **อีคอมเมิร์ซ**</span><span class="sxs-lookup"><span data-stu-id="fce67-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="fce67-128">เลือกตัวเชื่อมต่อ **ข้อความ/CSV** อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="fce67-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="fce67-129">ป้อน URL สำหรับข้อมูล **การซื้อออนไลน์** https://aka.ms/ciadclassonline</span><span class="sxs-lookup"><span data-stu-id="fce67-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="fce67-130">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="fce67-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fce67-131">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="fce67-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="fce67-132">**PurchasedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="fce67-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="fce67-133">**TotalPrice**: สกุลเงิน</span><span class="sxs-lookup"><span data-stu-id="fce67-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="fce67-134">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommercePurchases**</span><span class="sxs-lookup"><span data-stu-id="fce67-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="fce67-135">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="fce67-136">นำเข้าข้อมูลลูกค้าจากแบบแผนความภักดี</span><span class="sxs-lookup"><span data-stu-id="fce67-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="fce67-137">สร้างแหล่งข้อมูลที่ชื่อ **LoyaltyScheme** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="fce67-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fce67-138">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscustomerloyalty</span><span class="sxs-lookup"><span data-stu-id="fce67-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="fce67-139">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="fce67-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fce67-140">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="fce67-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="fce67-141">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="fce67-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fce67-142">**RewardsPoints**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="fce67-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="fce67-143">**CreatedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="fce67-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="fce67-144">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="fce67-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="fce67-145">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="fce67-146">งานที่ 2 - การรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-146">Task 2 - Data unification</span></span>

<span data-ttu-id="fce67-147">หลังจากนำเข้าข้อมูลตอนนี้เราเริ่มต้นกระบวนการ **แมป, จับคู่, ผสาน** เพื่อสร้างโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="fce67-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="fce67-148">สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [การรวมข้อมูล](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="fce67-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="fce67-149">แมป</span><span class="sxs-lookup"><span data-stu-id="fce67-149">Map</span></span>

1. <span data-ttu-id="fce67-150">หลังจากนำเข้าข้อมูลแล้ว ให้จับคู่ผู้ติดต่อจากข้อมูลอีคอมเมิร์ซและความภักดีกับชนิดข้อมูลทั่วไป</span><span class="sxs-lookup"><span data-stu-id="fce67-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="fce67-151">ไปที่ **ข้อมูล** > **รวม** > **แมป**</span><span class="sxs-lookup"><span data-stu-id="fce67-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="fce67-152">เลือกเอนทิตีที่แสดงถึงโปรไฟล์ลูกค้า - **eCommerceContacts** และ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="fce67-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="รวมแหล่งข้อมูลอีคอมเมิร์ซและความภักดี":::

1. <span data-ttu-id="fce67-154">เลือก **ContactId** เป็นคีย์หลักสำหรับ **eCommerceContacts** และ **LoyaltyID** เป็นคีย์หลักสำหรับ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="fce67-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="รวม LoyaltyId เป็นคีย์หลัก":::

### <a name="match"></a><span data-ttu-id="fce67-156">การจับคู่</span><span class="sxs-lookup"><span data-stu-id="fce67-156">Match</span></span>

1. <span data-ttu-id="fce67-157">ไปที่แท็บ **จับคู่** และเลือก **ตั้งค่าลำดับ**</span><span class="sxs-lookup"><span data-stu-id="fce67-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="fce67-158">ในรายการแบบหล่นลง **หลัก** เลือก **eCommerceContacts: eCommerce** เป็นแหล่งที่มาหลักและรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="fce67-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="fce67-159">ในรายการแบบหล่นลง **เอนทิตี 2** เลือก **oyCustomers : LoyaltyScheme** และรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="fce67-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="รวมอีคอมเมิร์ซและความภักดีที่ตรงกัน":::

1. <span data-ttu-id="fce67-161">เลือก **สร้างกฎใหม่**</span><span class="sxs-lookup"><span data-stu-id="fce67-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="fce67-162">เพิ่มเงื่อนไขแรกของคุณโดยใช้ FullName</span><span class="sxs-lookup"><span data-stu-id="fce67-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="fce67-163">สำหรับ eCommerceContacts เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="fce67-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="fce67-164">สำหรับ loyCustomers เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="fce67-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="fce67-165">เลือกรายการแบบหล่นลง **ทำให้เป็นมาตรฐาน** และเลือก **ชนิด (โทรศัพท์, ชื่อ, ที่อยู่... )**</span><span class="sxs-lookup"><span data-stu-id="fce67-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="fce67-166">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="fce67-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="fce67-167">ป้อนชื่อ **ชื่อเต็ม, อีเมล** สำหรับกฎใหม่</span><span class="sxs-lookup"><span data-stu-id="fce67-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="fce67-168">เพิ่มเงื่อนไขที่สองสำหรับที่อยู่อีเมลโดยการเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="fce67-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="fce67-169">สำหรับเอนทิตี eCommerceContacts เลือก **EMail** ในเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="fce67-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="fce67-170">สำหรับเอนทิตี loyCustomers เลือก **EMail** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="fce67-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="fce67-171">ปล่อยให้ ทำให้เป็นมาตรฐาน ว่างไว้</span><span class="sxs-lookup"><span data-stu-id="fce67-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="fce67-172">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="fce67-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="รวมกฎการจับคู่สำหรับชื่อและอีเมล":::

7. <span data-ttu-id="fce67-174">เลือก **บันทึก** และ **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="fce67-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="fce67-175">ผสาน</span><span class="sxs-lookup"><span data-stu-id="fce67-175">Merge</span></span>

1. <span data-ttu-id="fce67-176">ไปที่แท็บ **ผสาน**</span><span class="sxs-lookup"><span data-stu-id="fce67-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="fce67-177">ในเอนทิตี **ContactId** สำหรับ **loyCustomers** เปลี่ยนชื่อที่แสดงเป็น **ContactIdLOYALTY** เพื่อทำให้แตกต่างจากรหัสอื่นๆ ที่ส่งเข้ามา</span><span class="sxs-lookup"><span data-stu-id="fce67-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="เปลี่ยนชื่อ contactid จากรหัสความภักดี":::

1. <span data-ttu-id="fce67-179">เลือก **บันทึก** และ **เรียกใช้** เพื่อเริ่มกระบวนการผสาน</span><span class="sxs-lookup"><span data-stu-id="fce67-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="fce67-180">งานที่ 3 - กำหนดค่าการคาดคะเนการเลิกทำธุรรกรรม</span><span class="sxs-lookup"><span data-stu-id="fce67-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="fce67-181">ด้วยโปรไฟล์ลูกค้ารวมเข้าด้วยกัน ตอนนี้เราสามารถเรียกใช้การคาดคะเนการเลิกทำธุรรกรรม</span><span class="sxs-lookup"><span data-stu-id="fce67-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="fce67-182">สำหรับขั้นตอนโดยละเอียด โปรดดูบทความ [การคาดคะเนการเลิกทำธุรรกรรม (พรีวิว)](predict-subscription-churn.md)</span><span class="sxs-lookup"><span data-stu-id="fce67-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="fce67-183">ไปที่ **ระบบอัจฉริยะ** > **ค้นพบ** และเลือกใช้ **โมเดลการเลิกใช้บริการของลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="fce67-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="fce67-184">เลือกตัวเลือก **การทำธุรกรรม** และเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="fce67-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="fce67-185">ตั้งชื่อโมเดล **การคาดคะเนการเลิกทำธุรรกรรมอีคอมเมิร์ซ OOB** และเอนทิตีผลลัพธ์ **OOBeCommerceChurnPrediction**</span><span class="sxs-lookup"><span data-stu-id="fce67-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="fce67-186">กำหนดเงื่อนไขสองประการสำหรับโมเดลการเลิกใช้บริการ:</span><span class="sxs-lookup"><span data-stu-id="fce67-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="fce67-187">**กรอบเวลาการคาดคะเน**: **อย่างน้อย 60** วัน</span><span class="sxs-lookup"><span data-stu-id="fce67-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="fce67-188">การตั้งค่านี้กำหนดว่าเราต้องการคาดคะเนการเลิกใช้บริการของลูกค้าในอนาคตแค่ไหน</span><span class="sxs-lookup"><span data-stu-id="fce67-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="fce67-189">**การกำหนดการเลิกใช้**: **อย่างน้อย 60** วัน</span><span class="sxs-lookup"><span data-stu-id="fce67-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="fce67-190">ระยะเวลาที่ไม่มีการซื้อหลังจากนั้นจะถือว่าลูกค้าเลิกใช้บริการ</span><span class="sxs-lookup"><span data-stu-id="fce67-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="เลือกวิธีการของโมเดลกรอบเวลาการคาดคะเนและการกำหนดการเลิกใช้":::

1. <span data-ttu-id="fce67-192">เลือก **ประวัติการซื้อ (ที่จำเป็น)** และเลือก **เพิ่มข้อมูล** สำหรับประวัติการซื้อ</span><span class="sxs-lookup"><span data-stu-id="fce67-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="fce67-193">เพิ่มเอนทิตี **eCommercePurchases : eCommerce** และแมปฟิลด์จากอีคอมเมิร์ซไปยังฟิลด์ที่สอดคล้องกันที่โมเดลต้องการ</span><span class="sxs-lookup"><span data-stu-id="fce67-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="fce67-194">รวมเอนทิตี **eCommercePurchases : eCommerce** กับ **eCommerceContacts : eCommerce**</span><span class="sxs-lookup"><span data-stu-id="fce67-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="รวมเอนทิตี eCommerce":::

1. <span data-ttu-id="fce67-196">เลือก **ถัดไป** เพื่อตั้งกำหนดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="fce67-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="fce67-197">โมเดลจำเป็นต้องฝึกอย่างสม่ำเสมอเพื่อเรียนรู้รูปแบบใหม่เมื่อมีการนำเข้าข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="fce67-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="fce67-198">สำหรับตัวอย่างนี้ เลือก **รายเดือน**</span><span class="sxs-lookup"><span data-stu-id="fce67-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="fce67-199">หลังจากตรวจสอบรายละเอียดทั้งหมดแล้ว ให้เลือก **บันทึกและเรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="fce67-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="fce67-200">งานที่ 4 - ตรวจสอบผลลัพธ์และคำอธิบายของโมเดล</span><span class="sxs-lookup"><span data-stu-id="fce67-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="fce67-201">ให้โมเดลทำการฝึกและให้คะแนนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fce67-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="fce67-202">ตอนนี้คุณสามารถตรวจสอบคำอธิบายโมเดลการบอกเลิกการสมัครสมาชิกได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="fce67-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="fce67-203">สำหรับข้อมูลเพิ่มเติม โปรดดู [ตรวจสอบสถานะการคาดคะเนและผลลัพธ์](predict-subscription-churn.md#review-a-prediction-status-and-results)</span><span class="sxs-lookup"><span data-stu-id="fce67-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="fce67-204">งานที่ 5 - สร้างเซ็กเมนต์ของลูกค้าที่มีความเสี่ยงในการเลิกใช้บริการสูง</span><span class="sxs-lookup"><span data-stu-id="fce67-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="fce67-205">การเรียกใช้โมเดลการทำงานจริงจะสร้างเอนทิตีใหม่ที่คุณสามารถมองเห็นได้ใน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="fce67-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="fce67-206">คุณสามารถสร้างเซ็กเมนต์ใหม่โดยยึดตามเอนทิตีที่สร้างโดยโมเดล</span><span class="sxs-lookup"><span data-stu-id="fce67-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="fce67-207">ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="fce67-207">Go to **Segments**.</span></span> <span data-ttu-id="fce67-208">เลือก **ใหม่** และเลือก **สร้างจาก** > **ระบบอัจฉริยะ**</span><span class="sxs-lookup"><span data-stu-id="fce67-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="การสร้างเซ็กเมนต์ด้วยผลลัพธ์ของโมเดล":::

1. <span data-ttu-id="fce67-210">เลือกจุดสิ้นสุด **OOBSubscriptionChurnPrediction** และกำหนดเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="fce67-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="fce67-211">ฟิลด์: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="fce67-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="fce67-212">ตัวดำเนินการ: มากกว่า</span><span class="sxs-lookup"><span data-stu-id="fce67-212">Operator: greater than</span></span>
   - <span data-ttu-id="fce67-213">ค่า: 0.6</span><span class="sxs-lookup"><span data-stu-id="fce67-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="ตั้งค่าเซ็กเมนต์การบอกเลิกการสมัครสมาชิก":::

<span data-ttu-id="fce67-215">ตอนนี้คุณมีเซ็กเมนต์ที่ปรับปรุงแบบไดนามิกซึ่งระบุลูกค้าที่มีความเสี่ยงสูงที่จะเลิกใช้บริการสำหรับธุรกิจที่มีการสมัครสมาชิกนี้</span><span class="sxs-lookup"><span data-stu-id="fce67-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="fce67-216">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="fce67-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]