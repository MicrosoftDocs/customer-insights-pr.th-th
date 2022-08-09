---
title: ตัวเชื่อมต่อ Power Automate (พรีวิว) | เอกสาร Microsoft
description: สร้างโฟลว์ใน Microsoft Power Automate จาก Dynamics 365 Customer Insights
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196141"
---
# <a name="power-automate-connector-preview"></a>ตัวเชื่อมต่อ Power Automate (พรีวิว)

ทริกเกอร์เหตุการณ์เฉพาะที่จะเกิดขึ้นโดยอัตโนมัติเมื่อข้อมูลของคุณมีการเปลี่ยนแปลง และจัดการโฟลว์ที่ซับซ้อนมากขึ้นโดยตรงใน [Microsoft Power Automate](https://flow.microsoft.com/)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- เรียกได้สูงสุด 100 ครั้งต่อ 60 วินาที ใช้ [พารามิเตอร์ $skip](/connectors/customerinsights/#get-items-from-an-entity) เรียกตำแหน่งข้อมูล API หลายครั้ง

## <a name="power-automate-triggers"></a>ทริกเกอร์ Power Automate

ใช้ทริกเกอร์เพื่อสร้างโฟลว์ระบบคลาวด์ และทำให้งานซ้ำๆ เป็นแบบอัตโนมัติ เช่น การแจ้งเตือน หรือการดำเนินการขั้นสูงเพิ่มเติม ใช้ทริกเกอร์เมื่อ:

- การรีเฟรชแหล่งข้อมูล
- การรีเฟรชแหล่งข้อมูลสำเร็จ
- มีการข้ามขีดจำกัดในเซ็กเมนต์ ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- มีการข้ามขีดจำกัดในการวัดของธุรกิจ เฉพาะการวัดของธุรกิจที่ไม่มีมิติจะได้รับการสนับสนุน ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- การรีเฟรชตามกำหนดการแบบเต็มเสร็จสิ้นแล้ว ทริกเกอร์นี้ใช้ไม่ได้กับการรีเฟรชที่เริ่มด้วยตนเอง
- การรีเฟรชกระบวนการรวมเสร็จสิ้น

[กำหนดค่าทริกเกอร์ของคุณใน Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>การดำเนินการ Power Automate

ตัวเชื่อมต่อ Power Automate ให้การดำเนินการอื่นๆ นอกเหนือจากทริกเกอร์ที่มีอยู่ สำหรับข้อมูลเพิ่มเติม โปรดดู [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)

## <a name="create-a-power-automate-flow"></a>สร้างโฟลว์ Power Automate

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. บนไทล์ **Power Automate** เลือก **ตั้งค่า**

1. Customer Insights Connector (พรีวิว) ใน Power Automate เปิดขึ้น **ลงชื่อเข้าใช้** ไปยัง Power Automate

1. เลือกหนึ่งในทริกเกอร์ที่พร้อมใช้งาน และเพิ่มขั้นตอนเพิ่มเติมในโฟลว์ใหม่ของคุณ สำหรับข้อมูลเพิ่มเติม โปรดดู [สร้างโฟลว์ระบบคลาวด์ใน Power Automate](/power-automate/get-started-logic-flow)

ตัวอย่างวิธีการใช้โฟลว์: 
- โพสต์ข้อความไปยังช่องทาง Microsoft Teams หากการรีเฟรชแหล่งข้อมูลล้มเหลว 
- ส่งอีเมลไปยังเจ้าของข้อมูล เมื่อมีการข้ามขีดจำกัดในเซ็กเมนต์

[!INCLUDE [footer-include](includes/footer-banner.md)]
