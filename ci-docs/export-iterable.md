---
title: ส่งออกเซ็กเมนต์ไปยัง Iterable (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Iterable
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195452"
---
# <a name="export-segments-to-iterable-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Iterable (พรีวิว)

ส่งออกเซ็กเมนต์ของ unified customer profile ไปยัง Iterable และใช้สำหรับกิจกรรมทางการตลาด

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Iterable](https://iterable.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง
- [คีย์ API ของ Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าสูงสุด 1 ล้านรายไปยัง Iterable ซึ่งอาจใช้เวลานานถึง 30 นาทีจึงจะเสร็จสมบูรณ์ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง Iterable ขึ้นอยู่กับสัญญาของคุณกับ Iterable
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-iterable"></a>ตั้งค่าการเชื่อมต่อไปยัง Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Iterable**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ระบุ คีย์ Iterable API ของคุณเพื่อลงชื่อเข้าใช้ต่อ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับส่งออก** ให้เลือกการเชื่อมต่อจากส่วน Iterable ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า รายการที่สร้างใน Iterable จะได้รับชื่อเดียวกันกับชื่อเซ็กเมนต์ของคุณใน Dynamics 365 Customer Insights

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
