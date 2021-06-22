---
title: ภาพรวมเกี่ยวกับสถานการณ์การคาดคะเนที่รองรับ
description: สถานการณ์และตัวเลือกการคาดคะเนที่ครอบคลุมโดยแอปพลิเคชัน Dynamics 365 Customer Insights
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095757"
---
# <a name="predictions-overview"></a><span data-ttu-id="54ccd-103">ภาพรวมการคาดคะเน</span><span class="sxs-lookup"><span data-stu-id="54ccd-103">Predictions overview</span></span>

<span data-ttu-id="54ccd-104">Dynamics 365 Customer Insights มาพร้อมกับตัวเลือกมากมายที่ใช้ประโยชน์จาก AI และ Machine Learning ในการคาดคะเนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="54ccd-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="54ccd-105">โมเดลแบบสำเร็จรูป</span><span class="sxs-lookup"><span data-stu-id="54ccd-105">Out-of-box models</span></span>

<span data-ttu-id="54ccd-106">วิธีที่ง่ายที่สุดในการเริ่มต้นด้วยการคาดคะเนข้อมูลคือ โมเดลที่กำหนดไว้ล่วงหน้า ซึ่งมักเรียกว่าโมเดลสำเร็จรูป</span><span class="sxs-lookup"><span data-stu-id="54ccd-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="54ccd-107">พวกเขาต้องการเพียงข้อมูลและโครงสร้างบางอย่างเพื่อสร้างข้อมูลเชิงลึกอย่างรวดเร็ว</span><span class="sxs-lookup"><span data-stu-id="54ccd-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="54ccd-108">ในปัจจุบัน โมเดลต่อไปนี้พร้อมใช้งาน:</span><span class="sxs-lookup"><span data-stu-id="54ccd-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="54ccd-109">[มูลค่าตลอดอายุการใช้งานของลูกค้า](predict-customer-lifetime-value.md): คาดคะเนรายได้ที่เป็นไปได้ของลูกค้าตลอดการโต้ตอบทั้งหมดกับธุรกิจ</span><span class="sxs-lookup"><span data-stu-id="54ccd-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="54ccd-110">[คำแนะนำผลิตภัณฑ์](predict-product-recommendation.md): แนะนำชุดของคำแนะนำผลิตภัณฑ์ที่คาดคะเนได้ตามพฤติกรรมการซื้อและลูกค้าที่มีรูปแบบการซื้อที่คล้ายคลึงกัน</span><span class="sxs-lookup"><span data-stu-id="54ccd-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="54ccd-111">[การเลิกใช้การสมัครใช้งาน](predict-subscription-churn.md): คาดคะเนว่าลูกค้ามีความเสี่ยงในการหยุดใช้ผลิตภัณฑ์หรือบริการการสมัครใช้งานของบริษัทของคุณหรือไม่</span><span class="sxs-lookup"><span data-stu-id="54ccd-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="54ccd-112">[การเลิกทำธุรกรรม](predict-transactional-churn.md): คาดคะเนว่าลูกค้าจะไม่ซื้อผลิตภัณฑ์หรือบริการของคุณในกรอบเวลาหนึ่งๆ หรือไม่</span><span class="sxs-lookup"><span data-stu-id="54ccd-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="54ccd-113">การรวม Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="54ccd-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="54ccd-114">หากองค์กรใช้สถานการณ์ Machine Learning ตามการทดลองของ Azure Machine Learning แล้ว คุณลักษณะโมเดลที่กำหนดเองใน Customer Insights จะช่วยเชื่อมโยงจุดต่างๆ</span><span class="sxs-lookup"><span data-stu-id="54ccd-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="54ccd-115">สร้างเวิร์กโฟลว์ที่ช่วยคุณเลือกข้อมูลที่คุณต้องการสร้างข้อมูลเชิงลึก และแม็ปผลลัพธ์กับโปรไฟล์ลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="54ccd-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="54ccd-116">สำหรับข้อมูลเพิ่มเติม โปรดดู [โมเดล Machine Learning ที่กำหนดเอง](custom-models.md)</span><span class="sxs-lookup"><span data-stu-id="54ccd-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="54ccd-117">การคาดคะเน AI Builder</span><span class="sxs-lookup"><span data-stu-id="54ccd-117">AI Builder prediction</span></span>

<span data-ttu-id="54ccd-118">บางครั้ง ชุดข้อมูลไม่สมบูรณ์ และค่าบางค่าหายไป</span><span class="sxs-lookup"><span data-stu-id="54ccd-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="54ccd-119">Customer Insights สามารถช่วยในการคาดคะเนค่าที่ขาดหายไปสำหรับเอนทิตีและเซ็กเมนต์ของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="54ccd-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="54ccd-120">สำหรับข้อมูลเพิ่มเติม ดูที่ [กรอกข้อมูลบางส่วนของคุณด้วยการคาดคะเน](predictions.md)</span><span class="sxs-lookup"><span data-stu-id="54ccd-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
