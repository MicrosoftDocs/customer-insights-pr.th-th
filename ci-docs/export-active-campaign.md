---
title: ส่งออกเซ็กเมนต์ไปยัง ActiveCampaign
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง ActiveCampaign
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725423"
---
# <a name="export-segments-to-activecampaign-preview"></a>ส่งออกเซ็กเมนต์ไปยัง ActiveCampaign (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง ActiveCampaign และใช้สำหรับกิจกรรมทางการตลาด

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี ActiveCampaign](https://www.activecampaign.com/) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง
- [รหัสรายการ ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)
- [คีย์ API ของ ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) และชื่อโฮสต์จุดสิ้นสุด REST
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ไม่รองรับลิงก์ส่วนตัวร่วมกับการใช้ที่เก็บข้อมูลของคุณเอง (BYOS)
- ส่งออกโปรไฟล์ลูกค้าได้สูงสุดครั้งละ 1 ล้านรายการไปยัง ActiveCampaign ซึ่งอาจใช้เวลานานถึง 90 นาทีจึงจะเสร็จสมบูรณ์ จำนวนโปรไฟล์ลูกค้าที่คุณสามารถส่งออกไปยัง ActiveCampaign ขึ้นอยู่กับสัญญาของคุณกับ ActiveCampaign
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-activecampaign"></a>ตั้งค่าการเชื่อมต่อกับ ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **ActiveCampaign**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน คีย์ ActiveCampaign API และชื่อโฮสต์จุดสิ้นสุด REST ของคุณ ชื่อโฮสต์จุดสิ้นสุด REST เป็นชื่อโฮสต์เท่านั้น โดยไม่มี https://

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน ActiveCampaign ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ป้อน **รหัสรายการ ActiveCampaign** ของคุณ

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า

1. หรือส่งออก **ชื่อ**, **นามสกุล** และ **โทรศัพท์** เพื่อสร้างอีเมลที่ปรับให้เป็นแบบส่วนตัวเพิ่มเติม เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปฟิลด์เหล่านี้

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
