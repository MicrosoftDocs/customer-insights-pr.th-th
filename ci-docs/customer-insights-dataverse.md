---
title: ทำงานกับข้อมูล Customer Insights ใน Microsoft Dataverse
description: เรียนรู้วิธีการเชื่อมต่อ Customer Insights กับ Microsoft Dataverse และทำความเข้าใจเอนทิตีผลลัพธ์ที่ส่งออกไปยัง Dataverse
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833699"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>ทำงานกับข้อมูล Customer Insights ใน Microsoft Dataverse

Customer Insights มีตัวเลือกในการทำให้เอนทิตีผลลัพธ์สามารถใช้งานเป็น [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) การผสานรวมนี้ช่วยให้การแบ่งปันข้อมูลและการพัฒนาแบบกำหนดเองทำได้ง่ายโดยใช้แนวทางแบบเขียนโค้ดเล็กน้อย/แบบไม่ต้องใช้โค้ด [เอนทิตีผลลัพธ์](#output-entities) มีเป็นตารางในสภาพแวดล้อม Dataverse คุณสามารถใช้ข้อมูลนี้สำหรับแอปพลิเคชันอื่นตามตาราง Dataverse ตารางเหล่านี้เปิดใช้งานสถานการณ์ เช่น เวิร์กโฟลว์อัตโนมัติผ่าน Power Automate หรือการสร้างแอปด้วย Power Apps

การเชื่อมต่อกับสภาพแวดล้อม Dataverse ของคุณยังช่วยให้คุณสามารถ [นำเข้าข้อมูลจากแหล่งข้อมูลในสถานที่โดยใช้กระแสข้อมูล Power Platform และเกตเวย์](data-sources.md#add-data-from-on-premises-data-sources)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สภาพแวดล้อม Customer Insights และ Dataverse ต้องโฮสต์อยู่ในภูมิภาคเดียวกัน
- คุณต้องมีบทบาทผู้ดูแลระบบส่วนกลางในสภาพแวดล้อม Dataverse ตรวจสอบว่า [สภาพแวดล้อม Dataverse เชื่อมโยง](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) กับกลุ่มความปลอดภัยที่กำหนดหรือไม่ และตรวจสอบว่าคุณได้เพิ่มสภาพแวดล้อมลงในกลุ่มความปลอดภัยเหล่านั้นแล้ว
- ไม่มีสภาพแวดล้อม Customer Insights อื่นเชื่อมโยงกับสภาพแวดล้อม Dataverse ที่คุณต้องการเชื่อมต่อ เรียนรู้วิธีการ [ลบการเชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่](#remove-an-existing-connection-to-a-dataverse-environment)
- สภาพแวดล้อม Microsoft Dataverse สามารถเชื่อมต่อกับบัญชีที่เก็บข้อมูลเดียวเท่านั้น ใช้เฉพาะเมื่อคุณกำหนดค่าสภาพแวดล้อมที่จะ [ใช้ Azure Data Lake Storage ของคุณ](own-data-lake-storage.md)

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>เชื่อมต่อสภาพแวดล้อม Dataverse กับ Customer Insights

ขั้นตอน **Microsoft Dataverse** ช่วยให้คุณเชื่อมต่อ Customer Insights กับสภาพแวดล้อม Dataverse ขณะที่ [สร้างสภาพแวดล้อม Customer Insights](create-environment.md)

:::image type="content" source="media/dataverse-provisioning.png" alt-text="การแชร์ข้อมูลกับ Microsoft Dataverse ที่เปิดใช้งานอัตโนมัติสำหรับสภาพแวดล้อมใหม่ทั้งหมด":::

ผู้ดูแลระบบสามารถกำหนดค่า Customer Insights ให้เชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่ การระบุ URL ไปยังสภาพแวดล้อม Dataverse โดยแนบกับสภาพแวดล้อม Customer Insights ใหม่ของพวกเขา

หากคุณไม่ต้องการใช้สภาพแวดล้อม Dataverse ที่มีอยู่ ระบบจะสร้างสภาพแวดล้อมใหม่สำหรับข้อมูล Customer Insights ในผู้เช่าของคุณ [ผู้ดูแลระบบ Power Platform สามารถควบคุมว่าบุคคลใดที่สามารถสร้างสภาพแวดล้อม](/power-platform/admin/control-environment-creation) เมื่อคุณกำลังตั้งค่าสภาพแวดล้อม Customer Insights ใหม่และผู้ดูแลระบบได้ปิดใช้งานการสร้างสภาพแวดล้อม Dataverse สำหรับทุกคนยกเว้นผู้ดูแลระบบ คุณอาจไม่สามารถสร้างสภาพแวดล้อมใหม่ได้

**เปิดใช้งานการแชร์ข้อมูล** กับ Dataverse โดยเลือกกล่องกาเครื่องหมายการแชร์ข้อมูล

หากคุณใช้บัญชี Data Lake Storage ของคุณเอง คุณต้องมี **ตัวระบุสิทธิ์** ด้วย สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการรับตัวระบุสิทธิ์ ให้อ่านส่วนต่อไปนี้

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>เปิดใช้งานการแชร์ข้อมูลกับ Dataverse จาก Azure Data Lake Storage ของคุณเอง (พรีวิว)

การเปิดใช้งานการแชร์ข้อมูลกับ Microsoft Dataverse เมื่อสภาพแวดล้อมของคุณ [ใช้บัญชี Azure Data Lake Storage ของคุณเอง](own-data-lake-storage.md) ต้องมีการกำหนดค่าเพิ่มเติมบางอย่าง ผู้ใช้ที่ตั้งค่าสภาพแวดล้อม Customer Insights ต้องมีสิทธิ์ **ผู้อ่านข้อมูลของ Blob ในที่เก็บข้อมูล** เป็นอย่างน้อยสำหรับคอนเทนเนอร์ *CustomerInsights* ในบัญชี Azure Data Lake Storage

1. สร้างกลุ่มความปลอดภัยสองกลุ่มในการสมัครใช้งาน Azure ของคุณ กลุ่มหนึ่งคือ กลุ่มความปลอดภัย **ผู้อ่าน** และอีกกลุ่มคือ **ผู้มีส่วนร่วม** และตั้งค่าบริการ Microsoft Dataverse ในฐานะเจ้าของกลุ่มความปลอดภัยทั้งสองกลุ่ม
2. จัดการรายการตัวควบคุมการเข้าถึง (ACL) บนคอนเทนเนอร์ CustomerInsights ในบัญชีที่เก็บข้อมูลของคุณผ่านกลุ่มความปลอดภัยเหล่านี้ เพิ่มบริการ Microsoft Dataverse และแอปพลิเคชันทางธุรกิจบน Dataverse  ใดๆ เช่น Dynamics 365 Marketing ไปยังกลุ่มความปลอดภัย **ผู้อ่าน** ด้วยสิทธิ์การใช้งาน **อ่านอย่างเดียว** เพิ่ม *เฉพาะ* แอปพลิเคชัน Customers Insights ไปยังกลุ่มความปลอดภัย **ผู้มีส่วนร่วม** เพื่อให้ทั้งสิทธิ์การใช้งาน **อ่านและเขียน** ในการเขียนโปรไฟล์และข้อมูลเชิงลึก

### <a name="limitations"></a>ข้อจำกัด

มีข้อจำกัดสองประการเมื่อใช้ Dataverse กับบัญชี Azure Data Lake Storage ของคุณเอง:

- มีการแมปแบบหนึ่งต่อหนึ่งระหว่างองค์กร Dataverse กับบัญชี Azure Data Lake Storage เมื่อองค์กร Dataverse เชื่อมต่อกับบัญชีที่เก็บข้อมูล องค์กรจะไม่สามารถเชื่อมต่อกับบัญชีที่เก็บข้อมูลอื่นได้ ข้อจำกัดนี้ป้องกันไม่ให้ Dataverse เติมข้อมูลในบัญชีที่เก็บข้อมูลหลายบัญชี
- การแชร์ข้อมูลจะไม่ทำงานหากจำเป็นต้องตั้งค่า Azure Private Link เพื่อเข้าถึงบัญชี Azure Data Lake Storage เนื่องจากอยู่หลังไฟร์วอลล์ ขณะนี้ Dataverse ไม่รองรับการเชื่อมต่อกับตำแหน่งข้อมูลส่วนตัวผ่าน Private Link

### <a name="set-up-powershell"></a>ตั้งค่า PowerShell

ในการประมวลผลสคริปต์ PowerShell คุณต้องตั้งค่า PowerShell ตามนั้น

1. ติดตั้งเวอร์ชันล่าสุดของ [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. บนพีซีของคุณ เลือกคีย์ Windows บนแป้นพิมพ์ และค้นหา **Windows PowerShell** และเลือก **เรียกใช้เป็นผู้ดูแลระบบ**
   1. ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`
2. นำเข้าสามโมดูล
    1. ในหน้าต่าง PowerShell ให้ป้อน `Install-Module -Name Az.Accounts` และปฏิบัติตามขั้นตอน
    1. ทำซ้ำสำหรับ `Install-Module -Name Az.Resources` และ `Install-Module -Name Az.Storage`

### <a name="configuration-steps"></a>กำหนดค่าขั้นตอน

1. ดาวน์โหลดสคริปต์ PowerShell สองชุดที่คุณต้องเรียกใช้จาก [GitHub repo](https://github.com/trin-msft/byol) ของวิศวกรของเรา
    1. `CreateSecurityGroups.ps1`
       - คุณต้องมีสิทธิ์ *ผู้ดูแลระบบผู้เช่า* เพื่อเรียกใช้สคริปต์ PowerShell นี้
       - สคริปต์ PowerShell นี้สร้างกลุ่มความปลอดภัยสองกลุ่มในการสมัครใช้งาน Azure ของคุณ กลุ่มหนึ่งเป็นกลุ่มผู้อ่าน และอีกกลุ่มเป็นกลุ่ม ผู้มีส่วนร่วม และจะทำให้บริการ Microsoft Dataverse เป็นเจ้าของกลุ่มความปลอดภัยทั้งสองกลุ่มนี้
       - เรียกใช้สคริปต์ PowerShell นี้ใน Windows PowerShell โดยระบุรหัสการสมัครใช้งาน Azure ที่มี Azure Data Lake Storage ของคุณ เปิดสคริปต์ PowerShell ในตัวแก้ไขเพื่อตรวจสอบข้อมูลเพิ่มเติมและตรรกะที่นำไปใช้
       - บันทึกค่ารหัสกลุ่มความปลอดภัยที่สร้างโดยสคริปต์นี้ เพราะเราจะใช้ในสคริปต์ `ByolSetup.ps1`

        > [!NOTE]
        > การสร้างกลุ่มความปลอดภัยสามารถปิดใช้งานได้ในผู้เช่าของคุณ ในกรณีนั้น จำเป็นต้องมีการตั้งค่าด้วยตนเองและผู้ดูแลระบบ Azure AD ของคุณจะต้อง [เปิดใช้งานการสร้างกลุ่มความปลอดภัย](/azure/active-directory/enterprise-users/groups-self-service-management)

    2. `ByolSetup.ps1`
        - คุณต้องการสิทธิ์ *เจ้าของข้อมูลในที่เก็บข้อมูล Blob* ที่ระดับบัญชีที่จัดเก็บข้อมูล/คอนเทนเนอร์เพื่อเรียกใช้สคริปต์นี้ มิฉะนั้นสคริปต์นี้จะสร้างให้คุณ การกำหนดบทบาทของคุณสามารถเอาออกได้ด้วยตนเองหลังจากเรียกใช้สคริปต์สำเร็จ
        - สคริปต์ PowerShell นี้เพิ่มการควบคุมการเข้าถึงตามบทบาท (RBAC) ที่จำเป็นสำหรับบริการ Microsoft Dataverse และแอปพลิเคชันทางธุรกิจบน Dataverse นอกจากนี้ยังมีการปรับปรุงรายการตัวควบคุมการเข้าถึง (ACL) บนคอนเทนเนอร์ Customer Insights สำหรับกลุ่มความปลอดภัยที่สร้างด้วยสคริปต์ `CreateSecurityGroups.ps1` กลุ่มผู้มีส่วนร่วมจะมีสิทธิ์ *rwx* และกลุ่มผู้อ่านจะมีเฉพาะสิทธิ์ *r-x* เท่านั้น
        - เรียกใช้สคริปต์ PowerShell นี้ใน Windows PowerShell โดยระบุรหัสการสมัครใช้งาน Azure ที่มี Azure Data Lake Storage, ชื่อบัญชีที่เก็บข้อมูล ชื่อกลุ่มทรัพยากร และค่ารหัสกลุ่มความปลอดภัย ผู้อ่าน และผู้สนับสนุนของคุณ เปิดสคริปต์ PowerShell ในตัวแก้ไขเพื่อตรวจสอบข้อมูลเพิ่มเติมและตรรกะที่นำไปใช้
        - คัดลอกสตริงเอาต์พุตหลังจากเรียกใช้สคริปต์สำเร็จ สตริงเอาต์พุตมีลักษณะดังนี้: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. ป้อนสตริงเอาต์พุตที่คัดลอกจากด้านบนลงในฟิลด์ **ตัวระบุสิทธิ์** ของขั้นตอนการกำหนดค่าสภาพแวดล้อมสำหรับ Microsoft Dataverse

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="ตัวเลือกการกำหนดค่าเพื่อเปิดใช้งานการแชร์ข้อมูลจาก Azure Data Lake Storage ของคุณเองกับ Microsoft Dataverse":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>ลบการเชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่

เมื่อเชื่อมต่อกับสภาพแวดล้อม Dataverse ข้อความแสดงข้อผิดพลาด **องค์กร CDS นี้แนบกับอินสแตนซ์ Customer Insights อื่นอยู่แล้ว** หมายความว่าสภาพแวดล้อม Dataverse มีการใช้อยู่แล้วในสภาพแวดล้อม Customer Insights คุณสามารถลบการเชื่อมต่อที่มีอยู่ในสภาพแวดล้อม Dataverse ในฐานะผู้ดูแลระบบส่วนกลาง โดยอาจใช้เวลาสองสามชั่วโมงในการเติมข้อมูลการเปลี่ยนแปลง

1. ไปที่ [Power Apps](https://make.powerapps.com)
1. เลือกสภาพแวดล้อมจากตัวเลือกสภาพแวดล้อม
1. ไปที่ **โซลูชัน**
1. ถอนการติดตั้งหรือลบโซลูชันที่ชื่อ **Add-in การ์ดลูกค้าของ Dynamics 365 Customer Insights (พรีวิว)**

OR

1. เปิดสภาพแวดล้อม Dataverse ของคุณ
1. ไปที่ **การตั้งค่าขั้นสูง** > **โซลูชัน**
1. ถอนการติดตั้งโซลูชัน **CustomerInsightsCustomerCard**

หากการลบการเชื่อมต่อล้มเหลวเนื่องจากการขึ้นต่อกัน คุณต้องลบการขึ้นต่อกันด้วย สำหรับข้อมูลเพิ่มเติม โปรดดู [การลบการขึ้นต่อกัน](/power-platform/alm/removing-dependencies)

## <a name="output-entities"></a>เอนทิตีเอาต์พุต

เอนทิตีเอาต์พุตบางรายการจาก Customer Insights สามารถใช้งานเป็นตารางใน Dataverse ส่วนด้านล่างอธิบาย Schema ที่คาดไว้ของตารางเหล่านี้

- [โปรไฟล์ลูกค้า](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [การเพิ่มข้อมูลแล้ว](#enrichment)
- [การคาดคะเน](#prediction)
- [การเป็นสมาชิกเซ็กเมนต์](#segment-membership)

### <a name="customerprofile"></a>โปรไฟล์ลูกค้า

ตารางนี้มีโปรไฟล์ลูกค้าแบบรวมจาก Customer Insights Schema สำหรับโปรไฟล์ลูกค้าแบบรวมขึ้นอยู่กับเอนทิตีและแอตทริบิวต์ที่ใช้ในกระบวนการรวมข้อมูล schema โปรไฟล์ลูกค้ามักจะมีชุดย่อยของแอตทริบิวต์จาก [คำนิยาม Common Data Model ของ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile)

### <a name="alternatekey"></a>AlternateKey

ตาราง AlternateKey ประกอบด้วยคีย์ของเอนทิตี ซึ่งเข้าร่วมในกระบวนการ Unify

|Column  |พิมพ์ข้อความ  |รายละเอียด  |
|---------|---------|---------|
|DataSourceName    |String         | ชื่อของแหล่งข้อมูล ตัวอย่าง: `datasource5`        |
|EntityName        | สตริง        | ชื่อของเอนทิตีใน Customer Insights ตัวอย่าง: `contact1`        |
|AlternateValue    |สตริง         |รหัสแทนที่แมปกับรหัสลูกค้า ตัวอย่าง: `cntid_1078`         |
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
| SemanticData      | สตริง JSON | รวมรายการของคู่ค่าคีย์สำหรับฟิลด์การแมปเชิงความหมายที่เฉพาะเจาะจงสำหรับชนิดของกิจกรรม |
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
| SegmentProvider      | สตริง       | แอปที่เผยแพร่เซ็กเมนต์      |
| SegmentMembershipType | สตริง       | ชนิดของลูกค้าสำหรับเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์นี้ รองรับหลายชนิด เช่น ลูกค้า ผู้ติดต่อ หรือลูกค้าองค์กร ค่าเริ่มต้น: ลูกค้า  |
| เซ็กเมนต์       | สตริง JSON  | รายการเซ็กเมนต์เฉพาะที่โปรไฟล์ลูกค้าเป็นสมาชิก      |
| msdynci_identifier  | สตริง   | รหัสเฉพาะของเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์ `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID เชิงกำหนดที่สร้างจาก `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
