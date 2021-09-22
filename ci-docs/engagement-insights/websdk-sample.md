---
title: เรียกใช้ตัวอย่าง SDK ของเว็บ
description: เรียนรู้วิธีปรับแต่งและเรียกใช้ตัวอย่าง SDK ของเว็บ
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036626"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>เรียกใช้ตัวอย่าง SDK ของเว็บสำหรับความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วม Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ไลบรารี SDK ของเว็บของความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วมคือ ไลบรารี JavaScript ที่มีโค้ดตัวอย่างที่คุณสามารถใช้บนเว็บไซต์

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- ติดตั้ง [Visual Studio Code](https://code.visualstudio.com/)
- [ติดตั้งส่วนขยาย Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) ใน Visual Studio Code และทำความคุ้นเคยกับวิธีเรียกใช้ Live Server
- คุณต้องมี [คีย์การเพิ่มแหล่งข้อมูลเข้าระบบ](instrument-website.md)

## <a name="run-sample"></a>เรียกใช้ตัวอย่าง

1. [ดาวน์โหลดตัวอย่าง SDK ของเว็บ](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)

1. แตกไฟล์ที่บีบอัด `ei_websdk_sample.zip`

1. เปิดโฟลเดอร์ที่แตกไฟล์ใน Visual Studio Code

1. ในไฟล์ `ei_websdk_sample.html` แทนที่สตริง "INGESTION_KEY" ด้วยคีย์การนำเข้าของคุณจากพอร์ทัลความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วม และสตริง "NAME" ที่มีชื่อส่วนกลางที่คุณต้องการให้ SDK สร้างอินสแตนซ์ ตรวจสอบให้แน่ใจว่าคุณแทนที่เหตุการณ์ทั้งหมด

1. เปิดไฟล์ `ei_websdk_sample.html` โดยใช้ Live Server ใน Visual Studio Code โดยเลือก **ถ่ายทอดสด** จากแถบสถานะ

1. ในการเปิดหน้า ควรส่งเหตุการณ์มุมมองโดยอัตโนมัติ การคลิกที่ปุ่มใด ๆ ในหน้าจะส่งเหตุการณ์การดำเนินการ ปุ่ม **ติดตามเหตุการณ์** จะส่งเหตุการณ์ที่กำหนดเอง การเลือกปุ่ม **ไปที่ Bing** จะส่งเหตุการณ์การดำเนินการก่อนที่จะไปที่เว็บไซต์ Bing

1. ดูเหตุการณ์ที่กำลังไหลเมื่อคุณไปที่พื้นที่ทำงานของคุณ พื้นที่ทำงานนี้เชื่อมโยงกับคีย์การเพิ่มแหล่งข้อมูลเข้าระบบที่ป้อนในขั้นตอนที่ 4


[!INCLUDE[footer-include](../includes/footer-banner.md)]