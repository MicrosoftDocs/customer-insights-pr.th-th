---
title: ส่งออกเซ็กเมนต์ไปยัง Marketo (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Marketo
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195267"
---
# <a name="export-segments-to-marketo-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Marketo (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมเพื่อสร้างการส่งเสริมการขาย จัดทำการตลาดทางอีเมล และใช้กลุ่มลูกค้าเฉพาะกับ Marketo

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Marketo](https://login.marketo.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
- [รหัสไคลเอ็นต์ Marketo ข้อมูลลับของไคลเอ็นต์และชื่อโฮสต์จุดสิ้นสุด REST](https://developers.marketo.com/rest-api/authentication/)
- [รายการที่มีอยู่ใน Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) และรหัสที่เกี่ยวข้อง
- [เซ็กเมนต์ที่กำหนดค่า](segments.md)
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าสูงสุด 1 ล้านรายไปยัง Marketo โดยอาจใช้เวลานานถึง 3 ชั่วโมง จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง Marketo ขึ้นอยู่กับสัญญาของคุณกับ Marketo
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-marketo"></a>ตั้งค่าการเชื่อมต่อไปยัง Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Marketo**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **รหัสไคลเอ็นต์ Marketo ข้อมูลลับของไคลเอ็นต์และชื่อโฮสต์จุดสิ้นสุด REST** ของคุณ ชื่อโฮสต์จุดสิ้นสุด REST เป็นชื่อโฮสต์เท่านั้น โดยไม่มี https:// ตัวอย่าง: xyz-abc-123.mktorest.com

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Marketo ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ป้อน **รหัสรายการ Marketo** ของคุณ รหัสรายการเป็นค่าตัวเลขเท่านั้น ตัวอย่างเช่น หากรหัสรายการ Marketo ของคุณคือ ST12345A7 ให้ลบอักขระก่อนและหลังตัวเลข และป้อน *12345*

1. ในส่วน **การจับคู่ข้อมูล** ให้เลือกอย่างน้อยหนึ่งฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้าหรือรหัส Marketo ของลูกค้า

1. หรือส่งออก **ชื่อ** **นามสกุล** **เมือง** **รัฐ** และ **ประเทศ/ภูมิภาค**  เพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้นได้ เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ใน Marketo ให้ค้นหาเซ็กเมนต์ของคุณได้ที่ [รายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)

[!INCLUDE [footer-include](includes/footer-banner.md)]
