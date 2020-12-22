---
title: ค้นหาลูกค้าที่คล้ายกันด้วย AI
description: ค้นหาเซ็กเมนต์ลูกค้าที่คล้ายกันด้วยปัญญาประดิษฐ์
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407150"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="f23aa-103">ลูกค้าที่คล้ายกัน (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="f23aa-103">Similar Customers (preview)</span></span>

<span data-ttu-id="f23aa-104">คุณลักษณะนี้ช่วยให้คุณค้นหาลูกค้าที่คล้ายกันในฐานลูกค้าของคุณโดยใช้ปัญญาประดิษฐ์</span><span class="sxs-lookup"><span data-stu-id="f23aa-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="f23aa-105">คุณต้องสร้างอย่างน้อยหนึ่งเซ็กเมนต์ เพื่อใช้คุณสมบัตินี้</span><span class="sxs-lookup"><span data-stu-id="f23aa-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="f23aa-106">การขยายเกณฑ์ของเซ็กเมนต์ที่มีอยู่จะช่วยให้ค้นหาลูกค้าที่คล้ายกับเซ็กเมนต์ดังกล่าว</span><span class="sxs-lookup"><span data-stu-id="f23aa-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="f23aa-107">*ค้นหาลูกค้าที่คล้ายกัน* ใช้วิธีการอัตโนมัติในการประเมินข้อมูลและทำการคาดการณ์บนพื้นฐานของข้อมูลนั้น และดังนั้นจึงมีความสามารถที่จะใช้เป็นวิธีการทำโปรไฟล์ เนื่องจากคำดังกล่าวถูกกำหนดโดยข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล ("GDPR")</span><span class="sxs-lookup"><span data-stu-id="f23aa-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="f23aa-108">การใช้คุณลักษณะนี้ของลูกค้าเพื่อประมวลผลข้อมูลอาจอยู่ภายใต้ GDPR หรือกฎหมายหรือข้อบังคับอื่น ๆ</span><span class="sxs-lookup"><span data-stu-id="f23aa-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="f23aa-109">คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าคุณใช้ Dynamics 365 Customer Insights รวมถึงการคาดคะเนปฏิบัติตามกฎหมายและข้อบังคับที่เกี่ยวข้องทั้งหมด รวมถึงกฎหมายที่เกี่ยวข้องกับความเป็นส่วนตัว ข้อมูลส่วนบุคคล ข้อมูลไบโอเมตริก การปกป้องข้อมูล และการรักษาความลับของการสื่อสาร</span><span class="sxs-lookup"><span data-stu-id="f23aa-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="f23aa-110">การค้นหาลูกค้าที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-110">Finding similar customers</span></span>

