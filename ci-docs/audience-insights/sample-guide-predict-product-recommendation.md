---
title: คู่มือตัวอย่างการคาดคะเนคำแนะนำผลิตภัณฑ์
description: ใช้คู่มือตัวอย่างนี้เพื่อทดลองใช้โมเดลการคาดคะเนคำแนะนำผลิตภัณฑ์แบบสำเร็จรูป
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306189"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="b0d8a-103">คู่มือตัวอย่างการคาดคะเนคำแนะนำผลิตภัณฑ์ (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="b0d8a-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="b0d8a-104">เราจะอธิบายตัวอย่างแบบตั้งแต่ต้นจนจบของการคาดคะเนคำแนะนำผลิตภัณฑ์โดยใช้ข้อมูลตัวอย่างที่ให้ไว้ด้านล่าง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="b0d8a-105">สถานการณ์สมมติ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-105">Scenario</span></span>

<span data-ttu-id="b0d8a-106">Contoso เป็นบริษัทที่ผลิตกาแฟและเครื่องชงกาแฟคุณภาพสูง ซึ่งขายผ่านเว็บไซต์กาแฟ Contoso ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="b0d8a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="b0d8a-107">เป้าหมายของพวกเขาคือการทำความเข้าใจว่าควรแนะนำผลิตภัณฑ์ใดให้กับลูกค้าประจำ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="b0d8a-108">การรู้ว่าลูกค้า **มีแนวโน้มที่จะซื้อ** อะไรสามารถช่วยให้พวกเขาประหยัดความพยายามทางการตลาดโดยมุ่งเน้นไปที่สินค้าเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0d8a-109">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="b0d8a-109">Prerequisites</span></span>

- <span data-ttu-id="b0d8a-110">อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b0d8a-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="b0d8a-111">เราขอแนะนำให้คุณดำเนินการตามขั้นตอนต่อไปนี้ [ในสภาพแวดล้อมใหม่](manage-environments.md)</span><span class="sxs-lookup"><span data-stu-id="b0d8a-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b0d8a-112">งานที่ 1 - นำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="b0d8a-113">ตรวจสอบบทความ [เกี่ยวกับการนำเข้าข้อมูล](data-sources.md) และ [การนำเข้าแหล่งข้อมูลโดยใช้ตัวเชื่อมต่อ Power Query](connect-power-query.md) โดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="b0d8a-114">ข้อมูลต่อไปนี้ถือว่าคุณคุ้นเคยกับการนำเข้าข้อมูลโดยทั่วไป</span><span class="sxs-lookup"><span data-stu-id="b0d8a-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b0d8a-115">นำเข้าข้อมูลลูกค้าจากแพลตฟอร์มอีคอมเมิร์ซ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b0d8a-116">สร้างแหล่งข้อมูลที่ชื่อ **อีคอมเมิร์ซ** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b0d8a-117">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscontacts</span><span class="sxs-lookup"><span data-stu-id="b0d8a-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="b0d8a-118">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b0d8a-119">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="b0d8a-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b0d8a-120">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="b0d8a-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b0d8a-121">**CreatedOn**: วันที่/เวลา/โซน</span><span class="sxs-lookup"><span data-stu-id="b0d8a-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="เปลี่ยนวันเดือนปีเกิดเป็นวันที่":::

