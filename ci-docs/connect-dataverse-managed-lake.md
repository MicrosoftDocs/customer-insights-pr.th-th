---
title: เชื่อมต่อกับข้อมูลในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse
description: นำเข้าข้อมูลจากที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609874"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>เชื่อมต่อกับข้อมูลในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse

ผู้ใช้ Microsoft Dataverse สามารถเชื่อมต่อกับเอนทิตีการวิเคราะห์ในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse ได้อย่างรวดเร็ว แหล่งข้อมูลของสภาพแวดล้อมเดียวเท่านั้นที่สามารถใช้ที่จัดเก็บที่มีการจัดการของ Dataverse เดียวกันพร้อมกันได้

> [!NOTE]
> คุณต้องเป็นผู้ดูแลระบบในองค์กร Dataverse เพื่อดำเนินการและดูรายชื่อของเอนทิตีที่มีอยู่ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- ข้อมูลที่เก็บไว้ในบริการออนไลน์ เช่น Azure Data Lake Storage อาจถูกเก็บไว้ในตำแหน่งที่แตกต่างจากที่ที่มีการประมวลผลหรือจัดเก็บข้อมูลใน Dynamics 365 Customer Insights การนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ หมายถึงคุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)

- มองเห็นได้เฉพาะเอนทิตี Dataverse ที่เปิดใช้งาน [การติดตามการเปลี่ยนแปลง](/power-platform/admin/enable-change-tracking-control-data-synchronization) เท่านั้น เอนทิตีเหล่านี้สามารถส่งออกไปยังที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Dataverse และใช้ใน Customer Insights ตาราง Dataverse แบบสำเร็จูปมีการเปิดใช้งานการติดตามการเปลี่ยนแปลงตามค่าเริ่มต้น คุณต้องเปิดการติดตามการเปลี่ยนแปลงสำหรับตารางที่กำหนดเอง การตรวจสอบว่าตาราง Dataverse เปิดใช้งานการติดตามการเปลี่ยนแปลงหรือไม่ ไปที่ [Power Apps](https://make.powerapps.com) > **ข้อมูล** > **ตาราง** ค้นหาตารางที่คุณสนใจและเลือก ไปที่ **การตั้งค่า** > **ตัวเลือกขั้นสูง** และตรวจสอบการตั้งค่า **ติดตามการเปลี่ยนแปลง**

## <a name="connect-to-a-dataverse-managed-lake"></a>เชื่อมต่อกับที่จัดเก็บที่มีการจัดการของ Dataverse

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. เลือก **เพิ่มแหล่งข้อมูล**

1. เลือก **Microsoft Dataverse**

1. ป้อน **ชื่อ** สำหรับแหล่งข้อมูลและ **คำอธิบาย** ที่ระบุหรือไม่ก็ได้

1. ระบุ **ที่อยู่เซิฟเวอร์** สำหรับองค์กร Dataverse และเลือก **ลงชื่อเข้าใช้**

1. เลือกตารางที่คุณต้องการรับเข้าเป็นเอนทิตีใน Customer Insights จากรายการที่มีอยู่

   > [!NOTE]
   > หากมีการเลือกบางตารางไว้อยู่แล้ว แอปพลิเคชัน Dynamics 365 อื่นๆ อาจใช้ตารางเหล่านั้น (เช่น Dynamics 365 Sales Insights หรือ Customer Service Insights) คุณไม่สามารถเปลี่ยนการเลือก ตารางเหล่านี้จะสามารถใช้งานเป็นเอนทิตีเมื่อสร้างแหล่งข้อมูลแล้ว

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="กล่องโต้ตอบที่แสดงรายการเอนทิตีในสภาพแวดล้อม Dataverse":::

1. บันทึกการเลือกของคุณเพื่อเริ่มการซิงค์ตารางที่เลือกจาก Dataverse คุณจะพบการเชื่อมต่อที่เพิ่งเพิ่มเข้าไปในหน้า **แหล่งข้อมูล** ระบบจะจัดคิวเพื่อรีเฟรชและแสดงจำนวนเอนทิตีเป็น 0 จนกว่าตารางที่เลือกทั้งหมดจะถูกซิงค์

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

การโหลดข้อมูลอาจต้องใช้เวลา หลังจากการรีเฟรชที่สำเร็จ จะสามารถตรวจสอบข้อมูลที่ถูกนำไปใช้ได้จากหน้า [**เอนทิตี**](entities.md)

## <a name="edit-a-dataverse-managed-lake-data-source"></a>แก้ไขแหล่งข้อมูลที่จัดเก็บที่มีการจัดการของ Dataverse

คุณแก้ไขการเลือกเอนทิตีหลังจากสร้างแหล่งข้อมูลเท่านั้น ตัวอย่างเช่น หากมีการเพิ่มเอนทิตีเพิ่มเติมใน Dataverse และคุณต้องการนำเข้าด้วยเช่นกัน
หากต้องการเชื่อมต่อกับ Dataverse Data Lake อื่นๆ ให้ [สร้างแหล่งข้อมูลใหม่](#connect-to-a-dataverse-managed-lake)

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. ข้างแหล่งข้อมูลที่คุณต้องการปรับปรุง ให้เลือก **แก้ไข**

1. เลือกเอนทิตีเพิ่มเติมจากรายการเอนทิตีที่มีอยู่

1. คลิก **บันทึก** เพื่อใช้การเปลี่ยนแปลงของคุณและกลับไปที่หน้า **แหล่งข้อมูล**

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>สาเหตุทั่วไปของข้อผิดพลาดในการนำเข้าหรือข้อมูลที่เสียหาย

การตรวจสอบต่อไปนี้จะทำงานกับข้อมูลที่นำเข้าเพื่อแสดงเรกคอร์ดที่เสียหาย:

- ค่าของฟิลด์ไม่ตรงกับชนิดข้อมูลของคอลัมน์
- ฟิลด์มีอักขระที่ทำให้คอลัมน์ไม่ตรงกับ Schema ที่คาดไว้ ตัวอย่างเช่น: เครื่องหมายคำพูดที่มีรูปแบบไม่ถูกต้อง เครื่องหมายคำพูดที่ไม่ใช้ Escape หรืออักขระขึ้นบรรทัดใหม่
- หากมีคอลัมน์ datetime/date/datetimeoffset จะต้องระบุรูปแบบในโมเดลหากไม่เป็นไปตามรูปแบบ ISO มาตรฐาน

### <a name="schema-or-data-type-mismatch"></a>สคีมาหรือชนิดข้อมูลไม่ตรงกัน

หากข้อมูลไม่เป็นไปตามสคีมา เรกคอร์ดจะถูกจัดประเภทว่าเสียหาย แก้ไขแหล่งข้อมูลหรือสคีมาและนำเข้าข้อมูลอีกครั้ง

### <a name="datetime-fields-in-the-wrong-format"></a>ฟิลด์วันที่เวลาอยู่ในรูปแบบที่ไม่ถูกต้อง

ฟิลด์วันที่และเวลาในเอนทิตีไม่อยู่ในรูปแบบ ISO หรือ en-US รูปแบบวันที่และเวลาเริ่มต้นใน Customer Insights คือรูปแบบ en-US ฟิลด์วันที่และเวลาทั้งหมดในเอนทิตีควรอยู่ในรูปแบบเดียวกัน Customer Insights รองรับรูปแบบอื่นๆ ที่ให้คำอธิบายประกอบหรือคุณลักษณะที่ระดับแหล่งที่มาหรือเอนทิตีในโมเดลหรือ manifest.json ตัวอย่างเช่น

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  ใน manifest.json สามารถระบุรูปแบบวันที่และเวลาได้ที่ระดับเอนทิตีหรือที่ระดับแอตทริบิวต์ ที่ระดับเอนทิตี ใช้ "exhibitsTraits" ในเอนทิตีใน *.manifest.cdm.json เพื่อกำหนดรูปแบบวันที่และเวลา ที่ระดับแอตทริบิวต์ ใช้ "appliedTraits" ในแอตทริบิวต์ใน entityname.cdm.json

**Manifest.json ที่ระดับเอนทิตี**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json ที่ระดับแอตทริบิวต์**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
