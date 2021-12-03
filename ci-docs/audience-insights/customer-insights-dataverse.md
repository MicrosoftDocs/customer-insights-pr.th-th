---
title: ข้อมูล Customer Insights ใน Microsoft Dataverse
description: ใช้เอนทิตี Customer Insights เป็นตารางใน Microsoft Dataverse
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866957"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>ทำงานกับข้อมูล Customer Insights ใน Microsoft Dataverse

Customer Insights มีตัวเลือกในการทำให้เอนทิตีเอาต์พุตพร้อมใช้งานใน [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md) การผสานรวมนี้ช่วยให้การแบ่งปันข้อมูลและการพัฒนาแบบกำหนดเองทำได้ง่ายโดยใช้แนวทางแบบเขียนโค้ดเล็กน้อย / แบบไม่ต้องใช้โค้ด เอนทิตีเอาต์พุตจะพร้อมใช้งานเป็นตารางใน Dataverse ตารางเหล่านี้เปิดใช้งานสถานการณ์ เช่น [เวิร์กโฟลว์แบบอัตโนมัติผ่าน Power Automate](/power-automate/getting-started), [แอปแบบจำลอง](/powerapps/maker/model-driven-apps/) และ [แอปพื้นที่ทำงาน](/powerapps/maker/canvas-apps/) ผ่าน Power Apps คุณสามารถใช้ข้อมูลสำหรับแอปพลิเคชันอื่นๆ ที่อิงตามตาราง Dataverse การใช้งานปัจจุบันส่วนใหญ่สนับสนุนการค้นหา ที่ซึ่งสามารถดึงข้อมูลจากเอนทิตีข้อมูลเชิงลึกของผู้ชมที่พร้อมใช้งานสำหรับรหัสลูกค้าที่ระบุได้

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>แนบสภาพแวดล้อม Dataverse กับ Customer Insights

**องค์กรกับสภาพแวดล้อม Dataverse ที่มีอยู่**

องค์กรที่ใช้ Dataverse อยู่แล้ว สามารถ [ใช้หนึ่งในสภาพแวดล้อม Dataverse ที่มีอยู่ของพวกเขา](create-environment.md) เมื่อผู้ดูแลระบบตั้งค่าข้อมูลเชิงลึกของผู้ชม โดยการระบุ URL ไปที่สภาพแวดล้อม Dataverse ซึ่งจะแนบมากับสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชมใหม่ของพวกเขา เพื่อให้มั่นใจถึงประสิทธิภาพที่ดีที่สุด สภาพแวดล้อม Customer Insights และ Dataverse จะต้องถูกโฮสต์ในภูมิภาคเดียวกัน

**องค์กรใหม่**

หากคุณสร้างองค์กรใหม่ เมื่อตั้งค่า Customer Insights คุณจะได้รับสภาพแวดล้อม Dataverse ใหม่โดยอัตโนมัติ

> [!NOTE]
> หากองค์กรของคุณใช้ Dataverse อยู่แล้วในผู้เช่า สิ่งสำคัญคือต้องจำไว้ว่า [การสร้างสภาพแวดล้อม Dataverse ถูกควบคุมโดยผู้ดูแลระบบ](/power-platform/admin/control-environment-creation.md) ตัวอย่างเช่น หากคุณกำลังตั้งค่าสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชมใหม่ด้วยบัญชีองค์กรของคุณ และผู้ดูแลระบบได้ปิดการสร้างสภาพแวดล้อมการทดลองใช้ Dataverse สำหรับทุกคน ยกเว้นผู้ดูแลระบบ คุณไม่สามารถสร้างสภาพแวดล้อมการทดลองใช้ใหม่ได้
> 
> สภาพแวดล้อมการทดลองใช้ Dataverse ที่สร้างขึ้นใน Customer Insights มีพื้นที่เก็บข้อมูล 3 GB ซึ่งจะไม่นับรวมในความจุโดยรวมที่ให้สิทธิ์สำหรับผู้เช่า การสมัครใช้งานแบบเสียค่าบริการจะได้รับการให้สิทธิ์ Dataverse 15 GB สำหรับฐานข้อมูล และ 20 GB สำหรับที่เก็บไฟล์

