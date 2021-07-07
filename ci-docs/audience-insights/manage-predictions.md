---
title: งานที่ใช้ร่วมกันสำหรับสถานการณ์การคาดคะเน
description: เรียนรู้วิธีจัดการ แก้ไขปัญหา และปรับแต่งการคาดคะเน
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315901"
---
# <a name="manage-predictions"></a><span data-ttu-id="b5652-103">จัดการการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="b5652-103">Manage predictions</span></span>

<span data-ttu-id="b5652-104">บทความนี้กล่าวถึงงานบางอย่างที่สถานการณ์การคาดคะเนส่วนใหญ่ใช้ร่วมกัน</span><span class="sxs-lookup"><span data-stu-id="b5652-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="b5652-105">แก้ไขปัญหาการคาดคะเนที่ล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="b5652-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="b5652-106">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="b5652-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="b5652-107">เลือกจุดไข่ปลาแนวตั้งถัดจากการคาดคะเนที่คุณต้องการดูบันทึกข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="b5652-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="b5652-108">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="b5652-108">Select **Logs**.</span></span>

1. <span data-ttu-id="b5652-109">ตรวจทานข้อผิดพลาดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="b5652-109">Review all the errors.</span></span> <span data-ttu-id="b5652-110">มีข้อผิดพลาดหลายประเภทที่สามารถเกิดขึ้นได้ และข้อผิดพลาดเหล่านั้นอธิบายถึงเงื่อนไขที่ทำให้เกิดข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="b5652-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="b5652-111">ตัวอย่างเช่น ข้อผิดพลาดที่มีข้อมูลไม่เพียงพอที่จะคาดคะเนได้อย่างแม่นยำมักจะได้รับการแก้ไขโดยการโหลดข้อมูลเพิ่มเติมลงใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b5652-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="b5652-112">รายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="b5652-112">Input data usability report</span></span>

<span data-ttu-id="b5652-113">รายงานการใช้งานข้อมูลป้อนเข้ามีมุมมองแบบรวมของข้อผิดพลาดและคำเตือนที่อาจสร้างขึ้นจากการคาดคะเนแบบสำเร็จรูปของคุณ</span><span class="sxs-lookup"><span data-stu-id="b5652-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="b5652-114">นอกจากนี้ ยังให้คำแนะนำในการปรับปรุงประสิทธิภาพของแบบจำลอง</span><span class="sxs-lookup"><span data-stu-id="b5652-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="b5652-115">รายงานจะพร้อมใช้งานหลังจากแบบจำลองเสร็จสิ้นกระบวนการฝึกอบรม</span><span class="sxs-lookup"><span data-stu-id="b5652-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="b5652-116">ซึ่งถูกสร้างขึ้นสำหรับแต่ละโมเดลโดยแยกกัน โดยไม่คำนึงว่าจะสำเร็จหรือไม่</span><span class="sxs-lookup"><span data-stu-id="b5652-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="b5652-117">ดูรายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="b5652-117">View the input data usability report</span></span>

<span data-ttu-id="b5652-118">หลังจากที่โมเดลแบบสำเร็จรูปเสร็จสิ้นขั้นตอนการฝึกอบรมแล้ว ให้ดูรายงาน:</span><span class="sxs-lookup"><span data-stu-id="b5652-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="b5652-119">เลือกจุดไข่ปลาถัดจากชื่อโมเดล และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า**</span><span class="sxs-lookup"><span data-stu-id="b5652-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="b5652-120">เลือกสถานะของโมเดล เลือก **ดูรายงานการใช้งานข้อมูลป้อนเข้า** ในบานหน้าต่างด้านข้าง</span><span class="sxs-lookup"><span data-stu-id="b5652-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="b5652-121">การเลือกหนึ่งในโมเดลในรายการ และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="b5652-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="b5652-122">เปิดหน้าผลลัพธ์โมเดล และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="b5652-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="b5652-123">ข้อมูลในรายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="b5652-123">Information in the input data usability report</span></span>

<span data-ttu-id="b5652-124">คอลัมน์ต่อไปนี้ในรายงานมีข้อมูลที่เป็นประโยชน์ในการปรับปรุงข้อมูลสำหรับโมเดล</span><span class="sxs-lookup"><span data-stu-id="b5652-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="ตัวอย่างของรายงานการใช้งานข้อมูลป้อนเข้าที่แสดงตารางที่มีข้อผิดพลาด คำเตือน และคำแนะนำ":::

- <span data-ttu-id="b5652-126">ชื่อ: ชื่อที่เป็นคำอธิบายของข้อผิดพลาด คำเตือน หรือคำแนะนำ</span><span class="sxs-lookup"><span data-stu-id="b5652-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="b5652-127">ขั้นตอน: ระยะโมเดล การฝึก หรือคะแนน ที่ข้อมูลอ้างอิงถึง</span><span class="sxs-lookup"><span data-stu-id="b5652-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="b5652-128">สถานะ: ความรุนแรงของข้อมูล (ข้อผิดพลาด คำเตือน คำแนะนำ)</span><span class="sxs-lookup"><span data-stu-id="b5652-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="b5652-129">ชื่อคอลัมน์: คอลัมน์ในเอนทิตีที่ต้องมีการแก้ไขเพื่อปรับปรุงประสิทธิภาพของโมเดล</span><span class="sxs-lookup"><span data-stu-id="b5652-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="b5652-130">ชื่อเอนทิตี: ชื่อของเอนทิตีที่ต้องมีการแก้ไขเพื่อปรับปรุงประสิทธิภาพของโมเดล</span><span class="sxs-lookup"><span data-stu-id="b5652-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="b5652-131">รายละเอียด: รายละเอียดเกี่ยวกับข้อผิดพลาด คำเตือน หรือคำแนะนำ</span><span class="sxs-lookup"><span data-stu-id="b5652-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="b5652-132">รีเฟรชการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="b5652-132">Refresh a prediction</span></span>

<span data-ttu-id="b5652-133">การคาดคะเนจะรีเฟรชอัตโนมัติใน [กำหนดการรีเฟรชข้อมูลของคุณ](system.md#schedule-tab) เดียวกันกับที่กำหนดไว้ในการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="b5652-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="b5652-134">คุณสามารถรีเฟรชด้วยตนเองได้เช่นกัน</span><span class="sxs-lookup"><span data-stu-id="b5652-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="b5652-135">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="b5652-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="b5652-136">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="b5652-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="b5652-137">เลือก **รีเฟรช**</span><span class="sxs-lookup"><span data-stu-id="b5652-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="b5652-138">ลบการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="b5652-138">Delete a prediction</span></span>

<span data-ttu-id="b5652-139">การลบการคาดคะเนจะลบเอนทิตีผลลัพธ์ด้วย</span><span class="sxs-lookup"><span data-stu-id="b5652-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="b5652-140">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="b5652-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="b5652-141">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="b5652-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="b5652-142">เลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="b5652-142">Select **Delete**.</span></span>
