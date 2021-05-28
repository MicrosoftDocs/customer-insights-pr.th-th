---
title: สร้างและจัดการการวัด
description: กำหนดการวัดเพื่อวิเคราะห์และสะท้อนผลการดำเนินงานของธุรกิจของคุณ
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049273"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="cfcfe-103">กำหนดและจัดการการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-103">Define and manage measures</span></span>

<span data-ttu-id="cfcfe-104">การวัดช่วยให้คุณเข้าใจพฤติกรรมของลูกค้าและผลการดำเนินงานทางธุรกิจได้ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="cfcfe-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="cfcfe-105">พวกเขาดูค่าที่เกี่ยวข้องจาก [โปรไฟล์แบบรวม](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="cfcfe-106">ตัวอย่างเช่น ธุรกิจต้องการดู *ค่าใช้จ่ายทั้งหมดต่อลูกค้าหนึ่งราย* เพื่อทำความเข้าใจประวัติการซื้อของลูกค้าแต่ละรายหรือการวัดผล *ยอดขายรวมของบริษัท* เพื่อทำความเข้าใจรายได้ระดับรวมในธุรกิจทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="cfcfe-107">การวัดถูกสร้างขึ้นโดยใช้ตัวสร้างการวัด ซึ่งเป็นแพลตฟอร์มการสอบถามที่มีตัวดำเนินการต่างๆ และตัวเลือกการแม็ปอย่างง่าย</span><span class="sxs-lookup"><span data-stu-id="cfcfe-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="cfcfe-108">ช่วยให้คุณกรองข้อมูล จัดกลุ่มผลลัพธ์ ตรวจจับ [เส้นทางความสัมพันธ์ของเอนทิตี](relationships.md) และพรีวิวผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="cfcfe-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="cfcfe-109">ใช้ตัวสร้างการวัดเพื่อวางแผนกิจกรรมทางธุรกิจ โดยการสอบถามข้อมูลลูกค้าและดึงข้อมูลเชิงลึก</span><span class="sxs-lookup"><span data-stu-id="cfcfe-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="cfcfe-110">ตัวอย่างเช่น การสร้างการวัดของ *การใช้จ่ายทั้งหมดต่อลูกค้าหนึ่งราย* และ *ยอดรวมการคืนสินค้าต่อลูกค้าหนึ่งราย* ช่วยระบุกลุ่มลูกค้าที่มีการใช้จ่ายสูง แต่มีการคืนสินค้าสูง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="cfcfe-111">คุณสามารถ [สร้างเซ็กเมนต์](segments.md) เพื่อขับเคลื่อนการดำเนินการที่ดีที่สุดต่อไป</span><span class="sxs-lookup"><span data-stu-id="cfcfe-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="cfcfe-112">สร้างการวัดของคุณเองตั้งแต่ต้น</span><span class="sxs-lookup"><span data-stu-id="cfcfe-112">Build your own measure from scratch</span></span>

<span data-ttu-id="cfcfe-113">ส่วนนี้จะแนะนำคุณเกี่ยวกับการสร้างการวัดใหม่ตั้งแต่ต้น</span><span class="sxs-lookup"><span data-stu-id="cfcfe-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="cfcfe-114">คุณสามารถสร้างการวัดด้วยแอตทริบิวต์ข้อมูลจากเอนทิตีข้อมูลที่มีการตั้งค่าความสัมพันธ์เพื่อเชื่อมต่อกับเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="cfcfe-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="cfcfe-115">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **การวัด**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cfcfe-116">เลือก **สร้าง** และเลือก **สร้างของคุณเอง**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="cfcfe-117">เลือก **แก้ไขชื่อ** และระบุ **ชื่อ** สำหรับการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="cfcfe-118">หากการตั้งค่าคอนฟิกการวัดใหม่ของคุณมีเพียงสองฟิลด์ เช่น CustomerID และการคำนวณหนึ่งรายการ ผลลัพธ์จะถูกเพิ่มเป็นคอลัมน์ใหม่ในเอนทิตีที่ระบบสร้างขึ้นที่เรียกว่า Customer_Measure</span><span class="sxs-lookup"><span data-stu-id="cfcfe-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="cfcfe-119">และคุณจะสามารถเห็นค่าของการวัดในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="cfcfe-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="cfcfe-120">การวัดอื่นๆ จะสร้างเอนทิตีของตนเอง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="cfcfe-121">ในพื้นที่การกำหนดค่า ให้เลือกฟังก์ชันการรวมจากเมนูแบบหล่นลง **เลือกฟังก์ชัน**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="cfcfe-122">ฟังก์ชันการรวมประกอบด้วย:</span><span class="sxs-lookup"><span data-stu-id="cfcfe-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="cfcfe-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-123">**Sum**</span></span>
   - <span data-ttu-id="cfcfe-124">**ค่าเฉลี่ย**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-124">**Average**</span></span>
   - <span data-ttu-id="cfcfe-125">**นับจำนวน**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-125">**Count**</span></span>
   - <span data-ttu-id="cfcfe-126">**นับรายการที่ไม่ซ้ำกัน**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-126">**Count Unique**</span></span>
   - <span data-ttu-id="cfcfe-127">**ค่าสูงสุด**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-127">**Max**</span></span>
   - <span data-ttu-id="cfcfe-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-128">**Min**</span></span>
   - <span data-ttu-id="cfcfe-129">**อันดับแรก**: รับค่าแรกของเรกคอร์ดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="cfcfe-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="cfcfe-130">**สุดท้าย**: รับค่าสุดท้ายที่เพิ่มลงในเรกคอร์ดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="cfcfe-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="ตัวดำเนินการสำหรับการคำนวณการวัด":::

