---
title: กรอกข้อมูลบางส่วนโดยใช้การคาดคะเน
description: ใช้การคาดคะเนเพื่อกรอกข้อมูลลูกค้าที่ไม่สมบูรณ์
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648734"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="79725-103">กรอกข้อมูลบางส่วนของคุณให้สมบูรณ์ด้วยการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="79725-104">การคาดคะเนช่วยให้คุณสร้างค่าที่คาดคะเนได้ง่ายซึ่งสามารถเพิ่มความเข้าใจของลูกค้าได้</span><span class="sxs-lookup"><span data-stu-id="79725-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="79725-105">บนเพจ **ระบบอัจฉริยะ** > **การคาดคะเน** คุณสามารถเลือก **การคาดคะเนของฉัน** เพื่อดูการคาดคะเนที่คุณได้กำหนดค่าไว้ในส่วนอื่น ๆ ของข้อมูลเชิงลึกกลุ่มเป้าหมายและให้คุณสามารถปรับแต่งเพิ่มเติมได้</span><span class="sxs-lookup"><span data-stu-id="79725-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="79725-106">คุณไม่สามารถใช้คุณสมบัตินี้ได้หากสภาพแวดล้อมของคุณใช้ที่เก็บข้อมูล Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="79725-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="79725-107">คุณลักษณะการคาดคะเนใช้วิธีการอัตโนมัติในการประเมินข้อมูลและทำการคาดคะเนบนพื้นฐานของข้อมูลนั้น ดังนั้นจึงมีความสามารถที่จะใช้เป็นวิธีการทำโปรไฟล์ตามที่กำหนดไว้ในข้อบังคับในการป้องกันข้อมูลทั่วไป ("GDPR")</span><span class="sxs-lookup"><span data-stu-id="79725-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="79725-108">การใช้คุณลักษณะนี้ของลูกค้าเพื่อประมวลผลข้อมูลอาจอยู่ภายใต้ GDPR หรือกฎหมายหรือข้อบังคับอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="79725-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="79725-109">คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าคุณใช้ Dynamics 365 Customer Insights รวมถึงการคาดคะเนปฏิบัติตามกฎหมายและข้อบังคับที่เกี่ยวข้องทั้งหมด รวมถึงกฎหมายที่เกี่ยวข้องกับความเป็นส่วนตัว ข้อมูลส่วนบุคคล ข้อมูลไบโอเมตริก การปกป้องข้อมูล และการรักษาความลับของการสื่อสาร</span><span class="sxs-lookup"><span data-stu-id="79725-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79725-110">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="79725-110">Prerequisites</span></span>

