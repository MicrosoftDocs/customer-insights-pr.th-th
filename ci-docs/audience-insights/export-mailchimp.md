---
title: ส่งออกข้อมูล Customer Insights ไปยัง Mailchimp
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Mailchimp
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407124"
---
# <a name="connector-for-mailchimp-preview"></a>ตัวเชื่อมต่อสำหรับ Mailchimp (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Mailchimp เพื่อสร้างจดหมายข่าวและการส่งเสริมการขายทางอีเมล

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   คุณมี [บัญชี Mailchimp](https://mailchimp.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   มีผู้ชมที่มีอยู่ใน Mailchimp และรหัสที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Mailchimp](https://mailchimp.com/help/create-audience/)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="connect-to-mailchimp"></a>เชื่อมต่อกับ Mailchimp

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Mailchimp** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. ป้อน **[รหัสผู้ชม Mailchimp](https://mailchimp.com/help/find-audience-id/)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Mailchimp

1. เลือก **รับรองความถูกต้องกับ Mailchimp** และให้ข้อมูลประจำตัวของ Mailchimp ของคุณ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Mailchimp":::

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า 

1. หรือคุณสามารถส่งออก **ชื่อ** และ **นามสกุล** เป็นฟิลด์เพิ่มเติมเพื่อสร้างอีเมลที่เป็นส่วนตัวมากขึ้น เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Mailchimp ได้มากถึง 1 ล้านโปรไฟล์

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="เลือกฟิลด์และเซ็กเมนต์ที่จะส่งออกไปยัง Mailchimp":::

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง ใน Mailchimp ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [ผู้ชม Mailchimp](https://mailchimp.com/help/create-audience/)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ต่อการส่งออกไปยัง Mailchimp สูงสุด 1 ล้านโปรไฟล์
- การส่งออกไปยัง Mailchimp จำกัดเฉพาะเซ็กเมนต์
- การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึงสามชั่วโมงเนื่องจากข้อจำกัดของผู้ให้บริการ 
- จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง Mailchimp นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ Mailchimp

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Mailchimp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Mailchimp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้
