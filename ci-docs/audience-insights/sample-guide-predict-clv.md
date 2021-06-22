---
title: คู่มือตัวอย่างของการคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า
description: ใช้คู่มือตัวอย่างนี้เพื่อทดลองใช้โมเดลการคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129968"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="3a25f-103">คู่มือตัวอย่างของการคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า (CLV)</span><span class="sxs-lookup"><span data-stu-id="3a25f-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="3a25f-104">คู่มือนี้จะอธิบายตัวอย่างแบบครบวงจรของการคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า (CLV) ใน Customer Insights โดยใช้ข้อมูลตัวอย่าง</span><span class="sxs-lookup"><span data-stu-id="3a25f-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="3a25f-105">สถานการณ์สมมติ</span><span class="sxs-lookup"><span data-stu-id="3a25f-105">Scenario</span></span>

<span data-ttu-id="3a25f-106">Contoso เป็นบริษัทที่ผลิตกาแฟและเครื่องชงกาแฟคุณภาพสูง</span><span class="sxs-lookup"><span data-stu-id="3a25f-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="3a25f-107">พวกเขาขายสินค้าผ่านเว็บไซต์กาแฟ Contoso ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="3a25f-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="3a25f-108">บริษัทต้องการเข้าใจมูลค่า (รายได้) ที่ลูกค้าสามารถสร้างขึ้นได้ในอีก 12 เดือนข้างหน้า</span><span class="sxs-lookup"><span data-stu-id="3a25f-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="3a25f-109">การรู้มูลค่าที่คาดหวังของลูกค้าในอีก 12 เดือนข้างหน้า จะช่วยพวกเขาในการควบคุมความพยายามทางการตลาดกับลูกค้าที่มีมูลค่าสูง</span><span class="sxs-lookup"><span data-stu-id="3a25f-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a25f-110">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="3a25f-110">Prerequisites</span></span>

- <span data-ttu-id="3a25f-111">อย่างน้อย [สิทธิ์ของผู้สนับสนุน](permissions.md) ในข้อมูลเชิงลึกของผู้ชม</span><span class="sxs-lookup"><span data-stu-id="3a25f-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="3a25f-112">เราขอแนะนำให้คุณดำเนินการตามขั้นตอนต่อไปนี้ [ในสภาพแวดล้อมใหม่](manage-environments.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="3a25f-113">งานที่ 1 - นำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="3a25f-114">รีวิวบทความ [เกี่ยวกับการนำเข้าข้อมูล](data-sources.md) และ [การนำเข้าแหล่งข้อมูลโดยใช้ตัวเชื่อมต่อ Power Query](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="3a25f-115">ข้อมูลต่อไปนี้ถือว่าคุณคุ้นเคยกับการนำเข้าข้อมูลโดยทั่วไป</span><span class="sxs-lookup"><span data-stu-id="3a25f-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="3a25f-116">นำเข้าข้อมูลลูกค้าจากแพลตฟอร์มอีคอมเมิร์ซ</span><span class="sxs-lookup"><span data-stu-id="3a25f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="3a25f-117">สร้างแหล่งข้อมูลที่ชื่อ **eCommerce** เลือกตัวเลือกการนำเข้า และเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="3a25f-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3a25f-118">ป้อน URL สำหรับผู้ติดต่อ eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)</span><span class="sxs-lookup"><span data-stu-id="3a25f-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="3a25f-119">ในขณะแก้ไขข้อมูล ให้เลือก  **แปลง**  แล้วจากนั้น  **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="3a25f-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3a25f-120">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="3a25f-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3a25f-121">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="3a25f-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="3a25f-122">**CreatedOn**: วันที่/เวลา/โซน</span><span class="sxs-lookup"><span data-stu-id="3a25f-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="เปลี่ยนวันเดือนปีเกิดเป็นวันที่":::

