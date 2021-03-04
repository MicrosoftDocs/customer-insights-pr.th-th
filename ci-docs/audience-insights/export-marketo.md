---
title: ส่งออกข้อมูล Customer Insights ไปยัง Marketo
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Marketo
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267104"
---
# <a name="connector-for-marketo-preview"></a>ตัวเชื่อมต่อสำหรับ Marketo (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมเพื่อสร้างการส่งเสริมการขาย จัดทำการตลาดทางอีเมล และใช้กลุ่มลูกค้าเฉพาะกับ Marketo

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   คุณมี [บัญชี Marketo](https://login.marketo.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   มีรายการที่มีอยู่ใน Marketo และรหัสที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [รายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="connect-to-marketo"></a>เชื่อมต่อกับ Marketo

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Marketo** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

1. ป้อน **[รหัสไคลเอ็นต์ Marketo ข้อมูลลับของไคลเอ็นต์และชื่อโฮสต์จุดสิ้นสุด REST](https://developers.marketo.com/rest-api/authentication/)**

1. ป้อน **[รหัสรายชื่อ Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. เลือก **ฉันตกลง** เพื่อยืนยัน **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** และเลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ Marketo

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

   :::image type="content" source="media/export-connect-marketo.png" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Marketo":::

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า 

1. หรือคุณสามารถส่งออก **ชื่อ**, **นามสกุล**, **เมือง**, **รัฐ** และ **ประเทศ/ภูมิภาค** เป็นฟิลด์เพิ่มเติมเพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Marketo ได้มากถึง 1 ล้านโปรไฟล์

   :::image type="content" source="media/export-segment-marketo.png" alt-text="เลือกฟิลด์และเซ็กเมนต์ที่จะส่งออกไปยัง Marketo":::

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง ใน Marketo ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [รายชื่อ Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ต่อการส่งออกไปยัง Marketo สูงสุด 1 ล้านโปรไฟล์
- การส่งออกไปยัง Marketo จำกัดเฉพาะเซ็กเมนต์
- การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมง 
- จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Marketo นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Marketo

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Marketo คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Marketo ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้


[!INCLUDE[footer-include](../includes/footer-banner.md)]