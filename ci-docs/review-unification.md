---
title: ตรวจสอบการรวมข้อมูล
description: ตรวจสอบขั้นตอนการรวมข้อมูล สร้างโปรไฟล์ลูกค้าแบบรวม และตรวจสอบผลลัพธ์
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741742"
---
# <a name="review-data-unification"></a>ตรวจสอบการรวมข้อมูล

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

ขั้นตอนสุดท้ายในกระบวนการรวมจะแสดงการสรุปขั้นตอนในกระบวนการและให้โอกาสในการเปลี่ยนแปลงก่อนที่คุณจะสร้างโปรไฟล์แบบรวม

:::image type="content" source="media/m3_review.png" alt-text="ภาพหน้าจอของการตรวจสอบและสร้างโปรไฟล์ลูกค้า":::

## <a name="review-the-data-unification-steps"></a>ตรวจสอบขั้นตอนการรวมข้อมูล

1. เลือก **แก้ไข** ในขั้นตอนการรวมข้อมูลเพื่อตรวจสอบและทำการเปลี่ยนแปลงใดๆ

1. หากคุณพอใจกับการเลือกของคุณ ให้เลือก **สร้างโปรไฟล์ลูกค้า** หน้า **รวม** จะปรากฏขึ้นในขณะที่กำลังสร้างโปรไฟล์ลูกค้าแบบรวม อัลกอริธึมการรวมจะใช้เวลาสักครู่จึงจะเสร็จสมบูรณ์ และคุณไม่สามารถเปลี่ยนแปลงการกำหนดค่าได้จนกว่าจะเสร็จสิ้น

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

เมื่อกระบวนการรวมเสร็จสมบูรณ์ เอนทิตีโปรไฟล์ลูกค้าแบบรวมที่เรียกว่า *ลูกค้า* มีการระบุไว้ในหน้า **เอนทิตี** ในส่วน **โปรไฟล์** การเรียกใช้การรวมที่ประสบความสำเร็จครั้งแรกจะสร้างเอนทิตี *ลูกค้า* แบบรวม การดำเนินการในลำดับต่อมาทั้งหมดจะขยายเอนทิตีนั้น

## <a name="review-the-results-of-data-unification"></a>ตรวจสอบผลลัพธ์ของการรวมข้อมูล

หลังจากการรวมกัน หน้า **ข้อมูล** > **รวม** จะแสดงจำนวนโปรไฟล์ลูกค้าแบบรวม ผลลัพธ์ของแต่ละขั้นตอนในกระบวนการรวมจะแสดงในแต่ละไทล์ ตัวอย่างเช่น **ฟิลด์ต้นทาง** จะแสดงจำนวนแอตทริบิวต์ที่แมป (ฟิลด์) และ **เรกคอร์ดซ้ำ** จะแสดงจำนวนเรกคอร์ดซ้ำที่พบ

:::image type="content" source="media/m3_unified.png" alt-text="ภาพหน้าจอของหน้า Data Unify หลังจากรวมข้อมูลแล้ว":::

> [!TIP]
> ไทล์ **เงื่อนไขการจับคู่** จะแสดงก็ต่อเมื่อเลือกเอนทิตีหลายรายการ

เราขอแนะนำให้คุณตรวจสอบผลลัพธ์ โดยเฉพาะคุณภาพของ [กฎการจับคู่](data-unification-update.md#manage-match-rules) และปรับแต่งตามความจำเป็น

เมื่อมีความจำเป็น [ให้ทำการเปลี่ยนแปลงการตั้งค่าการรวม](data-unification-update.md) และเรียกใช้โปรไฟล์แบบรวมอีกครั้ง

## <a name="next-step"></a>ขั้นตอนถัดไป

กำหนดค่า [กิจกรรม](activities.md), [การเพิ่มความสมบูรณ์](enrichment-hub.md), [ความสัมพันธ์](relationships.md) หรือ [การวัด](measures.md) เพื่อรับข้อมูลเชิงลึกเพิ่มเติมเกี่ยวกับลูกค้าของคุณ

[!INCLUDE[footer-include](includes/footer-banner.md)]
