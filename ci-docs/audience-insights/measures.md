---
title: สร้างและจัดการการวัด
description: กำหนดการวัดเพื่อวิเคราะห์และสะท้อนผลการดำเนินงานของธุรกิจของคุณ
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269951"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="71532-103">กำหนดและจัดการการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-103">Define and manage measures</span></span>

<span data-ttu-id="71532-104">การวัดช่วยให้คุณเข้าใจพฤติกรรมของลูกค้าและผลการดำเนินงานทางธุรกิจได้ดียิ่งขึ้น โดยการดึงข้อมูลค่าที่เกี่ยวข้องจาก [โปรไฟล์แบบรวม](data-unification.md)</span><span class="sxs-lookup"><span data-stu-id="71532-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="71532-105">ตัวอย่างเช่น ธุรกิจต้องการดู *การใช้จ่ายทั้งหมดต่อลูกค้าหนึ่งราย* เพื่อทำความเข้าใจประวัติการซื้อของลูกค้าแต่ละราย</span><span class="sxs-lookup"><span data-stu-id="71532-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="71532-106">หรือวัดผล *ยอดขายรวมของบริษัท* เพื่อทำความเข้าใจรายได้ระดับรวมในธุรกิจทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="71532-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="71532-107">การวัดถูกสร้างขึ้นโดยใช้ตัวสร้างการวัด ซึ่งเป็นแพลตฟอร์มการสอบถามที่มีตัวดำเนินการต่างๆ และตัวเลือกการแม็ปอย่างง่าย</span><span class="sxs-lookup"><span data-stu-id="71532-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="71532-108">ช่วยให้คุณกรองข้อมูล จัดกลุ่มผลลัพธ์ ตรวจจับ [เส้นทางความสัมพันธ์ของเอนทิตี](relationships.md) และพรีวิวผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="71532-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="71532-109">ใช้ตัวสร้างการวัดเพื่อวางแผนกิจกรรมทางธุรกิจ โดยการสอบถามข้อมูลลูกค้าและดึงข้อมูลเชิงลึก</span><span class="sxs-lookup"><span data-stu-id="71532-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="71532-110">ตัวอย่างเช่น การสร้างการวัดของ *การใช้จ่ายทั้งหมดต่อลูกค้าหนึ่งราย* และ *ยอดรวมการคืนสินค้าต่อลูกค้าหนึ่งราย* ช่วยระบุกลุ่มลูกค้าที่มีการใช้จ่ายสูง แต่มีการคืนสินค้าสูง</span><span class="sxs-lookup"><span data-stu-id="71532-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="71532-111">คุณสามารถ [สร้างเซ็กเมนต์](segments.md) เพื่อขับเคลื่อนการดำเนินการที่ดีที่สุดต่อไป</span><span class="sxs-lookup"><span data-stu-id="71532-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="71532-112">สร้างการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-112">Create a measure</span></span>

<span data-ttu-id="71532-113">ส่วนนี้จะแนะนำคุณเกี่ยวกับการสร้างการวัดใหม่ตั้งแต่ต้น</span><span class="sxs-lookup"><span data-stu-id="71532-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="71532-114">คุณสามารถสร้างการวัดด้วยแอตทริบิวต์ข้อมูลจากเอนทิตีข้อมูลที่มีการตั้งค่าความสัมพันธ์เพื่อเชื่อมต่อกับเอนทิตีลูกค้า</span><span class="sxs-lookup"><span data-stu-id="71532-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="71532-115">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **การวัด**</span><span class="sxs-lookup"><span data-stu-id="71532-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="71532-116">เลือก **สร้าง**</span><span class="sxs-lookup"><span data-stu-id="71532-116">Select **New**.</span></span>

