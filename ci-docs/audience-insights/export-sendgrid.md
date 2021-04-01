---
title: ส่งออกข้อมูล Customer Insights ไปยัง SendGrid
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ SendGrid
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597304"
---
# <a name="connector-for-sendgrid-preview"></a>ตัวเชื่อมต่อสำหรับ SendGrid (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายชื่อผู้ติดต่อของ SendGrid และใช้สำหรับการส่งเสริมการขายและการตลาดทางอีเมลใน SendGrid 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   คุณมี [บัญชี SendGrid](https://sendgrid.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   มีรายการผู้ติดต่อที่มีอยู่ใน SendGrid และรหัสที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [SendGrid - จัดการผู้ติดต่อ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="connect-to-sendgrid"></a>เชื่อมต่อกับ SendGrid

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **SendGrid** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="บานหน้าต่างการตั้งค่าคอนฟิกการส่งออก SendGrid":::

1. ป้อน **คีย์ SendGrid API** [คีย์ SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)

1. ป้อน **[รหัสรายชื่อ SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ของคุณ

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ SendGrid

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ เช่น **ชื่อ**, **นามสกุล**, **ประเทศ/ภูมิภาค**, **รัฐ**, **เมือง** และ **รหัสไปรษณีย์**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก เรา **แนะนำอย่างยิ่งว่า อย่าส่งออกโปรไฟล์ลูกค้าทั้งหมดมากกว่า 100'000 โปรไฟล์** ไปยัง SendGrid 

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid
- การส่งออกไปยัง SendGrid ถูกจำกัดเฉพาะเซ็กเมนต์
- การส่งออกโปรไฟล์มากถึง 100'000 โปรไฟล์ไปยัง SendGrid อาจใช้เวลาสองสามชั่วโมงจึงจะเสร็จสมบูรณ์ 
- จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง SendGrid นั้น ขึ้นอยู่และถูกจำกัดตามสัญญาของคุณกับ SendGrid

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง SendGrid คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า SendGrid ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้


[!INCLUDE[footer-include](../includes/footer-banner.md)]