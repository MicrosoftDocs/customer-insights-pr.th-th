---
title: เซ็กเมนต์ตามผลลัพธ์การคาดคะเน
description: สร้างเซ็กเมนต์ตามเอนทิตีผลลัพธ์ของแบบจำลองการคาดคะเน
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647911"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>สร้างเซ็กเมนต์ตามแบบจำลองการคาดคะเน (ตัวอย่าง)

บางครั้งผลลัพธ์ของการคาดการณ์จะใช้กับลูกค้าบางส่วนของคุณเท่านั้น เพิ่มการปรับเปลี่ยนคำแนะนำในแบบของคุณโดยการสร้างเซ็กเมนต์จากผลลัพธ์ของแบบจำลองการคาดคะเน ตัวอย่างเช่น คุณอาจต้องการให้คำแนะนำเฉพาะแก่ลูกค้าที่ชอบบริการบางชนิด 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- อย่างน้อยต้องมี [สิทธิ์ผู้สนับสนุน](permissions.md) ใน Customer Insights

- คำแนะนำผลิตภัณฑ์ การยกเลิกธุรกรรม การเลิกใช้บริการสมัครสมาชิก หรือโมเดลมูลค่าตลอดอายุการใช้งานของลูกค้าที่กำหนดค่าไว้ใน Customer Insights ตรวจสอบข้อกำหนดในการตั้งค่ารุ่นต่าง ๆ:

  - [โมเดลการแนะนําผลิตภัณฑ์](predict-product-recommendation.md)
  - [แบบจำลองการเลิกใช้บริการสมัครใช้งาน](predict-subscription-churn.md)
  - [แบบจำลองการยกเลิกธุรกรรม](predict-transactional-churn.md)
  - [โมเดลมูลค่าตลอดอายุการใช้งานของลูกค้า](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>สร้างเซ็กเมนต์ลูกค้าตามการคาดคะเน

1. ไปที่ **ระบบอัจฉริยะ** > **การคาดคะเน** และเลือกแท็บ **การคาดคะเนของฉัน**

1. เลือกจุดไข่ปลาแนวตั้งถัดจากแบบจำลองที่คุณต้องการตรวจสอบและเลือก **ดู**

1. ในหน้าผลลัพธ์ ให้เลือก **สร้างเซ็กเมนต์** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับหน้าผลลัพธ์ โปรดอ่านบทความเกี่ยวกับแบบจำลอง

   :::image type="content" source="media/prediction-create-segment.png" alt-text="ภาพหน้าจอของหน้าผลลัพธ์การคาดคะเนพร้อมไฮไลต์ในการดำเนินการสร้างเซ็กเมนต์":::

1. สร้างเซ็กเมนต์ใหม่ตามเอนทิตีผลลัพธ์ของแบบจำลองที่เลือก สำหรับข้อมูลเพิ่มเติม ดู [สร้างและจัดการเซ็กเมนต์](segments.md)