1. <span data-ttu-id="cfcfe-132">เลือก **เพิ่มแอตทริบิวต์** เพื่อเลือกข้อมูลที่คุณต้องการสร้างการวัดนี้</span><span class="sxs-lookup"><span data-stu-id="cfcfe-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="cfcfe-133">เลือกแท็บ **แอตทริบิวต์**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="cfcfe-134">เอนทิตีข้อมูล: เลือกเอนทิตีที่มีแอตทริบิวต์ที่คุณต้องการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="cfcfe-135">แอตทริบิวต์ข้อมูล: เลือกแอตทริบิวต์ที่คุณต้องการใช้ในฟังก์ชันการรวมเพื่อคำนวณการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="cfcfe-136">คุณสามารถเลือกได้ครั้งละหนึ่งแอตทริบิวต์เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="cfcfe-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="cfcfe-137">คุณยังสามารถเลือกแอตทริบิวต์ข้อมูลจากการวัดที่มีอยู่ได้ โดยเลือกแท็บ **การวัด** หรือคุณสามารถค้นหาชื่อเอนทิตีหรือชื่อการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="cfcfe-138">เลือก **เพิ่ม** เพื่อเพิ่มแอตทริบิวต์ที่เลือกในการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="เลือกแอตทริบิวต์ที่จะใช้ในการคำนวณ":::

1. <span data-ttu-id="cfcfe-140">ในการสร้างการวัดที่ซับซ้อนยิ่งขึ้น คุณสามารถเพิ่มแอตทริบิวต์เพิ่มเติมหรือใช้ตัวดำเนินการทางคณิตศาสตร์กับฟังก์ชันการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="สร้างการวัดที่ซับซ้อนด้วยตัวดำเนินการทางคณิตศาสตร์":::

