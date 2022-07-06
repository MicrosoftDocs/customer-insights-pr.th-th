---
title: ตัวอย่างการสอบถาม OData สำหรับ Customer Insights API
description: ตัวอย่างที่ใช้กันทั่วไปของ Open Data Protocol (OData) เพื่อสอบถาม API ของ Customer Insights เพื่อตรวจสอบข้อมูล
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081999"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>ตัวอย่างการสอบถาม OData สำหรับ Customer Insights API

Open Data Protocol (OData) เป็นโปรโตคอลการเข้าถึงข้อมูลที่สร้างขึ้นบนโปรโตคอลหลัก เช่น HTTP ซึ่งใช้วิธีการที่ยอมรับกันทั่วไป เช่น REST สำหรับเว็บ มีไลบรารีและเครื่องมือหลายประเภทที่สามารถใช้เพื่อรับบริการ OData ได้

บทความนี้แสดงรายการการสอบถามตัวอย่างที่ร้องขอบ่อยครั้งเพื่อช่วยคุณในการสร้างการใช้งานของคุณเองโดยยึดตาม [API ของ Customer Insights](apis.md)

คุณต้องแก้ไขตัวอย่างการสอบถามเพื่อให้สามารถทำงานในสภาพแวดล้อมเป้าหมาย: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` ที่ {instanceId} คือ GUID ของสภาพแวดล้อม Customer Insights ที่คุณต้องการสอบถาม The [ListAllInstances operation](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) ให้คุณค้นหา {InstanceId} ที่คุณสามารถเข้าถึงได้
- {CID}: GUID ของบันทึกลูกค้าแบบรวม ตัวอย่าง: `ce759201f786d590bf2134bff576c369`
- {AlternateKey}: ตัวระบุคีย์หลักของบันทึกลูกค้าในแหล่งข้อมูล ตัวอย่าง: `CNTID_1002`
- {DSname}: สตริงที่มีชื่อเอนทิตีของแหล่งข้อมูลที่นำมาใช้กับ Customer Insights ตัวอย่าง: `Website_contacts`
- {SegmentName}: สตริงที่มีชื่อเอนทิตีเอาต์พุตของเซ็กเมนต์ใน Customer Insights ตัวอย่าง: `Male_under_40`

## <a name="customer"></a>ลูกค้า

ตารางต่อไปนี้ประกอบด้วยชุดของการสอบถามตัวอย่างสำหรับเอนทิตี *ลูกค้า*

|ชนิดการสอบถาม |ตัวอย่างเช่น  | หมายเหตุ  |
|---------|---------|---------|
|รหัสลูกค้ารายเดียว     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|คีย์สำรอง    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  คีย์สำรองยังคงอยู่ในเอนทิตีลูกค้าแบบรวม       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|ใน    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|คีย์สำรอง + ใน   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|การค้นหา  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   ส่งกลับผลลัพธ์ 10 อันดับแรกสำหรับสตริงการค้นหา      |
|การเป็นสมาชิกเซ็กเมนต์  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | ส่งกลับจำนวนแถวที่กำหนดไว้ล่วงหน้าจากเอนทิตีการแบ่งส่วน      |

## <a name="unified-activity"></a>กิจกรรมแบบรวม

ตารางต่อไปนี้ประกอบด้วยชุดของการสอบถามตัวอย่างสำหรับเอนทิตี *UnifiedActivity*

|ชนิดการสอบถาม |ตัวอย่างเช่น  | หมายเหตุ  |
|---------|---------|---------|
|กิจกรรมของ CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | แสดงรายการกิจกรรมของโปรไฟล์ลูกค้าเฉพาะ |
|กรอบเวลาของกิจกรรม    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  กิจกรรมของโปรไฟล์ลูกค้าในกรอบเวลา       |
|ประเภทกิจกรรม    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|กิจกรรมโดยชื่อที่แสดง     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|การเรียงลำดับกิจกรรม    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  เรียงกิจกรรมจากน้อยไปหามาก หรือมากไปหาน้อย       |
|กิจกรรมขยายจากการเป็นสมาชิกเซ็กเมนต์  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>ตัวอย่างอื่น

ตารางต่อไปนี้ประกอบด้วยชุดของการสอบถามตัวอย่างสำหรับเอนทิตีอื่นๆ

|ชนิดการสอบถาม |ตัวอย่างเช่น  | หมายเหตุ  |
|---------|---------|---------|
|การวัด CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|แบรนด์ของ CID ที่เพิ่มความสมบูรณ์แล้ว    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|ความสนใจ CID ที่เพิ่มความสมบูรณ์แล้ว    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|ในส่วนคำสั่ง + ขยาย     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>ไม่รองรับการสอบถามของ OData

Customer Insights ไม่รองรับการสอบถามต่อไปนี้:

- `$filter` กับเอนทิตีต้นทางที่นำเข้า คุณสามารถเรียกใช้การสอบถาม $filter กับเอนทิตีของระบบที่ Customer Insights สร้างขึ้นเท่านั้น
- `$expand` จากการสอบถาม `$search` ตัวอย่าง: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` จาก `$select` หากเลือกเฉพาะชุดย่อยของแอตทริบิวต์ ตัวอย่าง: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` แบรนด์ที่เพิ่มข้อมูลหรือความเกี่ยวข้องด้านความสนใจสำหรับลูกค้าที่กำหนด ตัวอย่าง: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- สอบถามเอนทิตีผลลัพธ์ของโมเดลการคาดคะเนผ่านคีย์สำรอง ตัวอย่าง: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
