---
title: ส่งออกเซ็กเมนต์ไปยัง Snapchat (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง Snapchat
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195405"
---
# <a name="export-segments-to-snapchat-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Snapchat (พรีวิว)

ส่งออกเซ็กเมนต์ของโปรไฟล์ลูกค้าแบบรวมไปยัง Snapchat และใช้สำหรับการโฆษณา

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี Snapchat Business](https://business.snapchat.com/) [บัญชี Snapchat Ads](https://ads.snapchat.com/) และข้อมูลประจำตัวผู้ดูแลระบบที่สอดคล้องกัน คุณต้องเป็นสมาชิกของบัญชีองค์กรและผู้จัดการข้อมูลของบัญชีโฆษณาเฉพาะเป็นอย่างน้อย
- มีผู้ชมอย่างน้อยหนึ่งรายในผู้จัดการผู้ชม Snapchat เป็นชนิด SAM (การจับคู่ผู้ชม Snap)
- [รหัสเซ็กเมนต์/ผู้ชม Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences) รหัสของผู้ชมสามารถพบได้ใน URL หลังจากเลือกผู้ชมในผู้จัดการผู้ชม Snapchat
- [กำหนดค่าเซ็กเมนต์](segments.md) ใน Customer Insights
- โปรไฟล์ลูกค้าแบบรวมในเซ็กเมนต์ที่ส่งออกประกอบด้วยฟิลด์ที่แสดงที่อยู่อีเมล

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- ส่งออกโปรไฟล์ลูกค้าได้สูงสุด 1 ล้านรายการ ซึ่งอาจใช้เวลานานถึง 15 นาทีจึงจะเสร็จสมบูรณ์
- เซ็กเมนต์เท่านั้น

## <a name="set-up-connection-to-snapchat"></a>ตั้งค่าการเชื่อมต่อไปยัง Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Snapchat**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **เชื่อมต่อ** เพื่อเริ่มต้นการเชื่อมต่อ

1. เลือก **รับรองความถูกต้องกับ Snapchat** และให้ข้อมูลรับรองผู้ดูแลระบบของคุณสำหรับ Snapchat

1. เลือก **เพิ่มตัวเองเป็นผู้ใช้ที่ส่งออก** และให้ข้อมูลประจำตัวของ Customer Insights ของคุณ

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Snapchat ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ป้อน **รหัสเซ็กเมนต์/ผู้ชม Snapchat**

1. ในส่วน **การจับคู่ข้อมูล** ในฟิลด์ **อีเมล** เลือกฟิลด์ที่แสดงถึงที่อยู่อีเมลของลูกค้า

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