1. <span data-ttu-id="f23aa-111">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **เซ็กเมนต์** และเลือกเซ็กเมนต์ที่คุณต้องการใช้เป็นฐานเซ็กเมนต์ใหม่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="f23aa-112">นั่นคือ *เซ็กเมนต์ต้นทาง* ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="f23aa-113">ในแถบการกระทำ ให้เลือก **ค้นหาลูกค้าที่คล้ายกัน**</span><span class="sxs-lookup"><span data-stu-id="f23aa-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="f23aa-114">ตรวจสอบชื่อที่แนะนำสำหรับเซ็กเมนต์ใหม่ของคุณ และเปลี่ยนหากจำเป็น</span><span class="sxs-lookup"><span data-stu-id="f23aa-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="f23aa-115">ตรวจสอบฟิลด์ที่กำหนดเซ็กเมนต์ใหม่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="f23aa-116">ฟิลด์เหล่านี้กำหนดพื้นฐานที่ระบบจะพยายามค้นหาลูกค้าที่คล้ายกันกับเซ็กเมนต์ต้นทางของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="f23aa-117">ระบบจะเลือกฟิลด์แนะนำตามค่าเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="f23aa-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="f23aa-118">ฟิลด์ที่สามารถลดประสิทธิภาพของโมเดลได้อย่างมากจะถูกยกเว้นโดยอัตโนมัติ:</span><span class="sxs-lookup"><span data-stu-id="f23aa-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="f23aa-119">ฟิลด์ที่มีชนิดข้อมูลต่อไปนี้: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="f23aa-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="f23aa-120">ฟิลด์ที่มีคาร์ดินาลลิตี้ (จำนวนองค์ประกอบในฟิลด์) น้อยกว่า 2 หรือมากกว่า 30</span><span class="sxs-lookup"><span data-stu-id="f23aa-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="f23aa-121">เลือกถ้าคุณต้องการรวม **ลูกค้าทุกคน** หรือเฉพาะลูกค้าใน **เซ็กเมนต์ที่มีอยู่เฉพาะ** ในเซ็กเมนต์ใหม่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="f23aa-122">ยกเว้นลูกค้าในเซ็กเมนต์ต้นทางของคุณ โดยเลือกกล่องกาเครื่องหมาย **ยกเว้นทุกคนในเซ็กเมนต์ต้นทาง**</span><span class="sxs-lookup"><span data-stu-id="f23aa-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="f23aa-123">ตามค่าเริ่มต้น ระบบจะแนะนำให้รวมขนาดผู้ชมเป้าหมายเพียง 20% ในเอาต์พุตของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="f23aa-124">แก้ไขเกณฑ์นี้ตามต้องการ</span><span class="sxs-lookup"><span data-stu-id="f23aa-124">Edit this threshold as needed.</span></span> <span data-ttu-id="f23aa-125">การเพิ่มเกณฑ์จะลดความแม่นยำ</span><span class="sxs-lookup"><span data-stu-id="f23aa-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="f23aa-126">เลือก **ดำเนินการ** ที่ด้านล่างของหน้า เพื่อเริ่มงานการจัดประเภทแบบไบนารี (วิธีการของการเรียนรู้เกี่ยวกับเครื่อง) ซึ่งวิเคราะห์ชุดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f23aa-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="f23aa-127">ดูเซ็กเมนต์ที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-127">View the similar segment</span></span>

