---
title: ตัวเชื่อมต่อ Power Automate | Microsoft Docs
description: สร้างโฟลว์ใน Microsoft Power Automate จาก Dynamics 365 Customer Insights
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 95e0fcbfb43f2b3e7e2d0e8a1690dc7ff5a44433402b7ef3d437710eb0efff15
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035622"
---
# <a name="power-automate-connector-preview"></a>ตัวเชื่อมต่อ Power Automate (ตัวอย่าง)

ทริกเกอร์เหตุการณ์เฉพาะที่จะเกิดขึ้นโดยอัตโนมัติเมื่อข้อมูลของคุณมีการเปลี่ยนแปลง และจัดการโฟลว์ที่ซับซ้อนมากขึ้นโดยตรงใน [Power Automate](https://flow.microsoft.com/)

## <a name="power-automate-triggers"></a>ทริกเกอร์ Power Automate

ใช้ทริกเกอร์เพื่อสร้างโฟลว์ระบบคลาวด์ และทำให้งานซ้ำๆ เป็นแบบอัตโนมัติ เช่น การแจ้งเตือน หรือการดำเนินการขั้นสูงเพิ่มเติม 

- ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลล้มเหลว 
- ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลสำเร็จ
- ทริกเกอร์เมื่อข้ามขีดจำกัดในเซ็กเมนต์ ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- ทริกเกอร์เมื่อข้ามขีดจำกัดในการวัดของธุรกิจ เฉพาะการวัดของธุรกิจที่ไม่มีมิติจะได้รับการสนับสนุน ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- ทริกเกอร์เมื่อการรีเฟรชทั้งหมด (แหล่งข้อมูล, เซ็กเมนต์, การวัด, ...) เสร็จสมบูรณ์
- ทริกเกอร์เมื่อการรีเฟรชของกระบวนการรวม (แผนที่ จับคู่ ผสาน) เสร็จสมบูรณ์

[ตั้งค่าคอนฟิกทริกเกอร์ของคุณใน Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>การดำเนินการ Power Automate

ตัวเชื่อมต่อ Power Automate ให้การดำเนินการอื่นๆ นอกเหนือจากทริกเกอร์ที่มีอยู่ สำหรับข้อมูลเพิ่มเติม โปรดดู [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)

## <a name="create-a-power-automate-flow"></a>สร้างโฟลว์ Power Automate

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. บนไทล์ **Power Automate** เลือก **ตั้งค่า**

1. Customer Insights Connector (พรีวิว) ใน Power Automate เปิดขึ้น **ลงชื่อเข้าใช้** ไปยัง Power Automate

1. เลือกหนึ่งในทริกเกอร์ที่พร้อมใช้งาน และเพิ่มขั้นตอนเพิ่มเติมในโฟลว์ใหม่ของคุณ สำหรับข้อมูลเพิ่มเติม โปรดดู [สร้างโฟลว์ระบบคลาวด์ใน Power Automate](/power-automate/get-started-logic-flow)

ตัวอย่างวิธีการใช้โฟลว์: 
- โพสต์ข้อความไปยังช่องทาง Microsoft Teams หากการรีเฟรชแหล่งข้อมูลล้มเหลว 
- ส่งอีเมลไปยังเจ้าของข้อมูล เมื่อมีการข้ามขีดจำกัดในเซ็กเมนต์



[!INCLUDE[footer-include](../includes/footer-banner.md)]
