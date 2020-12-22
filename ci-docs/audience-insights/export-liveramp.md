---
title: ตัวเชื่อมต่อ LiveRamp
description: เรียนรู้วิธีส่งออกข้อมูลไปยัง LiveRamp
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667207"
---
# <a name="liverampreg-connector-preview"></a>ตัวเชื่อมต่อ LiveRamp&reg; (แสดงตัวอย่าง)

เริ่มการใช้งานข้อมูลของคุณใน LiveRamp เพื่อเชื่อมต่อกับแพลตฟอร์มมากกว่า 500 ระบบในระบบดิจิทัล สังคม และทีวี ทำงานกับข้อมูลของคุณใน LiveRamp เพื่อกำหนดเป้าหมาย ปราบปราม และปรับแต่งแคมเปญโฆษณา

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- คุณต้องสมัครใช้งาน LiveRamp เพื่อใช้ตัวเชื่อมต่อนี้
- เพื่อรับการสมัครใช้งาน [ติดต่อ LiveRamp](https://liveramp.com/contact/) โดยตรง [เรียนรู้เพิ่มเติมเกี่ยวกับวิธีการเริ่มทำงาน LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>เชื่อมต่อกับ LiveRamp

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ในไทล์ **LiveRamp** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**

1. ใส่ **ชื่อผู้ใช้** และ **รหัสผ่าน** สำหรับบัญชี LiveRamp Secure FTP (SFTP) ของคุณ
ข้อมูลประจำตัวเหล่านี้อาจแตกต่างจากข้อมูลประจำตัววิธีการเริ่มทำงาน LiveRamp ของคุณ

1. เลือก **ยืนยัน** เพื่อทดสอบการเชื่อมต่อกับ LiveRamp

1. หลังจากการยืนยันสำเร็จ ให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**

1. เลือก **ต่อไป** เพื่อตั้งค่าตัวเชื่อมต่อ LiveRamp

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ในฟิลด์ **เลือกตัวระบุคีย์ของคุณ** เลือก **อีเมล**  **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไปยัง LiveRamp สำหรับการแก้ไขตัวตน

1. แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก

1. เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติม เพื่อส่งไปยัง LiveRamp

   > [!TIP]
   > การส่งแอตทริบิวต์ตัวระบุคีย์เพิ่มเติมไปยัง LiveRamp มีแนวโน้มที่จะทำให้คุณได้รับอัตราการจับคู่ที่สูงขึ้น

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออกไปยัง LiveRamp

1. เลือก **บันทึก**

> [!div class="mx-imgBorder"]
> ![ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์](media/export-liveramp-segments.png "ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์")

## <a name="export-the-data"></a>ส่งออกข้อมูล

การส่งออกจะเริ่มในไม่ช้า หากข้อกำหนดเบื้องต้นสำหรับการส่งออกเสร็จสมบูรณ์แล้ว นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง
เมื่อการส่งออกเสร็จสมบูรณ์ คุณสามารถเข้าสู่วิธีการเริ่มทำงาน LiveRamp เพื่อเริ่มการใช้งานและเผยแพร่ข้อมูลของคุณ

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Liveramp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Liveramp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้