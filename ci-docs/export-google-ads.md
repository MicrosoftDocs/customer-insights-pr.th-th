---
title: ส่งออกกลุ่มไปยัง Google Ads (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Google Ads
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725101"
---
# <a name="export-segments-to-google-ads-preview"></a>ส่งออกกลุ่มไปยัง Google Ads (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยังรายการผู้ชม Google Ads และใช้เพื่อโฆษณาบน Google Search, Gmail, YouTube และ Google Display Network

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Google Ads](https://ads.google.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
- [รหัสลูกค้าของ Google Ads](https://support.google.com/google-ads/answer/1704344)
- ตรงตามข้อกำหนดของ [นโยบาย Customer Match](https://support.google.com/adspolicy/answer/6299717)
- ตรงตามข้อกำหนดของ [ขนาดรายชื่อเพื่อทำการตลาดใหม่](https://support.google.com/google-ads/answer/7558048)
- [เซ็กเมนต์ที่กำหนดค่า](segments.md)
- Unified customer profile ในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล โทรศัพท์ รหัสผู้โฆษณาบนมือถือ รหัสผู้ใช้บุคคลที่สาม หรือที่อยู่

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ไม่รองรับลิงก์ส่วนตัวร่วมกับการใช้ที่เก็บข้อมูลของคุณเอง (BYOS)
- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 1 ล้านโปรไฟล์ไปยัง Google Ads ซึ่งอาจใช้เวลานานถึง 30 นาทีจึงจะเสร็จสมบูรณ์ เนื่องจากข้อจำกัดด้านผู้ให้บริการ
- เซ็กเมนต์เท่านั้น
- จับคู่ใน Google Ads อาจใช้เวลาถึง 48 ชั่วโมง

## <a name="set-up-connection-to-google-ads"></a>ตั้งค่าการเชื่อมต่อไปยัง Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Google Ads**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อนรหัสลูกค้า Google Ads ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **รับรองความถูกต้องกับ Google Ads** และให้ข้อมูลประจำตัวของ Google Ads ของคุณ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Google Ads ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกว่าจะใช้ผู้ชมที่มีอยู่หรือสร้างใหม่
   - หากต้องการปรับปรุงผู้ชม Google Ads ที่มีอยู่ ให้ป้อน [รหัสผู้ชม Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) ของคุณ
   - หากต้องการสร้างผู้ชมใหม่ ให้ปล่อยฟิลด์รหัสผู้ชม Google เว้นว่างไว้ Customer Insights จะสร้างผู้ชมใหม่ในบัญชี Google Ads ของคุณโดยอัตโนมัติ และใช้ชื่อของเซ็กเมนต์ที่ส่งออก

1. ในส่วน **การจับคู่ข้อมูล** ให้เลือกฟิลด์ข้อมูลอย่างน้อยหนึ่งฟิลด์เพื่อส่งออก และเลือกฟิลด์ที่แสดงถึงฟิลด์ข้อมูลที่สอดคล้องกันใน Customer Insights

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
