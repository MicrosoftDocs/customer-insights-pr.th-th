---
title: ส่งออกข้อมูล Customer Insights ไปยัง Google Ads
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Google Ads
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568511"
---
# <a name="connector-for-google-ads-preview"></a>ตัวเชื่อมต่อสำหรับ Google Ads (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายการผู้ชมของ Google Ads และใช้เพื่อโฆษณาบน Google Search, Gmail, YouTube และ Google Display Network 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   คุณมี [บัญชี Google Ads](https://ads.google.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   มีผู้ชมที่มีอยู่ใน Google Ads และรหัสที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล ชื่อ และ นามสกุล

## <a name="connect-to-google-ads"></a>เชื่อมต่อกับ Google Ads

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Google Ads** ให้เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

1. ป้อน **[รหัสลูกค้า Google Ads](https://support.google.com/google-ads/answer/1704344)**

1. ป้อน **[โทเค็นนักพัฒนาที่อนุมัติของ Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. ป้อน **[รหัสผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Google Ads

1. เลือก **รับรองความถูกต้องกับ Google Ads** และให้ข้อมูลประจำตัวของ Google Ads ของคุณ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="ส่งออกภาพหน้าจอสำหรับการเชื่อมต่อ Google Ads":::

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ **ชื่อ** และ **นามสกุล**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Google Ads ได้มากถึง 1 ล้านโปรไฟล์

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง ใน Google Ads ตอนนี้คุณสามารถค้นหาเซ็กเมนต์ของคุณได้ที่ [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ต่อการส่งออกไปยัง Google Ads สูงสุด 1 ล้านโปรไฟล์
- การส่งออกไปยัง Google Ads จำกัดเฉพาะเซ็กเมนต์
- การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 5 นาทีเนื่องจากข้อจำกัดของผู้ให้บริการ 
- การจับคู่ใน Google Ads อาจใช้เวลาถึง 48 ชั่วโมง

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Google Ads คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Google Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้
