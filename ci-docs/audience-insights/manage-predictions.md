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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095758"
---
# <a name="manage-predictions"></a><span data-ttu-id="305d2-103">จัดการการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="305d2-103">Manage predictions</span></span>

<span data-ttu-id="305d2-104">บทความนี้กล่าวถึงงานบางอย่างที่สถานการณ์การคาดคะเนส่วนใหญ่ใช้ร่วมกัน</span><span class="sxs-lookup"><span data-stu-id="305d2-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="305d2-105">แก้ไขปัญหาการคาดคะเนที่ล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="305d2-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="305d2-106">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="305d2-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="305d2-107">เลือกจุดไข่ปลาแนวตั้งถัดจากการคาดคะเนที่คุณต้องการดูบันทึกข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="305d2-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="305d2-108">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="305d2-108">Select **Logs**.</span></span>

1. <span data-ttu-id="305d2-109">ตรวจทานข้อผิดพลาดทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="305d2-109">Review all the errors.</span></span> <span data-ttu-id="305d2-110">มีข้อผิดพลาดหลายประเภทที่สามารถเกิดขึ้นได้ และข้อผิดพลาดเหล่านั้นอธิบายถึงเงื่อนไขที่ทำให้เกิดข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="305d2-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="305d2-111">ตัวอย่างเช่น ข้อผิดพลาดที่มีข้อมูลไม่เพียงพอที่จะคาดคะเนได้อย่างแม่นยำมักจะได้รับการแก้ไขโดยการโหลดข้อมูลเพิ่มเติมลงใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="305d2-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="305d2-112">รายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="305d2-112">Input data usability report</span></span>

<span data-ttu-id="305d2-113">รายงานการใช้งานข้อมูลป้อนเข้ามีมุมมองแบบรวมของข้อผิดพลาดและคำเตือนที่อาจสร้างขึ้นจากการคาดคะเนแบบสำเร็จรูปของคุณ</span><span class="sxs-lookup"><span data-stu-id="305d2-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="305d2-114">นอกจากนี้ ยังให้คำแนะนำในการปรับปรุงประสิทธิภาพของแบบจำลอง</span><span class="sxs-lookup"><span data-stu-id="305d2-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="305d2-115">รายงานจะพร้อมใช้งานหลังจากแบบจำลองเสร็จสิ้นกระบวนการฝึกอบรม</span><span class="sxs-lookup"><span data-stu-id="305d2-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="305d2-116">ซึ่งถูกสร้างขึ้นสำหรับแต่ละโมเดลโดยแยกกัน โดยไม่คำนึงว่าจะสำเร็จหรือไม่</span><span class="sxs-lookup"><span data-stu-id="305d2-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="305d2-117">ในปัจจุบัน คุณลักษณะนี้ใช้ได้เฉพาะสำหรับโมเดลการเลิกทำธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="305d2-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="305d2-118">ดูรายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="305d2-118">View the input data usability report</span></span>

<span data-ttu-id="305d2-119">หลังจากที่โมเดลแบบสำเร็จรูปเสร็จสิ้นขั้นตอนการฝึกอบรมแล้ว ให้ดูรายงาน:</span><span class="sxs-lookup"><span data-stu-id="305d2-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="305d2-120">เลือกจุดไข่ปลาถัดจากชื่อโมเดล และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า**</span><span class="sxs-lookup"><span data-stu-id="305d2-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="305d2-121">เลือกสถานะของโมเดล เลือก **ดูรายงานการใช้งานข้อมูลป้อนเข้า** ในบานหน้าต่างด้านข้าง</span><span class="sxs-lookup"><span data-stu-id="305d2-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="305d2-122">การเลือกหนึ่งในโมเดลในรายการ และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="305d2-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="305d2-123">เปิดหน้าผลลัพธ์โมเดล และเลือก **รายงานการใช้งานข้อมูลป้อนเข้า** ในแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="305d2-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="305d2-124">ข้อมูลในรายงานการใช้งานข้อมูลป้อนเข้า</span><span class="sxs-lookup"><span data-stu-id="305d2-124">Information in the input data usability report</span></span>

<span data-ttu-id="305d2-125">คอลัมน์ต่อไปนี้ในรายงานมีข้อมูลที่เป็นประโยชน์ในการปรับปรุงข้อมูลสำหรับโมเดล</span><span class="sxs-lookup"><span data-stu-id="305d2-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="ตัวอย่างของรายงานการใช้งานข้อมูลป้อนเข้าที่แสดงตารางที่มีข้อผิดพลาด คำเตือน และคำแนะนำ":::

- <span data-ttu-id="305d2-127">ชื่อ: ชื่อที่เป็นคำอธิบายของข้อผิดพลาด คำเตือน หรือคำแนะนำ</span><span class="sxs-lookup"><span data-stu-id="305d2-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="305d2-128">ขั้นตอน: ระยะโมเดล การฝึก หรือคะแนน ที่ข้อมูลอ้างอิงถึง</span><span class="sxs-lookup"><span data-stu-id="305d2-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="305d2-129">สถานะ: ความรุนแรงของข้อมูล (ข้อผิดพลาด คำเตือน คำแนะนำ)</span><span class="sxs-lookup"><span data-stu-id="305d2-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="305d2-130">ชื่อคอลัมน์: คอลัมน์ในเอนทิตีที่ต้องมีการแก้ไขเพื่อปรับปรุงประสิทธิภาพของโมเดล</span><span class="sxs-lookup"><span data-stu-id="305d2-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="305d2-131">ชื่อเอนทิตี: ชื่อของเอนทิตีที่ต้องมีการแก้ไขเพื่อปรับปรุงประสิทธิภาพของโมเดล</span><span class="sxs-lookup"><span data-stu-id="305d2-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="305d2-132">รายละเอียด: รายละเอียดเกี่ยวกับข้อผิดพลาด คำเตือน หรือคำแนะนำ</span><span class="sxs-lookup"><span data-stu-id="305d2-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="305d2-133">รีเฟรชการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="305d2-133">Refresh a prediction</span></span>

<span data-ttu-id="305d2-134">การคาดคะเนจะรีเฟรชอัตโนมัติใน [กำหนดการรีเฟรชข้อมูลของคุณ](system.md#schedule-tab) เดียวกันกับที่กำหนดไว้ในการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="305d2-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="305d2-135">คุณสามารถรีเฟรชด้วยตนเองได้เช่นกัน</span><span class="sxs-lookup"><span data-stu-id="305d2-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="305d2-136">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="305d2-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="305d2-137">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="305d2-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="305d2-138">เลือก **รีเฟรช**</span><span class="sxs-lookup"><span data-stu-id="305d2-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="305d2-139">ลบการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="305d2-139">Delete a prediction</span></span>

<span data-ttu-id="305d2-140">การลบการคาดคะเนจะลบเอนทิตีผลลัพธ์ด้วย</span><span class="sxs-lookup"><span data-stu-id="305d2-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="305d2-141">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="305d2-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="305d2-142">เลือกวงรีแนวตั้งถัดจากการคาดคะเนที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="305d2-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="305d2-143">เลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="305d2-143">Select **Delete**.</span></span>
