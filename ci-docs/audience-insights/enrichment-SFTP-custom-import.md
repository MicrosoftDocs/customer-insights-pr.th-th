---
title: การเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269629"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยข้อมูลแบบกำหนดเอง (พรีวิว)

การนำเข้าแบบกำหนดเองของ Secure File Transfer Protocol (SFTP) ช่วยให้คุณสามารถนำเข้าข้อมูลที่ไม่ต้องผ่านขั้นตอนการรวมข้อมูล เป็นวิธีที่ยืดหยุ่น ปลอดภัยและง่ายในการนำข้อมูลของคุณ การนำเข้าแบบกำหนดเองของ SFTP สามารถใช้ร่วมกับ [การส่งออก SFTP](export-sftp.md) ซึ่งช่วยให้คุณสามารถส่งออกข้อมูลโปรไฟล์ลูกค้าที่จำเป็นสำหรับการเพิ่มข้อมูล จากนั้นข้อมูลจะสามารถประมวลผล เพิ่ม และสามารถใช้การนำเข้าแบบกำหนดเองของ SFTP เพื่อนำข้อมูลที่มีการเพิ่มกลับมาที่ความสามารถข้อมูลเชิงลึกกลุ่มเป้าหมายของ Dynamics 365 Customer Insights

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

การกำหนดค่าการนําเข้าแบบกําหนดเองของ SFTP ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณมีข้อมูลประจำตัวของผู้ใช้ (ชื่อผู้ใช้และรหัสผ่าน) สำหรับตำแหน่งที่ตั้ง SFTP ที่จะนำเข้าข้อมูล
- คุณมี URL และหมายเลขพอร์ต (โดยทั่วไปคือ 22) สำหรับโฮสต์ STFP
- คุณมีชื่อไฟล์และตำแหน่งที่ตั้งของไฟล์ที่จะนำเข้าบนโฮสต์ SFTP
- มีไฟล์ *model.json* ที่ระบุ Schema สำหรับข้อมูลที่จะนำเข้า ไฟล์นี้ต้องอยู่ในไดเรกทอรีเดียวกับไฟล์ที่จะนำเข้า
- คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)

## <a name="configuration"></a>การกำหนดค่า

1. ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**

1. บน **ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP** ให้เลือก **เพิ่มข้อมูลของฉัน**

   > [!div class="mx-imgBorder"]
   > ![ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP](media/SFTP_Custom_Import_tile.png "ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP")

1. เลือก **เริ่มต้นใช้งาน** และระบุข้อมูลประจำตัวและที่อยู่สำหรับเซิร์ฟเวอร์ SFTP ตัวอย่างเช่น sftp: // mysftpserver.com: 22

1. ป้อนชื่อไฟล์ที่มีข้อมูลและพาธไปยังไฟล์บนเซิร์ฟเวอร์ SFTP หากไม่ได้อยู่ในโฟลเดอร์รูท

1. ยืนยันข้อมูลที่ป้อนทั้งหมดโดยการเลือก **เชื่อมต่อกับการนำเข้าแบบกำหนดเอง**

   > [!div class="mx-imgBorder"]
   > ![เมนูลอยการกำหนดค่าการนำเข้าแบบกำหนดเองของ SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "เมนูลอยการกำหนดค่าการนำเข้าแบบกำหนดเองของ SFTP")

## <a name="defining-field-mappings"></a>การกำหนดการแม็ปฟิลด์ 

ไดเรกทอรีที่มีไฟล์ที่จะนำเข้าบนเซิร์ฟเวอร์ SFTP ต้องมีไฟล์ *model.json* ไฟล์นี้กำหนด Schema ที่จะใช้สำหรับการนำเข้าข้อมูล Schema ต้องใช้ [Common Data Model](https://docs.microsoft.com/common-data-model/) เพื่อระบุการแมปฟิลด์ ตัวอย่างง่ายๆ ของไฟล์ model.json มีลักษณะดังนี้:

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>ผลการเพิ่มข้อมูล

ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab) เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลที่จะนำเข้าและการเชื่อมต่อกับเซิร์ฟเวอร์ SFTP

หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลที่มีการเพิ่มแบบกำหนดเองที่นำเข้าใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน** นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม

คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**

## <a name="next-steps"></a>ขั้นตอนถัดไป

สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ สร้าง [เซ็กเมนต์](segments.md), [การวัด](measures.md) และ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์แบบส่วนบุคคลให้กับลูกค้าของคุณ




[!INCLUDE[footer-include](../includes/footer-banner.md)]