<span data-ttu-id="79725-111">ก่อนที่องค์กรของคุณจะสามารถใช้คุณลักษณะการคาดคะเนได้ ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="79725-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="79725-112">องค์กรของคุณมี [การตั้งค่าอินสแตนซ์ใน Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) และอยู่ในองค์กรเดียวกันกับ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="79725-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="79725-113">สภาพแวดล้อมของคุณแนบมากับอินสแตนซ์ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="79725-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="79725-114">ถ้าคุณ [สร้างสภาพแวดล้อมใหม่](manage-environments.md) กำหนดค่าในกล่องโต้ตอบ **สร้างสภาพแวดล้อม** และเลือก **ขั้นสูง**</span><span class="sxs-lookup"><span data-stu-id="79725-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="79725-115">หากคุณได้สร้างสภาพแวดล้อมไว้แล้ว ให้ไปที่การตั้งค่าและเลือก **ขั้นสูง**</span><span class="sxs-lookup"><span data-stu-id="79725-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="79725-116">ไม่ว่าจะด้วยวิธีใดก็ตาม ในส่วน **ใช้การคาดคะเน** ให้ป้อน URL ของอินสแตนซ์ Common Data Service ที่คุณต้องการแนบสภาพแวดล้อมของคุณ</span><span class="sxs-lookup"><span data-stu-id="79725-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="79725-117">สร้างการคาดคะเนในเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="79725-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="79725-118">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="79725-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="79725-119">เลือกเอนทิตี **ลูกค้า** .</span><span class="sxs-lookup"><span data-stu-id="79725-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="79725-120">ในเอนทิตี **ลูกค้า: CustomerInsights** เลือกบนแท็บ **ฟิลด์** .</span><span class="sxs-lookup"><span data-stu-id="79725-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="79725-121">ค้นหาชื่อแอตทริบิวต์ที่คุณต้องการคาดคะเนค่า จากนั้นเลือกไอคอน **ภาพรวม** ในคอลัมน์ **สรุป** .</span><span class="sxs-lookup"><span data-stu-id="79725-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79725-122">![ไอคอนภาพรวม](media/intelligence-overviewicon.png "ไอคอนภาพรวม")</span><span class="sxs-lookup"><span data-stu-id="79725-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="79725-123">หากมีค่าที่ขาดหายไปในอัตราสูงสำหรับแอตทริบิวต์ของคุณ ให้เลือก **คาดคะเนค่าที่หายไป** เพื่อดำเนินการคาดคะเนของคุณต่อไป</span><span class="sxs-lookup"><span data-stu-id="79725-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79725-124">![ภาพรวมสถานะพร้อมปุ่มคาดคะเนค่าที่หายไปจะแสดงขึ้น](media/intelligence-overviewpredictmissingvalues.png "ภาพรวมสถานะพร้อมปุ่มคาดคะเนค่าที่หายไปจะแสดงขึ้น")</span><span class="sxs-lookup"><span data-stu-id="79725-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="79725-125">ให้ **ชื่อที่แสดง** และ **ชื่อเอนทิตีผลลัพธ์** สำหรับผลลัพธ์ของการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="79725-126">รายการตัวเลือกที่เติมข้อมูลไว้ล่วงหน้าจะแสดงตำแหน่งที่คุณสามารถจับคู่ค่ากับปรเภทที่คาดคะเนไว้ได้</span><span class="sxs-lookup"><span data-stu-id="79725-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="79725-127">ในกรณีนี้ ตัวเลือกประเภทเดียวของคุณจะเป็น 0 หรือ 1 เนื่องจากตัวเลือกเหล่านี้จับคู่กับลักษณะที่เป็นจริง/เท็จ หรือไบนารีของการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="79725-128">ในคอลัมน์ประเภท แม็ปค่าฟิลด์ที่คุณต้องการจัดเป็น "0" ในการคาดคะเนสุดท้ายเป็น "0" และรายการที่คุณต้องการจัดเป็น "1" ในการคาดคะเนสุดท้ายเป็น "1"</span><span class="sxs-lookup"><span data-stu-id="79725-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79725-129">![ตัวอย่างแสดงค่าของฟิลด์ที่แม็ปกับประเภท](media/intelligence-categorymapping.png "ตัวอย่างแสดงค่าของฟิลด์ที่แม็ปกับประเภท")</span><span class="sxs-lookup"><span data-stu-id="79725-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="79725-130">เลือก **เสร็จสิ้น** และการคาดคะเนจะถูกดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="79725-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="79725-131">การประมวลผลจะใช้เวลาสักครู่ขึ้นอยู่กับขนาดและความซับซ้อนของข้อมูล</span><span class="sxs-lookup"><span data-stu-id="79725-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="79725-132">ผลลัพธ์จะพร้อมใช้งานในเอนทิตีใหม่ตาม **ชื่อเอนทิตีผลลัพธ์** ของการคาดคะเนที่คุณสร้าง</span><span class="sxs-lookup"><span data-stu-id="79725-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="79725-133">สร้างการคาดคะเนในขณะที่สร้างเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="79725-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="79725-134">การคาดคะเนค่าที่ขาดหายไปสำหรับแอตทริบิวต์เฉพาะของตัวเลือกนั้นสามารถทำได้เช่นกันเมื่อสร้างเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="79725-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="79725-135">โดยเฉพาะอย่างยิ่ง เมื่อคุณสร้างเซ็กเมนต์อย่างรวดเร็วตามเอนทิตีลูกค้าแบบรวมหรือเอนทิตีการวัดของลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="79725-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="79725-136">ในฐานะที่เป็นส่วนหนึ่งของโฟลว์นี้ คุณจะเลือกแอททริบิวต์เฉพาะเพื่ออ้างอิงเซ็กเมนต์ของคุณ เช่น ความพึงพอใจของลูกค้า หรือจำนวนที่ซื้อ</span><span class="sxs-lookup"><span data-stu-id="79725-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="79725-137">เมื่อสร้างเซ็กเมนต์ ระบบจะแนะนำวิธีการทำนายค่าที่ขาดหายไปสำหรับแอตทริบิวต์นี้</span><span class="sxs-lookup"><span data-stu-id="79725-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="79725-138">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์** และเลือกไทล์ **โปรไฟล์**</span><span class="sxs-lookup"><span data-stu-id="79725-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="79725-139">เลือก **ฟิลด์** เพื่อสร้างเซ็กเมนต์และเลือก **ตัวดำเนินการ** จากนั้นเลือก **ทบทวน**.</span><span class="sxs-lookup"><span data-stu-id="79725-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="79725-140">ให้ **ชื่อ** และ **ชื่อที่แสดง** สำหรับเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="79725-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="79725-141">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="79725-141">Select **Save**.</span></span>

