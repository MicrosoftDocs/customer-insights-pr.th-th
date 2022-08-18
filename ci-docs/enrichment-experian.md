---
title: เพิ่มโปรไฟล์ลูกค้าด้วยข้อมูลประชากรจาก Experian (พรีวิว)
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลของบุคคลที่สาม Experian
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238019"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>เพิ่มโปรไฟล์ลูกค้าด้วยข้อมูลประชากรจาก Experian (พรีวิว)

Experian เป็นผู้นำระดับโลกในด้านการรายงานสินเชื่อของผู้บริโภคและธุรกิจและบริการด้านการตลาด ด้วยบริการการเพิ่มข้อมูลของ Experian คุณสามารถสร้างความเข้าใจที่ลึกซึ้งยิ่งขึ้นเกี่ยวกับลูกค้าของคุณ โดยการเพิ่มโปรไฟล์ลูกค้าของคุณด้วยข้อมูลประชากร เช่น ขนาดครัวเรือน รายได้ และอื่นๆ

## <a name="supported-countriesregions"></a>ประเทศ/ภูมิภาคที่รองรับ

ขณะนี้เราสนับสนุนการเพิ่มข้อมูลโปรไฟล์ลูกค้าในสหรัฐอเมริกาเท่านั้น

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- การสมัครใช้งาน Experian ที่ใช้งานอยู่ หากต้องการสมัครใช้งาน [ติดต่อ Experian](https://www.experian.com/marketing-services/contact) โดยตรง [เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูล Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)

- [การเชื่อมต่อ](connections.md) Experian ได้รับการ [กำหนดค่า](#configure-the-connection-for-experian) โดยผู้ดูแลระบบ

- รหัสผู้ใช้ Experian, รหัสฝ่าย และหมายเลขรุ่นสำหรับบัญชี Secure Transport (ST) ที่เปิดใช้งาน SSH ที่ Experian สร้างให้คุณ

## <a name="configure-the-connection-for-experian"></a>กำหนดค่าการเชื่อมต่อสำหรับ Experian

คุณต้องเป็น [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights และมีรหัสผู้ใช้ Experian, รหัสฝ่าย และหมายเลขรุ่น

1. เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มความสมบูรณ์ หรือไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Experian

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="บานหน้าต่างการกำหนดค่าการเชื่อมต่อ Experian":::

1. ป้อนชื่อสำหรับการเชื่อมต่อและรหัสผู้ใช้ รหัสฝ่าย และหมายเลขรุ่นที่ถูกต้องสำหรับบัญชี Experian Secure Transport ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **ตรวจสอบ** เพื่อตรวจสอบการกำหนดค่าแล้วเลือก **บันทึก**

## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มความสมบูรณ์

1. ไปที่ **ข้อมูล** > **การเพิ่มความสมบูรณ์** และเลือกแท็บ **ค้นหา**

1. เลือก **เพิ่มข้อมูลของฉัน** ใน **ข้อมูลประชากร** จากไทล์ Experian

   :::image type="content" source="media/experian-tile.png" alt-text="ไทล์ Experian ในหน้าภาพรวมของการเพิ่มความสมบูรณ์ ":::

1. ตรวจสอบภาพรวม แล้วเลือก **ถัดไป**

1. เลือกการเชื่อมต่อ ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. เลือก **ถัดไป**

1. เลือก **ชุดข้อมูลลูกค้า** และเลือกโปรไฟล์หรือเซ็กเมนต์ที่คุณต้องการเพิ่มด้วยข้อมูลประชากรจาก Experian เอนทิตี *ข้อมูล* จะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดของคุณ ขณะที่เซ็กเมนต์จะเพิ่มข้อมูลเฉพาะโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. กำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่จะใช้เพื่อค้นหาข้อมูลประชากรที่ตรงกันจาก Experian อย่างน้อยหนึ่งในฟิลด์ **ชื่อและที่อยู่** **โทรศัพท์** หรือ **อีเมล์** ต้องระบุ เพื่อความแม่นยำของการจับคู่ที่สูงขึ้น ให้เพิ่มฟิลด์อื่นๆ เลือก **ถัดไป**

1. แมปฟิลด์ของคุณกับข้อมูลประชากรจาก Experian

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
