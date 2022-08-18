---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237881"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)

HERE Technologies เป็นบริษัทแพลตฟอร์มด้านสถานที่ตั้งที่ให้บริการข้อมูลและสถานที่ตั้งเป็นหลัก บริการการเพิ่มข้อมูลของ HERE Technologies ช่วยปรับปรุงความแม่นยำของข้อมูลตำแหน่งที่ตั้งเกี่ยวกับลูกค้าของคุณ ซึ่งจะให้ที่อยู่แบบมาตรฐาน การแยกละติจูดและลองจิจูด และอื่นๆ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- การสมัครใช้งาน HERE Technologies ที่ใช้งานอยู่ หากต้องการรับการสมัครใช้งาน [ลงทะเบียนที่นี่](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) หรือ [ติดต่อ HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) โดยตรง [เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูลตำแหน่งที่ตั้งของ HERE Technologies](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [การเชื่อมต่อ](connections.md) HERE ได้รับการ [กำหนดค่า](#configure-the-connection-for-here-technologies) โดยผู้ดูแลระบบ

## <a name="configure-the-connection-for-here-technologies"></a>กำหนดค่าการเชื่อมต่อสำหรับ HERE Technologies

คุณต้องเป็น [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights และมีคีย์ API ของ HERE Technologies ที่ใช้งานอยู่

1. เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มข้อมูล หรือไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ HERE Technologies

1. ป้อนชื่อสำหรับการเชื่อมต่อและคีย์ API ของ HERE Technologies ที่ถูกต้อง

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **ตรวจสอบ** เพื่อตรวจสอบการกำหนดค่าแล้วเลือก **บันทึก**

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อสำหรับ HERE technologies":::

## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มความสมบูรณ์

1. ไปที่ **ข้อมูล** > **การเพิ่มความสมบูรณ์** และเลือกแท็บ **ค้นหา**

1. เลือก **เพิ่มข้อมูลของฉัน** บน **ตำแหน่งที่ตั้ง** จากไทล์ HERE Technologies

   :::image type="content" source="media/HERE-tile.png" alt-text="ไทล์ HERE Technologies":::

1. ตรวจสอบภาพรวม แล้วเลือก **ถัดไป**

1. เลือกการเชื่อมต่อ ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. เลือก **ถัดไป**

1. เลือก **ชุดข้อมูลลูกค้า** และเลือกโปรไฟล์หรือเซ็กเมนต์ที่คุณต้องการเพิ่มด้วยข้อมูลจาก HERE Technologies เอนทิตี *ข้อมูล* จะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดของคุณ ขณะที่เซ็กเมนต์จะเพิ่มข้อมูลเฉพาะโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น

1. กำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่จะใช้สำหรับการจับคู่: ที่อยู่หลักและ/หรือสำรอง คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งสองและเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งสองแยกกัน ตัวอย่างเช่น สำหรับที่อยู่บ้านและที่อยู่ธุรกิจ เลือก **ถัดไป**

1. แมปฟิลด์ของคุณกับข้อมูลจาก HERE Technologies ต้องระบุฟิลด์ **ถนน 1** และ **รหัสไปรษณีย์** สำหรับที่อยู่หลักและ/หรือรองที่เลือก เพื่อความแม่นยำของการจับคู่ที่สูงขึ้น ให้เพิ่มฟิลด์เพิ่มเติม

1. ให้เลือก **ถัดไป** เพื่อทำการแมปฟิลด์ให้เสร็จ

1. ระบุ **ชื่อ** สำหรับการเพิ่มความสมบูรณ์ และ **ชื่อเอนทิตีผลลัพธ์**

1. เลือก **บันทึกการเพิ่มความสมบูรณ์** หลังจากตรวจสอบตัวเลือกของคุณแล้ว

1. เลือก **เรียกใช้** เพื่อเริ่มกระบวนการเพิ่มความสมบูรณ์หรือปิดเพื่อกลับไปยังหน้า **การเพิ่มความสมบูรณ์**

## <a name="view-enrichment-results"></a>ดูผลลัพธ์การเพิ่มความสมบูรณ์

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**จำนวนของลูกค้าที่เพิ่มข้อมูลตามฟิลด์** จะแสดงรายละเอียดความครอบคลุมของแต่ละฟิลด์ที่ได้รับการเพิ่มข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