1. <span data-ttu-id="cfcfe-142">ในการเพิ่มตัวกรอง ให้เลือก **กรอง** ในพื้นที่การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="cfcfe-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="cfcfe-143">ในส่วน **เพิ่มแอตทริบิวต์** ของบานหน้าต่าง **ตัวกรอง** เลือกแอตทริบิวต์ที่คุณต้องการใช้เพื่อสร้างตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="cfcfe-144">ตั้งค่าตัวดำเนินการกรองเพื่อกำหนดตัวกรองสำหรับทุกแอ็ตทริบิวต์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="cfcfe-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="cfcfe-145">เลือก **นำไปใช้** เพื่อเพิ่มตัวกรองในการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="cfcfe-146">ในการเพิ่มมิติ ให้เลือก **มิติ** ในพื้นที่การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="cfcfe-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="cfcfe-147">ขนาดจะแสดงเป็นคอลัมน์ในเอนทิตีผลลัพธ์การวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="cfcfe-148">เลือก **แก้ไขขนาด** เพื่อเพิ่มแอตทริบิวต์ข้อมูลที่คุณต้องการจัดกลุ่มค่าการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="cfcfe-149">ตัวอย่างเช่น เมือง หรือ เพศ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-149">For example, city or gender.</span></span> <span data-ttu-id="cfcfe-150">โดยค่าเริ่มต้น ขนาด *CustomerID* จะถูกเลือกเพื่อสร้าง *การวัดระดับลูกค้า*</span><span class="sxs-lookup"><span data-stu-id="cfcfe-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="cfcfe-151">คุณสามารถลบขนาดเริ่มต้นได้หากต้องการสร้าง *การวัดระดับธุรกิจ*</span><span class="sxs-lookup"><span data-stu-id="cfcfe-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="cfcfe-152">เลือก **เสร็จสิ้น** เพื่อเพิ่มมิติในการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="cfcfe-153">หากมีค่าในข้อมูลของคุณที่คุณต้องแทนที่ด้วยจำนวนเต็ม ตัวอย่างเช่น แทนที่ *null* ด้วย *0* เลือก **กฎ**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="cfcfe-154">กำหนดค่ากฎและตรวจสอบให้แน่ใจว่าคุณได้เลือกเฉพาะตัวเลขทั้งหมดเป็นตัวทดแทน</span><span class="sxs-lookup"><span data-stu-id="cfcfe-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="cfcfe-155">หากมีหลายเส้นทางระหว่างเอนทิตีข้อมูลที่คุณแมปและเอนทิตี *ลูกค้า* คุณต้องเลือกหนึ่งรายการที่ระบุ [เส้นทางความสัมพันธ์ของเอนทิตี](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="cfcfe-156">ผลการวัดอาจแตกต่างกันไปขึ้นอยู่กับเส้นทางที่เลือก</span><span class="sxs-lookup"><span data-stu-id="cfcfe-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="cfcfe-157">เลือก **การกําหนดลักษณะข้อมูล** และเลือกเส้นทางเอนทิตีที่ควรใช้เพื่อระบุการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="cfcfe-158">หากมีเพียงเส้นทางเดียวไปยังเอนทิตี *ลูกค้า* ตัวควบคุมนี้จะไม่แสดง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="cfcfe-159">เลือก **เสร็จสิ้น** เพื่อใช้การเลือกของคุณ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="เลือกเส้นทางเอนทิตีสำหรับการวัด":::

1. <span data-ttu-id="cfcfe-161">หากต้องการเพิ่มการคำนวณเพิ่มเติมสำหรับการวัด ให้เลือก **การคำนวณใหม่**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="cfcfe-162">คุณสามารถใช้ได้เฉพาะเอนทิตีบนเส้นทางเอนทิตีเดียวกันสำหรับการคำนวณใหม่</span><span class="sxs-lookup"><span data-stu-id="cfcfe-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="cfcfe-163">การคำนวณเพิ่มเติมจะแสดงเป็นคอลัมน์ใหม่ ในเอนทิตีผลลัพธ์การวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="cfcfe-164">เลือก **...** บนการคำนวณ เพื่อ **ทำซ้ำ** **เปลี่ยนชื่อ** หรือ **ลบ** การคำนวณจากการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="cfcfe-165">ในพื้นที่ **การแสดงตัวอย่าง** คุณจะเห็น Schema ข้อมูลของเอนทิตีผลลัพธ์การวัด รวมถึงตัวกรองและมิติ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="cfcfe-166">การแสดงตัวอย่างจะตอบสนองแบบไดนามิกต่อการเปลี่ยนแปลงในการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="cfcfe-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="cfcfe-167">เลือก **รัน** เพื่อคำนวณผลลัพธ์สำหรับการวัดที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="cfcfe-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="cfcfe-168">เลือก **บันทึกและปิด** หากคุณต้องการเก็บการกำหนดค่าปัจจุบันไว้ และเรียกใช้การวัดในภายหลัง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="cfcfe-169">ไปที่ **การวัด** เพื่อดูการวัดที่สร้างขึ้นใหม่ในรายการ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="cfcfe-170">ใช้แม่แบบเพื่อสร้างการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-170">Use a template to build a measure</span></span>

