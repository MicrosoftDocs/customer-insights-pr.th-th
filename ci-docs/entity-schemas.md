---
title: Schema เอนทิตีใน Common Data Model
description: ทำงานกับเอนทิตีใน Common Data Model
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 92d37fc0950fefcb5c2a5d26214a469d3693980d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054777"
---
# <a name="entity-schemas-in-common-data-model"></a>Schema เอนทิตีใน Common Data Model

[Common Data Model](/common-data-model/) เป็นข้อมูลจำเพาะสำหรับประกาศ และคำนิยามของเอนทิตีมาตรฐาน ที่แสดงถึงแนวคิดและกิจกรรมที่ใช้กันทั่วไปในธุรกิจและโปรแกรมประยุกต์ประสิทธิภาพ โมเดลนี้ถูกขยายไปยังข้อมูลเชิงสังเกตการณ์และเชิงวิเคราะห์ด้วย Common Data Model ให้เอนทิตีธุรกิจที่ กำหนดไว้อย่างดี มีส่วนจำเพาะ และสามารถขยายได้ เช่น บัญชี หน่ายทางธุรกิจ กรณี ที่ติดต่อ ลูกค้าเป้าหมาย โอกาส และผลิตภัณฑ์ รวมถึงการปฏิสัมพันธ์ผู้ขาย พนักงาน และลูกค้า เช่น กิจกรรมและข้อตกลงระดับบริการ ทุกคนสามารถสร้างและขยายคำจำกัดความ Common Data Model เพื่อบันทึกแนวคิดเฉพาะทางธุรกิจเพิ่มเติม

โมเดลข้อมูลที่ใช้ร่วมกันนี้อนุญาตให้แอปพลิเคชันและผู้รวบรวมข้อมูลสามารถทำงานร่วมกันได้ง่ายขึ้น โดยการให้คำจำกัดความของข้อมูลแบบรวม Common Data Model มีระบบข้อมูลเมตาที่อุดมไปด้วยเอนทิตีมาตรฐาน ความสัมพันธ์ ลำดับชั้น ลักษณะ และอื่น ๆ มีที่มาจากแอป Dynamics 365 และเป็นแหล่งที่มาแบบเปิดบน GitHub ที่มีเอนทิตีมาตรฐานมากกว่า 260 รายการ ระบบขนาดใหญ่ของคู่ค้าภายในและภายนอกสนับสนุนแนวคิดเฉพาะอุตสาหกรรมให้กับ Common Data Model

หลายระบบและแพลตฟอร์มต่างๆ ใช้ Common Data Model ในวันนี้ รวมถึงโฟลว์ข้อมูล Power BI และ Azure Data Services ซึ่งได้รับการสนับสนุนอยู่แล้วใน Microsoft Dataverse, Dynamics 365, Power Apps, Power BI และบริการข้อมูล Azure ที่กำลังจะเกิดขึ้น ซึ่งสร้างมูลค่าโดยตรงต่อ [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/)

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

คุณสามารถดูเอนทิตีใน [ตัวนำทางเอนทิตี Common Data Model](https://microsoft.github.io/CDM/) เลือกเอนทิตีจากส่วนแอปพลิเคชันข้อมูลเชิงลึกเพื่อรับรายการของเอนทิตี Customer Insights และคำจำกัดความ
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator แสดงเอนทิตี CustomerActivity](media/CDM-entity-navigator.png "CDM Entity Navigator แสดงเอนทิตี CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
