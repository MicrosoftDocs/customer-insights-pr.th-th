---
title: เซ็กเมนต์ที่แนะนำตามกิจกรรม
description: อนุญาตให้การเรียนรู้เกี่ยวกับเครื่องช่วยคุณค้นหาเซ็กเมนต์ที่ใหม่และน่าสนใจตามกิจกรรมของลูกค้า
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034121"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="d8104-103">เซ็กเมนต์ที่แนะนำตามข้อมูลกิจกรรม (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="d8104-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="d8104-104">ค้นหาเซ็กเมนต์ที่น่าสนใจของลูกค้าของคุณตามข้อมูลกิจกรรมของลูกค้าที่ส่งเข้าสู่ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d8104-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="d8104-105">ตัวอย่างของข้อมูลกิจกรรม ได้แก่ ธุรกรรม ระยะเวลาการสนับสนุนการโทร การซื้อ หรือการคืนสินค้า</span><span class="sxs-lookup"><span data-stu-id="d8104-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="d8104-106">เพื่อแนะนำเซ็กเมนต์ ข้อมูลกิจกรรมจะได้รับการวิเคราะห์สำหรับความใหม่ ความถี่ และมูลค่าทางการเงิน (หรือระยะเวลา)</span><span class="sxs-lookup"><span data-stu-id="d8104-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="d8104-107">หรือคุณสามารถสร้าง [เซ็กเมนต์ที่แนะนำเพื่อปรับปรุงการวัด หรือทำความเข้าใจสิ่งที่มีอิทธิพลต่อแอตทริบิวต์ได้ดีขึ้น](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="d8104-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="แท็บเซ็กเมนต์ที่แนะนำซึ่งแสดงคำแนะนำเซ็กเมนต์สำหรับเซ็กเมนต์ที่อิงตามกิจกรรมและตามแอตทริบิวต์":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="d8104-109">จัดหมวดหมู่ลูกค้าตามกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="d8104-109">Categorize customers by activity</span></span>

<span data-ttu-id="d8104-110">ด้วย [ข้อมูลกิจกรรม](activities.md) ที่มีอยู่ใน Customer Insights เราสามารถสร้างคำแนะนำที่แสดงถึงกลุ่มลูกค้า:</span><span class="sxs-lookup"><span data-stu-id="d8104-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="d8104-111">ลูกค้าที่ใช้งานมากที่สุด</span><span class="sxs-lookup"><span data-stu-id="d8104-111">most active customers</span></span> 
- <span data-ttu-id="d8104-112">ลูกค้าที่ทำการซื้อมากที่สุด</span><span class="sxs-lookup"><span data-stu-id="d8104-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="d8104-113">ลูกค้าที่สร้างรายได้มากที่สุด</span><span class="sxs-lookup"><span data-stu-id="d8104-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="d8104-114">ลูกค้าที่ไม่ได้ใช้งานเมื่อเร็วๆ นี้</span><span class="sxs-lookup"><span data-stu-id="d8104-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="d8104-115">ลูกค้าที่ติดต่อกับธุรกิจของคุณบ่อยครั้ง</span><span class="sxs-lookup"><span data-stu-id="d8104-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="d8104-116">หากคุณมีธุรกิจค้าปลีก คุณสามารถค้นหาว่าลูกค้ารายใดสร้างรายได้มากที่สุดและให้รางวัลแก่พวกเขาด้วยคูปอง</span><span class="sxs-lookup"><span data-stu-id="d8104-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="d8104-117">หรือคุณสามารถระบุลูกค้าเป็นครั้งคราวและเสนอให้เข้าร่วมโปรแกรมรางวัล เพื่อให้พวกเขาเยี่ยมชมธุรกิจของคุณบ่อยขึ้น</span><span class="sxs-lookup"><span data-stu-id="d8104-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="d8104-118">หากคุณอยู่ในธุรกิจการดูแลสุขภาพที่ให้บริการด้านการดูแลสุขภาพสาธารณะ และเป้าหมายของคุณคือการลดค่าใช้จ่ายสำหรับผู้ป่วยแต่ละราย</span><span class="sxs-lookup"><span data-stu-id="d8104-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="d8104-119">วิธีที่ทำได้คือ การลดการเข้ารับการตรวจซ้ำโดยให้การดูแลที่ดีที่สุดเท่าที่จะเป็นไปได้ในการเข้ารับการตรวจน้อยที่สุด</span><span class="sxs-lookup"><span data-stu-id="d8104-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="d8104-120">ในกรณีนี้ เป้าหมายของคุณคือ การรักษาความถี่ในการเข้ารับการตรวจให้ต่ำและลดค่าใช้จ่ายที่เกิดขึ้นซ้ำสำหรับผู้ป่วย</span><span class="sxs-lookup"><span data-stu-id="d8104-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="d8104-121">หรือคุณสามารถระบุเซ็กเมนต์ของผู้ป่วยที่มีการนัดหมายบ่อยครั้งและค่าใช้จ่ายที่เกิดซ้ำสูง และวิเคราะห์กรณีเหล่านี้เพื่อปรับปรุงการรักษาของแต่ละบุคคล</span><span class="sxs-lookup"><span data-stu-id="d8104-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="d8104-122">ข้อมูลที่จําเป็น</span><span class="sxs-lookup"><span data-stu-id="d8104-122">Required data</span></span>

<span data-ttu-id="d8104-123">คำแนะนำถูกสร้างขึ้นตามข้อมูลอินพุตที่เลือก</span><span class="sxs-lookup"><span data-stu-id="d8104-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="d8104-124">โปรไฟล์ลูกค้า: ลูกค้าหรือสมาชิกทั้งหมดของเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="d8104-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="d8104-125">ช่วงเวลา: เดือนที่แล้ว ปีที่แล้ว หรือกรอบเวลาที่กำหนดเองใดๆ</span><span class="sxs-lookup"><span data-stu-id="d8104-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="d8104-126">ชนิดกิจกรรม: การซื้อ ธุรกรรมค้าปลีก ธุรกรรมออนไลน์ กรณีการสนับสนุนลูกค้า การสมัครใช้งาน และอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="d8104-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="d8104-127">เอนทิตีใน Customer Insights ที่มีข้อมูลกิจกรรม: เอนทิตี UnifiedActivity หรือเอนทิตีสำหรับกิจกรรมเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="d8104-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="d8104-128">มิติที่จะรวม: ความใหม่ ความถี่ หรือมิติทางการเงิน โดยขึ้นอยู่กับความต้องการทางธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="d8104-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="d8104-129">สร้างเซ็กเมนต์แนะนํา</span><span class="sxs-lookup"><span data-stu-id="d8104-129">Generate suggested segments</span></span>

1. <span data-ttu-id="d8104-130">ไปที่ **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="d8104-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="d8104-131">เลือกแท็บ **ข้อเสนอแนะ (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="d8104-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="d8104-132">เลือก **ค้นหาคำแนะนำใหม่ๆ** และเลือก **ดูหรือคาดการณ์พฤติกรรมของลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="d8104-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="d8104-133">เลือก **เริ่ม** เพื่อเรียกใช้ประสบการณ์ที่แนะนำ</span><span class="sxs-lookup"><span data-stu-id="d8104-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="ขั้นตอนแรกของวิซาร์ดการตั้งค่าคอนฟิกสำหรับเซ็กเมนต์ที่แนะนำตามกิจกรรม":::

1. <span data-ttu-id="d8104-135">ระบุข้อมูลอินพุตที่ต้องการ และเลือกดำเนินการ **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="d8104-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="d8104-136">เลือกลูกค้า: รวมลูกค้าทั้งหมดหรือเซ็กเมนต์เฉพาะ</span><span class="sxs-lookup"><span data-stu-id="d8104-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="d8104-137">เลือกกิจกรรม: เลือกชนิดกิจกรรมและเอนทิตีที่อธิบายกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="d8104-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="d8104-138">การกำหนดลักษณะ: กำหนดช่วงเวลาที่จะพิจารณา ปัจจัยสำหรับข้อเสนอแนะ และแม็ปแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="d8104-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="d8104-139">ตรวจสอบข้อมูลที่คุณป้อน และเลือก **เรียกใช้** เพื่อเรียกใช้โมเดลและสร้างคำแนะนำ</span><span class="sxs-lookup"><span data-stu-id="d8104-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="d8104-140">โดยขึ้นอยู่กับจำนวนโปรไฟล์ของลูกค้าและกิจกรรมที่เลือก อาจใช้เวลาสักครู่จึงจะเสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="d8104-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="d8104-141">หลังจากสร้างคำแนะนำแล้ว คุณสามารถกรองตามมิติหรือค่าที่คุณสนใจมากที่สุด</span><span class="sxs-lookup"><span data-stu-id="d8104-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="d8104-142">ดูรายละเอียดเซ็กเมนต์แนะนํา</span><span class="sxs-lookup"><span data-stu-id="d8104-142">View details of a suggested segment</span></span>

<span data-ttu-id="d8104-143">เมื่อสร้างคำแนะนำแล้ว คุณจะพบใน **เซ็กเมนต์** > **คำแนะนำ (พรีวิว)** ในส่วน **คำแนะนำตามกิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="d8104-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="บานหน้าต่างด้านข้างแบบขยายซึ่งแสดงข้อมูลโดยละเอียดของเซ็กเมนต์ที่แนะนำ":::

<span data-ttu-id="d8104-145">เลือก **ดูข้อเสนอแนะ** ในเซ็กเมนต์ที่แนะนำเพื่อดูรายละเอียดของเซ็กเมนต์นั้น</span><span class="sxs-lookup"><span data-stu-id="d8104-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="d8104-146">บานหน้าต่างด้านข้างให้รายละเอียด เช่น ขอบเขตของแต่ละมิติโดยเปรียบเทียบกับกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d8104-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="d8104-147">นอกจากนี้ ยังเน้นจำนวนสมาชิกที่มีศักยภาพในเซ็กเมนต์และเปอร์เซ็นต์ที่สอดคล้องกันของลูกค้าทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="d8104-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="d8104-148">หากคุณต้องการเก็บคำแนะนำไว้เป็นเซ็กเมนต์ ให้เลือก **สร้างเซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="d8104-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="d8104-149">บันทึกข้อเสนอแนะเป็นเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="d8104-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="d8104-150">ไปที่ **เซ็กเมนต์** > **ข้อเสนอแนะ (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="d8104-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="d8104-151">เลือกเซ็กเมนต์ที่คุณต้องการบันทึก</span><span class="sxs-lookup"><span data-stu-id="d8104-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="d8104-152">ในบานหน้าต่างด้านข้าง เลือก **สร้างเซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="d8104-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="d8104-153">หลังจากบันทึกเซ็กเมนต์แล้ว จะแสดงในรายการของเซ็กเมนต์บนแท็บ **เซ็กเมนต์ทั้งหมด** ซึ่งตอนนี้สามารถ [รีเฟรชหรือลบเหมือนกับเซ็กเมนต์อื่นๆ](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d8104-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="d8104-154">คุณไม่สามารถแก้ไขรายละเอียดเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="d8104-154">You can't edit the segment details.</span></span> <span data-ttu-id="d8104-155">อย่างไรก็ตาม คุณสามารถเปลี่ยนเกณฑ์การป้อนข้อมูลสำหรับคำแนะนำ และสร้างคำแนะนำที่แตกต่างกันได้</span><span class="sxs-lookup"><span data-stu-id="d8104-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="d8104-156">รีเฟรชหรือแก้ไขชุดข้อเสนอแนะ</span><span class="sxs-lookup"><span data-stu-id="d8104-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="d8104-157">ไปที่ **เซ็กเมนต์** > **คำแนะนำ (พรีวิว)** และค้นหาเซ็กเมนต์ในส่วน **คำแนะนำตามกิจกรรม**</span><span class="sxs-lookup"><span data-stu-id="d8104-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="d8104-158">เลือก **รีเฟรชข้อเสนอแนะ** เพื่อรีเฟรชข้อเสนอแนะในขณะที่ยังคงแอตทริบิวต์ที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="d8104-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="d8104-159">หรือเลือก **แก้ไขคำแนะนำ** เพื่อแก้ไขแอตทริบิวต์ที่มีการตั้งค่าคอนฟิก</span><span class="sxs-lookup"><span data-stu-id="d8104-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="d8104-160">ระบบจะเรียกใช้กระบวนการอีกครั้ง สร้างคำแนะนำเซ็กเมนต์ตามข้อมูลล่าสุด และแทนที่คำแนะนำปัจจุบัน</span><span class="sxs-lookup"><span data-stu-id="d8104-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
