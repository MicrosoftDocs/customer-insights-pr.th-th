---
title: ส่งออกเซ็กเมนต์ไปยัง Braze (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Braze
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725239"
---
# <a name="export-segments-to-braze-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Braze (พรีวิว)

ส่งออกเซ็กเมนต์ของ unified customer profile ไปยัง Braze และใช้สำหรับกิจกรรมทางการตลาด

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Braze](https://www.braze.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง
- [คีย์ API ของ Braze](https://www.braze.com/docs/api/basics/)
- [จุดสิ้นสุด REST ของ Braze](https://www.braze.com/docs/api/basics/#api-definitions) ของคุณ 
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- Unified customer profile ในเซ็กเมนต์ที่ส่งออกมีฟิลด์ที่แสดงที่อยู่อีเมลและรหัสลูกค้า Braze

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ไม่รองรับลิงก์ส่วนตัวร่วมกับการใช้ที่เก็บข้อมูลของคุณเอง (BYOS)
- ส่งออกโปรไฟล์ลูกค้าได้สูงสุด 1 ล้านรายไปยัง Braze ซึ่งอาจใช้เวลานานถึง 40 นาทีจึงจะเสร็จสมบูรณ์ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง Braze ขึ้นอยู่กับสัญญาของคุณกับ Braze
- เซ็กเมนต์เท่านั้น
- Azure Private Link ไม่รองรับการส่งออก Braze

## <a name="set-up-connection-to-braze"></a>ตั้งค่าการเชื่อมต่อไปยัง Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Braze**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ระบุ คีย์ Braze API ของคุณเพื่อลงชื่อเข้าใช้ต่อ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับส่งออก** ให้เลือกการเชื่อมต่อจากส่วน Braze ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนจุดสิ้นสุด REST ลงในฟิลด์ **ชื่อโฮสต์** ในรูปแบบต่อไปนี้: `rest.iad-03.braze.com`

1. ป้อนชื่อสำหรับการส่งออก

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า ในฟิลด์ **รหัสลูกค้า** ให้เลือกฟิลด์ที่แสดงรหัส Braze ของลูกค้า เซ็กเมนต์ใน Braze จะสร้างโดยใช้ชื่อเดียวกันกับเซ็กเมนต์ใน Dynamics 365 Customer Insights คุณสามารถเลือกฟิลด์ที่ไม่บังคับเพิ่มเติมสำหรับข้อมูลที่ตรงกัน

1. เลือกเอนทิตีหรือเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
