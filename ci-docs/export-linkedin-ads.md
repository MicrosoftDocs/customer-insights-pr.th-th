---
title: ส่งออกเซ็กเมนต์ไปยัง LinkedIn Ads (พรีวิว)
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง LinkedIn Ads
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304726"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>ส่งออกเซ็กเมนต์ไปยัง LinkedIn Ads (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง LinkedIn Ads เพื่อสร้าง Matched Audiences ใช้ Matched Audiences สำหรับการกำหนดเป้าหมายบริษัทและการกำหนดเป้าหมายผู้ติดต่อ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง
- [รหัสบัญชี LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270)
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- เซ็กเมนต์ที่ส่งออกต้องมีฟิลด์เฉพาะอย่างน้อยหนึ่งฟิลด์ ขึ้นอยู่กับว่าคุณเลือก [กำหนดเป้าหมายผู้ติดต่อ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) หรือ [กำหนดเป้าหมายบริษัท](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) บน LinkedIn ฟิลด์ที่เป็นไปได้มีการระบุไว้ในขั้นตอน **การจับคู่ข้อมูล** เมื่อ [กำหนดค่าการส่งออก](#configure-an-export)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 100,000 ล้านรายการไปยัง LinkedIn Ads ซึ่งอาจใช้เวลานานถึง 10 นาทีจึงจะเสร็จสมบูรณ์
- เซ็กเมนต์เท่านั้น เซ็กเมนต์ต้องมีโปรไฟล์อย่างน้อย 300 รายการ

## <a name="set-up-connection-to-linkedin-ads"></a>ตั้งค่าการเชื่อมต่อกับ LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **LinkedIn Ads**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ระบุรหัสบัญชี LinkedIn Campaign Manager ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **รับรองความถูกต้องกับ LinkedIn** และให้ข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับ LinkedIn Campaign Manager

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน LinkedIn Ads ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกว่าคุณต้องการส่งออกข้อมูลเพื่อทำ [การกำหนดเป้าหมายการติดต่อ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) หรือ [การกำหนดเป้าหมายบริษัท](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) บน LinkedIn

1. ในส่วน **การจับคู่ข้อมูล** สำหรับการกำหนดเป้าหมายผู้ติดต่อ ให้เลือกอย่างน้อยหนึ่งฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า รหัสโฆษณา Apple รหัสโฆษณา Google รหัสผู้ใช้ Google หรือชื่อและนามสกุล หากคุณเลือกการกำหนดเป้าหมายบริษัท ให้เลือกอย่างน้อยหนึ่งฟิลด์ที่แสดงถึงชื่อบริษัท โดเมนอีเมล URL หน้า LinkedIn สัญลักษณ์หุ้น หรือเว็บไซต์

1. หรือเพิ่มฟิลด์เพิ่มเติมเพื่อกำหนดการส่งออกของคุณเพิ่มเติม เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก Matched Audiences ใน LinkedIn Campaign Manager จะถูกสร้างขึ้นโดยอัตโนมัติด้วยชื่อของเซ็กเมนต์ที่คุณเลือกที่จะส่งออก แต่ละเซ็กเมนต์จะส่งผลให้มี Matched Audience ที่แยกจากกัน

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
