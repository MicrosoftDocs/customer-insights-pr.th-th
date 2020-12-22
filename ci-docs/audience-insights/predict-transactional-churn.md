---
title: การคาดคะเนการเลิกทำธุรกรรม
description: คาดคะเนว่าลูกค้ามีความเสี่ยงในการหยุดซื้อผลิตภัณฑ์หรือบริการของคุณหรือไม่
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644426"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="66afc-103">การคาดคะเนการเลิกทำธุรกรรม (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="66afc-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="66afc-104">การคาดคะเนการเลิกทำธุรกรรมช่วยคาดคะเนว่าลูกค้าจะไม่ซื้อสินค้าหรือบริการของคุณในช่วงเวลาที่กำหนดอีกต่อไปหรือไม่</span><span class="sxs-lookup"><span data-stu-id="66afc-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="66afc-105">คุณสามารถสร้างการคาดคะเนการยกเลิกใหม่ได้ใน **ระบบอัจฉริยะ** > **การคาดคะเน**</span><span class="sxs-lookup"><span data-stu-id="66afc-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="66afc-106">เลือก **การคาดคะเนของฉัน** เพื่อดูการคาดคะเนอื่นๆ ที่คุณได้สร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="66afc-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="66afc-107">ลองใช้บทช่วยสอนสำหรับการคาดคะเนการเลิกทำธุรกรรมโดยใช้ข้อมูลตัวอย่าง: [คู่มือตัวอย่างการคาดคะเนการเลิกทำธุรกรรม (พรีวิว)](sample-guide-predict-transactional-churn.md)</span><span class="sxs-lookup"><span data-stu-id="66afc-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66afc-108">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="66afc-108">Prerequisites</span></span>

