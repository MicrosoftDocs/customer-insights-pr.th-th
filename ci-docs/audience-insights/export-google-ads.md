---
title: ส่งออกข้อมูล Customer Insights ไปยัง Google Ads
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Google Ads
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305363"
---
# <a name="export-segments-to-google-ads-preview"></a>ส่งออกกลุ่มไปยัง Google Ads (ตัวอย่าง)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายการผู้ชม Google Ads และใช้เพื่อโฆษณาบน Google Search, Gmail, YouTube และ Google Display Network 

## <a name="prerequisites-for-connection"></a>ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ

-   คุณมี [บัญชี Google Ads](https://ads.google.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
-   คุณมี [โทเค็นนักพัฒนา Google Ads ที่ได้รับการอนุมัติ](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   คุณปฏิบัติตามข้อกำหนดของ [นโยบายการจับคู่ข้อมูลลูกค้า](https://support.google.com/adspolicy/answer/6299717)
-   คุณปฏิบัติตามข้อกำหนดของ [ขนาดรายชื่อเพื่อทำการตลาดใหม่](https://support.google.com/google-ads/answer/7558048)
-   มีผู้ชมที่มีอยู่ใน Google Ads และรหัสที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [ผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)
-   คุณมี [เซ็กเมนต์ที่กำหนดค่า](segments.md)
-   โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วย ฟิลด์ที่แสดงที่อยู่อีเมล ชื่อ และ นามสกุล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ต่อการส่งออกไปยัง Google Ads สูงสุด 1 ล้านโปรไฟล์
- การส่งออกไปยัง Google Ads จำกัดเฉพาะเซ็กเมนต์
- การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 1 ล้านโปรไฟล์อาจใช้เวลาถึง 5 นาทีเนื่องจากข้อจำกัดของผู้ให้บริการ 
- การจับคู่ใน Google Ads อาจใช้เวลาถึง 48 ชั่วโมง

## <a name="set-up-connection-to-google-ads"></a>ตั้งค่าการเชื่อมต่อไปยัง Google Ads

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Google Ads** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **[รหัสลูกค้า Google Ads](https://support.google.com/google-ads/answer/1704344)**

1. ป้อน **[โทเค็นนักพัฒนาที่อนุมัติของ Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. เลือก **รับรองความถูกต้องกับ Google Ads** และให้ข้อมูลประจำตัวของ Google Ads ของคุณ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น 

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Google Ads หากคุณไม่เห็นชื่อส่วนนี้ การเชื่อมต่อชนิดนี้ไม่พร้อมใช้งานสำหรับคุณ

1. ป้อน **[รหัสผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** และเลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อกับ Google Ads

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ในโปรไฟล์ลูกค้าแบบรวมของคุณที่แสดงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ **ชื่อ** และ **นามสกุล**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก คุณสามารถส่งออกโปรไฟล์ลูกค้าไปยัง Google Ads ได้มากถึง 1 ล้านโปรไฟล์

การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที

การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) 

นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand) 

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Google Ads คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Google Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้


[!INCLUDE[footer-include](../includes/footer-banner.md)]
