---
title: ส่งออกข้อมูลไปยัง Salesforce Marketing Cloud (พรีวิว)
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Salesforce Marketing Cloud
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197061"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>ส่งออกข้อมูลไปยัง Salesforce Marketing Cloud (พรีวิว)

ใช้ข้อมูลลูกค้าของคุณใน Salesforce Marketing Cloud โดยส่งออกผ่านตำแหน่ง Secure File Transfer Protocol (SFTP)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- An [โฮสต์ SFTP สำหรับ Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>ตั้งค่าการเชื่อมต่อกับ Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Salesforce Marketing Cloud**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ

1. เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SFTP ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกว่าคุณต้องการส่งออก **บีบอัดแบบ Gzip แล้ว** ข้อมูลของคุณหรือ **คลายการบีบอัดแล้ว** และ **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออกหรือไม่

1. เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์

   > [!NOTE]
   > แต่ละเอนทิตีที่เลือกจะถูกแบ่งออกเป็นไฟล์ผลลัพธ์สูงสุดห้าไฟล์เมื่อส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>นำเข้าข้อมูล Customer Insights จากตำแหน่ง SFTP ไปยัง Salesforce Marketing Cloud

1. สร้าง [ส่วนขยายข้อมูลใน Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) เพื่อนำเข้าไฟล์ข้อมูล Customer Insights จากตำแหน่ง SFTP

2. [นำเข้าข้อมูลจากตำแหน่ง SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ลงในส่วนขยายข้อมูล Salesforce Marketing Cloud

3. ตั้งค่าระบบอัตโนมัติเพื่อนำเข้าข้อมูลไปยังส่วนขยายข้อมูล เรียนรู้เพิ่มเติมเกี่ยวกับ [ระบบอัตโนมัติของการวางไฟล์และระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)

   กำหนด [ระบบอัตโนมัติของการวางไฟล์](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) หรือ [ระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)

นี่คือตัวอย่างของ [ระบบอัตโนมัติที่มี SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)

[!INCLUDE [footer-include](includes/footer-banner.md)]
