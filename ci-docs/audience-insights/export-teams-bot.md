---
title: บอทสำหรับ Microsoft Teams
description: ค้นหาโปรไฟล์ลูกค้าแบบรวมใน Microsoft Teams ด้วยความช่วยเหลือของบอท
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267975"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>บอท Teams สำหรับ Dynamics 365 Customer Insights (พรีวิว)

เชื่อมต่อ Microsoft Teams เพื่อให้บอทค้นหาโปรไฟล์ลูกค้าแบบรวมในช่องทาง Teams

> [!div class="mx-imgBorder"]
> ![บอทของ Teams แสดงเรกคอร์ดลูกค้า](media/teams-bot.png "บอทของ Teams แสดงเรกคอร์ดลูกค้า")

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ในการตั้งค่าและกำหนดค่าบอท ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

- มีอย่างน้อยหนึ่ง [แหล่งข้อมูลถูกเพิ่ม](data-sources.md)
- [กระบวนการรวมข้อมูล](data-unification.md) เสร็จสมบูรณ์
- ฟิลด์จะถูกเพิ่มไปยัง [ดัชนีการค้นหาและตัวกรอง](search-filter-index.md)
- Customer Insights และ Teams อยู่ในองค์กรเดียวกัน

## <a name="configure-the-bot"></a>ตั้งค่าคอนฟิกบอท

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**
1. บนไทล์ Microsoft Teams เลือก **ตั้งค่า**
1. คุณถูกเปลี่ยนเส้นทางไปยังพื้นที่ **แอป** ใน Teams คุณสามารถเปิด Teams และเลือก **แอป** ที่มุมล่างซ้ายหรือ [รับจาก AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) โดยตรง
1. ค้นหา **Customer Insights** และเลือกแอป
1. เลือก **เพิ่ม**
1. หลังจากลงชื่อเข้าใช้ Customer Insights ใน Teams คุณจะเห็นข้อความต้อนรับและสามารถเริ่มต้นได้

## <a name="things-you-can-do-with-the-bot"></a>สิ่งที่คุณสามารถทำได้ด้วยบอท

บอทให้ความสามารถในการค้นหาสำหรับโปรไฟล์ลูกค้าแบบรวม

- ป้อน **ค้นหา** ตามด้วยชื่อ ที่อยู่อีเมล หรือฟิลด์อื่นๆ ในโปรไฟล์ลูกค้าแบบรวมที่ถูกเพิ่มไปยังดัชนีการค้นหาและตัวกรอง

  คุณจะได้รับบัตรที่มีมากถึง 15 ฟิลด์จากโปรไฟล์ลูกค้าที่เป็นผลลัพธ์ รายการที่ตรงกันหลายรายการส่งคืนรายการผลลัพธ์ที่คุณสามารถเลือกโปรไฟล์ได้ คุณสามารถเพิ่มคำที่ใช้ค้นหาในเครื่องหมายคำพูดคู่เพื่อค้นหาการจับคู่ที่ตรงกัน

- หากองค์กรของคุณดูแลสภาพแวดล้อม Customer Insights หลายแห่งในองค์กรเดียวกัน คุณสามารถป้อน **switchinstance** เพื่อเลือกว่าสภาพแวดล้อมใดที่คุณต้องการเชื่อมต่อกับบอท

- ป้อน **วิธีใช้** เพื่อดูรายการคำสั่งที่มีสำหรับบอท  


[!INCLUDE[footer-include](../includes/footer-banner.md)]