---
title: Schema เอนทิตี Customer Insights ใน Common Data Model
description: ทำงานกับเอนทิตีใน Common Data Model
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596384"
---
# <a name="entity-schemas-in-common-data-model"></a>Schema เอนทิตีใน Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) เป็นข้อมูลจำเพาะสำหรับประกาศ และคำนิยามของเอนทิตีมาตรฐาน ที่แสดงถึงแนวคิดและกิจกรรมที่ใช้กันทั่วไปในธุรกิจและโปรแกรมประยุกต์ประสิทธิภาพ โมเดลนี้ถูกขยายไปยังข้อมูลเชิงสังเกตการณ์และเชิงวิเคราะห์ด้วย Common Data Model ให้เอนทิตีธุรกิจที่ กำหนดไว้อย่างดี มีส่วนจำเพาะ และสามารถขยายได้ เช่น บัญชี หน่ายทางธุรกิจ กรณี ที่ติดต่อ ลูกค้าเป้าหมาย โอกาส และผลิตภัณฑ์ รวมถึงการปฏิสัมพันธ์ผู้ขาย พนักงาน และลูกค้า เช่น กิจกรรมและข้อตกลงระดับบริการ ทุกคนสามารถสร้างและขยายคำจำกัดความ Common Data Model เพื่อบันทึกแนวคิดเฉพาะทางธุรกิจเพิ่มเติม

โมเดลข้อมูลที่ใช้ร่วมกันนี้อนุญาตให้แอปพลิเคชันและผู้รวบรวมข้อมูลสามารถทำงานร่วมกันได้ง่ายขึ้น โดยการให้คำจำกัดความของข้อมูลแบบรวม Common Data Model มีระบบข้อมูลเมตาที่อุดมไปด้วยเอนทิตีมาตรฐาน ความสัมพันธ์ ลำดับชั้น ลักษณะ และอื่น ๆ มีที่มาจากแอป Dynamics 365 และเป็นแหล่งที่มาแบบเปิดบน GitHub ที่มีเอนทิตีมาตรฐานมากกว่า 260 รายการ ระบบขนาดใหญ่ของคู่ค้าภายในและภายนอกสนับสนุนแนวคิดเฉพาะอุตสาหกรรมให้กับ Common Data Model

มีหลายระบบและแพลตฟอร์มที่ใช้ Common Data Model ในวันนี้ รวมถึงการรับส่งข้อมูล Power BI และ Azure Data Services ได้รับการสนับสนุนใน Common Data Service, Dynamics 365 Power Apps, Power BI และบริการข้อมูล Azure ที่กำลังจะมาถึง อย่างโดยตรงกับค่าค้างรับของ [Open Data Initiative](https://www.microsoft.com/open-data-initiative)

## <a name="customer-insights-entity-schemas"></a>Schema เอนทิตีของ Customer Insights

ในการสร้างมุมมอง 360 องศาของลูกค้า และสร้างโมเดล Customer Insights ให้พร้อมใช้งานใน Common Data Model เพื่อการขยาย เราได้เผยแพร่ schema เอนทิตีต่อไปนี้:

| เอนทิตี | คำอธิบาย |
|---------|---------|
|[กิจกรรมของลูกค้า](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | กิจกรรมที่ดำเนินการโดยผู้ใช้ที่มีมูลค่าเชิงธุรกิจที่สังเกตได้ |
|[โปรไฟล์ลูกค้า](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | บุคคลหรือองค์กรที่ดำเนินการ หรือมีศักยภาพที่จะมีส่วนร่วมในกิจกรรมทางธุรกิจ |
|[ข้อกำหนดการวัด](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | คำจำกัดความของ KPI ที่แบ่งพาร์ติชันด้วยมิติที่เป็นศูนย์หรือมากกว่า (เช่น ผู้ใช้งานรายเดือน ยอดการใช้จ่ายโดยลูกค้า ค่าใช้จ่ายในการจัดหาลูกค้าเฉลี่ย) |
|[เซ็กเมนต์](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | กำหนดกลุ่มสมาชิกที่มีลักษณะทั่วไป |
|[สมาชิกเซ็กเมนต์](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | สมาชิกที่เข้าร่วมในเซ็กเมนต์ที่กำหนด |

สำหรับข้อมูลเพิ่มเติม โปรดดูเอกสารประกอบเกี่ยวกับ [Schema เอนทิตีของ Customer Insights ใน Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>ดูเอนทิตีโดยใช้ Common Data Model Entity Navigator

คุณสามารถดูเอนทิตีใน [ตัวนำทางเอนทิตี Common Data Model](https://microsoft.github.io/CDM/) เลือก **โหลดจาก GitHub!** ปุ่มและนำทางไปที่ **foundationCommon** > **crmCommon** > **โซลูชัน** > **customerInsights** ที่คุณจะพบรายการเอนทิตีของ Customer Insights และคำจำกัดความของรายการ
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator แสดงเอนทิตี CustomerActivity](media/CDM-entity-navigator.png "CDM Entity Navigator แสดงเอนทิตี CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]