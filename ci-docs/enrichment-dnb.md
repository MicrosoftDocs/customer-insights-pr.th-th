---
title: การเพิ่มข้อมูลของโปรไฟล์บริษัทด้วย Dun & Bradstreet
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลของบุคคลที่สามของ Dun & Bradstreet
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653753"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>การเพิ่มข้อมูลของโปรไฟล์บริษัทด้วย Dun & Bradstreet (พรีวิว)

Dun & Bradstreet ให้ข้อมูลเชิงพาณิชย์ การวิเคราะห์ และข้อมูลเชิงลึกสำหรับธุรกิจ ซึ่งช่วยให้ลูกค้าที่มีโปรไฟล์ลูกค้าแบบรวมสำหรับบริษัทสามารถเพิ่มข้อมูลของพวกเขาได้ การเพิ่มข้อมูลมีแอตทริบิวต์ต่างๆ เช่น หมายเลข DUNS, ขนาดบริษัท ตำแหน่งที่ตั้ง อุตสาหกรรม และอื่นๆ อีกมากมาย

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

เมื่อต้องการกำหนดค่าการเพิ่มข้อมูล Dun & Bradstreet คุณต้องทำตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณต้องมีสิทธิ์การใช้งาน [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ที่ใช้งานอยู่
- คุณมี [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md) สำหรับบริษัท
- [การเชื่อมต่อ](connections.md) Dun & Bradstreet มีการกำหนดค่าโดยผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อได้ถ้าคุณมีสิทธิ์ของ [ผู้ดูแลระบบ](permissions.md#admin) และข้อมูลประจำตัวจาก Dun & Bradstreet Connect 

## <a name="setting-up-your-dun--bradstreet-project"></a>การตั้งค่าโครงการ Dun & Bradstreet ของคุณ

ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานของ Dun & Bradstreet คุณสามารถตั้งค่าโครงการใน [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) 


1. ลงชื่อเข้าใช้ [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) หากต้องการเรียกข้อมูลประจำตัว [คืนค่ารหัสผ่านของคุณ](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)

1. ดาวน์โหลด [ไฟล์เทมเพลต csv ของเรา](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ที่จะใช้ในการแมปฟิลด์ข้อมูลเชิงลึกของผู้ชมกับฟิลด์ของ Dun & Bradstreet ที่เกี่ยวข้อง 

1. อัปโหลดไฟล์ในขั้นตอน **อัปโหลดข้อมูล** ของประสบการณ์การสร้างโครงการ Dun & Bradstreet 

1. เลือกจุดแนวนอนภายใต้ **แหล่งที่มา** ที่เกี่ยวข้องในโครงการ Dun & Bradstreet ที่สร้างขึ้นใหม่เพื่อดูตัวเลือกที่มีอยู่

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="ภาพหน้าจอของจุดต่างๆ ในโครงการ Dun & Bradstreet":::

1. เลือก **รับรายละเอียด S3** เก็บข้อมูลนี้ไว้ในที่ปลอดภัย คุณจะต้อง [ตั้งค่าการเชื่อมต่อสำหรับการเพิ่มความสมบูรณ์](#configure-a-connection-for-dun--bradstreet) ในข้อมูลเชิงลึกของผู้ชม 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="ภาพหน้าจอของการเลือกข้อมูล s3 ในโครงการ Dun & Bradstreet":::



## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มข้อมูล

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**

1. เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ Dun & Bradstreet แล้วเลือก **เริ่มต้นใช้งาน**

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="ภาพหน้าจอของไทล์ Dun & Bradstreet":::

1. เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อได้ เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Dun & Bradstreet** 

1. เลือก **เชื่อมต่อกับ Dun & Bradstreet** เพื่อยืนยันการเชื่อมต่อ

1. เลือก **ถัดไป** และเลือก **ชุดข้อมูลลูกค้า** ที่คุณต้องการเพิ่มด้วยข้อมูลบริษัทจาก Dun & Bradstreet คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น

1. เลือก **ถัดไป** และกำหนดชนิดของฟิลด์จากโปรไฟล์แบบรวมของคุณที่จะใช้เพื่อค้นหาข้อมูลบริษัทที่ตรงกันจาก Dun & Bradstreet ต้องระบุข้อมูลในฟิลด์ **หมายเลข DUNS** หรือ **ชื่อบริษัท** และ **ประเทศ** ฟิลด์ประเทศรองรับ [รหัสประเทศแบบสองหรือสามตัวอักษร](https://www.iso.org/iso-3166-country-codes.html), ชื่อประเทศเป็นภาษาอังกฤษ, ชื่อประเทศเป็นภาษาแม่ และหมายเลขนำหน้าโทรศัพท์ ตัวแปรของประเทศทั่วไปบางส่วน ได้แก่:

   * US: สหรัฐอเมริกา, สหรัฐฯ, USA, อเมริกา
   * CA: แคนาดา
   * GB: สหราชอาณาจักร บริเตนใหญ่, GB, สหราชอาณาจักรบริเตนใหญ่และไอร์แลนด์เหนือ สหราชอาณาจักรบริเตนใหญ่
   * AU: ออสเตรเลีย เครือจักรภพออสเตรเลีย
   * FR: ฝรั่งเศส สาธารณรัฐฝรั่งเศส
   * DE: เยอรมนี เยอรมัน อัลเลอมาญ สหพันธ์สาธารณรัฐเยอรมนี สาธารณรัฐเยอรมนี

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="บานหน้าต่างการแมปฟิลด์ Dun & Bradstreet":::

1. ให้เลือก **ถัดไป** เพื่อทำการแมปฟิลด์ให้เสร็จ

1. ระบุชื่อสำหรับการเพิ่มข้อมูลและเลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว


## <a name="configure-a-connection-for-dun--bradstreet"></a>กำหนดค่าการเชื่อมต่อสำหรับ Dun & Bradstreet 

คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มความสมบูรณ์ *หรือ* ไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ Dun & Bradstreet

1. เลือก **เริ่มต้นใช้งาน** 

1. ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**

1. ระบุข้อมูลประจำตัวสำหรับ Dun & Bradstreet ที่ถูกต้องและรายละเอียดโครงการ Dun & Bradstreet *ภูมิภาค, พาธโฟลเดอร์ที่เก็บ และชื่อโฟลเดอร์ที่เก็บ* คุณ [รับข้อมูลนี้](#setting-up-your-dun--bradstreet-project) จากโครงการ Dun & Bradstreet

1. รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** โดยการเลือก **ฉันเห็นด้วย**

1. เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า

1. หลังจากเสร็จสิ้นการตรวจสอบแล้ว ให้เลือก **บันทึก**
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อกับ Dun & Bradstreet":::

## <a name="enrichment-results"></a>ผลลัพธ์การเพิ่มข้อมูล

หลังจากรีเฟรชการเพิ่มข้อมูล คุณสามารถตรวจสอบข้อมูลบริษัทที่ปรับปรุงใหม่ได้ภายใต้ [การเพิ่มความสมบูรณ์ของฉัน](enrichment-hub.md) คุณสามารถค้นหาเวลาของการปรับปรุงครั้งล่าสุดและจำนวนของโปรไฟล์ที่มีการเพิ่มข้อมูล

คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**

## <a name="next-steps"></a>ขั้นตอนถัดไป

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Dun & Bradstreet คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่ในการทำให้แน่ใจว่า Dun & Bradstreet ปฏิบัติตามภาระผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ


[!INCLUDE[footer-include](includes/footer-banner.md)]