- <span data-ttu-id="66afc-109">อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="66afc-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="66afc-110">ความรู้ทางธุรกิจเพื่อทำความเข้าใจว่าการเลิกใช้บริการส่งผลต่อธุรกิจของคุณอย่างไร</span><span class="sxs-lookup"><span data-stu-id="66afc-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="66afc-111">เราสนับสนุนการกำหนดการยกเลิกตามเวลา ซึ่งหมายความว่าลูกค้าได้รับการพิจารณาว่าเลิกใช้งานหลังจากไม่มีการซื้อ</span><span class="sxs-lookup"><span data-stu-id="66afc-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="66afc-112">ข้อมูลเกี่ยวกับธุรกรรม/การซื้อและประวัติ:</span><span class="sxs-lookup"><span data-stu-id="66afc-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="66afc-113">ตัวระบุธุรกรรมเพื่อแยกแยะการซื้อ/ธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="66afc-114">ตัวระบุลูกค้าเพื่อจับคู่ธุรกรรมกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="66afc-115">วันที่ของเหตุการณ์ธุรกรรม ซึ่งกำหนดวันที่ที่ธุรกรรมเกิดขึ้น</span><span class="sxs-lookup"><span data-stu-id="66afc-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="66afc-116">แบบแผนข้อมูลเชิงความหมายสำหรับการซื้อ/ธุรกรรมต้องการข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="66afc-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="66afc-117">**รหัสธุรกรรม:** รหัสเฉพาะของการซื้อหรือธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="66afc-118">**วันที่ทำธุรกรรม:** วันที่ของการซื้อหรือธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="66afc-119">**มูลค่าของธุรกรรม:** สกุลเงิน/มูลค่าที่เป็นตัวเลขของธุรกรรม/รายการ</span><span class="sxs-lookup"><span data-stu-id="66afc-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="66afc-120">(ไม่จำเป็น) **รหัสผลิตภัณฑ์เฉพาะ:** รหัสของผลิตภัณฑ์หรือบริการที่ซื้อหากข้อมูลของคุณอยู่ในระดับสินค้าในรายการ</span><span class="sxs-lookup"><span data-stu-id="66afc-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="66afc-121">(ไม่จำเป็น) **การทำธุรกรรมนี้เป็นการคืนสินค้าหรือไม่:** ฟิลด์จริง/เท็จที่ระบุว่าธุรกรรมเป็นการส่งคืนหรือไม่</span><span class="sxs-lookup"><span data-stu-id="66afc-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="66afc-122">ถ้า **มูลค่าของธุรกรรม** เป็นลบ เราจะใช้ข้อมูลนี้เพื่ออนุมานการส่งคืน</span><span class="sxs-lookup"><span data-stu-id="66afc-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="66afc-123">(ไม่บังคับ) ข้อมูลเกี่ยวกับกิจกรรมของลูกค้า:</span><span class="sxs-lookup"><span data-stu-id="66afc-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="66afc-124">ตัวระบุกิจกรรมเพื่อแยกความแตกต่างของกิจกรรมประเภทเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="66afc-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="66afc-125">ตัวระบุลูกค้าเพื่อแม็ปกิจกรรมกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="66afc-126">ข้อมูลกิจกรรมที่มีชื่อและวันที่ของกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="66afc-127">Scheme ข้อมูลทางความหมายสำหรับกิจกรรมของลูกค้าประกอบด้วย:</span><span class="sxs-lookup"><span data-stu-id="66afc-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="66afc-128">**คีย์หลัก:** ตัวบ่งชี้เฉพาะสำหรับกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="66afc-129">ตัวอย่างเช่น การเยี่ยมชมเว็บไซต์หรือเรกคอร์ดการใช้งานที่แสดงว่าลูกค้าได้ลองใช้ตัวอย่างผลิตภัณฑ์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="66afc-130">**การประทับเวลา:** วันที่และเวลาของเหตุการณ์ที่ระบุโดยคีย์หลัก</span><span class="sxs-lookup"><span data-stu-id="66afc-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="66afc-131">**เหตุการณ์:** ชื่อของกลุ่มเหตุการณ์ที่คุณต้องการใช้</span><span class="sxs-lookup"><span data-stu-id="66afc-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="66afc-132">ตัวอย่างเช่น ฟิลด์ที่ชื่อว่า "UserAction" ในร้านขายของชำอาจเป็นคูปองที่ลูกค้าใช้</span><span class="sxs-lookup"><span data-stu-id="66afc-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="66afc-133">**รายละเอียด:** ข้อมูลรายละเอียดเกี่ยวกับเหตุการณ์</span><span class="sxs-lookup"><span data-stu-id="66afc-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="66afc-134">ตัวอย่างเช่น ฟิลด์ที่ชื่อว่า "CouponValue" ในร้านขายของชำอาจเป็นมูลค่าสกุลเงินของคูปอง</span><span class="sxs-lookup"><span data-stu-id="66afc-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="66afc-135">สร้างการคาดคะเนการเลิกทำธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="66afc-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="66afc-136">ใน Customer Insights ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน**.</span><span class="sxs-lookup"><span data-stu-id="66afc-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="66afc-137">เลือกไทล์ **โมเดลการเลิกใช้บริการของลูกค้า (พรีวิว)** และเลือก **ใช้โมเดลนี้**</span><span class="sxs-lookup"><span data-stu-id="66afc-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="66afc-138">ในบานหน้าต่าง **โมเดลการเลิกใช้บริการของลูกค้า** เลือก **การทำธุรกรรม** และเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="66afc-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="ภาพหน้าจอที่มีตัวเลือกการทำธุรกรรมที่เลือกในบานหน้าต่างโมเดลการเลิกใช้บริการของลูกค้า":::

### <a name="name-model"></a><span data-ttu-id="66afc-140">ตั้งชื่อโมเดล</span><span class="sxs-lookup"><span data-stu-id="66afc-140">Name model</span></span>

1. <span data-ttu-id="66afc-141">ระบุชื่อสำหรับโมเดลเพื่อแยกความแตกต่างจากโมเดลอื่น</span><span class="sxs-lookup"><span data-stu-id="66afc-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="66afc-142">ระบุชื่อให้กับเอนทิตีผลลัพธ์โดยใช้ตัวอักษรและตัวเลขเท่านั้น โดยไม่มีช่องว่าง</span><span class="sxs-lookup"><span data-stu-id="66afc-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="66afc-143">นั่นคือชื่อที่เอนทิตีโมเดลจะใช้</span><span class="sxs-lookup"><span data-stu-id="66afc-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="66afc-144">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="66afc-145">กำหนดการเลิกใช้บริการของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="66afc-145">Define customer churn</span></span>

