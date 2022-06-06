---
title: เริ่มต้นใช้งานด้วย Dynamics 365 Customer Insights
description: ภาพรวมของ Customer Insights ช่วยให้ข้อมูลเพื่อให้คุณเริ่มต้นใช้งานได้อย่างรวดเร็ว
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833598"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>เริ่มต้นใช้งานด้วย Dynamics 365 Customer Insights

Customer Insights สามารถช่วยให้คุณสร้างความเข้าใจที่ลึกซึ้งยิ่งขึ้นเกี่ยวกับลูกค้าของคุณ เชื่อมต่อข้อมูลจากแหล่งธุรกรรม พฤติกรรม และแหล่งสังเกตการณ์ต่างๆ เพื่อสร้างมุมมองลูกค้า 360 องศา ใช้ข้อมูลเชิงลึกเหล่านี้เพื่อผลักดันประสบการณ์และกระบวนการที่ยึดลูกค้าเป็นศูนย์กลาง รวมและทำความเข้าใจข้อมูลลูกค้าและใช้ประโยชน์จากข้อมูลเชิงลึกและการดำเนินการที่มีประสิทธิภาพ

## <a name="step-1-create-an-environment"></a>ขั้นตอนที่ 1: สร้างสภาพแวดล้อม

อันดับแรก ให้สร้างสภาพแวดล้อมที่จะทำงาน หากองค์กรของคุณซื้อสิทธิ์การใช้งานแล้ว ดูที่ [สร้างสภาพแวดล้อม](create-environment.md) หากต้องการเริ่มการทดลองใช้ Customer Insights โปรดดู [ตั้งค่าสภาพแวดล้อมการทดลองใช้](trial-signup.md)

## <a name="step-2-explore-customer-insights"></a>ขั้นตอนที่ 2: สำรวจ Customer Insights

กำหนดการตั้งค่าและสำรวจผลิตภัณฑ์เมื่อคุณลงชื่อเข้าใช้ Customer Insights ในครั้งแรก

1. [ลงชื่อเข้าใช้ Customer Insights](https://home.ci.ai.dynamics.com) ด้วยบัญชีผู้ใช้ Microsoft Azure Active Directory (AAD) ของคุณ

1. เปลี่ยนสภาพแวดล้อมเพื่อดูข้อมูลสาธิตและ [สำรวจ Customer Insights](home.md)

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>ขั้นตอนที่ 3: นำเข้า รวมรวม และตั้งค่าความสัมพันธ์สำหรับข้อมูลของคุณ

โปรไฟล์แบบรวมเป็นพื้นฐานในการรับข้อมูลเชิงลึกและดำเนินการกับข้อมูล นำเข้าข้อมูลจากแหล่งต่างๆ และเรียกใช้กระบวนการรวมข้อมูลเพื่อรวมโปรไฟล์แบบรวม ระบุความสัมพันธ์ระหว่างเอนทิตีที่นำเข้าและใช้คุณลักษณะการเพิ่มความสมบูรณ์เพื่อเพิ่มข้อมูลในโปรไฟล์

1. นำเข้าข้อมูลโดยการสร้างแหล่งข้อมูลจากหลายตัวเลือก เลือกระหว่าง [ตัวเชื่อมต่อ Power Query](connect-power-query.md), [โฟลเดอร์ Common Data Model](connect-common-data-model.md) หรือ [Microsoft Dataverse](connect-dataverse-managed-lake.md)

1. เรียกใช้ [กระบวนการรวมข้อมูล](data-unification.md) โดยการระบุ [ฟิลด์ต้นทาง](map-entities.md), ลบ [รายการซ้ำ](remove-duplicates.md), [เงื่อนไขการจับคู่](match-entities.md), และ [ฟิล์ดการรวม](merge-entities.md)

1. ทำความคุ้นเคยกับ [เอนทิตีที่ระบบสร้างขึ้น](entities.md) และสร้าง [ความสัมพันธ์ระหว่างเอนทิตีที่นำเข้า](relationships.md)

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>ขั้นตอนที่ 4: ปรับปรุงโปรไฟล์แบบรวมด้วยการคาดคะเน กิจกรรม และการวัดต่างๆ

ด้วยการตั้งค่าโปรไฟล์แบบรวม คุณสามารถปรับปรุงข้อมูลและเพิ่มข้อมูลที่พวกเขาระบุได้เพิ่มเติม

1. เลือกจากไลบรารีที่ขยายของผู้ให้บริการการเพิ่มข้อมูลเพื่อ [เพิ่มข้อมูลลูกค้าของคุณ](enrichment-hub.md)

1. ใช้ [โมเดลแบบสำเร็จรูป](predictions-overview.md) เพื่อคาดคะเนแนวโน้มการเลิกใช้บริการหรือรายได้ที่คาดหวัง

1. [กำหนดค่ากิจกรรม](activities.md) ตามข้อมูลที่นำเข้าและแสดงภาพการโต้ตอบกับลูกค้าของคุณในไทม์ไลน์ตามลำดับเวลา

1. [สร้างการวัด](measures.md) เพื่อวัดเป้าหมายธุรกิจและ KPI ของคุณ

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>ขั้นตอนที่ 5: สร้างเซ็กเมนต์และเริ่มการใช้งานข้อมูลผ่านตัวเลือกการส่งออกต่างๆ

เมื่อข้อมูลของคุณสมบูรณ์แล้วและมีข้อมูลที่หลากหลายเกี่ยวกับลูกค้าของคุณ ให้ค้นหาวิธีดำเนินการกับข้อมูลนั้น

1. [สร้างเซ็กเมนต์](segments.md) ชุดย่อยของฐานลูกค้าของคุณ เพื่อให้แน่ใจว่าการดำเนินการของคุณเกี่ยวข้องกับลูกค้าเป้าหมาย

1. เรียกดูแค็ตตาล็อกที่ขยายของ [ตัวเลือกการส่งออก](export-destinations.md) ที่คุณสามารถใช้ข้อมูลลูกค้าได้ ตัวอย่างเช่น คุณสามารถใช้ข้อมูลเพื่อจัดการโปรโมชั่นและติดต่อด้วยการตลาดดิจิทัล

1. ตรวจสอบตัวเลือกการรวม เช่น การรวมกับแอป Dynamics 365 อื่นๆ ด้วย [Add-in การ์ดลูกค้า](customer-card-add-in.md)  


[!INCLUDE [footer-include](includes/footer-banner.md)]
