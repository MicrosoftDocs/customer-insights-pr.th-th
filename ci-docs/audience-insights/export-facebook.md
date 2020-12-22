---
title: ส่งออกข้อมูล Customer Insights ไปยัง Facebook Ads Manager
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Facebook Ads Manager
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643706"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>ตัวเชื่อมต่อสำหรับ Facebook Ads Manager (แสดงตัวอย่าง)

ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยัง Facebook Ads Manager เพื่อสร้างแคมเปญใน Facebook และ Instagram

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- คุณต้องมี [**บัญชี Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ซึ่งรวมถึง [**บัญชี Facebook Business**](https://business.facebook.com/)
- คุณต้องเป็นผู้ดูแลระบบใน [**บัญชี Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)

## <a name="connect-to-facebook-ads-manager"></a>เชื่อมต่อกับ Facebook Ads Manager

1. ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Facebook Ads Manager** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

1. เลือก **ดำเนินการต่อด้วย Facebook** เพื่อเข้าสู่ระบบบัญชี Facebook Ad ของคุณ

1. อนุญาตสิทธิ์ **ads_management** หลังจากการรับรองความถูกต้องกับ Facebook

1. เลือก **บัญชี Facebook Ads** ที่คุณต้องการใช้งาน

1. เลือก **ผู้ชมแบบกำหนดเองที่มีอยู่** จากรายการแบบหล่นลง หรือสร้าง **ผู้ชมแบบกำหนดเองใหม่** สำหรับข้อมูลเพิ่มเติม โปรดดู [**ผู้ชมใน Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)

1. เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก

## <a name="configure-the-connector"></a>กำหนดค่าตัวเชื่อมต่อ

1. ใน **เลือกฟิลด์ตัวระบุคีย์ของคุณ** เลือก **อีเมล์** **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไป่ยัง Facebook Ads Manager

1. แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก
   > [เคล็ดลับ] โอกาสที่ดีที่สุดสำหรับการแข่งขันจะเกิดขึ้นหากคุณเลือก **อีเมล์** เป็นตัวระบุที่สำคัญ การเพิ่มตัวระบุเพิ่มเติมอาจช่วยปรับปรุงการจับคู่ให้ดีขึ้น

1. เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมที่จะส่งไปยัง Facebook Ads Manager แอตทริบิวต์จาก Facebook Ads Manager กำลังจับคู่กับชื่อที่เป็นมิตรต่อผู้ใช้: **FN** = **ชื่อ** **LN** = **นามสกุล** **FI** = **เริ่มต้นครั้งแรก** **โทรศัพท์** = **โทรศัพท์** **GEN** = **เพศ** **DOB** = **วันเกิด** **ST** = **สถานะ** **CT** = **เมือง** **ZIP** = **รหัสไปรษณีย์/รหัสไปรษณีย์** **ประเทศ** = **ประเทศ ภูมิภาค**

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Facebook Ads Manager คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Facebook Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้