5. <span data-ttu-id="b0d8a-123">ในฟิลด์ "ชื่อ" ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="b0d8a-124">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b0d8a-125">นำเข้าข้อมูลการซื้อออนไลน์</span><span class="sxs-lookup"><span data-stu-id="b0d8a-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="b0d8a-126">เพิ่มชุดข้อมูลอื่นให้เหมือนกันแหล่งข้อมูล **อีคอมเมิร์ซ**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b0d8a-127">เลือกตัวเชื่อมต่อ **ข้อความ/CSV** อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b0d8a-128">ป้อน URL สำหรับข้อมูล **การซื้อออนไลน์** https://aka.ms/ciadclassonline</span><span class="sxs-lookup"><span data-stu-id="b0d8a-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b0d8a-129">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b0d8a-130">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="b0d8a-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b0d8a-131">**PurchasedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="b0d8a-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b0d8a-132">**TotalPrice**: สกุลเงิน</span><span class="sxs-lookup"><span data-stu-id="b0d8a-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="b0d8a-133">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านข้าง ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommercePurchases**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b0d8a-134">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b0d8a-135">นำเข้าข้อมูลลูกค้าจากแบบแผนความภักดี</span><span class="sxs-lookup"><span data-stu-id="b0d8a-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b0d8a-136">สร้างแหล่งข้อมูลที่ชื่อ **LoyaltyScheme** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b0d8a-137">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscustomerloyalty</span><span class="sxs-lookup"><span data-stu-id="b0d8a-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b0d8a-138">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b0d8a-139">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="b0d8a-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b0d8a-140">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="b0d8a-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b0d8a-141">**RewardsPoints**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="b0d8a-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b0d8a-142">**CreatedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="b0d8a-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b0d8a-143">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b0d8a-144">**บันทึก** แหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="b0d8a-145">งานที่ 2 - การรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-145">Task 2 - Data unification</span></span>

<span data-ttu-id="b0d8a-146">หลังจากนำเข้าข้อมูลแล้ว ตอนนี้เราเริ่มกระบวนการรวมข้อมูลเพื่อสร้างโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="b0d8a-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="b0d8a-147">สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [การรวมข้อมูล](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="b0d8a-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b0d8a-148">แมป</span><span class="sxs-lookup"><span data-stu-id="b0d8a-148">Map</span></span>

