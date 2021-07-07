---
title: คู่มือตัวอย่างสำหรับการคาดคะเนการบอกเลิกการสมัครสมาชิก
description: ใช้คู่มือตัวอย่างนี้เพื่อทดลองใช้โมเดลการคาดคะเนการบอกเลิกการสมัครสมาชิกแบบสำเร็จรูป
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306326"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1566b-103">คู่มือตัวอย่างการคาดคะเนการบอกเลิกการสมัครสมาชิก (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="1566b-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1566b-104">เราจะอธิบายตัวอย่างแบบตั้งแต่ต้นจนจบของการคาดคะเนการบอกเลิกการสมัครสมาชิกโดยใช้ข้อมูลตัวอย่างที่ให้ไว้ด้านล่าง</span><span class="sxs-lookup"><span data-stu-id="1566b-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1566b-105">สถานการณ์สมมติ</span><span class="sxs-lookup"><span data-stu-id="1566b-105">Scenario</span></span>

<span data-ttu-id="1566b-106">Contoso เป็นบริษัทที่ผลิตกาแฟและเครื่องชงกาแฟคุณภาพสูง ซึ่งขายผ่านเว็บไซต์กาแฟ Contoso ของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="1566b-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1566b-107">พวกเขาเพิ่งเริ่มธุรกิจแบบการสมัครสมาชิกเพื่อให้ลูกค้าได้ดื่มกาแฟเป็นประจำ</span><span class="sxs-lookup"><span data-stu-id="1566b-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1566b-108">เป้าหมายของพวกเขาคือการทำความเข้าใจลูกค้าที่สมัครสมาชิกอาจยกเลิกการสมัครสมาชิกในอีกไม่กี่เดือนข้างหน้า</span><span class="sxs-lookup"><span data-stu-id="1566b-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1566b-109">รู้ว่าลูกค้าของพวกเขารายใด **มีแนวโน้มที่จะเลิกใช้บริการ** สามารถช่วยให้พวกเขาประหยัดความพยายามทางการตลาดโดยมุ่งเน้นที่การรักษาลูกค้าเอาไว้</span><span class="sxs-lookup"><span data-stu-id="1566b-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1566b-110">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="1566b-110">Prerequisites</span></span>

- <span data-ttu-id="1566b-111">อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1566b-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1566b-112">เราขอแนะนำให้คุณดำเนินการตามขั้นตอนต่อไปนี้ [ในสภาพแวดล้อมใหม่](manage-environments.md)</span><span class="sxs-lookup"><span data-stu-id="1566b-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1566b-113">งานที่ 1 - นำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1566b-114">ตรวจสอบบทความ [เกี่ยวกับการนำเข้าข้อมูล](data-sources.md) และ [การนำเข้าแหล่งข้อมูลโดยใช้ตัวเชื่อมต่อ Power Query](connect-power-query.md) โดยเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="1566b-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1566b-115">ข้อมูลต่อไปนี้ถือว่าคุณคุ้นเคยกับการนำเข้าข้อมูลโดยทั่วไป</span><span class="sxs-lookup"><span data-stu-id="1566b-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1566b-116">นำเข้าข้อมูลลูกค้าจากแพลตฟอร์มอีคอมเมิร์ซ</span><span class="sxs-lookup"><span data-stu-id="1566b-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1566b-117">สร้างแหล่งข้อมูลที่ชื่อ **อีคอมเมิร์ซ** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="1566b-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1566b-118">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscontacts</span><span class="sxs-lookup"><span data-stu-id="1566b-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1566b-119">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="1566b-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1566b-120">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="1566b-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1566b-121">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="1566b-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1566b-122">**CreatedOn**: วันที่/เวลา/โซน</span><span class="sxs-lookup"><span data-stu-id="1566b-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="เปลี่ยนวันเดือนปีเกิดเป็นวันที่":::

1. <span data-ttu-id="1566b-124">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="1566b-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1566b-125">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1566b-126">นำเข้าข้อมูลลูกค้าจากแบบแผนความภักดี</span><span class="sxs-lookup"><span data-stu-id="1566b-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1566b-127">สร้างแหล่งข้อมูลที่ชื่อ **LoyaltyScheme** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="1566b-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1566b-128">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasscustomerloyalty</span><span class="sxs-lookup"><span data-stu-id="1566b-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1566b-129">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="1566b-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1566b-130">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="1566b-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1566b-131">**DateOfBirth**: วันที่</span><span class="sxs-lookup"><span data-stu-id="1566b-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1566b-132">**RewardsPoints**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="1566b-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1566b-133">**CreatedOn**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="1566b-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1566b-134">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="1566b-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1566b-135">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1566b-136">นำเข้าข้อมูลการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="1566b-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1566b-137">สร้างแหล่งข้อมูลที่ชื่อ **SubscriptionHistory** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="1566b-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1566b-138">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadchurnsubscriptionhistory</span><span class="sxs-lookup"><span data-stu-id="1566b-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1566b-139">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="1566b-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1566b-140">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="1566b-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1566b-141">**SubscriptioID**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="1566b-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1566b-142">**SubscriptionAmount**: สกุลเงิน</span><span class="sxs-lookup"><span data-stu-id="1566b-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1566b-143">**SubscriptionEndDate**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="1566b-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1566b-144">**SubscriptionStartDate**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="1566b-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1566b-145">**TransactionDate**: วันที่/เวลา</span><span class="sxs-lookup"><span data-stu-id="1566b-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1566b-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="1566b-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1566b-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="1566b-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1566b-148">**RecurringFrequencyInMonths**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="1566b-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1566b-149">ในฟิลด์ **ชื่อ** ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **SubscriptionHistory**</span><span class="sxs-lookup"><span data-stu-id="1566b-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1566b-150">บันทึกแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1566b-151">นำเข้าข้อมูลลูกค้าจากบทวิจารณ์เว็บไซต์</span><span class="sxs-lookup"><span data-stu-id="1566b-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1566b-152">สร้างแหล่งข้อมูลที่ชื่อ **เว็บไซต์** เลือกตัวเลือกการนำเข้าและเลือกตัวเชื่อมต่อ **ข้อความ/CSV**</span><span class="sxs-lookup"><span data-stu-id="1566b-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1566b-153">ป้อน URL สำหรับผู้ติดต่ออีคอมเมิร์ซ https://aka.ms/ciadclasswebsite</span><span class="sxs-lookup"><span data-stu-id="1566b-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1566b-154">ในขณะแก้ไขข้อมูล ให้เลือก **แปลง** แล้ว **ใช้แถวแรกเป็นส่วนหัว**</span><span class="sxs-lookup"><span data-stu-id="1566b-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1566b-155">ปรับปรุงชนิดข้อมูลสำหรับคอลัมน์ที่แสดงด้านล่าง:</span><span class="sxs-lookup"><span data-stu-id="1566b-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1566b-156">**ReviewRating**: จำนวนเต็ม</span><span class="sxs-lookup"><span data-stu-id="1566b-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1566b-157">**ReviewDate**: วันที่</span><span class="sxs-lookup"><span data-stu-id="1566b-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1566b-158">ในฟิลด์ "ชื่อ" ในบานหน้าต่างด้านขวา ให้เปลี่ยนชื่อแหล่งข้อมูลจาก **การสอบถาม** เป็น **webReviews**</span><span class="sxs-lookup"><span data-stu-id="1566b-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1566b-159">งานที่ 2 - การรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1566b-160">หลังจากนำเข้าข้อมูลตอนนี้เราเริ่มต้นกระบวนการ **แมป, จับคู่, ผสาน** เพื่อสร้างโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="1566b-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1566b-161">สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [การรวมข้อมูล](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="1566b-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1566b-162">แมป</span><span class="sxs-lookup"><span data-stu-id="1566b-162">Map</span></span>

1. <span data-ttu-id="1566b-163">หลังจากนำเข้าข้อมูลแล้ว ให้จับคู่ผู้ติดต่อจากข้อมูลอีคอมเมิร์ซและความภักดีกับชนิดข้อมูลทั่วไป</span><span class="sxs-lookup"><span data-stu-id="1566b-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1566b-164">ไปที่ **ข้อมูล** > **รวม** > **แมป**</span><span class="sxs-lookup"><span data-stu-id="1566b-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1566b-165">เลือกเอนทิตีที่แสดงถึงโปรไฟล์ลูกค้า - **eCommerceContacts** และ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="1566b-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="รวมแหล่งข้อมูลอีคอมเมิร์ซและความภักดี":::

1. <span data-ttu-id="1566b-167">เลือก **ContactId** เป็นคีย์หลักสำหรับ **eCommerceContacts** และ **LoyaltyID** เป็นคีย์หลักสำหรับ **loyCustomers**</span><span class="sxs-lookup"><span data-stu-id="1566b-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="รวม LoyaltyId เป็นคีย์หลัก":::

### <a name="match"></a><span data-ttu-id="1566b-169">การจับคู่</span><span class="sxs-lookup"><span data-stu-id="1566b-169">Match</span></span>

1. <span data-ttu-id="1566b-170">ไปที่แท็บ **จับคู่** และเลือก **ตั้งค่าลำดับ**</span><span class="sxs-lookup"><span data-stu-id="1566b-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1566b-171">ในรายการแบบหล่นลง **หลัก** เลือก **eCommerceContacts: eCommerce** เป็นแหล่งที่มาหลักและรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="1566b-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1566b-172">ในรายการแบบหล่นลง **เอนทิตี 2** เลือก **oyCustomers : LoyaltyScheme** และรวมเรกคอร์ดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="1566b-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="รวมอีคอมเมิร์ซและความภักดีที่ตรงกัน":::

1. <span data-ttu-id="1566b-174">เลือก **สร้างกฎใหม่**</span><span class="sxs-lookup"><span data-stu-id="1566b-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1566b-175">เพิ่มเงื่อนไขแรกของคุณโดยใช้ FullName</span><span class="sxs-lookup"><span data-stu-id="1566b-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1566b-176">สำหรับ eCommerceContacts เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1566b-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="1566b-177">สำหรับ loyCustomers เลือก **FullName** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1566b-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="1566b-178">เลือกรายการแบบหล่นลง **ทำให้เป็นมาตรฐาน** และเลือก **ชนิด (โทรศัพท์, ชื่อ, ที่อยู่... )**</span><span class="sxs-lookup"><span data-stu-id="1566b-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1566b-179">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="1566b-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1566b-180">ป้อนชื่อ **ชื่อเต็ม, อีเมล** สำหรับกฎใหม่</span><span class="sxs-lookup"><span data-stu-id="1566b-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1566b-181">เพิ่มเงื่อนไขที่สองสำหรับที่อยู่อีเมลโดยการเลือก **เพิ่มเงื่อนไข**</span><span class="sxs-lookup"><span data-stu-id="1566b-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1566b-182">สำหรับเอนทิตี eCommerceContacts เลือก **EMail** ในเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1566b-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="1566b-183">สำหรับเอนทิตี loyCustomers เลือก **EMail** ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1566b-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="1566b-184">ปล่อยให้ ทำให้เป็นมาตรฐาน ว่างไว้</span><span class="sxs-lookup"><span data-stu-id="1566b-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1566b-185">ตั้งค่า **ระดับความแม่นยำ**: **พื้นฐาน** และ **ค่า**: **สูง**</span><span class="sxs-lookup"><span data-stu-id="1566b-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="รวมกฎการจับคู่สำหรับชื่อและอีเมล":::

7. <span data-ttu-id="1566b-187">เลือก **บันทึก** และ **เรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="1566b-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1566b-188">ผสาน</span><span class="sxs-lookup"><span data-stu-id="1566b-188">Merge</span></span>

1. <span data-ttu-id="1566b-189">ไปที่แท็บ **ผสาน**</span><span class="sxs-lookup"><span data-stu-id="1566b-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1566b-190">ในเอนทิตี **ContactId** สำหรับ **loyCustomers** เปลี่ยนชื่อที่แสดงเป็น **ContactIdLOYALTY** เพื่อทำให้แตกต่างจากรหัสอื่นๆ ที่ส่งเข้ามา</span><span class="sxs-lookup"><span data-stu-id="1566b-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="เปลี่ยนชื่อ contactid จากรหัสความภักดี":::

1. <span data-ttu-id="1566b-192">เลือก **บันทึก** และ **เรียกใช้** เพื่อเริ่มกระบวนการผสาน</span><span class="sxs-lookup"><span data-stu-id="1566b-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1566b-193">งานที่ 3 - กำหนดค่าการคาดคะเนการบอกเลิกการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="1566b-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1566b-194">ด้วยโปรไฟล์ลูกค้ารวมเข้าด้วยกัน ตอนนี้เราสามารถเรียกใช้การคาดคะเนการเลิกทำธุรรกรรม</span><span class="sxs-lookup"><span data-stu-id="1566b-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1566b-195">สำหรับขั้นตอนโดยละเอียด โปรดดูบทความ [การคาดคะเนการเลิกทำธุรรกรรม (พรีวิว)](predict-subscription-churn.md)</span><span class="sxs-lookup"><span data-stu-id="1566b-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1566b-196">ไปที่ **ระบบอัจฉริยะ** > **ค้นพบ** และเลือกใช้ **โมเดลการเลิกใช้บริการของลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="1566b-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1566b-197">เลือกตัวเลือก **การสมัครใช้งาน** และเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="1566b-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1566b-198">ตั้งชื่อโมเดล **การคาดคะเนการบอกเลิกการสมัครสมาชิก OOB** และเอนทิตีผลลัพธ์ **OOBSubscriptionChurnPrediction**</span><span class="sxs-lookup"><span data-stu-id="1566b-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1566b-199">กำหนดเงื่อนไขสองประการสำหรับโมเดลการเลิกใช้บริการ:</span><span class="sxs-lookup"><span data-stu-id="1566b-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1566b-200">**วันนับตั้งแต่การสมัครใช้งานสิ้นสุดลง**: **อย่างน้อย 60** วัน</span><span class="sxs-lookup"><span data-stu-id="1566b-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1566b-201">หากลูกค้ายังไม่ได้ต่ออายุการสมัครสมาชิกเป็นระยะเวลานี้หลังจากหมดอายุการเป็นสมาชิก จะถือว่าพวกเขาเลิกใช้งาน</span><span class="sxs-lookup"><span data-stu-id="1566b-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1566b-202">**การกำหนดการเลิกใช้**: **อย่างน้อย 93** วัน</span><span class="sxs-lookup"><span data-stu-id="1566b-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1566b-203">ระยะเวลาที่โมเดลคาดคะเนว่าลูกค้ารายใดอาจเลิกใช้</span><span class="sxs-lookup"><span data-stu-id="1566b-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1566b-204">ยิ่งคุณมองอนาคตไกลเท่าไร ผลลัพธ์ก็จะยิ่งแม่นยำน้อยลงเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="1566b-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="เลือกวิธีการของโมเดลกรอบเวลาการคาดคะเนและการกำหนดการเลิกใช้":::

1. <span data-ttu-id="1566b-206">เลือก **เพิ่มข้อมูลที่จำเป็น** และเลือก **เพิ่มข้อมูล** สำหรับประวัติการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="1566b-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1566b-207">เพิ่มเอนทิตี **การสมัครสมาชิก : SubscriptionHistory** และแมปฟิลด์จากอีคอมเมิร์ซไปยังฟิลด์ที่สอดคล้องกันที่โมเดลต้องการ</span><span class="sxs-lookup"><span data-stu-id="1566b-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1566b-208">รวมเอนทิตี **การสมัครสมาชิก : SubscriptionHistory** กับ **eCommerceContacts : อีคอมเมิร์ซ** ตั้งชื่อความสัมพันธ์ **eCommerceSubscription**</span><span class="sxs-lookup"><span data-stu-id="1566b-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="รวมเอนทิตี eCommerce":::

1. <span data-ttu-id="1566b-210">ภายใต้กิจกรรมของลูกค้า ให้เพิ่มเอนทิตี **webReviews : เว็บไซต์** และแมปฟิลด์จาก webReviews กับฟิลด์ที่สอดคล้องกันที่โมเดลต้องการ</span><span class="sxs-lookup"><span data-stu-id="1566b-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1566b-211">คีย์หลัก: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1566b-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1566b-212">ประทับเวลา: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1566b-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1566b-213">เหตุการณ์: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1566b-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1566b-214">กำหนดค่ากิจกรรมสำหรับบทวิจารณ์เว็บไซต์</span><span class="sxs-lookup"><span data-stu-id="1566b-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1566b-215">เลือกกิจกรรม **บทวิจารณ์** และรวมเอนทิตี **webReviews: เว็บไซต์** กับ **eCommerceContacts : eCommerce**</span><span class="sxs-lookup"><span data-stu-id="1566b-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1566b-216">เลือก **ถัดไป** เพื่อตั้งกำหนดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="1566b-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1566b-217">โมเดลจำเป็นต้องฝึกอย่างสม่ำเสมอเพื่อเรียนรู้รูปแบบใหม่เมื่อมีการนำเข้าข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="1566b-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1566b-218">สำหรับตัวอย่างนี้ เลือก **รายเดือน**</span><span class="sxs-lookup"><span data-stu-id="1566b-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1566b-219">หลังจากตรวจสอบรายละเอียดทั้งหมดแล้ว ให้เลือก **บันทึกและเรียกใช้**</span><span class="sxs-lookup"><span data-stu-id="1566b-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1566b-220">งานที่ 4 - ตรวจสอบผลลัพธ์และคำอธิบายของโมเดล</span><span class="sxs-lookup"><span data-stu-id="1566b-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1566b-221">ให้โมเดลทำการฝึกและให้คะแนนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1566b-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1566b-222">ตอนนี้คุณสามารถตรวจสอบคำอธิบายโมเดลการบอกเลิกการสมัครสมาชิกได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="1566b-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1566b-223">สำหรับข้อมูลเพิ่มเติม โปรดดู [ตรวจสอบสถานะการคาดคะเนและผลลัพธ์](predict-subscription-churn.md#review-a-prediction-status-and-results)</span><span class="sxs-lookup"><span data-stu-id="1566b-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1566b-224">งานที่ 5 - สร้างเซ็กเมนต์ของลูกค้าที่มีความเสี่ยงในการเลิกใช้บริการสูง</span><span class="sxs-lookup"><span data-stu-id="1566b-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1566b-225">การเรียกใช้โมเดลการทำงานจริงจะสร้างเอนทิตีใหม่ที่คุณสามารถมองเห็นได้ใน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="1566b-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1566b-226">คุณสามารถสร้างเซ็กเมนต์ใหม่โดยยึดตามเอนทิตีที่สร้างโดยโมเดล</span><span class="sxs-lookup"><span data-stu-id="1566b-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1566b-227">ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="1566b-227">Go to **Segments**.</span></span> <span data-ttu-id="1566b-228">เลือก **ใหม่** และเลือก **สร้างจาก** > **ระบบอัจฉริยะ**</span><span class="sxs-lookup"><span data-stu-id="1566b-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="การสร้างเซ็กเมนต์ด้วยผลลัพธ์ของโมเดล":::

1. <span data-ttu-id="1566b-230">เลือกจุดสิ้นสุด **OOBSubscriptionChurnPrediction** และกำหนดเซ็กเมนต์:</span><span class="sxs-lookup"><span data-stu-id="1566b-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1566b-231">ฟิลด์: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1566b-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1566b-232">ตัวดำเนินการ: มากกว่า</span><span class="sxs-lookup"><span data-stu-id="1566b-232">Operator: greater than</span></span>
   - <span data-ttu-id="1566b-233">ค่า: 0.6</span><span class="sxs-lookup"><span data-stu-id="1566b-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="ตั้งค่าเซ็กเมนต์การบอกเลิกการสมัครสมาชิก":::

<span data-ttu-id="1566b-235">ตอนนี้คุณมีเซ็กเมนต์ที่ปรับปรุงแบบไดนามิกซึ่งระบุลูกค้าที่มีความเสี่ยงสูงที่จะเลิกใช้บริการสำหรับธุรกิจที่มีการสมัครสมาชิกนี้</span><span class="sxs-lookup"><span data-stu-id="1566b-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1566b-236">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="1566b-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]