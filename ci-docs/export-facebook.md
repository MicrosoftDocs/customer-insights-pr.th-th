---
title: ส่งออกเซกเมนต์ไปยัง Facebook Ads Manager (พรีวิว) (มีวิดีโอ)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยังตัวจัดการโฆษณาบน Facebook
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195037"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>ส่งออกเซกเมนต์ไปยัง Facebook Ads Manager (พรีวิว)

ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยัง Facebook Ads Manager เพื่อสร้างแคมเปญใน Facebook และ Instagram

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ที่มี [บัญชี Facebook Business](https://business.facebook.com/)
- สิทธิ์การใช้งานของผู้ดูแลระบบใน [บัญชี Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 10 ล้านรายการไปยัง Facebook Ads Manager ซึ่งอาจใช้เวลานานถึง 90 นาที
- เซ็กเมนต์เท่านั้น
- ชนิด *รายชื่อลูกค้า* Facebook ใน [ผู้ชมที่กำหนดเอง](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) เท่านั้น
  > [!NOTE]
  > ในบางกรณี คุณอาจเห็นผู้ชมแบบกำหนดเองชนิดต่างๆ ในรายการแบบหล่นลง หากคุณเลือกชนิดที่แตกต่างจาก *รายชื่อลูกค้า* การส่งออกจะล้มเหลว

## <a name="set-up-connection-to-facebook-ads-manager"></a>ตั้งค่าการเชื่อมต่อกับตัวจัดการโฆษณาบน Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Facebook Ads Manager**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. รับรองความถูกต้องด้วยโฆษณา Facebook:

   1. เลือก **ดำเนินการต่อด้วย Facebook** เพื่อลงชื่อเข้าใช้บัญชี Facebook Ads ของคุณ

   1. อนุญาตสิทธิ์ **ads_management** หลังจากการรับรองความถูกต้องกับ Facebook

   1. เลือก **บัญชี Facebook Ads** ที่คุณต้องการใช้งาน

   1. เลือก **ผู้ชมแบบกำหนดเองที่มีอยู่** จากรายการแบบหล่นลง หรือสร้าง **ผู้ชมแบบกำหนดเองใหม่**

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Facebook Ads Manager ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ในฟิลด์ **เชื่อมต่อข้อมูล** เลือก **อีเมล** **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไปยัง Facebook Ads Manager

1. แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก
   > [!TIP]
   > โอกาสที่ดีที่สุดสำหรับการจับคู่จะเกิดขึ้น หากคุณเลือก **อีเมล** เป็นรหัสคีย์ การเพิ่มตัวระบุเพิ่มเติมอาจช่วยปรับปรุงการจับคู่ให้ดีขึ้น

1. เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมเพื่อส่งไปยังตัวจัดการโฆษณาบน Facebook แอตทริบิวต์จาก Facebook Ads Manager กำลังแมปกับชื่อที่เป็นมิตรต่อผู้ใช้: **FN** = **ชื่อ**, **LN** = **นามสกุล**, **FI** = **เริ่มต้นครั้งแรก**, **PHONE** = **โทรศัพท์**, **GEN** = **เพศ**, **DOB** = **วันเกิด**, **ST** = **สถานะ**, **CT** = **เมือง**, **ZIP** = **รหัสไปรษณีย์ / รหัสไปรษณีย์**, **ประเทศ** = **ประเทศ / ภูมิภาค**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
