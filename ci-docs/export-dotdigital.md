---
title: ส่งออกเซ็กเมนต์ไปยัง DotDigital (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง DotDigital
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196095"
---
# <a name="export-segments-to-dotdigital-preview"></a>ส่งออกเซ็กเมนต์ไปยัง DotDigital (พรีวิว)

ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยังสมุดที่อยู่ DotDigital และใช้สำหรับการส่งเสริมการขาย การตลาดทางอีเมล และเพื่อสร้างกลุ่มลูกค้าด้วย DotDigital

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี DotDigital](https://dotdigital.com/) และ [ผู้ใช้ API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user)
- รหัส DotDigital จากสมุดรายชื่อ [ใหม่](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) หรือที่มีอยู่ใน DotDigital คุณสามารถดูรหัสได้ใน URL เมื่อเลือกและเปิดสมุดรายชื่อ
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 1 ล้านโปรไฟล์ไปยัง DotDigital ซึ่งอาจใช้เวลานานถึงสามชั่วโมงจึงจะเสร็จสมบูรณ์ เนื่องจากข้อจำกัดด้านผู้ให้บริการ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง DotDigital ขึ้นอยู่กับสัญญาของคุณกับ DotDigital
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-dotdigital"></a>ตั้งค่าการเชื่อมต่อไปยัง DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **DotDigital**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อผู้ใช้และรหัสผ่าน API DotDigital** ของคุณ

1. ป้อน **รหัสสมุดรายชื่อ DotDigital** ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน DotDigital ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า

1. หรือส่งออก **ชื่อ**, **นามสกุล**, **ชื่อเต็ม**, **เพศ** และ **รหัสไปรษณีย์**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ใน DotDigital ให้ค้นหาเซ็กเมนต์ของคุณใน [สมุดรายชื่อ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)

[!INCLUDE [footer-include](includes/footer-banner.md)]
