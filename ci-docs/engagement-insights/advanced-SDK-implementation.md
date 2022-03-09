---
title: สถานการณ์ web SDK ขั้นสูง
description: สถานการณ์ขั้นสูงที่ควรพิจารณาเมื่อใช้เครื่องมือวัดเว็บไซต์ของคุณด้วย SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227221"
---
# <a name="advanced-web-sdk-instrumentation"></a>เครื่องมือวัด SDK บนเว็บขั้นสูง

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

บทความนี้จะแนะนำคุณเกี่ยวกับสถานการณ์ขั้นสูงเพื่อพิจารณา เมื่อ [ใช้เครื่องมือวัดเว็บไซต์ของคุณ](instrument-website.md) ด้วย SDK ความสามารถข้อมูลเชิงลึกของการมีส่วนร่วมของ Dynamics 365 Customer Insights

## <a name="setting-user-details-for-your-event"></a>การตั้งค่ารายละเอียดผู้ใช้สำหรับเหตุการณ์ของคุณ

SDK ช่วยให้คุณสามารถกำหนดข้อมูลผู้ใช้ที่สามารถส่งไปพร้อมกับทุกๆ เหตุการณ์ คุณสามารถระบุรายละเอียดผู้ใช้ในคุณสมบัติที่เรียกว่า `user` (ข้อมูลที่คาดหวังสำหรับคุณสมบัตินี้คือ วัตถุ `IUser`) ซึ่งคล้ายกับ `src`, `name` และ `cfg` ในการกำหนดค่าส่วนย่อยของโค้ด

วัตถุ `IUser` มีคุณสมบัติสตริงต่อไปนี้:

- **localId**: ID ภายในของผู้ใช้
- **authId**: ID ของผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **authType**: ชนิดการรับรองความถูกต้องที่ใช้เพื่อรับ ID ของผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **ชื่อ**: ชื่อของผู้ใช้
- **อีเมล**: ที่อยู่อีเมลของผู้ใช้

ตัวอย่างต่อไปนี้แสดงส่วนย่อยของโค้ดที่ส่งข้อมูลผู้ใช้ เมื่อคุณเห็นฟังก์ชันที่มีเครื่องหมายดอกจัน * นำหน้า ให้แทนที่ฟังก์ชันดังกล่าวด้วยการใช้งานแบบกำหนดเองของคุณ:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

คุณยังสามารถระบุข้อมูลผู้ใช้ได้โดยการเรียก `setUser(user: IUser)` API การวัดและส่งข้อมูลทางไกลที่ส่งหลังจากการเรียก `setUser` API จะมีข้อมูลผู้ใช้

## <a name="adding-custom-properties-for-each-event"></a>การเพิ่มคุณสมบัติที่กำหนดเองสำหรับแต่ละเหตุการณ์

SDK ช่วยให้คุณสามารถระบุคุณสมบัติที่กำหนดเองที่สามารถส่งไปพร้อมกับทุกๆ เหตุการณ์ คุณสามารถระบุคุณสมบัติแบบกำหนดเองเป็นวัตถุที่มีคู่ของคีย์ - ค่า (ค่าสามารถเป็นชนิด `string | number | boolean`) คุณสามารถเพิ่มออบเจ็กต์ในคุณสมบัติที่เรียกว่า `props` ซึ่งคล้ายกับ `src`, `name` และ `cfg` ในการกำหนดค่าส่วนย่อยของโค้ด

ตัวอย่างต่อไปนี้แสดงส่วนย่อยของโค้ดที่ส่งคุณสมบัติแบบกำหนดเอง:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

คุณยังสามารถระบุคุณสมบัติที่กำหนดเองแต่ละรายการได้โดยการเรียก `setProperty(name: string, value: string | number | boolean)` API

## <a name="sending-custom-events"></a>การส่งเหตุการณ์ที่กําหนดเอง

คุณสามารถใช้ SDK เพื่อส่งเหตุการณ์ที่กำหนดเอง คุณต้องระบุชื่อสำหรับเหตุการณ์และคุณสมบัติที่จะส่งไปพร้อมกับเหตุการณ์

ตัวอย่างต่อไปนี้แสดงส่วนย่อยของโค้ดที่ติดตามเหตุการณ์ที่กำหนดเอง "NAME" คือค่าในคีย์ `name` ในการกำหนดค่าส่วนย่อย นอกจากนี้ ยังเป็นชื่อตัวแปรในวัตถุหน้าต่างที่มีการโหลด SDK อีกด้วย

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