1. <span data-ttu-id="71532-117">เลือก **แก้ไขชื่อ** และระบุ **ชื่อ** สำหรับการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="71532-118">หากการกำหนดค่าการวัดใหม่ของคุณมีเพียงสองฟิลด์ ตัวอย่างเช่น CustomerID และการคำนวณหนึ่งรายการ ผลลัพธ์จะถูกเพิ่มเป็นคอลัมน์ใหม่ในเอนทิตีที่ระบบสร้างขึ้นที่เรียกว่า Customer_Measure</span><span class="sxs-lookup"><span data-stu-id="71532-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="71532-119">และคุณจะสามารถเห็นค่าของการวัดในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="71532-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="71532-120">การวัดอื่นๆ จะสร้างเอนทิตีของตนเอง</span><span class="sxs-lookup"><span data-stu-id="71532-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="71532-121">ในพื้นที่การกำหนดค่า ให้เลือกฟังก์ชันการรวมจากเมนูแบบหล่นลง **เลือกฟังก์ชัน**</span><span class="sxs-lookup"><span data-stu-id="71532-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="71532-122">ฟังก์ชันการรวมประกอบด้วย:</span><span class="sxs-lookup"><span data-stu-id="71532-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="71532-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="71532-123">**Sum**</span></span>
   - <span data-ttu-id="71532-124">**ค่าเฉลี่ย**</span><span class="sxs-lookup"><span data-stu-id="71532-124">**Average**</span></span>
   - <span data-ttu-id="71532-125">**นับจำนวน**</span><span class="sxs-lookup"><span data-stu-id="71532-125">**Count**</span></span>
   - <span data-ttu-id="71532-126">**นับรายการที่ไม่ซ้ำกัน**</span><span class="sxs-lookup"><span data-stu-id="71532-126">**Count Unique**</span></span>
   - <span data-ttu-id="71532-127">**ค่าสูงสุด**</span><span class="sxs-lookup"><span data-stu-id="71532-127">**Max**</span></span>
   - <span data-ttu-id="71532-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="71532-128">**Min**</span></span>
   - <span data-ttu-id="71532-129">**อันดับแรก**: รับค่าแรกของเรกคอร์ดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="71532-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="71532-130">**สุดท้าย**: รับค่าสุดท้ายที่เพิ่มลงในเรกคอร์ดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="71532-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="ตัวดำเนินการสำหรับการคำนวณการวัด":::

1. <span data-ttu-id="71532-132">เลือก **เพิ่มแอตทริบิวต์** เพื่อเลือกข้อมูลที่คุณต้องการสร้างการวัดนี้</span><span class="sxs-lookup"><span data-stu-id="71532-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="71532-133">เลือกแท็บ **แอตทริบิวต์**</span><span class="sxs-lookup"><span data-stu-id="71532-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="71532-134">เอนทิตีข้อมูล: เลือกเอนทิตีที่มีแอตทริบิวต์ที่คุณต้องการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="71532-135">แอตทริบิวต์ข้อมูล: เลือกแอตทริบิวต์ที่คุณต้องการใช้ในฟังก์ชันการรวมเพื่อคำนวณการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="71532-136">คุณสามารถเลือกได้ครั้งละหนึ่งแอตทริบิวต์เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="71532-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="71532-137">คุณยังสามารถเลือกแอตทริบิวต์ข้อมูลจากการวัดที่มีอยู่ได้ โดยเลือกแท็บ **การวัด** หรือคุณสามารถค้นหาชื่อเอนทิตีหรือชื่อการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="71532-138">เลือก **เพิ่ม** เพื่อเพิ่มแอตทริบิวต์ที่เลือกในการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="เลือกแอตทริบิวต์ที่จะใช้ในการคำนวณ":::

1. <span data-ttu-id="71532-140">ในการสร้างการวัดที่ซับซ้อนยิ่งขึ้น คุณสามารถเพิ่มแอตทริบิวต์เพิ่มเติมหรือใช้ตัวดำเนินการทางคณิตศาสตร์กับฟังก์ชันการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="71532-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="สร้างการวัดที่ซับซ้อนด้วยตัวดำเนินการทางคณิตศาสตร์":::

