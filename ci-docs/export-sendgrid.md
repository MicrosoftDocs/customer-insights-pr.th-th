---
title: ส่งออกเซ็กเมนต์ไปยัง SendGrid (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง SendGrid
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724871"
---
# <a name="export-segments-to-sendgrid-preview"></a>ส่งออกเซ็กเมนต์ไปยัง SendGrid (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายชื่อผู้ติดต่อของ SendGrid และใช้สำหรับการส่งเสริมการขายและการตลาดทางอีเมลใน SendGrid

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี SendGrid](https://sendgrid.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
- [รายการผู้ติดต่อที่มีอยู่ใน SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) และรหัสที่เกี่ยวข้อง
- [คีย์ API ของ SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ไม่รองรับลิงก์ส่วนตัวร่วมกับการใช้ที่เก็บข้อมูลของคุณเอง (BYOS)
- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 100,000 รายไปยัง SendGrid ซึ่งอาจใช้เวลานานสองสามชั่วโมงจึงจะเสร็จสมบูรณ์ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง SendGrid ขึ้นอยู่กับสัญญาของคุณกับ SendGrid
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-sendgrid"></a>ตั้งค่าการเชื่อมต่อไปยัง SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **SendGrid**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **คีย์ API ของ SendGrid** ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SendGrid ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ป้อน **รหัสรายชื่อ SendGrid** ของคุณ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า

1. หรือเลือกฟิลด์ เช่น **ชื่อ**, **นามสกุล**, **ประเทศ/ภูมิภาค**, **รัฐ**, **เมือง** และ **รหัสไปรษณีย์**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก โดยปฏิบัติตามข้อจำกัดที่ทราบ

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