5. <span data-ttu-id="79725-142">หากเซ็กเมนต์ที่คุณเพิ่งสร้างมีข้อมูลที่ไม่สมบูรณ์ในฟิลด์ต้นทาง คุณสามารถเลือกที่จะคาดคะเนค่าที่ขาดหายไปได้</span><span class="sxs-lookup"><span data-stu-id="79725-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79725-143">![ปุ่มคาดคะเน](media/segments-predictoption.png "ปุ่มคาดคะเน")</span><span class="sxs-lookup"><span data-stu-id="79725-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="79725-144">ให้ **ชื่อที่แสดง** และ **ชื่อเอนทิตีผลลัพธ์** สำหรับผลลัพธ์ของการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="79725-145">เลือก **เสร็จสิ้น**</span><span class="sxs-lookup"><span data-stu-id="79725-145">Select **Done**.</span></span> <span data-ttu-id="79725-146">การคาดคะเนของคุณจะถูกสร้างขึ้นในไม่ช้าและจะพร้อมใช้งานในเอนทิตีใหม่ที่มีชื่อที่คุณให้ไว้สำหรับ **ชื่อเอนทิตีผลลัพธ์**</span><span class="sxs-lookup"><span data-stu-id="79725-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="79725-147">ดูการคาดคะเน </span><span class="sxs-lookup"><span data-stu-id="79725-147">View a prediction</span></span>

1. <span data-ttu-id="79725-148">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** > **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="79725-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="79725-149">เลือกการคาดคะเนที่คุณต้องการตรวจทาน</span><span class="sxs-lookup"><span data-stu-id="79725-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="79725-150">เลือกจุดไข่ปลาในคอลัมน์ **การดำเนินการ** และเลือก **ดู**.</span><span class="sxs-lookup"><span data-stu-id="79725-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="79725-151">คุณจะเห็นจุดข้อมูลจำนวนมากในมุมมองการคาดคะเนของคุณ</span><span class="sxs-lookup"><span data-stu-id="79725-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79725-152">![หน้าการคาดคะเน](media/intelligence-predictionsviewpage.png "หน้าการคาดคะเน")</span><span class="sxs-lookup"><span data-stu-id="79725-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="79725-153">**ค่าคาดคะเน** แสดงการแม็ปที่คุณสร้างระหว่างค่าฟิลด์กับเฟสของการแม็ปประเภท</span><span class="sxs-lookup"><span data-stu-id="79725-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="79725-154">สิ่งเหล่านี้จะแสดงค่าในชุดข้อมูลของคุณที่ถูกแม็ปกับประเภทเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="79725-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="79725-155">-**ผู้มีอิทธิพลอันดับต้น ๆ** เป็นปัจจัยภายในชุดข้อมูลของคุณซึ่งมีแนวโน้มที่จะมีอิทธิพลต่อความเชื่อมั่นของการคาดคะเนค่าของฟิลด์ของคุณที่ถูกแม็ปกับประเภทเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="79725-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="79725-156">**ประสิทธิภาพ** บ่งบอกถึงวิธีการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="79725-157">เลือกลิงก์เพื่อเรียนรู้เพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="79725-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="79725-158">**ดูตัวอย่าง** แสดงตัวอย่างของชุดข้อมูลผลลัพธ์จากการคาดคะเนของคุณและความน่าจะเป็นหรือความเชื่อมั่นของเราเกี่ยวกับค่าที่คาดคะเนไว้เมื่อ 0 ไม่แน่นอนและ 1 แน่นอน</span><span class="sxs-lookup"><span data-stu-id="79725-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="79725-159">ปรับปรุงการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="79725-159">Update a prediction</span></span>

1. <span data-ttu-id="79725-160">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** > **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="79725-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="79725-161">เลือกการคาดคะเนที่คุณต้องการปรับปรุงและเลือกไอคอน **ปรับปรุง** .</span><span class="sxs-lookup"><span data-stu-id="79725-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="79725-162">การคาดคะเนจะถูกจัดกำหนดการไว้สำหรับการประมวลผล</span><span class="sxs-lookup"><span data-stu-id="79725-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="79725-163">คุณสามารถดูเวลาที่ได้รับการปรับปรุงล่าสุดในคอลัมน์ **ปรับปรุงแล้ว** ของหน้า **การคาดคะเน** .</span><span class="sxs-lookup"><span data-stu-id="79725-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="79725-164">แก้ไขการคาดคะเน </span><span class="sxs-lookup"><span data-stu-id="79725-164">Edit a prediction</span></span>

