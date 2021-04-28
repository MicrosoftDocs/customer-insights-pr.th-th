---
title: เซ็กเมนต์ตามผลลัพธ์การคาดคะเน
description: สร้างเซ็กเมนต์ตามเอนทิตีผลลัพธ์ของแบบจำลองการคาดคะเน
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741452"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="f1b56-103">สร้างเซ็กเมนต์ตามแบบจำลองการคาดคะเน (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="f1b56-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="f1b56-104">บางครั้งผลลัพธ์ของการคาดการณ์จะใช้กับลูกค้าบางส่วนของคุณเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="f1b56-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="f1b56-105">เพิ่มการปรับเปลี่ยนคำแนะนำในแบบของคุณโดยการสร้างเซ็กเมนต์จากผลลัพธ์ของแบบจำลองการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="f1b56-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="f1b56-106">ตัวอย่างเช่น คุณอาจต้องการให้คำแนะนำเฉพาะแก่ลูกค้าที่ชอบบริการบางชนิด</span><span class="sxs-lookup"><span data-stu-id="f1b56-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f1b56-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="f1b56-107">Prerequisites</span></span>

- <span data-ttu-id="f1b56-108">อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f1b56-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="f1b56-109">คำแนะนำผลิตภัณฑ์ การยกเลิกธุรกรรม การยกเลิกการสมัครสมาชิก หรือแบบจำลองมูลค่าตลอดอายุการใช้งานของลูกค้าที่กำหนดค่าไว้ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f1b56-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="f1b56-110">ตรวจสอบข้อกำหนดในการตั้งค่ารุ่นต่าง ๆ:</span><span class="sxs-lookup"><span data-stu-id="f1b56-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="f1b56-111">โมเดลการแนะนําผลิตภัณฑ์</span><span class="sxs-lookup"><span data-stu-id="f1b56-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="f1b56-112">แบบจำลองการเลิกใช้บริการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="f1b56-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="f1b56-113">แบบจำลองการยกเลิกธุรกรรม</span><span class="sxs-lookup"><span data-stu-id="f1b56-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="f1b56-114">แบบจำลองมูลค่าตลอดอายุการใช้งานของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="f1b56-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="f1b56-115">สร้างเซ็กเมนต์ลูกค้าตามการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="f1b56-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="f1b56-116">ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**</span><span class="sxs-lookup"><span data-stu-id="f1b56-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f1b56-117">เลือกจุดไข่ปลาแนวตั้งถัดจากแบบจำลองที่คุณต้องการตรวจสอบและเลือก **ดู**</span><span class="sxs-lookup"><span data-stu-id="f1b56-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="f1b56-118">ในหน้าผลลัพธ์ ให้เลือก **สร้างเซ็กเมนต์**</span><span class="sxs-lookup"><span data-stu-id="f1b56-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="f1b56-119">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับหน้าผลลัพธ์ โปรดอ่านบทความเกี่ยวกับแบบจำลอง</span><span class="sxs-lookup"><span data-stu-id="f1b56-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="ภาพหน้าจอของหน้าผลลัพธ์การคาดคะเนพร้อมไฮไลต์ในการดำเนินการสร้างเซ็กเมนต์":::

1. <span data-ttu-id="f1b56-121">สร้างเซ็กเมนต์ใหม่ตามเอนทิตีผลลัพธ์ของแบบจำลองที่เลือก</span><span class="sxs-lookup"><span data-stu-id="f1b56-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="f1b56-122">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f1b56-122">For more information, see [Create and manage segments](segments.md).</span></span>