---
title: ตัวเชื่อมต่อ Power Automate | Microsoft Docs
description: สร้างโฟลว์ใน Microsoft Power Automate จาก Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407118"
---
# <a name="power-automate-connector-preview"></a>ตัวเชื่อมต่อ Power Automate (ตัวอย่าง)

ทริกเกอร์เหตุการณ์เฉพาะที่จะเกิดขึ้นโดยอัตโนมัติเมื่อข้อมูลของคุณมีการเปลี่ยนแปลง และจัดการโฟลว์ที่ซับซ้อนมากขึ้นโดยตรงใน [Power Automate](https://flow.microsoft.com/)

## <a name="power-automate-triggers"></a>ทริกเกอร์ Power Automate

คุณสามารถใช้ทริกเกอร์ที่หลากหลายที่อนุญาตให้คุณสร้างโฟลว์เพื่อทำงานซ้ำอัตโนมัติ เช่น การแจ้งเตือน หรือการดำเนินการขั้นสูงอื่นๆ 

- ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลล้มเหลว 
- ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลสำเร็จ
- ทริกเกอร์เมื่อข้ามขีดจำกัดในเซ็กเมนต์ ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- ทริกเกอร์เมื่อข้ามขีดจำกัดในการวัดของธุรกิจ ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด
- ทริกเกอร์เมื่อการรีเฟรชทั้งหมด (แหล่งข้อมูล, เซ็กเมนต์, การวัด...) เสร็จสมบูรณ์
- ทริกเกอร์เมื่อการรีเฟรชของกระบวนการรวม (แผนที่ จับคู่ ผสาน) เสร็จสมบูรณ์

[กำหนดค่าทริกเกอร์ของคุณใน Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>การดำเนินการ Power Automate
ตัวเชื่อมต่อ Power Automate ให้การดำเนินการอื่นๆ นอกเหนือจากทริกเกอร์ที่มีอยู่ สำหรับข้อมูลเพิ่มเติม โปรดดู [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)

## <a name="create-a-power-automate-flow-in-audience-insights"></a>สร้างโฟลว์ Power Automate ในข้อมูลเชิงลึกกลุ่มเป้าหมาย

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ระบบ**

1. บนหน้า **ระบบ** เลือกแท็บ **สถานะ**.

1. ในส่วน **แหล่งข้อมูล** ให้เลือก **โฟลว์** และเลือก **สร้างโฟลว์** จากรายการแบบเลื่อนลง
   > [!div class="mx-imgBorder"]
   > ![ตัวเชื่อมต่อ Power Automate ที่แสดงการสร้างการดำเนินการของโฟลว์](media/power-automate-connector-create-flow.png "ตัวเชื่อมต่อ Power Automate แสดงการสร้างการดำเนินการของโฟลว์")

1. ใน Power Automate เลือกหนึ่งในทริกเกอร์ที่มีอยู่เพื่อสร้างโฟลว์ที่คุณต้องการ หากคุณกำลังสร้างโฟลว์แรก คุณต้องรับรองความถูกต้องด้วยตัวเชื่อมต่อ Power Automate ก่อน