1. <span data-ttu-id="71532-142">ในการเพิ่มตัวกรอง ให้เลือก **กรอง** ในพื้นที่การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="71532-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="71532-143">ในส่วน **เพิ่มแอตทริบิวต์** ของบานหน้าต่าง **ตัวกรอง** เลือกแอตทริบิวต์ที่คุณต้องการใช้เพื่อสร้างตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="71532-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="71532-144">ตั้งค่าตัวดำเนินการกรองเพื่อกำหนดตัวกรองสำหรับทุกแอ็ตทริบิวต์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="71532-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="71532-145">เลือก **นำไปใช้** เพื่อเพิ่มตัวกรองในการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="71532-146">ในการเพิ่มมิติ ให้เลือก **มิติ** ในพื้นที่การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="71532-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="71532-147">ขนาดจะแสดงเป็นคอลัมน์ในเอนทิตีผลลัพธ์การวัด</span><span class="sxs-lookup"><span data-stu-id="71532-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="71532-148">เลือก **แก้ไขขนาด** เพื่อเพิ่มแอตทริบิวต์ข้อมูลที่คุณต้องการจัดกลุ่มค่าการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="71532-149">ตัวอย่างเช่น เมือง หรือ เพศ</span><span class="sxs-lookup"><span data-stu-id="71532-149">For example, city or gender.</span></span> <span data-ttu-id="71532-150">โดยค่าเริ่มต้น ขนาด *CustomerID* จะถูกเลือกเพื่อสร้าง *การวัดระดับลูกค้า*</span><span class="sxs-lookup"><span data-stu-id="71532-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="71532-151">คุณสามารถลบขนาดเริ่มต้นได้หากต้องการสร้าง *การวัดระดับธุรกิจ*</span><span class="sxs-lookup"><span data-stu-id="71532-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="71532-152">เลือก **เสร็จสิ้น** เพื่อเพิ่มมิติในการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="71532-153">หากมีหลายเส้นทางระหว่างเอนทิตีข้อมูลที่คุณแมปและเอนทิตีลูกค้า คุณต้องเลือกหนึ่งรายการที่ระบุ [เส้นทางความสัมพันธ์ของเอนทิตี](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="71532-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="71532-154">ผลการวัดอาจแตกต่างกันไปขึ้นอยู่กับเส้นทางที่เลือก</span><span class="sxs-lookup"><span data-stu-id="71532-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="71532-155">เลือก **การกําหนดลักษณะข้อมูล** และเลือกเส้นทางเอนทิตีที่ควรใช้เพื่อระบุการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="71532-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="71532-156">เลือก **เสร็จสิ้น** เพื่อใช้การเลือกของคุณ</span><span class="sxs-lookup"><span data-stu-id="71532-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="เลือกเส้นทางเอนทิตีสำหรับการวัด":::

1. <span data-ttu-id="71532-158">หากต้องการเพิ่มการคำนวณเพิ่มเติมสำหรับการวัด ให้เลือก **การคำนวณใหม่**</span><span class="sxs-lookup"><span data-stu-id="71532-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="71532-159">คุณสามารถใช้ได้เฉพาะเอนทิตีบนเส้นทางเอนทิตีเดียวกันสำหรับการคำนวณใหม่</span><span class="sxs-lookup"><span data-stu-id="71532-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="71532-160">การคำนวณเพิ่มเติมจะแสดงเป็นคอลัมน์ใหม่ ในเอนทิตีผลลัพธ์การวัด</span><span class="sxs-lookup"><span data-stu-id="71532-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="71532-161">เลือก **...** บนการคำนวณ เพื่อ **ทำซ้ำ** **เปลี่ยนชื่อ** หรือ **ลบ** การคำนวณจากการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="71532-162">ในพื้นที่ **การแสดงตัวอย่าง** คุณจะเห็น Schema ข้อมูลของเอนทิตีผลลัพธ์การวัด รวมถึงตัวกรองและมิติ</span><span class="sxs-lookup"><span data-stu-id="71532-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="71532-163">การแสดงตัวอย่างจะตอบสนองแบบไดนามิกต่อการเปลี่ยนแปลงในการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="71532-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="71532-164">เลือก **รัน** เพื่อคำนวณผลลัพธ์สำหรับการวัดที่กำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="71532-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="71532-165">เลือก **บันทึกและปิด** หากคุณต้องการเก็บการกำหนดค่าปัจจุบันไว้ และเรียกใช้การวัดในภายหลัง</span><span class="sxs-lookup"><span data-stu-id="71532-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="71532-166">ไปที่ **การวัด** เพื่อดูการวัดที่สร้างขึ้นใหม่ในรายการ</span><span class="sxs-lookup"><span data-stu-id="71532-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="71532-167">จัดการการวัดของคุณ</span><span class="sxs-lookup"><span data-stu-id="71532-167">Manage your measures</span></span>