1. <span data-ttu-id="b0d8a-149">หลังจากนำเข้าข้อมูลแล้ว ให้จับคู่ผู้ติดต่อจากข้อมูลอีคอมเมิร์ซและความภักดีกับชนิดข้อมูลทั่วไป</span><span class="sxs-lookup"><span data-stu-id="b0d8a-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b0d8a-150">ไปที่ **ข้อมูล** > **รวม** > **แมป**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="b0d8a-151">เลือกเอนทิตีที่แสดงถึงโปรไฟล์ลูกค้า - **eCommerceContacts** และ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![รวมแหล่งข้อมูลอีคอมเมิร์ซและความภักดี](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="b0d8a-153">เลือก **ContactId** เป็นคีย์หลักสำหรับ **eCommerceContacts** และ **LoyaltyID** เป็นคีย์หลักสำหรับ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![รวม LoyaltyId เป็นคีย์หลัก](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="b0d8a-155">การจับคู่</span><span class="sxs-lookup"><span data-stu-id="b0d8a-155">Match</span></span>

1. <span data-ttu-id="b0d8a-156">ไปที่แท็บ **จับคู่** และเลือก **ตั้งค่าลำดับ**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="b0d8a-157">ในรายการแบบหล่นลง **หลัก** เลือก **eCommerceContacts: eCommerce** เป็นแหล่งที่มาหลักและรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="b0d8a-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="b0d8a-158">ในรายการแบบหล่นลง **เอนทิตี 2** เลือก **oyCustomers : LoyaltyScheme** และรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="b0d8a-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![รวมอีคอมเมิร์ซและความภักดีที่ตรงกัน](media/unify-match-order.png)

4. <span data-ttu-id="b0d8a-160">เลือก **สร้างกฎใหม่**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="b0d8a-161">เพิ่มเงื่อนไขแรกของคุณโดยใช้ FullName</span><span class="sxs-lookup"><span data-stu-id="b0d8a-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="b0d8a-162">สำหรับ eCommerceContacts เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b0d8a-163">สำหรับ loyCustomers เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b0d8a-164">เลือกรายการแบบหล่นลง **ทำให้เป็นมาตรฐาน** และเลือก **ชนิด (โทรศัพท์, ชื่อ, ที่อยู่... )**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="b0d8a-165">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="b0d8a-166">ป้อนชื่อ **ชื่อเต็ม, อีเมล** สำหรับกฎใหม่</span><span class="sxs-lookup"><span data-stu-id="b0d8a-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="b0d8a-167">เพิ่มเงื่อนไขที่สองสำหรับที่อยู่อีเมลโดยการเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="b0d8a-168">สำหรับเอนทิตี eCommerceContacts เลือก **EMail** ในเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="b0d8a-169">สำหรับเอนทิตี loyCustomers เลือก **EMail** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="b0d8a-170">ปล่อยให้ ทำให้เป็นมาตรฐาน ว่างไว้</span><span class="sxs-lookup"><span data-stu-id="b0d8a-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="b0d8a-171">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![รวมกฎการจับคู่สำหรับชื่อและอีเมล](media/unify-match-rule.png)

7. <span data-ttu-id="b0d8a-173">เลือก **บันทึก** และ **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b0d8a-174">ผสาน</span><span class="sxs-lookup"><span data-stu-id="b0d8a-174">Merge</span></span>

1. <span data-ttu-id="b0d8a-175">ไปที่แท็บ **ผสาน**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b0d8a-176">ในเอนทิตี **ContactId** สำหรับ **loyCustomers** เปลี่ยนชื่อที่แสดงเป็น **ContactIdLOYALTY** เพื่อทำให้แตกต่างจากรหัสอื่นๆ ที่ส่งเข้ามา</span><span class="sxs-lookup"><span data-stu-id="b0d8a-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![เปลี่ยนชื่อ contactid จากรหัสความภักดี](media/unify-merge-contactid.png)

1. <span data-ttu-id="b0d8a-178">เลือก **บันทึก** และ **เรียกใช้** เพื่อเริ่มกระบวนการผสาน</span><span class="sxs-lookup"><span data-stu-id="b0d8a-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="b0d8a-179">งาน 3 - กำหนดค่าการคาดคะเนคำแนะนำผลิตภัณฑ์</span><span class="sxs-lookup"><span data-stu-id="b0d8a-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="b0d8a-180">ด้วยโปรไฟล์ลูกค้ารวมเข้าด้วยกัน ตอนนี้เราสามารถเรียกใช้การคาดคะเนการเลิกทำธุรรกรรม</span><span class="sxs-lookup"><span data-stu-id="b0d8a-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="b0d8a-181">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** เลือก **คำแนะนำผลิตภัณฑ์**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="b0d8a-182">เลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-182">Select **Get started**.</span></span>

1. <span data-ttu-id="b0d8a-183">ตั้งชื่อแบบจำลอง **การคาดคะเนแบบจำลองคำแนะนำผลิตภัณฑ์ OOB** และเอนทิตีผลลัพธ์ **OOBProductRecommendationModelPrediction**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="b0d8a-184">กำหนดเงื่อนไขสามประการสำหรับแบบจำลอง:</span><span class="sxs-lookup"><span data-stu-id="b0d8a-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="b0d8a-185">**จำนวนผลิตภัณฑ์**: ตั้งค่านี้เป็น **5**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="b0d8a-186">การตั้งค่านี้กำหนดจำนวนผลิตภัณฑ์ที่คุณต้องการแนะนำให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="b0d8a-187">**คาดว่าจะซื้อซ้ำ**: เลือก **ใช่** เพื่อระบุว่าคุณต้องการรวมผลิตภัณฑ์ไว้ในคำแนะนำที่ลูกค้าของคุณเคยซื้อมาก่อน</span><span class="sxs-lookup"><span data-stu-id="b0d8a-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="b0d8a-188">**หน้าต่างการมองย้อนกลับ:** เลือกอย่างน้อย **365 วัน**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="b0d8a-189">การตั้งค่านี้กำหนดว่าแบบจำลองจะย้อนกลับไปดูกิจกรรมของลูกค้านานแค่ไหนเพื่อใช้เป็นข้อมูลในการแนะนำ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="การกำหนดลักษณะแบบจำลองสำหรับแบบจำลองคำแนะนำผลิตภัณฑ์":::

1. <span data-ttu-id="b0d8a-191">เลือก **ข้อมูลที่จำเป็น** และเลือก **เพิ่มข้อมูล** สำหรับประวัติการซื้อ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="b0d8a-192">เพิ่มเอนทิตี **eCommercePurchases : eCommerce** และแมปฟิลด์จากอีคอมเมิร์ซไปยังฟิลด์ที่สอดคล้องกันที่โมเดลต้องการ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="b0d8a-193">รวมเอนทิตี **eCommercePurchases : eCommerce** กับ **eCommerceContacts : eCommerce**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![รวมเอนทิตี eCommerce](media/model-purchase-join.png)

1. <span data-ttu-id="b0d8a-195">เลือก **ถัดไป** เพื่อตั้งกำหนดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b0d8a-196">โมเดลจำเป็นต้องฝึกอย่างสม่ำเสมอเพื่อเรียนรู้รูปแบบใหม่เมื่อมีการนำเข้าข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="b0d8a-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="b0d8a-197">สำหรับตัวอย่างนี้ เลือก **รายเดือน**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="b0d8a-198">หลังจากตรวจสอบรายละเอียดทั้งหมดแล้ว ให้เลือก **บันทึกและเรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b0d8a-199">งานที่ 4 - ตรวจสอบผลลัพธ์และคำอธิบายของโมเดล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b0d8a-200">ให้โมเดลทำการฝึกและให้คะแนนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b0d8a-201">ตอนนี้คุณสามารถตรวจสอบคำอธิบายแบบจำลองคำแนะนำผลิตภัณฑ์ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="b0d8a-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="b0d8a-202">สำหรับข้อมูลเพิ่มเติม โปรดดู [ตรวจสอบสถานะการคาดคะเนและผลลัพธ์](predict-subscription-churn.md#review-a-prediction-status-and-results)</span><span class="sxs-lookup"><span data-stu-id="b0d8a-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="b0d8a-203">งาน 5 - สร้างเซ็กเมนต์ผลิตภัณฑ์ที่มีการซื้อสูง</span><span class="sxs-lookup"><span data-stu-id="b0d8a-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="b0d8a-204">การเรียกใช้โมเดลการทำงานจริงจะสร้างเอนทิตีใหม่ที่คุณสามารถมองเห็นได้ใน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="b0d8a-205">คุณสามารถสร้างเซ็กเมนต์ใหม่โดยยึดตามเอนทิตีที่สร้างโดยโมเดล</span><span class="sxs-lookup"><span data-stu-id="b0d8a-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="b0d8a-206">ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-206">Go to **Segments**.</span></span> <span data-ttu-id="b0d8a-207">เลือก **ใหม่** และเลือก **สร้างจาก** > **ระบบอัจฉริยะ**</span><span class="sxs-lookup"><span data-stu-id="b0d8a-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![การสร้างเซ็กเมนต์ด้วยผลลัพธ์ของโมเดล](media/segment-intelligence.png)

1. <span data-ttu-id="b0d8a-209">เลือกจุดสิ้นสุด **OOBProductRecommendationModelPrediction** และกำหนดเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="b0d8a-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="b0d8a-210">ฟิลด์: ProductID</span><span class="sxs-lookup"><span data-stu-id="b0d8a-210">Field: ProductID</span></span>
   - <span data-ttu-id="b0d8a-211">ตัวดำเนินการ: ค่า</span><span class="sxs-lookup"><span data-stu-id="b0d8a-211">Operator: Value</span></span>
   - <span data-ttu-id="b0d8a-212">ค่า: เลือกรหัสผลิตภัณฑ์สามอันดับแรก</span><span class="sxs-lookup"><span data-stu-id="b0d8a-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="สร้างเซ็กเมนต์จากผลลัพธ์แบบจำลอง":::

<span data-ttu-id="b0d8a-214">ขณะนี้คุณมีเซ็กเมนต์ที่ได้รับการอัปเดตแบบไดนามิกซึ่งระบุลูกค้าที่เต็มใจซื้อผลิตภัณฑ์ที่แนะนำมากที่สุดสามรายการ</span><span class="sxs-lookup"><span data-stu-id="b0d8a-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="b0d8a-215">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b0d8a-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