<span data-ttu-id="f23aa-128">หลังจากประมวลผลเซ็กเมนต์ที่คล้ายกัน คุณจะพบเซ็กเมนต์ใหม่ที่ปรากฏในหน้า **เซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="f23aa-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f23aa-129">![เซ็กเมนต์ลูกค้าที่คล้ายกัน](media/expanded-segment.png "เซ็กเมนต์ลูกค้าที่คล้ายกัน")</span><span class="sxs-lookup"><span data-stu-id="f23aa-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="f23aa-130">เลือก **ดู** ในแถบการกระทำ เพื่อเปิดรายละเอียดของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="f23aa-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="f23aa-131">มุมมองนี้มีข้อมูลเกี่ยวกับการกระจายผลลัพธ์ข้าม [คะแนนความคล้ายคลึงกัน](#about-similarity-scores)</span><span class="sxs-lookup"><span data-stu-id="f23aa-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="f23aa-132">นอกจากนี้คุณยังจะพบค่าคะแนนความคล้ายคลึงกันใน **ดูตัวอย่างสมาชิกเซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="f23aa-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="f23aa-133">ใช้ผลลัพธ์ของเซ็กเมนต์ที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-133">Use the output of a similar segment</span></span>

<span data-ttu-id="f23aa-134">คุณสามารถ [ทำงานกับผลลัพธ์ของเซ็กเมนต์ที่คล้ายกัน](segments.md) เช่นเดียวกับเซ็กเมนต์อื่นๆ</span><span class="sxs-lookup"><span data-stu-id="f23aa-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="f23aa-135">ตัวอย่างเช่น ส่งออกเซ็กเมนต์หรือสร้างการวัด</span><span class="sxs-lookup"><span data-stu-id="f23aa-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="f23aa-136">รีเฟรชและแก้ไขเซ็กเมนต์ที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="f23aa-137">หากต้องการรีเฟรชเซ็กเมนต์ที่คล้ายกัน ให้เลือกเซ็กเมนต์บนหน้า **เซ็กเมนต์** และเลือก **รีเฟรช** ในแถบการกระทำ</span><span class="sxs-lookup"><span data-stu-id="f23aa-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="f23aa-138">การแก้ไขเซ็กเมนต์ที่คล้ายกันจะประมวลผลข้อมูลของคุณอีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="f23aa-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="f23aa-139">เซ็กเมนต์ที่สร้างไว้ก่อนหน้านี้ได้รับการอัปเดตด้วยข้อมูลที่รีเฟรช</span><span class="sxs-lookup"><span data-stu-id="f23aa-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="f23aa-140">หากต้องการแก้หขเซ็กเมนต์ที่คล้ายกัน ให้เลือกเซ็กเมนต์บนหน้า **เซ็กเมนต์** และเลือก **แก้ไข** ในแถบการกระทำ</span><span class="sxs-lookup"><span data-stu-id="f23aa-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="f23aa-141">ใช้การเปลี่ยนแปลงของคุณ และเลือก **ดำเนินการ** เพื่อเริ่มการประมวลผล</span><span class="sxs-lookup"><span data-stu-id="f23aa-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="f23aa-142">ลบเซ็กเมนต์ที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-142">Delete a similar segment</span></span>

<span data-ttu-id="f23aa-143">เลือกเซ็กเมนต์บนหน้า **เซ็กเมนต์** และเลือก **ลบ** ในแถบการกระทำ</span><span class="sxs-lookup"><span data-stu-id="f23aa-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="f23aa-144">จากนั้น ยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="f23aa-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="f23aa-145">เกี่ยวกับคะแนนความคล้ายคลึง</span><span class="sxs-lookup"><span data-stu-id="f23aa-145">About similarity scores</span></span>

<span data-ttu-id="f23aa-146">การเรียนรู้เกี่ยวกับเครื่องของการจัดประเภทแบบไบนารี กำหนดคะแนนให้กับลูกค้าในเซ็กเมนต์ที่คล้ายกัน</span><span class="sxs-lookup"><span data-stu-id="f23aa-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="f23aa-147">คะแนนขึ้นอยู่กับความคล้ายคลึงกันกับลูกค้าในเซ็กเมนต์ต้นทาง</span><span class="sxs-lookup"><span data-stu-id="f23aa-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="f23aa-148">คะแนนความคล้ายคลึงกันต่ำกว่า 0.55 เป็นลูกค้าที่ระบบจัดเป็น *ไม่เหมือนกัน* ให้กับลูกค้าในเซ็กเมนต์ต้นทาง</span><span class="sxs-lookup"><span data-stu-id="f23aa-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="f23aa-149">คะแนนความคล้ายคลึงกันระหว่าง 0.55 - 0.7 ถูกจัดประเภทเป็น *ค่อนข้างคล้ายกัน*</span><span class="sxs-lookup"><span data-stu-id="f23aa-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="f23aa-150">คะแนนความคล้ายคลึงกันระหว่าง 0.7 - 0.85 ถูกจัดประเภทเป็น *คล้ายกัน*</span><span class="sxs-lookup"><span data-stu-id="f23aa-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="f23aa-151">คะแนนความคล้ายคลึงกันระหว่าง 0.85 - 1 คือลูกค้าที่ระบบจัดเป็น *คล้ายกันมาก*</span><span class="sxs-lookup"><span data-stu-id="f23aa-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="f23aa-152">ลูกค้าที่มีคะแนนความคล้ายคลึงกันต่ำกว่า 0.4 จะไม่รวมอยู่ในโมเดลผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="f23aa-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="f23aa-153">ระบบไม่ถือว่าพวกเขาคล้ายกันมากพอสำหรับเซ็กเมนต์ต้นทาง</span><span class="sxs-lookup"><span data-stu-id="f23aa-153">The system doesn't consider them similar enough to the source segment.</span></span>