<span data-ttu-id="79725-165">หลังจากที่คุณสร้างการคาดคะเนแล้ว คุณสามารถปรับแต่งโมเดลใน AI Builder เพื่อเพิ่มประสิทธิภาพของโมเดลของคุณ</span><span class="sxs-lookup"><span data-stu-id="79725-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="79725-166">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** > **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="79725-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="79725-167">เลือกการคาดคะเนที่คุณต้องการจะแก้ไข</span><span class="sxs-lookup"><span data-stu-id="79725-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="79725-168">เลือกจุดไข่ปลาในคอลัมน์ **การดำเนินการ** และเลือก **ดู**.</span><span class="sxs-lookup"><span data-stu-id="79725-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="79725-169">เลือก **กำหนดเองใน AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="79725-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="79725-170">ปรับปรุงโมเดลของคุณใน AI Builder</span><span class="sxs-lookup"><span data-stu-id="79725-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="79725-171">[เรียนรู้เพิ่มเติมเกี่ยวกับการจัดการโมเดลใน AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models)</span><span class="sxs-lookup"><span data-stu-id="79725-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="79725-172">การคาดคะเนครั้งต่อไปของคุณจะใช้โมเดลที่ปรับปรุงแล้วที่คุณสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="79725-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="79725-173">โมเดลใหม่ที่สร้างขึ้นใน AI Builder จะไม่แสดงในข้อมูลเชิงลึกกลุ่มเป้าหมาย เว้นแต่วมีการสร้างโมเดลจากประสบการณ์ใช้งานที่ระบุไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="79725-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="79725-174">เอาการคาดคะเนออก</span><span class="sxs-lookup"><span data-stu-id="79725-174">Remove a prediction</span></span>

1. <span data-ttu-id="79725-175">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** > **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="79725-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="79725-176">เลือกการคาดคะเนที่คุณต้องการจะลบทิ้ง</span><span class="sxs-lookup"><span data-stu-id="79725-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="79725-177">เลือกจุดไข่ปลาในคอลัมน์ **การดำเนินการ** และเลือก **ลบ**.</span><span class="sxs-lookup"><span data-stu-id="79725-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="79725-178">ยืนยันการลบ</span><span class="sxs-lookup"><span data-stu-id="79725-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="79725-179">การแก้ไขปัญหา</span><span class="sxs-lookup"><span data-stu-id="79725-179">Troubleshooting</span></span>

<span data-ttu-id="79725-180">หากคุณไม่สามารถแนบไฟล์กระบวนการ Common Data Service เนื่องจากข้อผิดพลาด คุณสามารถลองทำกระบวนการด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="79725-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="79725-181">มีปัญหาที่ทราบสองประการที่สามารถเกิดขึ้นได้ในกระบวนการแนบไฟล์:</span><span class="sxs-lookup"><span data-stu-id="79725-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="79725-182">ไม่ได้ติดตั้งโซลูชัน Add-in การ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="79725-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="79725-183">ทำตามคำแนะนำเพื่อ [ติดตั้งและกำหนดค่าโซลูชัน ](customer-card-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="79725-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="79725-184">ไม่ได้ให้สิทธิ์แอป</span><span class="sxs-lookup"><span data-stu-id="79725-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="79725-185">ไปที่ [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="79725-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="79725-186">เลือก **สภาพแวดล้อม**</span><span class="sxs-lookup"><span data-stu-id="79725-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="79725-187">เลือกจุดไข่ปลาถัดจากสภาพแวดล้อมที่คุณต้องการเพิ่มการอนุญาตและเลือก **การตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="79725-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="79725-188">ขยาย **ผู้ใช้ + สิทธิ์** และเลือก **ผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="79725-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="79725-189">เลือก **+สร้าง** และเลือก **ผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="79725-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="79725-190">เลือก **ผู้ใช้แอปพลิเคชัน** หากยังไม่ได้เลือกและป้อนข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="79725-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="79725-191">**ชื่อผู้ใช้:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="79725-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="79725-192">**รหัสแอปพลิเคชัน:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="79725-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="79725-193">**ชื่อ:** ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="79725-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="79725-194">**นามสกุล:** ข้อมูลเชิงลึก</span><span class="sxs-lookup"><span data-stu-id="79725-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="79725-195">**อีเมลหลัก:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="79725-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="79725-196">เลือก **บันทึกและปิด**</span><span class="sxs-lookup"><span data-stu-id="79725-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="79725-197">เลือกผู้ใช้ที่คุณเพิ่งสร้าง</span><span class="sxs-lookup"><span data-stu-id="79725-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="79725-198">เลือก **จัดการบทบาท** ในแถบเมนูด้านบน</span><span class="sxs-lookup"><span data-stu-id="79725-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="79725-199">เลือก **ผู้ดูแลระบบ** จากนั้นเลือก **ตกลง**</span><span class="sxs-lookup"><span data-stu-id="79725-199">Select **System Administrator**, then select **OK**.</span></span>
