---
title: ส่งออกเซ็กเมนต์ไปยัง MoEngage
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง MoEngage
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199149"
---
# <a name="export-segments-to-moengage-preview"></a>ส่งออกเซ็กเมนต์ไปยัง MoEngage (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง MoEngage และใช้สำหรับการตลาดทางอีเมลใน MoEngage

## <a name="prerequisites-for-a-connection"></a>ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ

- [บัญชี MoEngage](https://www.moengage.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง
- คีย์ API ของ MoEngage จากการตั้งค่า > API ใน MoEngage
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าสูงสุด 100,000 รายไปยัง MoEngage ซึ่งอาจใช้เวลานาน 15 นาที จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง MoEngage ขึ้นอยู่กับสัญญาของคุณกับ MoEngage
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-moengage"></a>ตั้งค่าการเชื่อมต่อไปยัง MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **MoEngage** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน [รหัส API ข้อมูล MoEngage และคีย์ API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY)

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ MoEngage

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน MoEngage หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก เราจะสร้างเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์ที่มีชื่อเดียวกับที่เลือกใน MoEngage ภายใต้ **เซ็กเมนต์** > **เซ็กเมนต์ที่กำหนดเอง**

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