1. <span data-ttu-id="66afc-146">ตั้งค่ากรอบเวลาเป็นวันเพื่อการเลิกใช้บริการในฟิลด์ **ระบุลูกค้าที่อาจเลิกใช้บริการในครั้งต่อไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="66afc-147">ตัวอย่างเช่น คาดคะเนความเสี่ยงที่ลูกค้าจะเลิกใช้บริการใน 90 วันข้างหน้าเพื่อให้สอดคล้องกับความพยายามในการรักษาลูกค้าทางการตลาดของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="66afc-148">การคาดคะเนความเสี่ยงของการเลิกใช้บริการเป็นระยะเวลานานขึ้นหรือสั้นลงอาจทำให้ยากต่อการระบุปัจจัยในโปรไฟล์ความเสี่ยงของการเลิกใช้บริการ แต่ขึ้นอยู่กับข้อกำหนดทางธุรกิจเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="66afc-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="66afc-149">คุณสามารถเลือก **บันทึกและปิด** เมื่อใดก็ได้เพื่อบันทึกการคาดคะเนเป็นแบบร่าง</span><span class="sxs-lookup"><span data-stu-id="66afc-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="66afc-150">คุณจะพบการคาดคะเนของแบบร่างในแท็บ **การคาดคะเนของฉัน** เพื่อดำเนินการต่อ</span><span class="sxs-lookup"><span data-stu-id="66afc-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="66afc-151">ป้อนจำนวนวันเพื่อกำหนดการเลิกใช้บริการในฟิลด์ **ลูกค้าเลิกใช้บริการหากพวกเขาไม่ได้ทำการซื้อใน:**</span><span class="sxs-lookup"><span data-stu-id="66afc-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="66afc-152">ตัวอย่างเช่น หากลูกค้าไม่ได้ทำการซื้อใดๆ ในช่วง 30 วันที่ผ่านมา พวกเขาอาจได้รับการพิจารณาว่าเลิกใช้บริการสำหรับธุรกิจของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="66afc-153">เมื่อต้องการดำเนินการต่อ ให้เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="66afc-154">เพิ่มข้อมูลที่จำเป็น</span><span class="sxs-lookup"><span data-stu-id="66afc-154">Add required data</span></span>

