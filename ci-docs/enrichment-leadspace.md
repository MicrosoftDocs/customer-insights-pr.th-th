---
title: การเพิ่มข้อมูลโปรไฟล์ของบริษัทด้วยการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม Leadspace
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954202"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>การเพิ่มข้อมูลของโปรไฟล์บริษัทด้วย Leadspace (พรีวิว)

Leadspace เป็นบริษัทวิทยาศาสตร์ข้อมูลที่ให้บริการแพลตฟอร์มข้อมูลลูกค้าแบบ B-to-B ซึ่งเปิดใช้งานสภาพแวดล้อมที่มีโปรไฟล์ลูกค้าแบบรวมตามบัญชีเพื่อเพิ่มข้อมูลของพวกเขา เพิ่ม *โปรไฟล์ลูกค้า* ด้วยคุณลักษณะต่างๆ เช่น ขนาดบริษัท ที่ตั้ง หรืออุตสาหกรรม เพิ่ม *โปรไฟล์ผู้ติดต่อ* ด้วยคุณลักษณะ เช่น ตำแหน่ง ลักษณะ หรือการยืนยันอีเมล

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สิทธิ์การใช้งาน Leadspace ที่ใช้งานอยู่
- [Unified customer profile](customer-profiles.md) ตามบัญชี
- [การเชื่อมต่อ](connections.md) Leadspace ได้รับการ [กำหนดค่า](#configure-the-connection-for-leadspace) โดยผู้ดูแลระบบ ติดต่อ [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) โดยตรงสำหรับรายละเอียดเกี่ยวกับผลิตภัณฑ์ของพวกเขา

## <a name="configure-the-connection-for-leadspace"></a>กำหนดค่าการเชื่อมต่อสำหรับ Leadspace

คุณต้องเป็น [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights และมี “คีย์ถาวร” (เรียกว่า **โทเค็น Leadspace**)

1. เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มความสมบูรณ์ หรือไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Leadspace

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อสำหรับ Leadspace":::

1. ป้อนชื่อสำหรับการเชื่อมต่อและโทเค็น Leadspace ที่ถูกต้อง

1. รีวิวและให้ความยินยอมของคุณสำหรับ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](#data-privacy-and-compliance) โดยการเลือก **ฉันเห็นด้วย**

1. เลือก **ตรวจสอบ** เพื่อตรวจสอบการกำหนดค่าแล้วเลือก **บันทึก**

### <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Leadspace คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Leadspace ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ

## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มข้อมูล

1. ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**

1. เลือก **เพิ่มข้อมูลของฉัน** บน **ข้อมูลบริษัท** จากไทล์ Leadspace

   :::image type="content" source="media/leadspace-tile.png" alt-text="ภาพหน้าจอของไทล์ Leadspace":::

1. ตรวจสอบภาพรวม แล้วเลือก **ถัดไป**

1. เลือกการเชื่อมต่อ ติดต่อผู้ดูแลระบบ หากไม่มี

1. เลือก **ถัดไป**

1. เลือก **ชุดข้อมูลลูกค้า** และเลือกโปรไฟล์หรือเซ็กเมนต์ที่คุณต้องการเพิ่มด้วยข้อมูลบริษัทจาก Leadspace เอนทิตี *ข้อมูล* จะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดของคุณ ขณะที่เซ็กเมนต์จะเพิ่มข้อมูลเฉพาะโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. กำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่จะใช้สำหรับการจับคู่: ที่อยู่หลักและ/หรือสำรอง คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งสองและเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งสองแยกกัน ตัวอย่างเช่น สำหรับที่อยู่บ้านและที่อยู่ธุรกิจ เลือก **ถัดไป**

1. แมปฟิลด์ของคุณกับข้อมูลบริษัทจาก Leadspace ต้องระบุฟิลด์ **ชื่อของบริษัท** เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถได้อีกสองฟิลด์ **เว็บไซต์ของบริษัท** และ **ตำแหน่งที่ตั้งบริษัท**

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="บานหน้าต่างการแมปฟิลด์ Leadspace":::

1. ให้เลือก **ถัดไป** เพื่อทำการแมปฟิลด์ให้เสร็จ

1. เลือกกล่องกาเครื่องหมาย ถ้าคุณมี *โปรไฟล์ผู้ติดต่อ* ที่คุณต้องการเพิ่ม Customer Insights จะจับคู่ฟิลด์ที่จำเป็นโดยอัตโนมัติ

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="การเพิ่มข้อมูลเรกคอร์ดผู้ติดต่อของ Leadspace":::

1. เลือก **ถัดไป**

1. ระบุ **ชื่อ** สำหรับการเพิ่มความสมบูรณ์ และ **ชื่อเอนทิตีผลลัพธ์**

1. เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว

1. เลือก **เรียกใช้** เพื่อเริ่มกระบวนการเพิ่มความสมบูรณ์หรือปิดเพื่อกลับไปยังหน้า **การเพิ่มความสมบูรณ์**

## <a name="enrichment-results"></a>ผลลัพธ์การเพิ่มข้อมูล

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

สำหรับข้อมูลเพิ่มเติม โปรดดู [APIs ของ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
