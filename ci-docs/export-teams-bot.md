---
title: บอท Teams สำหรับ Dynamics 365 Customer Insights (พรีวิว)
description: ค้นหาโปรไฟล์ลูกค้าแบบรวมใน Microsoft Teams ด้วยความช่วยเหลือของบอท
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195865"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>บอท Teams สำหรับ Dynamics 365 Customer Insights (พรีวิว)

เชื่อมต่อ Microsoft Teams เพื่อให้บอทค้นหาโปรไฟล์ลูกค้าแบบรวมในช่องทาง Teams

:::image type="content" source="media/teams-bot.png" alt-text="บอทของ Teams แสดงเรกคอร์ดลูกค้า":::

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- อย่างน้อยหนึ่ง [แหล่งข้อมูลถูกเพิ่ม](data-sources.md)
- [กระบวนการรวมข้อมูล](data-unification.md) เสร็จสมบูรณ์
- ฟิลด์จะถูกเพิ่มไปยัง [ดัชนีการค้นหาและตัวกรอง](search-filter-index.md)
- Customer Insights และ Teams อยู่ในองค์กรเดียวกัน
- สภาพแวดล้อมของคุณมีผู้ชมเป้าหมายหลักที่ตั้งไว้สำหรับลูกค้ารายบุคคล บัญชีธุรกิจไม่ได้รับการสนับสนุน


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>กำหนดค่าบอท

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**
1. บนไทล์ Microsoft Teams เลือก **ตั้งค่า**
1. คุณถูกเปลี่ยนเส้นทางไปยังพื้นที่ **แอป** ใน Teams คุณสามารถเปิด Teams และเลือก **แอป** ที่มุมล่างซ้ายหรือ [รับจาก AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) โดยตรง
1. ค้นหา **Customer Insights** และเลือกแอป
1. เลือก **เพิ่ม**
1. ลงชื่อเข้าใช้ Customer Insights ใน Teams ข้อความต้อนรับจะปรากฏขึ้น

## <a name="things-you-can-do-with-the-bot"></a>สิ่งที่คุณสามารถทำได้ด้วยบอท

บอทให้ความสามารถในการค้นหาสำหรับโปรไฟล์ลูกค้าแบบรวม

- ป้อน **ค้นหา** ตามด้วยชื่อ ที่อยู่อีเมล หรือฟิลด์อื่นๆ ในโปรไฟล์ลูกค้าแบบรวมที่ถูกเพิ่มไปยังดัชนีการค้นหาและตัวกรอง

  คุณจะได้รับบัตรที่มีมากถึง 15 ฟิลด์จากโปรไฟล์ลูกค้าที่เป็นผลลัพธ์ รายการที่ตรงกันหลายรายการส่งคืนรายการผลลัพธ์ที่คุณสามารถเลือกโปรไฟล์ได้ หากต้องการค้นหาการตรงกันทุกประการ ให้เพิ่มคำที่ใช้ค้นหาในเครื่องหมายคำพูดคู่

- หากองค์กรของคุณดูแลสภาพแวดล้อม Customer Insights หลายแห่งในองค์กรเดียวกัน ให้ป้อน **switchinstance** เพื่อเลือกว่าสภาพแวดล้อมใดที่คุณต้องการเชื่อมต่อกับบอท

- ป้อน **วิธีใช้** เพื่อดูรายการคำสั่งที่มีสำหรับบอท  

[!INCLUDE [footer-include](includes/footer-banner.md)]