## <a name="output-entities"></a>เอนทิตีเอาต์พุต

เอนทิตีเอาต์พุตบางรายการจากข้อมูลเชิงลึกของผู้ดูแลระบบ พร้อมใช้งานเป็นตารางใน Dataverse ส่วนด้านล่างอธิบาย Schema ที่คาดไว้ของตารางเหล่านี้

- [โปรไฟล์ลูกค้า](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [การเพิ่มข้อมูลแล้ว](#enrichment)
- [การคาดคะเน](#prediction)
- [การเป็นสมาชิกเซ็กเมนต์](#segment-membership)


### <a name="customerprofile"></a>โปรไฟล์ลูกค้า

ตารางนี้มีโปรไฟล์ลูกค้าแบบรวมจาก Customer Insights schema สำหรับโปรไฟล์ลูกค้าแบบรวม ขึ้นอยู่กับเอนทิตีและแอตทริบิวต์ที่ใช้ในกระบวนการรวมเข้าด้วยกัน schema โปรไฟล์ลูกค้ามักจะมีชุดย่อยของแอตทริบิวต์จาก [คำนิยาม Common Data Model ของ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)

### <a name="alternatekey"></a>AlternateKey

ตาราง AlternateKey ประกอบด้วยคีย์ของเอนทิตี ซึ่งเข้าร่วมในกระบวนการ Unify

|Column  |พิมพ์ข้อความ  |รายละเอียด  |
|---------|---------|---------|
|DataSourceName    |String         | ชื่อของแหล่งข้อมูล ตัวอย่าง: `datasource5`        |
|EntityName        | String        | ชื่อของเอนทิตีในข้อมูลเชิงลึกของผู้ชม ตัวอย่าง: `contact1`        |
|AlternateValue    |String         |รหัสแทนที่แม็ปกับรหัสลูกค้า ตัวอย่าง: `cntid_1078`         |
|KeyRing           | ข้อความแบบหลายบรรทัด        | ค่า JSON  </br> ตัวอย่าง: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|รหัสลูกค้า         | String        | ID ของโปรไฟล์ลูกค้าแบบรวม         |
|AlternateKeyId     | GUID         |  GUID เชิงกำหนดของ AlternateKey ตาม msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> ตัวอย่าง: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

ตารางนี้มีกิจกรรมโดยผู้ใช้ที่มีอยู่ใน Customer Insights

| Column            | พิมพ์ข้อความ        | รายละเอียด                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| รหัสลูกค้า        | String      | รหัสโปรไฟล์ลูกค้า                                                                      |
| ActivityId        | String      | ID ภายในของกิจกรรมของลูกค้า (คีย์หลัก)                                       |
| SourceEntityName  | String      | ชื่อเอนทิตีต้นทาง                                                                |
| SourceActivityId  | String      | คีย์หลักจากเอนทิตีต้นทาง                                                       |
| ActivityType      | String      | ชนิดกิจกรรมเชิงความหมาย หรือชื่อของกิจกรรมที่กำหนดเอง                                        |
| ActivityTimeStamp | DATETIME    | การประทับเวลาของกิจกรรม                                                                      |
| คำนำหน้าชื่อ             | String      | ชื่อเรื่องหรือชื่อกิจกรรม                                                               |
| รายละเอียด       | String      | Description ของกิจกรรม                                                                     |
| URL                | String      | ลิงก์ไปยัง URL ภายนอกที่เฉพาะเจาะจงสำหรับกิจกรรม                                         |
| SemanticData      | สตริง JSON | รวมรายการของคู่ค่าคีย์สำหรับฟิลด์การแม็ปเชิงความหมายที่เฉพาะเจาะจงสำหรับชนิดของกิจกรรม |
| RangeIndex        | String      | การประทับเวลา Unix ที่ใช้สำหรับเรียงลำดับไทม์ไลน์กิจกรรมและการสืบค้นช่วงที่มีประสิทธิภาพ |
| mydynci_unifiedactivityid   | GUID | รหัสภายในของกิจกรรมของลูกค้า (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

ตารางนี้ประกอบด้วยข้อมูลผลลัพธ์ของการวัดตามแอตทริบิวต์ของลูกค้า

| Column             | พิมพ์ข้อความ             | รายละเอียด                 |
|--------------------|------------------|-----------------------------|
| รหัสลูกค้า         | String           | รหัสโปรไฟล์ลูกค้า        |
| การวัด           | สตริง JSON      | รวมรายการของคู่ค่าคีย์สำหรับชื่อการวัดและค่าสำหรับลูกค้าที่กำหนด | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | รหัสโปรไฟล์ลูกค้า |


### <a name="enrichment"></a>การเพิ่มข้อมูลแล้ว

ตารางนี้มีผลลัพธ์ของกระบวนการเพิ่มข้อมูล

| Column               | พิมพ์ข้อความ             |  รายละเอียด                                          |
|----------------------|------------------|------------------------------------------------------|
| รหัสลูกค้า           | String           | รหัสโปรไฟล์ลูกค้า                                 |
| EnrichmentProvider   | String           | ชื่อของผู้ให้บริการสำหรับการเพิ่มข้อมูล                                  |
| EnrichmentType       | String           | ชนิดของการเพิ่มข้อมูล                                      |
| ค่า               | สตริง JSON      | รายการของแอตทริบิวต์ที่สร้างโดยกระบวนการเพิ่มข้อมูล |
| msdynci_enrichmentid | GUID             | GUID เชิงกำหนดที่สร้างจาก msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>การคาดคะเน

ตารางนี้มีผลลัพธ์ของการคาดคะเนแบบจำลอง

| Column               | พิมพ์ข้อความ        | รายละเอียด                                          |
|----------------------|-------------|------------------------------------------------------|
| รหัสลูกค้า           | String      | รหัสโปรไฟล์ลูกค้า                                  |
| ModelProvider        | String      | ชื่อของผู้ให้บริการของแบบจำลอง                                      |
| แบบจำลอง                | String      | ชื่อรูปแบบ                                                |
| ค่า               | สตริง JSON | รายการของแอตทริบิวต์ที่สร้างโดยแบบจำลอง |
| msdynci_predictionid | GUID        | GUID เชิงกำหนดที่สร้างจาก msdynci_identifier | 
| msdynci_identifier   | สตริง      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>การเป็นสมาชิกเซ็กเมนต์

ตารางนี้มีข้อมูลการเป็นสมาชิกเซ็กเมนต์ของโปรไฟล์ลูกค้า

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| รหัสลูกค้า        | สตริง       | รหัสโปรไฟล์ลูกค้า        |
| SegmentProvider      | สตริง       | แอปที่เผยแพร่เซ็กเมนต์ ค่าเริ่มต้น: ข้อมูลเชิงลึกของผู้ชม         |
| SegmentMembershipType | สตริง       | ชนิดของลูกค้าสำหรับเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์นี้ รองรับหลายชนิด เช่น ลูกค้า ผู้ติดต่อ หรือลูกค้าองค์กร ค่าเริ่มต้น: ลูกค้า  |
| เซ็กเมนต์       | สตริง JSON  | รายการเซ็กเมนต์เฉพาะที่โปรไฟล์ลูกค้าเป็นสมาชิก      |
| msdynci_identifier  | สตริง   | รหัสเฉพาะของเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์ `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID เชิงกำหนดที่สร้างจาก `msdynci_identifier`          |
