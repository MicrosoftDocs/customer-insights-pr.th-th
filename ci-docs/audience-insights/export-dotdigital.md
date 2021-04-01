---
title: ส่งออกข้อมูล Customer Insights ไปยัง DotDigital
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ DotDigital
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598040"
---
# <a name="connector-for-dotdigital-preview"></a>ตัวเชื่อมต่อสำหรับ DotDigital (พรีวิว)

ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยังสมุดที่อยู่ DotDigital และใช้สำหรับการส่งเสริมการขาย การตลาดทางอีเมล และเพื่อสร้างกลุ่มลูกค้าด้วย DotDigital 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   คุณมี [บัญชี DotDigital](https://dotdigital.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   มีสมุดรายชื่อที่มีอยู่ใน DotDigital และรหัสที่เกี่ยวข้อง คุณสามารถดูรหัสได้ใน URL เมื่อเลือกและเปิดสมุดรายชื่อ สำหรับข้อมูลเพิ่มเติม โปรดดู [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="connect-to-dotdigital"></a>เชื่อมต่อกับ DotDigital

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **DotDigital** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="บานหน้าต่างการกำหนดค่าสำหรับการส่งออก DotDigital":::

1. ป้อน **ชื่อผู้ใช้และรหัสผ่าน DotDigital** ของคุณ

1. ป้อน **[รหัสสมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อกับ DotDigital

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่น ๆ เช่น **ชื่อ**, **นามสกุล**, **ชื่อเต็ม**, **เพศ** และ **รหัสไปรษณีย์**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง DotDigital ได้มากถึง 1 ล้านโปรไฟล์

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง ใน DotDigital คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ใน [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ต่อการส่งออกไปยัง DotDigital สูงสุด 1 ล้านโปรไฟล์
- การส่งออกไปยัง DotDigital จำกัดเฉพาะเซ็กเมนต์
- การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 3 ชั่วโมงเนื่องจากข้อจำกัดของผู้ให้บริการ 
- จำนวนโปรไฟล์ที่คุณสามารถส่งออกไปยัง DotDigital นั้นขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ DotDigital

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง DotDigital คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า DotDigital ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้


[!INCLUDE[footer-include](../includes/footer-banner.md)]