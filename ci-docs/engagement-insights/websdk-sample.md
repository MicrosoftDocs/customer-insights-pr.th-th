---
title: เรียกใช้ตัวอย่าง SDK ของเว็บ
description: เรียนรู้วิธีปรับแต่งและเรียกใช้ตัวอย่าง SDK ของเว็บ
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225354"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>เรียกใช้ตัวอย่าง SDK ของเว็บสำหรับความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วม Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ไลบรารี SDK ของเว็บของความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วมคือ ไลบรารี JavaScript ที่มีโค้ดตัวอย่างที่คุณสามารถใช้บนเว็บไซต์

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- ติดตั้ง [Visual Studio Code](https://code.visualstudio.com/)
- [ติดตั้งส่วนขยาย Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) ใน Visual Studio Code และทำความคุ้นเคยกับวิธีเรียกใช้ Live Server
- คุณต้องมี [พื้นที่ทำงานข้อมูลเชิงลึกของการมีส่วนร่วม](create-workspace.md)

## <a name="run-sample"></a>เรียกใช้ตัวอย่าง

1. [ดาวน์โหลดตัวอย่าง SDK ของเว็บ](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)

1. แตกไฟล์ที่บีบอัด `ei_websdk_sample.zip`

1. เปิดโฟลเดอร์ที่แตกไฟล์ใน Visual Studio Code

1. ไปที่พอร์ทัลข้อมูลเชิงลึกของการมีส่วนร่วมสำหรับพื้นที่ทำงานของคุณ เลือก **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** และจากนั้น **คู่มือการติดตั้ง** ทำตามตัวเลือกแรก และเลือก **คัดลอกรหัส** เพื่อคัดลอกส่วนย่อยของโค้ด JavaScript

1. ในไฟล์ `ei_websdk_sample.html` ให้วางส่วนย่อยของโค้ดที่คุณเพิ่งคัดลอกไว้ใต้บรรทัดนี้:

   - <-- วางส่วนย่อยของโค้ด JAVASCRIPT จากพอร์ทัลข้อมูลเชิงลึกของการมีส่วนร่วมที่นี่ด้านล่างบรรทัดนี้ -->

1. เปิดไฟล์ `ei_websdk_sample.html` โดยใช้ Live Server ใน Visual Studio Code โดยเลือก **ถ่ายทอดสด** จากแถบสถานะ

1. ในการเปิดหน้า ควรส่งเหตุการณ์มุมมองโดยอัตโนมัติ การคลิกที่ปุ่มใด ๆ ในหน้าจะส่งเหตุการณ์การดำเนินการ ปุ่ม **ติดตามเหตุการณ์** จะส่งเหตุการณ์ที่กำหนดเอง การเลือกปุ่ม **ไปที่ Bing** จะส่งเหตุการณ์การดำเนินการก่อนที่จะไปที่เว็บไซต์ Bing

1. ดูเหตุการณ์ที่กำลังไหลเมื่อคุณไปที่พื้นที่ทำงานของคุณ พื้นที่ทำงานนี้เชื่อมโยงกับคีย์การเพิ่มแหล่งข้อมูลเข้าระบบที่ป้อนในขั้นตอนที่ 4


[!INCLUDE[footer-include](../includes/footer-banner.md)]
