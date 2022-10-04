---
title: ส่งออกข้อมูล Customer Insights ไปยัง HubSpot
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง HubSpot
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588917"
---
# <a name="export-segments-to-hubspot-preview"></a>ส่งออกเซ็กเมนต์ไปยัง HubSpot (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง HubSpot และใช้สำหรับการตลาดทางอีเมล

## <a name="prerequisites-for-a-connection"></a>ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ

- คุณมี [บัญชี HubSpot](https://www.hubspot.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่เกี่ยวข้อง
- [คีย์ API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) จาก HubSpot
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- โปรไฟล์ลูกค้าสูงสุด 100,000 รายการต่อการส่งออกไปยัง HubSpot ซึ่งอาจใช้เวลาถึง 15 นาทีจึงจะเสร็จสมบูรณ์ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง HubSpot จะขึ้นอยู่กับและจำกัดตามสัญญาของคุณกับ HubSpot
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-hubspot"></a>ตั้งค่าการเชื่อมต่อไปยัง HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **HubSpot** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อนข้อมูลประจำตัวของ HubSpot ของคุณเมื่อได้รับแจ้ง

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มการเชื่อมต่อ HubSpot

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน HubSpot หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า ทำซ้ำขั้นตอนเดียวกันสำหรับฟิลด์ที่ไม่บังคับอื่นๆ

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