<span data-ttu-id="cfcfe-171">คุณสามารถใช้แม่แบบที่กำหนดไว้ล่วงหน้าของการวัดที่ใช้ทั่วไปเพื่อสร้างได้</span><span class="sxs-lookup"><span data-stu-id="cfcfe-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="cfcfe-172">คำอธิบายโดยละเอียดของแม่แบบและประสบการณ์ที่แนะนำช่วยให้คุณสร้างการวัดได้อย่างมีประสิทธิภาพ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="cfcfe-173">แม่แบบสร้างจากข้อมูลที่แมปจากเอนทิตี *กิจกรรมแบบรวม*</span><span class="sxs-lookup"><span data-stu-id="cfcfe-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="cfcfe-174">ดังนั้นตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่า [กิจกรรมของลูกค้า](activities.md) ก่อนที่คุณจะสร้างการวัดจากแม่แบบ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="cfcfe-175">แม่แบบการวัดที่พร้อมใช้งาน:</span><span class="sxs-lookup"><span data-stu-id="cfcfe-175">Available measure templates:</span></span> 
- <span data-ttu-id="cfcfe-176">มูลค่าธุรกรรมเฉลี่ย (ATV)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="cfcfe-177">มูลค่าธุรกรรมรวม</span><span class="sxs-lookup"><span data-stu-id="cfcfe-177">Total transaction value</span></span>
- <span data-ttu-id="cfcfe-178">รายได้เฉลี่ยต่อวัน</span><span class="sxs-lookup"><span data-stu-id="cfcfe-178">Average daily revenue</span></span>
- <span data-ttu-id="cfcfe-179">รายได้เฉลี่ยต่อปี</span><span class="sxs-lookup"><span data-stu-id="cfcfe-179">Average yearly revenue</span></span>
- <span data-ttu-id="cfcfe-180">จำนวนธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="cfcfe-180">Transaction count</span></span>
- <span data-ttu-id="cfcfe-181">คะแนนสะสมสำหรับสมาชิกที่ได้รับ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-181">Loyalty points earned</span></span>
- <span data-ttu-id="cfcfe-182">คะแนนสะสมที่แลก</span><span class="sxs-lookup"><span data-stu-id="cfcfe-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="cfcfe-183">ยอดคงเหลือคะแนนสะสมสําหรับสมาชิก</span><span class="sxs-lookup"><span data-stu-id="cfcfe-183">Loyalty points balance</span></span>
- <span data-ttu-id="cfcfe-184">อายุการใช้งานของลูกค้าที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="cfcfe-184">Active customer lifespan</span></span>
- <span data-ttu-id="cfcfe-185">ระยะเวลาการเป็นสมาชิกที่ภักดี</span><span class="sxs-lookup"><span data-stu-id="cfcfe-185">Loyalty membership duration</span></span>
- <span data-ttu-id="cfcfe-186">เวลานับตั้งแต่การซื้อครั้งล่าสุด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-186">Time since last purchase</span></span>

<span data-ttu-id="cfcfe-187">ขั้นตอนต่อไปนี้สรุปขั้นตอนในการสร้างการวัดใหม่โดยใช้แม่แบบ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="cfcfe-188">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **การวัด**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="cfcfe-189">เลือก **สร้าง** และเลือก **เลือกแม่แบบ**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="ภาพหน้าจอของเมนูแบบหล่นลงเมื่อสร้างการวัดใหม่โดยเน้นที่แม่แบบ":::

1. <span data-ttu-id="cfcfe-191">ค้นหาแม่แบบที่เหมาะกับความต้องการของคุณ แล้วเลือก **เลือกแม่แบบ**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="cfcfe-192">ตรวจสอบข้อมูลที่จำเป็นและเลือก **เริ่มต้นใช้งาน** หากคุณมีข้อมูลทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="cfcfe-193">ในบานหน้าต่าง **แก้ไขชื่อ** ตั้งชื่อสำหรับการวัดของคุณและเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="cfcfe-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="cfcfe-194">เลือก **สำเร็จ**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-194">Select **Done**.</span></span>

1. <span data-ttu-id="cfcfe-195">ในส่วน **กำหนดช่วงเวลา** กำหนดกรอบเวลาของข้อมูลที่จะใช้</span><span class="sxs-lookup"><span data-stu-id="cfcfe-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="cfcfe-196">เลือกว่าคุณต้องการให้การวัดใหม่ครอบคลุมชุดข้อมูลทั้งหมดหรือไม่โดยการเลือก **ตลอดเวลา**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="cfcfe-197">หรือถ้าคุณต้องการให้การวัดเน้นไปที่ **ช่วงเวลาเฉพาะ**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="ภาพหน้าจอแสดงส่วนช่วงเวลาเมื่อกำหนดค่าการวัดจากแม่แบบ":::

