---
title: ภาพรวมเกี่ยวกับสถานการณ์การคาดคะเนที่รองรับ
description: สถานการณ์และตัวเลือกการคาดคะเนที่ครอบคลุมโดยแอปพลิเคชัน Dynamics 365 Customer Insights
ms.date: 12/21/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: c692785c7d81ab660ba2e07411e986c67c1a5d0a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228267"
---
# <a name="predictions-overview"></a>ภาพรวมการคาดคะเน

Dynamics 365 Customer Insights มาพร้อมกับตัวเลือกมากมายที่ใช้ประโยชน์จาก AI และ Machine Learning ในการคาดคะเนข้อมูล 

## <a name="out-of-box-models"></a>โมเดลแบบสำเร็จรูป

วิธีที่ง่ายที่สุดในการเริ่มต้นด้วยการคาดคะเนข้อมูลคือ โมเดลที่กำหนดไว้ล่วงหน้า ซึ่งมักเรียกว่าโมเดลสำเร็จรูป พวกเขาต้องการเพียงข้อมูลและโครงสร้างบางอย่างเพื่อสร้างข้อมูลเชิงลึกอย่างรวดเร็ว ในปัจจุบัน โมเดลต่อไปนี้พร้อมใช้งาน: 

# <a name="individual-consumers-b-to-c"></a>[ผู้บริโภครายบุคคล (B-to-C)](#tab/b2c)

- [มูลค่าตลอดอายุการใช้งานของลูกค้า](predict-customer-lifetime-value.md): คาดคะเนรายได้ที่เป็นไปได้ของลูกค้าตลอดการโต้ตอบทั้งหมดกับธุรกิจ
- [คำแนะนำผลิตภัณฑ์](predict-product-recommendation.md): แนะนำชุดของคำแนะนำผลิตภัณฑ์ที่คาดคะเนได้ตามพฤติกรรมการซื้อและลูกค้าที่มีรูปแบบการซื้อที่คล้ายคลึงกัน
- [การเลิกใช้บริการสมัครสมาชิก](predict-subscription-churn.md): คาดคะเนว่าลูกค้ามีความเสี่ยงในการหยุดใช้ผลิตภัณฑ์หรือบริการการสมัครสมาชิกของบริษัทของคุณหรือไม่
- [การเลิกทำธุรกรรม](predict-transactional-churn.md): คาดคะเนว่าลูกค้าจะไม่ซื้อผลิตภัณฑ์หรือบริการของคุณในกรอบเวลาหนึ่งๆ หรือไม่
- [การวิเคราะห์ความคิดเห็น](sentiment-analysis.md): วิเคราะห์ความคิดเห็นจากคำติชมของลูกค้าและระบุแง่มุมทางธุรกิจที่ถูกกล่าวถึงบ่อยๆ

# <a name="business-accounts-b-to-b"></a>[บัญชีธุรกิจ (B-to-B)](#tab/b2b)

- [การเลิกทำธุรกรรม](predict-transactional-churn.md): คาดคะเนว่าลูกค้าจะไม่ซื้อผลิตภัณฑ์หรือบริการของคุณในกรอบเวลาหนึ่งๆ หรือไม่

---


## <a name="azure-machine-learning-integration"></a>การรวม Azure Machine Learning

หากองค์กรใช้สถานการณ์ Machine Learning ตามการทดลองของ Azure Machine Learning แล้ว คุณลักษณะโมเดลที่กำหนดเองใน Customer Insights จะช่วยเชื่อมโยงจุดต่างๆ สร้างเวิร์กโฟลว์ที่ช่วยคุณเลือกข้อมูลที่คุณต้องการสร้างข้อมูลเชิงลึก และแมปผลลัพธ์กับโปรไฟล์ลูกค้าแบบรวมของคุณ สำหรับข้อมูลเพิ่มเติม โปรดดู [โมเดล Machine Learning ที่กำหนดเอง](custom-models.md)

## <a name="ai-builder-prediction"></a>การคาดคะเนของ AI Builder

บางครั้ง ชุดข้อมูลไม่สมบูรณ์ และค่าบางค่าหายไป Customer Insights สามารถช่วยในการคาดคะเนค่าที่ขาดหายไปสำหรับเอนทิตีและเซ็กเมนต์ของลูกค้า สำหรับข้อมูลเพิ่มเติม ดูที่ [กรอกข้อมูลบางส่วนของคุณด้วยการคาดคะเน](predictions.md)