1. <span data-ttu-id="3a25f-124">ในฟิลด์ "ชื่อ" ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="3a25f-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="3a25f-125">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="3a25f-126">นำเข้าข้อมูลการซื้อออนไลน์</span><span class="sxs-lookup"><span data-stu-id="3a25f-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="3a25f-127">เพิ่มชุดข้อมูลอื่นให้เหมือนกันแหล่งข้อมูล **อีคอมเมิร์ซ**</span><span class="sxs-lookup"><span data-stu-id="3a25f-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="3a25f-128">เลือกตัวเชื่อมต่อ **ข้อความ/CSV** อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="3a25f-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="3a25f-129">ป้อน URL สำหรับข้อมูล **การซื้อออนไลน์** https://aka.ms/ciadclassonline</span><span class="sxs-lookup"><span data-stu-id="3a25f-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="3a25f-130">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="3a25f-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3a25f-131">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="3a25f-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3a25f-132">**PurchasedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="3a25f-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="3a25f-133">**TotalPrice**: สกุลเงิน</span><span class="sxs-lookup"><span data-stu-id="3a25f-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="3a25f-134">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านข้าง ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommercePurchases**</span><span class="sxs-lookup"><span data-stu-id="3a25f-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="3a25f-135">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="3a25f-136">นำเข้าข้อมูลลูกค้าจากแบบแผนความภักดี</span><span class="sxs-lookup"><span data-stu-id="3a25f-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="3a25f-137">สร้างแหล่งข้อมูลที่ชื่อ **LoyaltyScheme** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="3a25f-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3a25f-138">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscustomerloyalty</span><span class="sxs-lookup"><span data-stu-id="3a25f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="3a25f-139">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="3a25f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3a25f-140">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="3a25f-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3a25f-141">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="3a25f-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3a25f-142">**RewardsPoints**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="3a25f-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="3a25f-143">**CreatedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="3a25f-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="3a25f-144">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="3a25f-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="3a25f-145">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="3a25f-146">นำเข้าข้อมูลลูกค้าจากบทวิจารณ์เว็บไซต์</span><span class="sxs-lookup"><span data-stu-id="3a25f-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="3a25f-147">สร้างแหล่งข้อมูลที่ชื่อ **เว็บไซต์** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="3a25f-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3a25f-148">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/CI-ILT/WebReviews</span><span class="sxs-lookup"><span data-stu-id="3a25f-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="3a25f-149">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="3a25f-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3a25f-150">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="3a25f-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="3a25f-151">**ReviewRating**: เลขทศนิยม</span><span class="sxs-lookup"><span data-stu-id="3a25f-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="3a25f-152">**ReviewDate**: วันที่</span><span class="sxs-lookup"><span data-stu-id="3a25f-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="3a25f-153">ในฟิลด์ 'ชื่อ' บนบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **แบบสอบถาม** เป็น **การวิจารณ์**</span><span class="sxs-lookup"><span data-stu-id="3a25f-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="3a25f-154">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="3a25f-155">งานที่ 2 - การรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-155">Task 2 - Data unification</span></span>

<span data-ttu-id="3a25f-156">หลังจากนำเข้าข้อมูลแล้ว ตอนนี้เราเริ่มกระบวนการรวมข้อมูลเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="3a25f-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="3a25f-157">สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [การรวมข้อมูล](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="3a25f-158">แมป</span><span class="sxs-lookup"><span data-stu-id="3a25f-158">Map</span></span>