1. <span data-ttu-id="cfcfe-199">ในส่วนถัดไป เลือก **เพิ่มข้อมูล** เพื่อเลือกกิจกรรมและแมปข้อมูลที่เกี่ยวข้องจากเอนทิตี *กิจกรรมแบบรวม*</span><span class="sxs-lookup"><span data-stu-id="cfcfe-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="cfcfe-200">ขั้นตอนที่ 1 จาก 2: ภายใต้ **ชนิดกิจกรรม** เลือกชนิดของเอนทิตีที่คุณต้องการใช้</span><span class="sxs-lookup"><span data-stu-id="cfcfe-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="cfcfe-201">สำหรับ **กิจกรรม** เลือกเอนทิตีที่คุณต้องการแมป</span><span class="sxs-lookup"><span data-stu-id="cfcfe-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="cfcfe-202">ขั้นตอนที่ 2 จาก 2: เลือกแอตทริบิวต์จากเอนทิตี *กิจกรรมแบบรวม* สำหรับส่วนประกอบที่สูตรต้องการ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="cfcfe-203">ตัวอย่างเช่น สำหรับมูลค่าธุรกรรมโดยเฉลี่ย เป็นแอตทริบิวต์ที่แสดงมูลค่าธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="cfcfe-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="cfcfe-204">สำหรับ **การประทับเวลากิจกรรม** เลือกแอตทริบิวต์จากเอนทิตีกิจกรรมแบบรวมที่แสดงวันที่และเวลาของกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="cfcfe-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="cfcfe-205">เมื่อการแมปข้อมูลสำเร็จ คุณจะเห็นสถานะเป็น **เสร็จสมบูรณ์** และชื่อของกิจกรรมและแอตทริบิวต์ที่แมป</span><span class="sxs-lookup"><span data-stu-id="cfcfe-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="ภาพหน้าจอของการกำหนดค่าแม่แบบการวัดที่เสร็จสมบูรณ์":::

1. <span data-ttu-id="cfcfe-207">ตอนนี้คุณสามารถเลือก **เรียกใช้** เพื่อคำนวณผลลัพธ์ของการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="cfcfe-208">หากต้องการปรับแต่งในภายหลัง ให้เลือก **บันทึกแบบร่าง**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="cfcfe-209">จัดการการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-209">Manage your measures</span></span>

<span data-ttu-id="cfcfe-210">คุณสามารถดูรายการการวัดได้ที่หน้า **การวัด**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="cfcfe-211">คุณจะพบข้อมูลเกี่ยวกับชนิดการวัด ผู้สร้าง วันที่สร้าง สถานะ และสถานะ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="cfcfe-212">เมื่อคุณเลือกหน่วยวัดจากรายการ คุณสามารถพรีวิวผลลัพธ์และดาวน์โหลดไฟล์ .CSV</span><span class="sxs-lookup"><span data-stu-id="cfcfe-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="cfcfe-213">หากต้องการรีเฟรชมาตรการทั้งหมดของคุณในเวลาเดียวกัน ให้เลือก **รีเฟรชทั้งหมด** โดยไม่ต้องเลือกการวัดที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="cfcfe-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cfcfe-214">![การดำเนินการเพื่อจัดการมาตรการเดียว](media/measure-actions.png "การดำเนินการเพื่อจัดการมาตรการเดียว")</span><span class="sxs-lookup"><span data-stu-id="cfcfe-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="cfcfe-215">เลือกการวัดจากรายการสำหรับตัวเลือกต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="cfcfe-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="cfcfe-216">เลือกชื่อการวัดเพื่อดูรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="cfcfe-217">**แก้ไข** การกำหนดค่าของการวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="cfcfe-218">**รีเฟรช** การวัดตามข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="cfcfe-219">**เปลี่ยนชื่อ** การวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-219">**Rename** the measure.</span></span>
- <span data-ttu-id="cfcfe-220">**ลบ** การวัด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-220">**Delete** the measure.</span></span>
- <span data-ttu-id="cfcfe-221">**เปิดใช้งาน** หรือ **ปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="cfcfe-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="cfcfe-222">การวัดที่ไม่ใช้งานจะไม่ได้รับการรีเฟรชในช่วง [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="cfcfe-223">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="cfcfe-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cfcfe-224">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cfcfe-225">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="cfcfe-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cfcfe-226">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="cfcfe-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="cfcfe-227">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="cfcfe-227">Next step</span></span>

<span data-ttu-id="cfcfe-228">คุณใช้การวัดที่มีอยู่เพื่อสร้าง [เซ็กเมนต์ลูกค้า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="cfcfe-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