1. <span data-ttu-id="66afc-155">เลือก **เพิ่มข้อมูล** สำหรับ **ประวัติการซื้อ** และเลือกเอนทิตีที่ให้ข้อมูลประวัติการทำธุรกรรม/การซื้อตามที่อธิบายไว้ใน [ข้อกำหนดเบื้องต้น](#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="66afc-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="66afc-156">แมปฟิลด์ความหมายกับแอตทริบิวต์ภายในเอนทิตีประวัติการซื้อของคุณและเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="66afc-157">สำหรับคำอธิบายของฟิลด์ ให้ดูที่ [ข้อกำหนดเบื้องต้น](#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="66afc-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="แมปฟิลด์ความหมายของเอนทิตีการซื้อ":::

1. <span data-ttu-id="66afc-159">หากไม่มีการเติมข้อมูลในฟิลด์ด้านล่าง ให้กำหนดค่าความสัมพันธ์จากเอนทิตีประวัติการซื้อของคุณกับเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="66afc-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="66afc-160">เลือก **เอนทิตีประวัติการซื้อ**</span><span class="sxs-lookup"><span data-stu-id="66afc-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="66afc-161">เลือก **ฟิลด์** ที่ระบุลูกค้าในเอนทิตีประวัติการซื้อ</span><span class="sxs-lookup"><span data-stu-id="66afc-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="66afc-162">จะต้องเกี่ยวข้องกับรหัสลูกค้าหลักของเอนทิตีลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="66afc-163">เลือก **เอนทิตีลูกค้า** ที่ตรงกับเอนทิตีลูกค้าหลักของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="66afc-164">ป้อนชื่อที่อธิบายความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="เพจประวัติการซื้อที่แสดงการสร้างความสัมพันธ์กับลูกค้า":::
   
1. <span data-ttu-id="66afc-166">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-166">Select **Next**.</span></span>

1. <span data-ttu-id="66afc-167">หรือเลือก **เพิ่มข้อมูล** สำหรับ **กิจกรรมของลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="66afc-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="66afc-168">เลือกเอนทิตีที่ให้ข้อมูลกิจกรรมของลูกค้าตามที่อธิบายไว้ในข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="66afc-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="66afc-169">แมปฟิลด์ความหมายกับแอตทริบิวต์ภายในเอนทิตีกิจกรรมของลูกค้าของคุณและเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="66afc-170">สำหรับคำอธิบายของฟิลด์ ให้ดูที่ [ข้อกำหนดเบื้องต้น](#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="66afc-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="66afc-171">เลือกประเภทกิจกรรมที่ตรงกับประเภทกิจกรรมลูกค้าที่คุณกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="66afc-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="66afc-172">เลือก **สร้างใหม่** และเลือกชนิดกิจกรรมที่มีอยู่หรือสร้างชนิดใหม่</span><span class="sxs-lookup"><span data-stu-id="66afc-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="66afc-173">คุณจะต้องกำหนดค่าความสัมพันธ์จากเอนทิตีกิจกรรมลูกค้าของคุณไปยังเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="66afc-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="66afc-174">เลือกฟิลด์ที่ระบุลูกค้าในเอนทิตีกิจกรรมของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="66afc-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="66afc-175">โดยสามารถเกี่ยวข้องโดยตรงกับรหัสลูกค้าหลักของเอนทิตีลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="66afc-176">เลือกเอนทิตีลูกค้าที่ตรงกับเอนทิตีลูกค้าหลักของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="66afc-177">ป้อนชื่อที่อธิบายความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="66afc-178">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="66afc-178">Select **Save**.</span></span>

1. <span data-ttu-id="66afc-179">หากคุณมีกิจกรรมอื่นๆ ของลูกค้าที่คุณต้องการรวมไว้ ให้ทำซ้ำขั้นตอนข้างต้น</span><span class="sxs-lookup"><span data-stu-id="66afc-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="66afc-180">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="66afc-181">กำหนดตารางเวลาและตรวจสอบการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="66afc-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="66afc-182">ตั้งค่าความถี่เพื่อฝึกฝนโมเดลของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="66afc-183">การตั้งค่านี้มีความสำคัญในการปรับปรุงความถูกต้องของการคาดคะเนเนื่องจากมีการนำเข้าข้อมูลใหม่</span><span class="sxs-lookup"><span data-stu-id="66afc-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="66afc-184">ธุรกิจส่วนใหญ่สามารถฝึกใหม่เดือนละครั้งและได้รับความแม่นยำที่ดีสำหรับการคาดคะเนของธุรกิจ</span><span class="sxs-lookup"><span data-stu-id="66afc-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="66afc-185">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="66afc-185">Select **Next**.</span></span>

1. <span data-ttu-id="66afc-186">ตรวจสอบการกำหนดค่าของการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="66afc-187">คุณสามารถย้อนกลับไปยังขั้นตอนก่อนหน้าได้โดยการเลือก **แก้ไข** ภายใต้ค่าที่แสดง</span><span class="sxs-lookup"><span data-stu-id="66afc-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="66afc-188">หรือคุณสามารถเลือกขั้นตอนการกำหนดค่าจากตัวบ่งชี้ความคืบหน้า</span><span class="sxs-lookup"><span data-stu-id="66afc-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="66afc-189">หากกำหนดค่าทั้งหมดถูกต้องให้เลือก **บันทึกและเรียกใช้** เพื่อเริ่มกระบวนการการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="66afc-190">บนแท็บ **การคาดคะเนของฉัน** คุณสามารถดูสถานะการคาดคะเนของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="66afc-191">กระบวนการนี้อาจใช้เวลาหลายชั่วโมงกว่าจะเสร็จสมบูรณ์ ทั้งนี้ขึ้นอยู่กับปริมาณข้อมูลที่ใช้ในการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="66afc-192">ตรวจสอบสถานะการคาดคะเนและผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="66afc-193">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="66afc-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="66afc-194">เลือกการคาดคะเนที่คุณต้องการตรวจทาน</span><span class="sxs-lookup"><span data-stu-id="66afc-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="66afc-195">**ชื่อการคาดคะเน:** ชื่อของการคาดคะเนที่ระบุเมื่อสร้าง</span><span class="sxs-lookup"><span data-stu-id="66afc-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="66afc-196">**ชนิดการคาดคะเน:** ชนิดของโมเดลที่ใช้สำหรับการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="66afc-197">**เอนทิตีผลลัพธ์:** ชื่อของเอนทิตีที่จะเก็บผลลัพธ์ของการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="66afc-198">คุณสามารถค้นหาเอนทิตีที่ใช้ชื่อนี้ได้บน **ข้อมูล** > **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="66afc-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="66afc-199">**ฟิลด์ที่คาดคะเน:** ฟิลด์นี้ได้รับการเติมข้อมูลสำหรับการคาดคะเนบางชนิดเท่านั้นและไม่ได้ใช้ในการคาดคะเนการเลิกใช้บริการ</span><span class="sxs-lookup"><span data-stu-id="66afc-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="66afc-200">**สถานะ:** สถานะของการคาดคะเนที่ดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="66afc-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="66afc-201">**อยู่ในคิว:** การคาดคะเนกำลังรอให้กระบวนการอื่นทำงาน</span><span class="sxs-lookup"><span data-stu-id="66afc-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="66afc-202">**กำลังรีเฟรช:** การคาดคะเนกำลังทำงานเพื่อสร้างผลลัพธ์ที่จะส่งไปยังเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="66afc-203">**ล้มเหลว:** การดำเนินการคาดคะเนล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="66afc-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="66afc-204">[ตรวจสอบบันทึก](#troubleshoot-a-failed-prediction) สำหรับรายละเอียดเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="66afc-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="66afc-205">**สำเร็จแล้ว:** การคาดคะเนประสบความสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="66afc-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="66afc-206">เลือก **ดู** ภายใต้วงรีแนวตั้งเพื่อตรวจทานการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="66afc-207">**แก้ไขแล้ว:** วันที่ของการกำหนดค่าสำหรับการคาดคะเนถูกเปลี่ยน</span><span class="sxs-lookup"><span data-stu-id="66afc-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="66afc-208">**รีเฟรชครั้งล่าสุด:** วันที่การคาดคะเนรีเฟรชผลลัพธ์ในเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="66afc-209">เลือกจุดไข่ปลาแนวตั้งถัดจากการคาดคะเนที่คุณต้องการตรวจทานผลลัพธ์ และเลือก **ดู**</span><span class="sxs-lookup"><span data-stu-id="66afc-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="ดูการควบคุมเพื่อดูผลลัพธ์ของการคาดคะเน":::   

1. <span data-ttu-id="66afc-211">มีข้อมูลหลักสามส่วนภายในหน้าผลลัพธ์:</span><span class="sxs-lookup"><span data-stu-id="66afc-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="66afc-212">**ประสิทธิภาพรูปแบบการฝึกอบรม:** A, B หรือ C เป็นคะแนนที่เป็นไปได้</span><span class="sxs-lookup"><span data-stu-id="66afc-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="66afc-213">คะแนนนี้บ่งชี้ประสิทธิภาพของการคาดคะเนและสามารถช่วยให้คุณตัดสินใจใช้ผลลัพธ์ที่เก็บไว้ในเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="66afc-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="66afc-214">คะแนนจะถูกกำหนดตามกฎต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="66afc-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="66afc-215">**A** เมื่อโมเดลคาดคะเนแม่นยำอย่างน้อย 50% ของการคาดคะเนทั้งหมดและเมื่อเปอร์เซ็นต์ของการคาดคะเนที่แม่นยำสำหรับลูกค้าที่เลิกใช้บริการมากกว่าอัตราพื้นฐานอย่างน้อย 10%</span><span class="sxs-lookup"><span data-stu-id="66afc-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="66afc-216">**B** เมื่อโมเดลคาดคะเนแม่นยำอย่างน้อย 50% ของการคาดคะเนทั้งหมดและเมื่อเปอร์เซ็นต์ของการคาดคะเนที่แม่นยำสำหรับลูกค้าที่เลิกใช้บริการมากกว่าอัตราพื้นฐานสูงสุด 10%</span><span class="sxs-lookup"><span data-stu-id="66afc-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="66afc-217">**C** เมื่อโมเดลคาดคะเนแม่นยำน้อยกว่า 50% ของการคาดคะเนทั้งหมด หรือเมื่อเปอร์เซ็นต์ของการคาดคะเนที่แม่นยำสำหรับลูกค้าที่เลิกใช้บริการน้อยกว่าอัตราพื้นฐาน</span><span class="sxs-lookup"><span data-stu-id="66afc-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="66afc-218">**พื้นฐาน** ใช้การป้อนข้อมูลกรอบเวลาการคาดคะเนสำหรับโมเดล (ตัวอย่างเช่น หนึ่งปี) และโมเดลจะสร้างเศษส่วนของเวลาที่แตกต่างกันโดยหารด้วย 2 จนกว่าจะถึงหนึ่งเดือนหรือน้อยกว่านั้น</span><span class="sxs-lookup"><span data-stu-id="66afc-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="66afc-219">โดยใช้เศษส่วนเหล่านี้เพื่อสร้างกฎธุรกิจสำหรับลูกค้าที่ไม่ได้ซื้อในกรอบเวลานี้</span><span class="sxs-lookup"><span data-stu-id="66afc-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="66afc-220">ลูกค้าเหล่านี้ถือว่าเลิกใช้บริการ</span><span class="sxs-lookup"><span data-stu-id="66afc-220">These customers are considered as churned.</span></span> <span data-ttu-id="66afc-221">กฎธุรกิจตามเวลาที่มีความสามารถสูงสุดในการคาดคะเนว่าใครมีแนวโน้มที่จะเลิกใช้บริการจะถูกเลือกเป็นโมเดลพื้นฐาน</span><span class="sxs-lookup"><span data-stu-id="66afc-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="66afc-222">**โอกาสที่จะเลิกใช้บริการ (จำนวนลูกค้า):** กลุ่มลูกค้าขึ้นอยู่กับความเสี่ยงที่คาดคะเนไว้ของการเลิกใช้บริการ</span><span class="sxs-lookup"><span data-stu-id="66afc-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="66afc-223">ข้อมูลนี้สามารถช่วยคุณได้ในภายหลังหากคุณต้องการสร้างเซ็กเมนต์ลูกค้าที่มีความเสี่ยงในการเลิกใช้บริการสูง</span><span class="sxs-lookup"><span data-stu-id="66afc-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="66afc-224">เซ็กเมนต์ดังกล่าวช่วยให้เข้าใจว่าการตัดยอดของคุณควรเป็นอย่างไรสำหรับการเป็นสมาชิกเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="66afc-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="66afc-225">**ปัจจัยที่มีอิทธิพลมากที่สุด:** มีหลายปัจจัยที่นำมาพิจารณาเมื่อสร้างการคาดคะเนของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="66afc-226">ปัจจัยแต่ละอย่างมีความสำคัญในการคำนวณสำหรับการคาดคะเนแบบรวมที่โมเดลสร้าง</span><span class="sxs-lookup"><span data-stu-id="66afc-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="66afc-227">คุณสามารถใช้ปัจจัยเหล่านี้เพื่อช่วยตรวจสอบผลการคาดคะเนของคุณ</span><span class="sxs-lookup"><span data-stu-id="66afc-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="66afc-228">หรือคุณสามารถใช้ข้อมูลนี้ในภายหลังเพื่อ [สร้างเซ็กเมนต์](segments.md) ที่สามารถช่วยโน้มน้าวความเสี่ยงในการเลิกใช้บริการให้กับลูกค้า</span><span class="sxs-lookup"><span data-stu-id="66afc-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="66afc-229">แก้ไขปัญหาการคาดคะเนที่ล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="66afc-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="66afc-230">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="66afc-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="66afc-231">เลือกจุดไข่ปลาแนวตั้งถัดจากการคาดคะเนที่คุณต้องการดูบันทึกข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="66afc-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="66afc-232">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="66afc-232">Select **Logs**.</span></span>

1. <span data-ttu-id="66afc-233">ตรวจทานข้อผิดพลาดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="66afc-233">Review all the errors.</span></span> <span data-ttu-id="66afc-234">มีข้อผิดพลาดหลายประเภทที่สามารถเกิดขึ้นได้ และข้อผิดพลาดเหล่านั้นอธิบายถึงเงื่อนไขที่ทำให้เกิดข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="66afc-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="66afc-235">ตัวอย่างเช่น ข้อผิดพลาดที่มีข้อมูลไม่เพียงพอที่จะคาดคะเนได้อย่างแม่นยำมักจะได้รับการแก้ไขโดยการโหลดข้อมูลเพิ่มเติมลงใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="66afc-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="66afc-236">รีเฟรชการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-236">Refresh a prediction</span></span>

<span data-ttu-id="66afc-237">การคาดคะเนจะรีเฟรชอัตโนมัติใน [กำหนดการรีเฟรชข้อมูลของคุณ](system.md#schedule-tab) เดียวกันกับที่กำหนดไว้ในการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="66afc-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="66afc-238">คุณสามารถรีเฟรชด้วยตนเองได้เช่นกัน</span><span class="sxs-lookup"><span data-stu-id="66afc-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="66afc-239">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="66afc-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="66afc-240">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="66afc-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="66afc-241">เลือก **รีเฟรช**</span><span class="sxs-lookup"><span data-stu-id="66afc-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="66afc-242">ลบการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="66afc-242">Delete a prediction</span></span>

<span data-ttu-id="66afc-243">การลบการคาดคะเนจะลบเอนทิตีผลลัพธ์ด้วย</span><span class="sxs-lookup"><span data-stu-id="66afc-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="66afc-244">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="66afc-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="66afc-245">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="66afc-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="66afc-246">เลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="66afc-246">Select **Delete**.</span></span>
