---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยการนําเข้าแบบกําหนดเองของ SFTP (พรีวิว)
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มความสมบูรณ์ด้วยการนําเข้าแบบกําหนดเองของ SFTP
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195819"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยการนําเข้าแบบกําหนดเองของ SFTP (พรีวิว)

การนำเข้าแบบกำหนดเองของ Secure File Transfer Protocol (SFTP) ช่วยให้คุณสามารถนำเข้าข้อมูลที่ไม่ต้องผ่านขั้นตอนการรวมข้อมูล เป็นวิธีที่ยืดหยุ่น ปลอดภัยและง่ายในการนำข้อมูลของคุณ การนำเข้าแบบกำหนดเองของ SFTP สามารถใช้ร่วมกับ [การส่งออก SFTP](export-sftp.md) ซึ่งช่วยให้คุณสามารถส่งออกข้อมูลโปรไฟล์ลูกค้าที่จำเป็นสำหรับการเพิ่มความสมบูรณ์ ข้อมูลสามารถประมวลผลและเพิ่มความสมบูรณ์ได้ และการนำเข้าแบบกำหนดเองของ SFTP สามารถใช้เพื่อนำข้อมูลที่เพิ่มความสมบูรณ์กลับมาที่ Dynamics 365 Customer Insights

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- ชื่อไฟล์และตำแหน่ง (พาธ) ของไฟล์ที่จะนำเข้าบนโฮสต์ SFTP เป็นที่รู้จัก

- ไฟล์ *model.json* ที่ระบุ Common Data Model Schema สำหรับข้อมูลที่จะนำเข้าพร้อมใช้งาน ไฟล์นี้ต้องอยู่ในไดเรกทอรีเดียวกับไฟล์ที่จะนำเข้า

- [การเชื่อมต่อ](connections.md) SFTP ได้รับการ [กำหนดค่า](#configure-the-connection-for-sftp-custom-import)

## <a name="file-schema-example"></a>ตัวอย่าง Schema ของไฟล์

ไดเรกทอรีที่มีไฟล์ที่จะนำเข้าบนเซิร์ฟเวอร์ SFTP ต้องมีไฟล์ *model.json* ไฟล์นี้กำหนด Schema ที่จะใช้สำหรับการนำเข้าข้อมูล Schema ต้องใช้ [Common Data Model](/common-data-model/) เพื่อระบุการแมปฟิลด์ ตัวอย่างง่ายๆ ของไฟล์ model.json มีลักษณะดังนี้:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>กำหนดค่าการเชื่อมต่อสำหรับการนำเข้าแบบกำหนดเองของ SFTP

คุณต้องเป็น [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights และมีข้อมูลประจำตัวผู้ใช้, URL และหมายเลขพอร์ตสำหรับตำแหน่ง SFTP ที่คุณต้องการนำเข้าข้อมูล

1. เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มความสมบูรณ์ หรือไปที่ **ผู้ดูแลระบบ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์การนำเข้าที่กำหนดเอง

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="หน้าการกำหนดค่าการเชื่อมต่อกับการนำเข้าที่กำหนดเอง":::

1. ป้อนชื่อสำหรับการเชื่อมต่อ

1. ป้อนชื่อผู้ใช้ รหัสผ่าน และ URL โฮสต์ที่ถูกต้องสำหรับเซิร์ฟเวอร์ SFTP ที่มีข้อมูลที่จะถูกนำเข้า

1. รีวิวและให้ความยินยอมของคุณสำหรับ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](#data-privacy-and-compliance) โดยการเลือก **ฉันเห็นด้วย**

1. เลือก **ตรวจสอบ** เพื่อตรวจสอบการกำหนดค่าแล้วเลือก **บันทึก**

### <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลโดยใช้การนำเข้าที่กำหนดเอง คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่ในการทำให้แน่ใจว่าข้อมูลตรงตามภาระผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มความสมบูรณ์นี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ

## <a name="configure-the-import"></a>กำหนดค่าการนำเข้า

1. ไปที่ **ข้อมูล** > **การเพิ่มความสมบูรณ์** และเลือกแท็บ **ค้นหา**

1. เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ **การนำเข้าที่กำหนดเองของ SFTP**

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP":::

1. ตรวจสอบภาพรวม แล้วเลือก **ถัดไป**

1. เลือกการเชื่อมต่อ ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. เลือก **ชุดข้อมูลลูกค้า** และเลือกโปรไฟล์หรือเซ็กเมนต์ที่คุณต้องการเพิ่มข้อมูล เอนทิตี *ข้อมูล* จะเพิ่มข้อมูลโปรไฟล์ลูกค้าทั้งหมดของคุณ ขณะที่เซ็กเมนต์จะเพิ่มข้อมูลเฉพาะโปรไฟล์ลูกค้าที่อยู่ในเซ็กเมนต์นั้น

1. เลือก **ถัดไป**

1. ป้อน **พาธ** และ **ชื่อไฟล์** ของไฟล์ข้อมูลที่คุณต้องการนำเข้า

1. เลือก **ถัดไป**

1. ระบุ **ชื่อ** สำหรับการเพิ่มความสมบูรณ์ และ **ชื่อเอนทิตีผลลัพธ์**

1. เลือก **บันทึกการเพิ่มความสมบูรณ์** หลังจากตรวจสอบตัวเลือกของคุณแล้ว

1. เลือก **เรียกใช้** เพื่อเริ่มกระบวนการเพิ่มความสมบูรณ์หรือปิดเพื่อกลับไปยังหน้า **การเพิ่มความสมบูรณ์**

## <a name="view-enrichment-results"></a>ดูผลลัพธ์การเพิ่มความสมบูรณ์

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
