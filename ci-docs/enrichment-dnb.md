---
title: เพิ่มข้อมูลโปรไฟล์บริษัทด้วย Dun & Bradstreet (พรีวิว)
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลของบุคคลที่สามของ Dun & Bradstreet
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196049"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>เพิ่มข้อมูลโปรไฟล์บริษัทด้วย Dun & Bradstreet (พรีวิว)

Dun & Bradstreet ให้ข้อมูลเชิงพาณิชย์ การวิเคราะห์ และข้อมูลเชิงลึกสำหรับธุรกิจ ซึ่งช่วยให้ลูกค้าที่มีโปรไฟล์ลูกค้าแบบรวมสำหรับบริษัทสามารถเพิ่มข้อมูลของพวกเขาได้ การเพิ่มความสมบูรณ์มีแอตทริบิวต์ต่างๆ เช่น หมายเลข DUNS, ขนาดบริษัท ตำแหน่งที่ตั้ง อุตสาหกรรม และอื่นๆ อีกมากมาย

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สิทธิ์การใช้งาน [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ที่ใช้งานอยู่
- [Unified customer profile](customer-profiles.md) สำหรับบริษัท
- มีการตั้งค่า [โครงการ](#set-up-your-dun--bradstreet-project) Dun & Bradstreet
- [การเชื่อมต่อ](connections.md) Dun & Bradstreet ได้รับการ [กำหนดค่า](#configure-a-connection-for-dun--bradstreet) โดยผู้ดูแลระบบ

## <a name="set-up-your-dun--bradstreet-project"></a>ตั้งค่าโครงการ Dun & Bradstreet ของคุณ

ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานของ Dun & Bradstreet คุณสามารถตั้งค่าโครงการใน [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)

1. ลงชื่อเข้าใช้ [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) หากต้องการเรียกข้อมูลประจำตัว [คืนค่ารหัสผ่านของคุณ](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)

1. ดาวน์โหลด [ไฟล์เทมเพลต csv ของเรา](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ที่จะใช้ในการแมปฟิลด์ Customer Insights กับฟิลด์ของ Dun & Bradstreet ที่เกี่ยวข้อง

1. อัปโหลดไฟล์ในขั้นตอน **อัปโหลดข้อมูล** ของประสบการณ์การสร้างโครงการ Dun & Bradstreet

1. เลือกจุดแนวนอนภายใต้ **แหล่งที่มา** ที่เกี่ยวข้องในโครงการ Dun & Bradstreet ที่สร้างขึ้นใหม่เพื่อดูตัวเลือกที่มีอยู่

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="ภาพหน้าจอของจุดต่างๆ ในโครงการ Dun & Bradstreet":::

1. เลือก **รับรายละเอียด S3** เก็บข้อมูลนี้ไว้ในที่ปลอดภัย คุณจะต้อง [ตั้งค่าการเชื่อมต่อสำหรับการเพิ่มความสมบูรณ์](#configure-a-connection-for-dun--bradstreet) ใน Customer Insights

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="ภาพหน้าจอของการเลือกข้อมูล s3 ในโครงการ Dun & Bradstreet":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>กำหนดค่าการเชื่อมต่อสำหรับ Dun & Bradstreet

คุณต้องเป็น [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights และมีข้อมูลประจำตัวจาก Dun & Bradstreet Connect

1. เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มความสมบูรณ์ หรือไปที่ **ผู้ดูแลระบบ** > **การชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Dun & Bradstreet

1. ป้อนชื่อสำหรับการเชื่อมต่อ

1. ระบุข้อมูลประจำตัวสำหรับ Dun & Bradstreet ที่ถูกต้องและรายละเอียดโครงการ Dun & Bradstreet *ภูมิภาค, พาธโฟลเดอร์ที่เก็บ และชื่อโฟลเดอร์ที่เก็บ* คุณ [รับข้อมูลนี้](#set-up-your-dun--bradstreet-project) จากโครงการ Dun & Bradstreet

1. รีวิวและให้ความยินยอมของคุณสำหรับ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](#data-privacy-and-compliance) โดยการเลือก **ฉันเห็นด้วย**

1. เลือก **ตรวจสอบ** เพื่อตรวจสอบการกำหนดค่าแล้วเลือก **บันทึก**

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อกับ Dun & Bradstreet":::

### <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Dun & Bradstreet คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่ในการทำให้แน่ใจว่า Dun & Bradstreet ปฏิบัติตามภาระผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มความสมบูรณ์นี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ

## <a name="supported-countries-or-regions"></a>ประเทศหรือภูมิภาคที่รองรับ

ขณะนี้เรารองรับตัวเลือกประเทศ/ภูมิภาคต่อไปนี้: แคนาดา (อังกฤษ) หรือสหรัฐอเมริกา (อังกฤษ)

## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มความสมบูรณ์

1. ไปที่ **ข้อมูล** > **การเพิ่มความสมบูรณ์** และเลือกแท็บ **ค้นหา**

1. เลือก **เพิ่มข้อมูลของฉัน** บน **ข้อมูลบริษัท** สำหรับไทล์ Dun & Bradstreet

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="ภาพหน้าจอของไทล์ Dun & Bradstreet":::

1. ตรวจสอบภาพรวม แล้วเลือก **ถัดไป**

1. เลือกการเชื่อมต่อและยืนยัน ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. เลือก **ถัดไป**

1. เลือก **ชุดข้อมูลลูกค้า** และเลือกโปรไฟล์หรือเซ็กเมนต์ที่คุณต้องการเพิ่มด้วยข้อมูลบริษัทจาก Dun & Bradstreet เอนทิตี *ข้อมูล* จะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดของคุณ ขณะที่เซ็กเมนต์จะเพิ่มข้อมูลเฉพาะโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น

1. กำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่จะใช้เพื่อค้นหาข้อมูลบริษัทที่ตรงกันจาก Dun & Bradstreet อย่างน้อยหนึ่งในฟิลด์ **ชื่อและที่อยู่** **โทรศัพท์** หรือ **อีเมล์** ต้องระบุ

1. เลือก **ถัดไป**

1. แมปฟิลด์ของคุณกับข้อมูลบริษัทจาก Dun & Bradstreet ต้องระบุข้อมูลในฟิลด์ **หมายเลข DUNS** หรือ **ชื่อบริษัท** และ **ประเทศ**

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="บานหน้าต่างการแมปฟิลด์ Dun & Bradstreet":::

1. ให้เลือก **ถัดไป** เพื่อทำการแมปฟิลด์ให้เสร็จ

1. ระบุ **ชื่อ** สำหรับการเพิ่มความสมบูรณ์ และ **ชื่อเอนทิตีผลลัพธ์**

1. เลือก **บันทึกการเพิ่มความสมบูรณ์** หลังจากตรวจสอบตัวเลือกของคุณแล้ว

1. เลือก **เรียกใช้** เพื่อเริ่มกระบวนการเพิ่มความสมบูรณ์หรือปิดเพื่อกลับไปยังหน้า **การเพิ่มความสมบูรณ์**

## <a name="view-enrichment-results"></a>ดูผลลัพธ์การเพิ่มความสมบูรณ์

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
