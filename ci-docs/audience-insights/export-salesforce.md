---
title: ส่งออกข้อมูล Customer Insights ไปยัง Salesforce Marketing Cloud
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Salesforce Marketing Cloud
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8ce243918c2388e931a98df3bbe576ddf692f707
ms.sourcegitcommit: 4823684a1399fd66ffecfce21735f2bc90a1733c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2021
ms.locfileid: "6660290"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>ส่งออกเซ็กเมนต์และข้อมูลอื่นๆ ไปยัง Salesforce Marketing Cloud (พรีวิว)

ใช้ข้อมูลลูกค้าของคุณใน Salesforce Marketing Cloud โดยส่งออกผ่านตำแหน่ง Secure File Transfer Protocol (SFTP)

## <a name="prerequisites-for-connection"></a>ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ

- ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง [วิธีตั้งค่าตำแหน่ง SFTP สำหรับ Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>ตั้งค่าการเชื่อมต่อกับ Salesforce Marketing Cloud

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Salesforce Marketing Cloud** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ

1. เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SFTP หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้

1. เลือกว่าคุณต้องการส่งออก **บีบอัดแบบ Gzip แล้ว** ข้อมูลของคุณหรือ **คลายการบีบอัดแล้ว** และ **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออกหรือไม่

1. เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์

   > [!NOTE]
   > แต่ละเอนทิตีที่เลือกจะถูกแบ่งออกเป็นไฟล์ผลลัพธ์สูงสุดห้าไฟล์เมื่อส่งออก 

1. เลือก **บันทึก**

การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที

การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand) 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>นำเข้าข้อมูล Customer Insights จากตำแหน่ง SFTP ไปยัง Salesforce Marketing Cloud

1. สร้าง [ส่วนขยายข้อมูลใน Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) เพื่อนำเข้าไฟล์ข้อมูล Customer Insights จากตำแหน่ง SFTP

2. [นำเข้าข้อมูลจากตำแหน่ง SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ลงในส่วนขยายข้อมูล Salesforce Marketing Cloud 

3. ตั้งค่าระบบอัตโนมัติเพื่อนำเข้าข้อมูลไปยังส่วนขยายข้อมูล เรียนรู้เพิ่มเติมเกี่ยวกับ [ระบบอัตโนมัติของการวางไฟล์และระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)

   กำหนด [ระบบอัตโนมัติของการวางไฟล์](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) หรือ [ระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) 

นี่คือตัวอย่างของ [ระบบอัตโนมัติที่มี SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้

[!INCLUDE[footer-include](../includes/footer-banner.md)]