<span data-ttu-id="71532-168">หลังจาก [สร้างการวัด](#create-a-measure) คุณจะเห็นรายการของการวัดในหน้า **การวัด**</span><span class="sxs-lookup"><span data-stu-id="71532-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="71532-169">คุณจะพบข้อมูลเกี่ยวกับชนิดการวัด ผู้สร้าง วันที่สร้าง สถานะ และสถานะ</span><span class="sxs-lookup"><span data-stu-id="71532-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="71532-170">เมื่อคุณเลือกหน่วยวัดจากรายการ คุณสามารถพรีวิวผลลัพธ์และดาวน์โหลดไฟล์ .CSV</span><span class="sxs-lookup"><span data-stu-id="71532-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="71532-171">หากต้องการรีเฟรชมาตรการทั้งหมดของคุณในเวลาเดียวกัน ให้เลือก **รีเฟรชทั้งหมด** โดยไม่ต้องเลือกการวัดที่เฉพาะเจาะจง</span><span class="sxs-lookup"><span data-stu-id="71532-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71532-172">![การดำเนินการเพื่อจัดการมาตรการเดียว](media/measure-actions.png "การดำเนินการเพื่อจัดการมาตรการเดียว")</span><span class="sxs-lookup"><span data-stu-id="71532-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="71532-173">เลือกการวัดจากรายการสำหรับตัวเลือกต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="71532-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="71532-174">เลือกชื่อการวัดเพื่อดูรายละเอียด</span><span class="sxs-lookup"><span data-stu-id="71532-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="71532-175">**แก้ไข** การกำหนดค่าของการวัด</span><span class="sxs-lookup"><span data-stu-id="71532-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="71532-176">**รีเฟรช** การวัดตามข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="71532-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="71532-177">**เปลี่ยนชื่อ** การวัด</span><span class="sxs-lookup"><span data-stu-id="71532-177">**Rename** the measure.</span></span>
- <span data-ttu-id="71532-178">**ลบ** การวัด</span><span class="sxs-lookup"><span data-stu-id="71532-178">**Delete** the measure.</span></span>
- <span data-ttu-id="71532-179">**เปิดใช้งาน** หรือ **ปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="71532-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="71532-180">การวัดที่ไม่ใช้งานจะไม่ได้รับการรีเฟรชในช่วง [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="71532-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="71532-181">โดยมี [สถานะหกชนิด](system.md#status-types) สำหรับงาน/กระบวนการ</span><span class="sxs-lookup"><span data-stu-id="71532-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="71532-182">นอกจากนี้กระบวนการส่วนใหญ่ [ขึ้นอยู่กับกระบวนการดาวน์สตรีมอื่นๆ](system.md#refresh-policies)</span><span class="sxs-lookup"><span data-stu-id="71532-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="71532-183">คุณสามารถเลือกสถานะของกระบวนการเพื่อดูรายละเอียดความคืบหน้าของงานที่เกิดขึ้นทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="71532-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="71532-184">หลังจากเลือก **ดูรายละเอียด** สำหรับหนึ่งในงานของงาน คุณจะพบข้อมูลเพิ่มเติม ได้แก่ เวลาในการประมวลผล วันที่ประมวลผลล่าสุด และข้อผิดพลาดและคำเตือนทั้งหมดที่เกี่ยวข้องกับงาน</span><span class="sxs-lookup"><span data-stu-id="71532-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="71532-185">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="71532-185">Next step</span></span>

<span data-ttu-id="71532-186">คุณใช้การวัดที่มีอยู่เพื่อสร้าง [เซ็กเมนต์ลูกค้า](segments.md)</span><span class="sxs-lookup"><span data-stu-id="71532-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]