1. <span data-ttu-id="3a25f-159">หลังจากนำเข้าข้อมูลแล้ว ให้จับคู่ผู้ติดต่อจากข้อมูลอีคอมเมิร์ซและความภักดีกับชนิดข้อมูลทั่วไป</span><span class="sxs-lookup"><span data-stu-id="3a25f-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="3a25f-160">ไปที่ **ข้อมูล** > **รวม** > **แมป**</span><span class="sxs-lookup"><span data-stu-id="3a25f-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="3a25f-161">เลือกเอนทิตีที่แสดงถึงโปรไฟล์ลูกค้า - **eCommerceContacts** และ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="3a25f-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="3a25f-162">จากนั้น เลือก **นำไปใช้**</span><span class="sxs-lookup"><span data-stu-id="3a25f-162">Then, select **Apply**.</span></span>

   ![รวมแหล่งข้อมูลอีคอมเมิร์ซและความภักดี](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="3a25f-164">เลือก **ContactId** เป็นคีย์หลักสำหรับ **eCommerceContacts** และ **LoyaltyID** เป็นคีย์หลักสำหรับ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="3a25f-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![รวม LoyaltyId เป็นคีย์หลัก](media/unify-loyaltyid.png)

1. <span data-ttu-id="3a25f-166">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="3a25f-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="3a25f-167">การจับคู่</span><span class="sxs-lookup"><span data-stu-id="3a25f-167">Match</span></span>

1. <span data-ttu-id="3a25f-168">ไปที่แท็บ **จับคู่** และเลือก **ตั้งค่าลำดับ**</span><span class="sxs-lookup"><span data-stu-id="3a25f-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="3a25f-169">ในรายการแบบหล่นลง **หลัก** ให้เลือก **eCommerceContacts : eCommerce** เป็นแหล่งข้อมูลหลักและรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="3a25f-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="3a25f-170">ในรายการแบบหล่นลง **เอนทิตี 2** ให้เลือก **loyCustomers : LoyaltyScheme** และรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="3a25f-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![รวมอีคอมเมิร์ซและความภักดีที่ตรงกัน](media/unify-match-order.png)

1. <span data-ttu-id="3a25f-172">เลือก **เพิ่มกฎ**</span><span class="sxs-lookup"><span data-stu-id="3a25f-172">Select **Add rule**</span></span>

1. <span data-ttu-id="3a25f-173">เพิ่มเงื่อนไขแรกของคุณโดยใช้ FullName</span><span class="sxs-lookup"><span data-stu-id="3a25f-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="3a25f-174">สำหรับ eCommerceContacts ให้เลือก **FullName** ในเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3a25f-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3a25f-175">สำหรับ loyCustomers ให้เลือก **FullName** ในเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3a25f-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3a25f-176">เลือกรายการแบบหล่นลง **ทำให้เป็นมาตรฐาน** และเลือก **ชนิด (โทรศัพท์, ชื่อ, ที่อยู่... )**</span><span class="sxs-lookup"><span data-stu-id="3a25f-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="3a25f-177">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="3a25f-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="3a25f-178">ป้อนชื่อ **ชื่อเต็ม, อีเมล** สำหรับกฎใหม่</span><span class="sxs-lookup"><span data-stu-id="3a25f-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="3a25f-179">เพิ่มเงื่อนไขที่สองสำหรับที่อยู่อีเมลโดยการเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="3a25f-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="3a25f-180">สำหรับเอนทิตี eCommerceContacts ให้เลือก **อีเมล** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3a25f-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="3a25f-181">สำหรับเอนทิตี loyCustomers ให้เลือก **EMail** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="3a25f-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="3a25f-182">ปล่อยให้ ทำให้เป็นมาตรฐาน ว่างไว้</span><span class="sxs-lookup"><span data-stu-id="3a25f-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="3a25f-183">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="3a25f-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![รวมกฎการจับคู่สำหรับชื่อและอีเมล](media/unify-match-rule.png)

1. <span data-ttu-id="3a25f-185">เลือก **สำเร็จ**</span><span class="sxs-lookup"><span data-stu-id="3a25f-185">Select **Done**.</span></span>

1. <span data-ttu-id="3a25f-186">เลือก **บันทึก** และ **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="3a25f-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="3a25f-187">ผสาน</span><span class="sxs-lookup"><span data-stu-id="3a25f-187">Merge</span></span>

1. <span data-ttu-id="3a25f-188">ไปที่แท็บ **ผสาน**</span><span class="sxs-lookup"><span data-stu-id="3a25f-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="3a25f-189">ในเอนทิตี **ContactId** สำหรับ **loyCustomers** เปลี่ยนชื่อที่แสดงเป็น **ContactIdLOYALTY** เพื่อทำให้แตกต่างจากรหัสอื่นๆ ที่ส่งเข้ามา</span><span class="sxs-lookup"><span data-stu-id="3a25f-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![เปลี่ยนชื่อ contactid จากรหัสความภักดี](media/unify-merge-contactid.png)

1. <span data-ttu-id="3a25f-191">เลือก **บันทึก** และ **เรียกใช้กระบวนการผสานและกระบวนการดาวน์สตรีม**</span><span class="sxs-lookup"><span data-stu-id="3a25f-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="3a25f-192">งานที่ 3 - ตั้งค่าคอนฟิกการคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3a25f-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="3a25f-193">ด้วยโปรไฟล์ลูกค้าแบบรวม ตอนนี้เราสามารถเรียกใช้การคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3a25f-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="3a25f-194">สำหรับขั้นตอนโดยละเอียด โปรดดูที่ [การคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า (พรีวิว)](predict-customer-lifetime-value.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="3a25f-195">ไปที่  **ระบบอัจฉริยะ**  > **การคาดคะเน** แล้วจากนั้น เลือก **โมเดลมูลค่าตลอดอายุการใช้งานของลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="3a25f-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="3a25f-196">ดำเนินการข้อมูลในบานหน้าต่างด้านข้าง แล้วเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="3a25f-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="3a25f-197">ตั้งชื่อโมเดล **การคาดคะเน OOB eCommerce CLV** และเอนทิตีเอาท์พุท **OOBeCommerceCLVPrediction**</span><span class="sxs-lookup"><span data-stu-id="3a25f-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="3a25f-198">กำหนดการกำหนดลักษณะของโมเดลสำหรับโมเดล CLV:</span><span class="sxs-lookup"><span data-stu-id="3a25f-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="3a25f-199">**ช่วงเวลาการคาดคะเน**: **12 เดือน หรือ 1 ปี**</span><span class="sxs-lookup"><span data-stu-id="3a25f-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="3a25f-200">การตั้งค่านี้กำหนดระยะในอนาคตที่จะคาดคะเนมูลค่าตลอดอายุการใช้งานของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="3a25f-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="3a25f-201">**ลูกค้าที่ใช้งาน**: ระบุว่าลูกค้าที่ใช้งานอยู่มีความหมายต่อธุรกิจของคุณอย่างไร</span><span class="sxs-lookup"><span data-stu-id="3a25f-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="3a25f-202">ตั้งค่ากรอบเวลาในอดีตซึ่งลูกค้าต้องมีธุรกรรมอย่างน้อยหนึ่งรายการให้ถือว่าใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="3a25f-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="3a25f-203">แบบจำลองจะคาดคะเน CLV สำหรับลูกค้าที่ใช้งานอยู่เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="3a25f-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="3a25f-204">เลือกระหว่างการอนุญาตให้โมเดลคำนวณระยะเวลาตามข้อมูลการทำธุรกรรมในอดีต หรือระบุกรอบเวลาที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="3a25f-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="3a25f-205">ในคู่มือตัวอย่างนี้ เรา **อนุญาตให้โมเดลคำนวณช่วงการซื้อ** ซึ่งเป็นตัวเลือกเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="3a25f-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="3a25f-206">**ลูกค้าที่มีมูลค่าสูง**: กำหนดลูกค้าที่มีมูลค่าสูงเป็นเปอร์เซ็นต์ไทล์ของลูกค้าที่จ่ายเงินสูงสุด</span><span class="sxs-lookup"><span data-stu-id="3a25f-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="3a25f-207">โมเดลใช้ข้อมูลป้อนเข้านี้เพื่อให้ผลลัพธ์ที่ตรงกับคำนิยามธุรกิจของคุณของลูกค้าที่มีมูลค่าสูง</span><span class="sxs-lookup"><span data-stu-id="3a25f-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="3a25f-208">คุณสามารถเลือกอนุญาตให้โมเดลกําหนดลูกค้าที่มีมูลค่าสูง</span><span class="sxs-lookup"><span data-stu-id="3a25f-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="3a25f-209">ซึ่งใช้กฎฮิวริสติกที่ได้ค่าเปอร์เซ็นต์ไทล์</span><span class="sxs-lookup"><span data-stu-id="3a25f-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="3a25f-210">นอกจากนี้ คุณยังสามารถกำหนดลูกค้าที่มีมูลค่าสูงเป็นเปอร์เซ็นต์ไทล์ของลูกค้าที่จ่ายเงินสูงสุดในอนาคตได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="3a25f-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="3a25f-211">ในคู่มือตัวอย่างนี้ เรากำหนดลูกค้าที่มีมูลค่าสูงด้วยตนเองเป็น **30% สูงสุดของลูกค้าที่ชำระเงินที่ใช้งานอยู่** และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="3a25f-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="ขั้นตอนการกำหนดลักษณะในประสบการณ์ที่แนะนำสำหรับโมเดล CLV":::

1. <span data-ttu-id="3a25f-213">ในขั้นตอน **ข้อมูลที่จำเป็น** เลือก **เพิ่มข้อมูล** เพื่อให้ข้อมูลประวัติการทำธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="3a25f-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="3a25f-214">เพิ่มเอนทิตี **eCommercePurchases : eCommerce** และแม็ปแอตทริบิวต์ที่โมเดลต้องการ:</span><span class="sxs-lookup"><span data-stu-id="3a25f-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="3a25f-215">รหัสธุรกรรม: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="3a25f-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="3a25f-216">วันที่ธุรกรรม: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="3a25f-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="3a25f-217">จำนวนธุรกรรม: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="3a25f-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="3a25f-218">รหัสผลิตภัณฑ์: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="3a25f-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="3a25f-219">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="3a25f-219">Select **Next**.</span></span>

1. <span data-ttu-id="3a25f-220">กำหนดความสัมพันธ์ระหว่างเอนทิตี **eCommercePurchases : eCommerce** และ **eCommerceContacts : eCommerce**</span><span class="sxs-lookup"><span data-stu-id="3a25f-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="3a25f-221">ขั้นตอน **ข้อมูลเพิ่มเติม (ไม่บังคับ)** ช่วยให้คุณสามารถเพิ่มข้อมูลกิจกรรมของลูกค้าได้มากขึ้น</span><span class="sxs-lookup"><span data-stu-id="3a25f-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="3a25f-222">ข้อมูลนี้สามารถช่วยให้ได้รับข้อมูลเชิงลึกมากขึ้นสำหรับการโต้ตอบกับลูกค้ากับธุรกิจของคุณ ซึ่งอาจส่งผลต่อ CLV</span><span class="sxs-lookup"><span data-stu-id="3a25f-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="3a25f-223">การเพิ่มการโต้ตอบกับลูกค้าที่สำคัญ เช่น บันทึกการใช้เว็บ บันทึกส่วนบริการลูกค้า หรือประวัติโปรแกรมรางวัล สามารถปรับปรุงความแม่นยำของการคาดคะเนได้</span><span class="sxs-lookup"><span data-stu-id="3a25f-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="3a25f-224">เลือก **เพิ่มข้อมูล** เพื่อรวมข้อมูลกิจกรรมของลูกค้าเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="3a25f-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="3a25f-225">เพิ่มเอนทิตีกิจกรรมลูกค้า และแม็ปชื่อฟิลด์กับฟิลด์ที่เกี่ยวข้องซึ่งโมเดลต้องการ:</span><span class="sxs-lookup"><span data-stu-id="3a25f-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="3a25f-226">เอนทิตีกิจกรรมของลูกค้า: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="3a25f-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="3a25f-227">คีย์หลัก: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="3a25f-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="3a25f-228">การประทับเวลา: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="3a25f-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="3a25f-229">เหตุการณ์ (ชื่อกิจกรรม): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="3a25f-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="3a25f-230">รายละเอียด (จำนวนหรือมูลค่า): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="3a25f-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="3a25f-231">เลือก **ต่อไป** และตั้งค่าคอนฟิกกิจกรรมและความสัมพันธ์ระหว่างข้อมูลธุรกรรมและข้อมูลลูกค้า:</span><span class="sxs-lookup"><span data-stu-id="3a25f-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="3a25f-232">ชนิดกิจกรรม: เลือกชนิดที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="3a25f-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="3a25f-233">ป้ายชื่อกิจกรรม: รีวิว</span><span class="sxs-lookup"><span data-stu-id="3a25f-233">Activity label: Review</span></span>
   - <span data-ttu-id="3a25f-234">ป้ายชื่อที่สอดคล้องกัน: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="3a25f-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="3a25f-235">เอนทิตีลูกค้า: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="3a25f-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="3a25f-236">ความสัมพันธ์: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="3a25f-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="3a25f-237">เลือก **ถัดไป** เพื่อตั้งกำหนดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="3a25f-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="3a25f-238">โมเดลจำเป็นต้องฝึกเป็นประจำเพื่อเรียนรู้รูปแบบใหม่ๆ เมื่อมีการนำเข้าข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="3a25f-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="3a25f-239">สำหรับตัวอย่างนี้ เลือก **รายเดือน**</span><span class="sxs-lookup"><span data-stu-id="3a25f-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="3a25f-240">หลังจากตรวจสอบรายละเอียดทั้งหมดแล้ว ให้เลือก  **บันทึกและเรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="3a25f-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="3a25f-241">งานที่ 4 - ตรวจสอบผลลัพธ์และคำอธิบายของโมเดล</span><span class="sxs-lookup"><span data-stu-id="3a25f-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="3a25f-242">ให้โมเดลทำการฝึกและให้คะแนนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="3a25f-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="3a25f-243">ถัดไป คุณสามารถรีวิวผลลัพธ์ของโมเดล CLV และคำอธิบายได้</span><span class="sxs-lookup"><span data-stu-id="3a25f-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="3a25f-244">สำหรับข้อมูลเพิ่มเติม โปรดดู [ตรวจสอบสถานะการคาดคะเนและผลลัพธ์](predict-customer-lifetime-value.md#review-prediction-status-and-results)</span><span class="sxs-lookup"><span data-stu-id="3a25f-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="3a25f-245">งานที่ 5 - สร้างเซ็กเมนต์ของลูกค้าที่มีมูลค่าสูง</span><span class="sxs-lookup"><span data-stu-id="3a25f-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="3a25f-246">การรันโมเดลจะสร้างเอนทิตีใหม่ ซึ่งแสดงอยู่บน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="3a25f-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="3a25f-247">คุณสามารถสร้างเซ็กเมนต์ลูกค้าใหม่โดยยึดตามเอนทิตีที่สร้างโดยแบบจำลอง</span><span class="sxs-lookup"><span data-stu-id="3a25f-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="3a25f-248">ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="3a25f-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="3a25f-249">เลือก  **ใหม่** และเลือก **สร้างจาก** > **ระบบอัจฉริยะ**</span><span class="sxs-lookup"><span data-stu-id="3a25f-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![การสร้างเซ็กเมนต์ด้วยผลลัพธ์ของโมเดล](media/segment-intelligence.png)

1. <span data-ttu-id="3a25f-251">เลือกเอนทิตี  **OOBeCommerceCLVPrediction** และกำหนดเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="3a25f-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="3a25f-252">ฟิลด์: CLVScore</span><span class="sxs-lookup"><span data-stu-id="3a25f-252">Field: CLVScore</span></span>
  - <span data-ttu-id="3a25f-253">ตัวดำเนินการ: มากกว่า</span><span class="sxs-lookup"><span data-stu-id="3a25f-253">Operator: greater than</span></span>
  - <span data-ttu-id="3a25f-254">ค่า: 1500</span><span class="sxs-lookup"><span data-stu-id="3a25f-254">Value: 1500</span></span>

1. <span data-ttu-id="3a25f-255">เลือก **รีวิว** และ **บันทึก** เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="3a25f-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="3a25f-256">ตอนนี้คุณมีเซ็กเมนต์ที่ระบุลูกค้าที่คาดว่าจะสร้างรายได้มากกว่า $1500 ใน 12 เดือนข้างหน้า</span><span class="sxs-lookup"><span data-stu-id="3a25f-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="3a25f-257">เซ็กเมนต์นี้ได้รับการอัปเดตแบบไดนามิก หากมีการนำเข้าข้อมูลมากขึ้น</span><span class="sxs-lookup"><span data-stu-id="3a25f-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="3a25f-258">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-258">For more information, see [Create and manage segments](segments.md).</span></span>
