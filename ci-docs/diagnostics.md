---
title: ตรวจสอบ Dynamics 365 Customer Insights ด้วย Azure Monitor
description: เรียนรู้วิธีส่งบันทึกไปยัง Microsoft Azure Monitor
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 15ae772617efa4c64cf79d0bac10a0c3cb28ca30
ms.sourcegitcommit: a92bf5985263240fd07bad98d8e119b88cf2c9d9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/26/2022
ms.locfileid: "8807604"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>การส่งต่อบันทึกใน Dynamics 365 Customer Insights ด้วย Azure Monitor (พรีวิว)

Dynamics 365 Customer Insights มีการรวมโดยตรงกับ Azure Monitor บันทึกทรัพยากร Azure Monitor ให้คุณสามารถตรวจสอบและส่งบันทึกไปที่ [ที่เก็บข้อมูล Azure](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) หรือสตรีมไปที่ [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)

Customer Insights จะส่งบันทึกเหตุการณ์ต่อไปนี้:

- **เหตุการณ์ตรวจสอบ**
  - **APIEvent** - เปิดใช้งานการติดตามการเปลี่ยนแปลงที่ทำผ่าน Dynamics 365 Customer Insights UI
- **เหตุการณ์การดำเนินงาน**
  - **WorkflowEvent** - เวิร์กโฟลว์อนุญาตให้คุณตั้งค่า [แหล่งข้อมูล](data-sources.md), [รวม](data-unification.md), [เพิ่ม](enrichment-hub.md) และสุดท้าย [ส่งออก](export-destinations.md) ข้อมูลไปยังระบบอื่นๆ ขั้นตอนทั้งหมดเหล่านี้สามารถทำได้ทีละรายการ (เช่น ทริกเกอร์การส่งออกรายการเดียว) นอกจากนี้ยังสามารถใช้งานการประสานงาน (เช่น การรีเฟรชข้อมูลจากแหล่งข้อมูลที่ทริกเกอร์กระบวนการรวม ซึ่งจะดึงการเพิ่มความสมบูรณ์และเมื่อส่งออกข้อมูลไปยังระบบอื่นเสร็จแล้ว) สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [WorkflowEvent Schema](#workflow-event-schema)
  - **APIEvent** - การเรียก API ทั้งหมดสำหรับอินสแตนซ์ของลูกค้าไปยัง Dynamics 365 Customer Insights สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [APIEvent Schema](#api-event-schema)

## <a name="set-up-the-diagnostic-settings"></a>ตั้งค่าการตั้งค่าการวินิจฉัย

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ในการกำหนดค่าการวินิจฉัยใน Customer Insights ต้องเป็นไปตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณต้องมี [การสมัครใช้งาน Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) ที่ใช้งานอยู่
- คุณมีสิทธิ์ของ [ผู้ดูแลระบบ](permissions.md#admin) ใน Customer Insights
- คุณมีบทบาท **ผู้สนับสนุน** และ **ผู้ดูแลระบบการเข้าถึงของผู้ใช้** ในทรัพยากรปลายทางบน Azure ทรัพยากรอาจเป็นบัญชี Azure Data Lake Storage, ฮับเหตุการณ์ Azure หรือพื้นที่ทำงาน Azure Log Analytics ดูข้อมูลเพิ่มเติมที่ [เพิ่มหรือลบการกำหนดบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal) สิทธิ์นี้จำเป็นขณะกำหนดการตั้งค่าการวินิจฉัยใน Customer Insights ซึ่งสามารถเปลี่ยนแปลงได้หลังจากตั้งค่าสำเร็จ
- [ข้อกำหนดปลายทาง](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) สำหรับที่เก็บข้อมูล Azure, ฮับเหตุการณ์ Azure หรือ Azure Log Analytics
- อย่างน้อยคุณก็มีบทบาท **ผู้อ่าน** ในกลุ่มทรัพยากรที่มีทรัพยากรอยู่

### <a name="set-up-diagnostics-with-azure-monitor"></a>ตั้งค่าการวินิจฉัยด้วย Azure Monitor

1. ใน Customer Insights ให้เลือก **ระบบ** > **การวินิจฉัย** เพื่อดูปลายทางการวินิจฉัยที่กำหนดค่าอินสแตนซ์นี้

1. เลือก **เพิ่มปลายทาง**

   > [!div class="mx-imgBorder"]
   > ![การเชื่อมต่อการวินิจฉัย](media/diagnostics-pane.png "การเชื่อมต่อการวินิจฉัย")

1. ระบุชื่อในฟิลด์ **ชื่อสำหรับปลายทางการวินิจฉัย**

1. เลือก **ผู้เช่า** ของการสมัครใช้งาน Azure ด้วยทรัพยากรปลายทางและเลือก **ลงชื่อเข้าใช้**

1. เลือก **ชนิดทรัพยากร** (บัญชีที่เก็บข้อมูล, ฮับเหตุการณ์ หรือการวิเคราะห์บันทึก)

1. เลือก **การสมัครใช้งาน** สำหรับทรัพยากรปลายทาง

1. เลือก **กลุ่มทรัพยากร** สำหรับทรัพยากรปลายทาง

1. เลือก **ทรัพยากร**

1. ยืนยันคำชี้แจง **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**

1. เลือก **เชื่อมต่อกับระบบ** เพื่อเชื่อมต่อกับทรัพยากรปลายทาง บันทึกจะเริ่มปรากฏในปลายทางหลังจากผ่านไป 15 นาที หากมีการใช้งาน API และสร้างเหตุการณ์

### <a name="remove-a-destination"></a>เอาปลายทางออก

1. ไปที่ **ระบบ** > **การวินิจฉัย**

1. เลือกปลายทางการวินิจฉัยในรายการ

1. ในคอลัมน์ **การดำเนินการ** ให้เลือกไอคอน **ลบ**

1. ยืนยันการลบเพื่อหยุดการส่งต่อบันทึก ทรัพยากรในการสมัครใช้งาน Azure จะไม่ถูกลบ คุณสามารถเลือกลิงก์ในคอลัมน์ **การดำเนินการ** เพื่อเปิดพอร์ทัล Azure สำหรับทรัพยากรที่เลือกและลบออกที่นั่น

## <a name="log-categories-and-event-schemas"></a>ประเภทบันทึกและแบบแผนเหตุการณ์

ปัจจุบัน [เหตุการณ์ API](apis.md) และเหตุการณ์เวิร์กโฟลว์ได้รับการสนับสนุนและมีการใช้ประเภทและแบบแผนต่อไปนี้
แบบแผนบันทึกเป็นไปตาม [แบบแผนทั่วไปของ Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)

### <a name="categories"></a>หมวดหมู่

Customer Insights มีสองประเภท:

- **เหตุการณ์การตรวจสอบ**: [เหตุการณ์ API](#api-event-schema) เพื่อติดตามการเปลี่ยนแปลงการกำหนดค่าในบริการ การดำเนินการ `POST|PUT|DELETE|PATCH` จะอยู่ในประเภทนี้
- **เหตุการณ์การดำเนินงาน**: [เหตุการณ์ API](#api-event-schema) หรือ [เหตุการณ์เวิร์กโฟลว์](#workflow-event-schema) ที่เกิดขึ้นขณะใช้บริการ  ตัวอย่างเช่น คำขอ `GET` หรือเหตุการณ์การดำเนินการของเวิร์กโฟลว์

## <a name="configuration-on-the-destination-resource"></a>การกำหนดค่าทรัพยากรปลายทาง

ขั้นตอนต่อไปนี้จะมีการใช้โดยอัตโนมัติตามประเภททรัพยากรที่คุณเลือก:

### <a name="storage-account"></a>Storage account

บริการหลักของ Customer Insights ขอสิทธิ์ **ผู้สนับสนุนบัญชีการจัดเก็บ** สำหรับทรัพยากรที่เลือกและสร้างสองคอนเทนเนอร์ภายใต้เนมสเปซที่เลือก:

- `insight-logs-audit` ที่มี **เหตุการณ์การตรวจสอบ**
- `insight-logs-operational` ที่มี **เหตุการณ์การดำเนินงาน**

### <a name="event-hub"></a>ศูนย์กิจกรรม

บริการหลักของ Customer Insights ขอสิทธิ์ **เจ้าของข้อมูล Azure Event Hubs** สำหรับทรัพยากรและจะสร้าง Event Hubs ภายใต้เนมสเปซที่เลือก:

- `insight-logs-audit` ที่มี **เหตุการณ์การตรวจสอบ**
- `insight-logs-operational` ที่มี **เหตุการณ์การดำเนินงาน**

### <a name="log-analytics"></a>การวิเคราะห์บันทึก

บริการหลัก Customer Insights ขอสิทธิ์ **ผู้สนับสนุน Log Analytics** สำหรับทรัพยากร บันทึกจะสามารถใช้ได้ภายใต้ **บันทึก** > **ตาราง** > **การจัดการบันทึก** บนพื้นที่ทำงาน Log Analytics ที่เลือก ขยายโซลูชัน **การจัดการบันทึก** และค้นหาตาราง `CIEventsAudit` และ `CIEventsOperational`

- `CIEventsAudit` ที่มี **เหตุการณ์การตรวจสอบ**
- `CIEventsOperational` ที่มี **เหตุการณ์การดำเนินงาน**

ภายใต้หน้าต่าง **การสอบถาม** ให้ขยายโซลูชัน **การตรวจสอบ** และค้นหาตัวอย่างการสอบถามที่กำหนดโดยการค้นหา `CIEvents`

## <a name="event-schemas"></a>แบบแผนเหตุการณ์

เหตุการณ์ API และเหตุการณ์เวิร์กโฟลว์มีโครงสร้างและรายละเอียดที่เหมือนกัน ดูที่ [แบบแผนเหตุการณ์ API](#api-event-schema) หรือ [แบบแผนเหตุการณ์เวิร์กโฟลว์](#workflow-event-schema)

### <a name="api-event-schema"></a>แบบแผนเหตุการณ์ API

| เขตข้อมูล             | DataType  | บังคับ/ไม่บังคับ | Description       | ตัวอย่างเช่น        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | ประทับเวลา | ต้องมี          | ประทับเวลาของเหตุการณ์ (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | สตริง    | ต้องมี          | ResourceId ของอินสแตนซ์ที่ปล่อยเหตุการณ์         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | สตริง    | ต้องมี          | ชื่อของการดำเนินการที่แสดงโดยเหตุการณ์นี้                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | สตริง    | ต้องมี          | ประเภทบันทึกของเหตุการณ์ ไม่ว่าจะ `Operational` หรือ `Audit` คำขอ POST/PUT/PATCH/DELETE HTTP ทั้งหมดถูกแท็กด้วย `Audit` ส่วนอย่างอื่นเป็น `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | สตริง    | ต้องมี          | สถานะของเหตุการณ์ `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | สตริง    | ระบุหรือไม่ก็ได้          | สถานะผลลัพธ์ของเหตุการณ์ หากการดำเนินการสอดคล้องกับการเรียก REST API แสดงว่าเป็นรหัสสถานะ HTTP        | `200`             |
| `durationMs`      | Long      | ระบุหรือไม่ก็ได้          | ระยะเวลาของกฎของการดำเนินงานเป็นมิลลินาที     | `133`     |
| `callerIpAddress` | สตริง    | ระบุหรือไม่ก็ได้          | ที่อยู่ IP ของผู้โทร หากการดำเนินการสอดคล้องกับการเรียก API ที่มาจากที่อยู่ IP ที่เปิดเผยต่อสาธารณะ                                                 | `144.318.99.233`         |
| `identity`        | สตริง    | ระบุหรือไม่ก็ได้          | ออบเจ็กต์ JSON ที่อธิบายข้อมูลเฉพาะตัวของผู้ใช้หรือแอปพลิเคชันที่ดำเนินการ       | ดูที่ส่วน [ข้อมูลเฉพาะตัว](#identity-schema)     |  
| `properties`      | สตริง    | ระบุหรือไม่ก็ได้          | ออบเจ็กต์ JSON ที่มีคุณสมบัติเพิ่มเติมสำหรับประเภทเหตุการณ์เฉพาะ      | ดูที่ส่วน [คุณสมบัติ](#api-properties-schema)    |
| `level`           | สตริง    | ต้องมี          | ระดับความรุนแรงของเหตุการณ์    | `Informational`, `Warning`, `Error` หรือ `Critical`           |
| `uri`             | สตริง    | ระบุหรือไม่ก็ได้          | URI คำขอแบบสัมบูรณ์    |               |

#### <a name="identity-schema"></a>แบบแผนข้อมูลเฉพาะตัว

ออบเจ็กต์ `identity` JSON มีโครงสร้างต่อไปนี้

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| เขตข้อมูล                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | บทบาทที่กำหนดสำหรับผู้ใช้หรือแอป ดูข้อมูลเพิ่มเติมที่ [สิทธิ์ของผู้ใช้](permissions.md)                                     |
| `Authorization.RequiredRoles` | บทบาทที่จำเป็นในการดำเนินการ บทบาท `Admin` ได้รับอนุญาตให้ดำเนินการทั้งหมด                                                    |
| `Claims`                      | การอ้างสิทธิ์ของผู้ใช้หรือ JSON Web Token (JWT) ของแอป คุณสมบัติการอ้างสิทธิ์แตกต่างกันไปตามองค์กรและการกำหนดค่า Azure Active Directory |

#### <a name="api-properties-schema"></a>แบบแผนคุณสมบัติ API

[เหตุการณ์ API](apis.md) มีคุณสมบัติดังต่อไปนี้

| เขตข้อมูล                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | `ApiEvent` เสมอเมื่อทำเครื่องหมายเหตุการณ์บันทึกเป็นเหตุการณ์ API                                                                 |
| `properties.userAgent`       | เอเจนต์ของเบราว์เซอร์ที่ส่งคำขอหรือ `unknown`                                                                        |
| `properties.method`          | วิธีการ HTTP: `GET/POST/PUT/PATCH/HEAD`                                                                                |
| `properties.path`            | เส้นทางสัมพัทธ์ของคำขอ                                                                                          |
| `properties.origin`          | URI ที่ระบุว่าการดึงข้อมูลมาจากที่ใดหรือ `unknown`                                                                  |
| `properties.operationStatus` | `Success` สำหรับรหัสสถานะ HTTP < 400 <br> `ClientError` สำหรับรหัสสถานะ HTTP < 500 <br> `Error` สำหรับสถานะ HTTP >= 500 |
| `properties.tenantId`        | รหัสองค์กร                                                                                                        |
| `properties.tenantName`      | ชื่อขององค์กร                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId ของผู้โทร                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>แบบแผนเหตุการณ์เวิร์กโฟลว์

เวิร์กโฟลว์ประกอบด้วยหลายขั้นตอน [นำเข้าแหล่งข้อมูล](data-sources.md), [รวม](data-unification.md), [เพิ่ม](enrichment-hub.md) และ [ส่งออก](export-destinations.md) ข้อมูล ขั้นตอนทั้งหมดเหล่านี้สามารถเรียกใช้ทีละรายการหรือประสานงานกับกระบวนการต่อไปนี้

#### <a name="operation-types"></a>ชนิดการดำเนินงาน

| ชนิดของการดำเนินการ     | กลุ่ม                                     |
| ----------------- | ----------------------------------------- |
| การนำเข้า         | [แหล่งข้อมูล](data-sources.md)           |
| DataPreparation   | [แหล่งข้อมูล](data-sources.md)           |
| แมป               | [การรวมข้อมูล](data-unification.md)   |
| Match             | [การรวมข้อมูล](data-unification.md)   |
| ผสาน             | [การรวมข้อมูล](data-unification.md)   |
| ProfileStore      | [โปรไฟล์ลูกค้า](customer-profiles.md) |
| การค้นหา            | [โปรไฟล์ลูกค้า](customer-profiles.md) |
| กิจกรรม          | [กิจกรรม](activities.md)                  |
| AttributeMeasures | [เซ็กเมนต์และการวัด](segments.md)      |
| EntityMeasures    | [เซ็กเมนต์และการวัด](segments.md)      |
| การวัด          | [เซ็กเมนต์และการวัด](segments.md)      |
| การแบ่งเซ็กเมนต์      | [เซ็กเมนต์และการวัด](segments.md)      |
| การเพิ่มข้อมูลแล้ว        | [การเพิ่มข้อมูลแล้ว](enrichment-hub.md)                                          |
| ระบบอัจฉริยะ      | [การคาดคะเน](predictions-overview.md)                                          |
| AiBuilder         | [การคาดคะเน](predictions-overview.md)                                          |
| ข้อมูลเชิงลึก          | [การคาดคะเน](predictions-overview.md)                                          |
| Export            | [การส่งออก](export-destinations.md)                                          |
| ModelManagement   | [การคาดคะเน](custom-models.md)                                           |
| ความสัมพันธ์      | [การรวมข้อมูล](relationships.md)                                           |

#### <a name="field-description"></a>คำอธิบายฟิลด์

| เขตข้อมูล           | DataType  | บังคับ/ไม่บังคับ | Description                                                                                                                                                   | ตัวอย่างเช่น                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | ประทับเวลา | ต้องมี          | ประทับเวลาของเหตุการณ์ (UTC)                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | สตริง    | ต้องมี          | ResourceId ของอินสแตนซ์ที่ปล่อยเหตุการณ์                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | สตริง    | ต้องมี          | ชื่อของการดำเนินการที่แสดงโดยเหตุการณ์นี้ `{OperationType}.[WorkFlow|Task][Started|Completed]` ดู [ชนิดการดำเนินงาน](#operation-types) สำหรับการอ้างอิง | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | สตริง    | ต้องมี          | ประเภทบันทึกของเหตุการณ์ `Operational` เสมอสำหรับเหตุการณ์เวิร์กโฟลว์                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | สตริง    | ต้องมี          | สถานะของเหตุการณ์ `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | ระบุหรือไม่ก็ได้          | ระยะเวลาของกฎของการดำเนินงานเป็นมิลลินาที                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | สตริง    | ระบุหรือไม่ก็ได้          | ออบเจ็กต์ JSON ที่มีคุณสมบัติเพิ่มเติมสำหรับประเภทเหตุการณ์เฉพาะ                                                                                        | ดูส่วนย่อย [คุณสมบัติเวิร์กโฟลว์](#workflow-properties-schema)                                                                                                       |
| `level`         | สตริง    | ต้องมี          | ระดับความรุนแรงของเหตุการณ์                                                                                                                                  | `Informational`, `Warning` หรือ `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>แบบแผนคุณสมบัติเวิร์กโฟลว์

เหตุการณ์เวิร์กโฟลว์มีคุณสมบัติดังต่อไปนี้

| เขตข้อมูล              | Workflow | งาน | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | ตกลง      | ตกลง  | `WorkflowEvent` เสมอเมื่อทำเครื่องหมายเหตุการณ์บันทึกเป็นเหตุการณ์เวิร์กโฟลว์                                                                                                                                                                                                |
| `properties.workflowJobId`                   | ตกลง      | ตกลง  | ตัวระบุของการเรียกใช้เวิร์กโฟลว์ เหตุการณ์เวิร์กโฟลว์และงานทั้งหมดภายในการดำเนินการเวิร์กโฟลว์มี `workflowJobId` เหมือนกัน                                                                                                                                   |
| `properties.operationType`                   | ตกลง      | ตกลง  | ตัวระบุของการดำเนินงาน ดูที่ [ชนิดการดำเนินงาน](#operation-types)                                                                                                                                                                               |
| `properties.tasksCount`                      | ตกลง      | ไม่   | เวิร์กโฟลว์เท่านั้น จํานวนของงานที่เวิร์กโฟลว์ทริกเกอร์                                                                                                                                                                                                       |
| `properties.submittedBy`                     | ตกลง      | ไม่   | เลือกได้ เหตุการณ์เวิร์กโฟลว์เท่านั้น Azure Active Directory [objectId ของผู้ใช้](/azure/marketplace/find-tenant-object-id#find-user-object-id) ที่ทริกเกอร์เวิร์กโฟลว์ ดูเพิ่มเติมที่ `properties.workflowSubmissionKind`                                   |
| `properties.workflowType`                    | ตกลง      | ไม่   | การรีเฟรชแบบ `full` หรือ `incremental`                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | ตกลง      | ไม่   | `OnDemand` หรือ`Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | ตกลง      | ไม่   | `Running` หรือ `Successful`                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | ตกลง      | ตกลง  | ประทับเวลา UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | ตกลง      | ตกลง  | ประทับเวลา UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | ตกลง      | ตกลง  | ประทับเวลา UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | ตกลง      | ตกลง  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | ไม่       | ตกลง  | - สำหรับ OperationType = `Export` ตัวระบุเป็น GUID ของการกำหนดค่าการส่งออก <br> - สำหรับ OperationType = `Enrichment` เป็น GUID ของการเพิ่มความสมบูรณ์ <br> - สำหรับ OperationType `Measures` และ `Segmentation` ตัวระบุคือชื่อเอนทิตี |
| `properties.friendlyName`                    | ไม่       | ตกลง  | ชื่อที่จำได้ง่ายของการส่งออกหรือเอนทิตีที่ประมวลผล                                                                                                                                                                                           |
| `properties.error`                           | ไม่       | ตกลง  | เลือกได้ ข้อความแสดงข้อผิดพลาดที่มีรายละเอียดเพิ่มเติม                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | ไม่       | ตกลง  | เลือกได้ สำหรับ OperationType `Export` เท่านั้น ระบุชนิดของการส่งออก ดูข้อมูลเพิ่มเติมที่ [ภาพรวมของปลายทางการส่งออก](export-destinations.md)                                                                                          |
| `properties.additionalInfo.AffectedEntities` | ไม่       | ตกลง  | เลือกได้ สำหรับ OperationType `Export` เท่านั้น ประกอบด้วยรายการของเอนทิตีที่กำหนดค่าไว้ในการส่งออก                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | ไม่       | ตกลง  | เลือกได้ สำหรับ OperationType `Export` เท่านั้น ข้อความโดยละเอียดสำหรับการส่งออก                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | ไม่       | ตกลง  | เลือกได้ สำหรับ OperationType `Segmentation` เท่านั้น ระบุจำนวนสมาชิกทั้งหมดที่เซ็กเมนต์มี                                                                                                                                                    |
