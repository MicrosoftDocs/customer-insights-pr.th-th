---
title: ทำงานกับข้อมูล Customer Insights ใน Microsoft Dataverse
description: เรียนรู้วิธีการเชื่อมต่อ Customer Insights กับ Microsoft Dataverse และทำความเข้าใจเอนทิตีผลลัพธ์ที่ส่งออกไปยัง Dataverse
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671274"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>ทำงานกับข้อมูล Customer Insights ใน Microsoft Dataverse

Customer Insights มีตัวเลือกในการทำให้เอนทิตีเอาต์พุตพร้อมใช้งานใน [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) การผสานรวมนี้ช่วยให้การแบ่งปันข้อมูลและการพัฒนาแบบกำหนดเองทำได้ง่ายโดยใช้แนวทางแบบเขียนโค้ดเล็กน้อย/แบบไม่ต้องใช้โค้ด [เอนทิตีผลลัพธ์](#output-entities) มีเป็นตารางในสภาพแวดล้อม Dataverse คุณสามารถใช้ข้อมูลนี้สำหรับแอปพลิเคชันอื่นตามตาราง Dataverse ตารางเหล่านี้เปิดใช้งานสถานการณ์ เช่น เวิร์กโฟลว์อัตโนมัติผ่าน Power Automate หรือการสร้างแอปด้วย Power Apps

การเชื่อมต่อกับสภาพแวดล้อม Dataverse ของคุณยังช่วยให้คุณสามารถ [นำเข้าข้อมูลจากแหล่งข้อมูลในสถานที่โดยใช้กระแสข้อมูล Power Platform และเกตเวย์](connect-power-query.md#add-data-from-on-premises-data-sources)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สภาพแวดล้อม Customer Insights และ Dataverse ต้องโฮสต์อยู่ในภูมิภาคเดียวกัน
- บทบาทผู้ดูแลระบบส่วนกลางตั้งค่าในสภาพแวดล้อม Dataverse ตรวจสอบว่า [สภาพแวดล้อม Dataverse เชื่อมโยง](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) กับกลุ่มความปลอดภัยที่กำหนดหรือไม่ และตรวจสอบว่าคุณได้เพิ่มสภาพแวดล้อมลงในกลุ่มความปลอดภัยเหล่านั้นแล้ว
- ไม่มีสภาพแวดล้อม Customer Insights อื่นเชื่อมโยงกับสภาพแวดล้อม Dataverse ที่คุณต้องการเชื่อมต่อ เรียนรู้วิธีการ [ลบการเชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่](#remove-an-existing-connection-to-a-dataverse-environment)
- สภาพแวดล้อม Microsoft Dataverse ที่เชื่อมต่อกับบัญชีที่เก็บข้อมูลเดียว หากคุณกำหนดค่าสภาพแวดล้อมเป็น [ใช้ Azure Data Lake Storage ของคุณ](own-data-lake-storage.md)

## <a name="dataverse-storage-capacity-entitlement"></a>การให้สิทธิ์ความจุที่เก็บข้อมูล Dataverse

การสมัครใช้งาน Customer Insights จะทำให้คุณได้รับความจุเพิ่มเติมสำหรับ [ความจุ Dataverse](/power-platform/admin/capacity-storage) ที่องค์กรของคุณมีอยู่ ความจุที่เพิ่มขึ้นจะขึ้นอยู่กับจำนวนโปรไฟล์ที่การสมัครใช้งานของคุณใช้

**ตัวอย่าง:**

สมมติว่าคุณได้รับที่เก็บฐานข้อมูล 15 GB และที่เก็บไฟล์ 20 GB ต่อโปรไฟล์ลูกค้า 100,000 ราย หากการสมัครใช้งานของคุณมีโปรไฟล์ลูกค้า 300,000 โปรไฟล์ ความจุรวมของที่เก็บข้อมูลของคุณคือ ที่เก็บข้อมูลฐานข้อมูล 45 GB (3 x 15 GB) และที่เก็บข้อมูลไฟล์ 60 GB (3 x 20 GB) ในทำนองเดียวกัน หากคุณมีการสมัครสมาชิกใช้งานแบบ B-to-B ที่มีบัญชี 30K ความจุรวมของที่เก็บข้อมูลของคุณคือ ที่เก็บข้อมูลฐานข้อมูล 45 GB (3 x 15 GB) และที่เก็บข้อมูลไฟล์ 60 GB (3 x 20 GB)

ความจุไฟล์บันทึกไม่ได้เพิ่มขึ้นและเป็นแบบคงที่สำหรับองค์กรของคุณ

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการให้สิทธิ์ความจุโดยละเอียด โปรดดู [คู่มือการให้สิทธิ์การใช้งาน Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544)

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>เชื่อมต่อสภาพแวดล้อม Dataverse กับ Customer Insights

ขั้นตอน **Microsoft Dataverse** ช่วยให้คุณเชื่อมต่อ Customer Insights กับสภาพแวดล้อม Dataverse ขณะที่ [สร้างสภาพแวดล้อม Customer Insights](create-environment.md)

:::image type="content" source="media/dataverse-provisioning.png" alt-text="การแชร์ข้อมูลกับ Microsoft Dataverse ที่เปิดใช้งานอัตโนมัติสำหรับสภาพแวดล้อมใหม่":::

1. ระบุ URL ไปยังสภาพแวดล้อม Dataverse ของคุณหรือเว้นว่างไว้เพื่อให้มีการสร้างใหม่ให้กับคุณ

   > [!NOTE]
   > หลังจากสร้างการเชื่อมต่อระหว่าง Customer Insights กับ Dataverse อย่าเปลี่ยนชื่อองค์กรสำหรับสภาพแวดล้อม Dataverse ชื่อองค์กรที่ใช้ใน Dataverse URL และชื่อที่เปลี่ยนจะทำลายการเชื่อมต่อกับ Customer Insights

   [ผู้ดูแลระบบ Power Platform สามารถควบคุมว่าบุคคลใดที่สามารถสร้างสภาพแวดล้อม Dataverse ใหม่](/power-platform/admin/control-environment-creation) หากคุณพยายามตั้งค่าสภาพแวดล้อม Customer Insights ใหม่และและไม่สามารถทำได้ แสดงว่าผู้ดูแลระบบอาจปิดใช้งานการสร้างสภาพแวดล้อม Dataverse สำหรับทุกคนยกเว้นผู้ดูแลระบบ

1. หากคุณกำลังใช้บัญชี Data Lake Storage ของคุณเอง:
   1. เลือก **เปิดใช้งานการแชร์ข้อมูล** กับ Dataverse
   1. ป้อน **ตัวระบุสิทธิ์** ในการรับตัวระบุสิทธิ์ ให้ [เปิดใช้งานการแชร์ข้อมูลกับ Dataverse จาก Azure Data Lake Storage ของคุณเอง](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>เปิดใช้งานการแชร์ข้อมูลกับ Dataverse จาก Azure Data Lake Storage ของคุณเอง (พรีวิว)

ใน [บัญชี Azure Data Lake Storage ของคุณเอง](own-data-lake-storage.md) ตรวจสอบว่าผู้ใช้ที่ตั้งค่าสภาพแวดล้อม Customer Insights มีสิทธิ์ **ผู้อ่านข้อมูลในที่เก็บข้อมูล Blob** บนคอนเทนเนอร์ `customerinsights` ในบัญชีที่เก็บข้อมูล

> [!NOTE]
> การแบ่งปันข้อมูลจะใช้ได้เฉพาะเมื่อคุณใช้ข้อมูลบัญชี Azure Data Lake Storage ของคุณเอง การตั้งค่านี้ไม่สามารถใช้ได้หากสภาพแวดล้อม Customer Insights ใช้ที่เก็บข้อมูล Dataverse เริ่มต้น

### <a name="limitations"></a>ข้อจำกัด

- มีเฉพาะการแมปแบบหนึ่งต่อหนึ่งระหว่างองค์กร Dataverse กับบัญชี Azure Data Lake Storage เมื่อองค์กร Dataverse เชื่อมต่อกับบัญชีที่เก็บข้อมูล องค์กรจะไม่สามารถเชื่อมต่อกับบัญชีที่เก็บข้อมูลอื่นได้ ข้อจำกัดนี้ทำให้ Dataverse ไม่สามารถเติมข้อมูลในบัญชีที่เก็บข้อมูลหลายบัญชี
- การแชร์ข้อมูลจะไม่ทำงานหากจำเป็นต้องตั้งค่า Azure Private Link เพื่อเข้าถึงบัญชี Azure Data Lake Storage เนื่องจากอยู่หลังไฟร์วอลล์ ขณะนี้ Dataverse ไม่รองรับการเชื่อมต่อกับตำแหน่งข้อมูลส่วนตัวผ่าน Private Link

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>ตั้งค่ากลุ่มความปลอดภัยบน Azure Data Lake Storage ของคุณเอง

1. สร้างกลุ่มความปลอดภัยสองกลุ่มในการสมัครใช้งาน Azure ของคุณ กลุ่มหนึ่งคือ กลุ่มความปลอดภัย **ผู้อ่าน** และอีกกลุ่มคือ **ผู้มีส่วนร่วม** และตั้งค่าบริการ Microsoft Dataverse ในฐานะเจ้าของกลุ่มความปลอดภัยทั้งสองกลุ่ม

1. จัดการรายการตัวควบคุมการเข้าถึง (ACL) บนคอนเทนเนอร์ `customerinsights` ในบัญชีที่เก็บข้อมูลของคุณผ่านกลุ่มความปลอดภัยเหล่านี้
   1. เพิ่มบริการ Microsoft Dataverse และแอปพลิเคชันทางธุรกิจบน Dataverse  ใดๆ เช่น Dynamics 365 Marketing ไปยังกลุ่มความปลอดภัย **ผู้อ่าน** ด้วยสิทธิ์การใช้งาน **อ่านอย่างเดียว**
   1. เพิ่ม *เฉพาะ* แอปพลิเคชัน Customers Insights ไปยังกลุ่มความปลอดภัย **ผู้มีส่วนร่วม** เพื่อให้ทั้งสิทธิ์การใช้งาน **อ่านและเขียน** ในการเขียนโปรไฟล์และข้อมูลเชิงลึก

### <a name="set-up-powershell"></a>ตั้งค่า PowerShell

ตั้งค่า PowerShell เพื่อเรียกใช้สคริปต์ PowerShell

1. ติดตั้งเวอร์ชันล่าสุดของ [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. บนพีซีของคุณ เลือกคีย์ Windows บนแป้นพิมพ์ และค้นหา **Windows PowerShell** และเลือก **เรียกใช้เป็นผู้ดูแลระบบ**
   1. ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`

1. นำเข้าสามโมดูล
   1. ในหน้าต่าง PowerShell ให้ป้อน `Install-Module -Name Az.Accounts` และปฏิบัติตามขั้นตอน
   1. ทำซ้ำสำหรับ `Install-Module -Name Az.Resources` และ `Install-Module -Name Az.Storage`

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>เรียกใช้สคริปต์ PowerShell และขอรับตัวระบุสิทธิ์

1. ดาวน์โหลดสคริปต์ PowerShell สองชุดที่คุณต้องเรียกใช้จาก [GitHub repo](https://github.com/trin-msft/byol) ของวิศวกรของเรา
   - `CreateSecurityGroups.ps1`: ต้องการสิทธิ์ระดับผู้ดูแลระบบผู้เช่า
   - `ByolSetup.ps1`: ต้องการสิทธิ์เจ้าของข้อมูลในที่เก็บข้อมูล Blob ที่ระดับบัญชีที่เก็บข้อมูล/คอนเทนเนอร์ สคริปต์นี้จะสร้างสิทธิ์ให้กับคุณ การกำหนดบทบาทของคุณสามารถเอาออกได้ด้วยตนเองหลังจากเรียกใช้สคริปต์สำเร็จ

1. เรียกใช้ `CreateSecurityGroups.ps1` ใน Windows PowerShell โดยระบุรหัสการสมัครใช้งาน Azure ที่มี Azure Data Lake Storage ของคุณ เปิดสคริปต์ PowerShell ในตัวแก้ไขเพื่อตรวจสอบข้อมูลเพิ่มเติมและตรรกะที่นำไปใช้

   สคริปต์นี้สร้างกลุ่มความปลอดภัยสองกลุ่มในการสมัครใช้งาน Azure ของคุณ กลุ่มหนึ่งสำหรับผู้อ่าน และอีกกลุ่มสำหรับผู้มีส่วนร่วม บริการ Microsoft Dataverse เป็นเจ้าของกลุ่มความปลอดภัยทั้งคู่นี้

1. บันทึกค่ารหัสกลุ่มความปลอดภัยทั้งคู่ที่สร้างโดยสคริปต์นี้เพื่อใช้ในสคริปต์ `ByolSetup.ps1`

   > [!NOTE]
   > การสร้างกลุ่มความปลอดภัยสามารถปิดใช้งานได้ในผู้เช่าของคุณ ในกรณีนั้น จำเป็นต้องมีการตั้งค่าด้วยตนเองและผู้ดูแลระบบ Azure AD ของคุณจะต้อง [เปิดใช้งานการสร้างกลุ่มความปลอดภัย](/azure/active-directory/enterprise-users/groups-self-service-management)

1. เรียกใช้ `ByolSetup.ps1` ใน Windows PowerShell โดยระบุรหัสการสมัครใช้งาน Azure ที่มี Azure Data Lake Storage ของคุณ ชื่อบัญชีที่เก็บข้อมูล ชื่อกลุ่มทรัพยากร และค่ารหัสกลุ่มความปลอดภัย ผู้อ่าน และผู้สนับสนุนของคุณ เปิดสคริปต์ PowerShell ในตัวแก้ไขเพื่อตรวจสอบข้อมูลเพิ่มเติมและตรรกะที่นำไปใช้

   สคริปต์นี้เพิ่มการควบคุมการเข้าถึงตามบทบาทที่จำเป็นสำหรับบริการ Microsoft Dataverse และแอปพลิเคชันทางธุรกิจบน Dataverse ใดๆ นอกจากนี้ยังมีการปรับปรุงรายการตัวควบคุมการเข้าถึง (ACL) บนคอนเทนเนอร์ `customerinsights` สำหรับกลุ่มความปลอดภัยที่สร้างด้วยสคริปต์ `CreateSecurityGroups.ps1` กลุ่มผู้มีส่วนร่วมจะได้รับสิทธิ์ *rwx* และกลุ่มผู้อ่านจะได้รับสิทธิ์ *r-x* เท่านั้น

1. คัดลอกสตริงเอาต์พุตที่มีลักษณะดังนี้: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. ป้อนสตริงเอาต์พุตที่คัดลอกลงในฟิลด์ **ตัวระบุสิทธิ์** ของขั้นตอนการกำหนดค่าสภาพแวดล้อมสำหรับ Microsoft Dataverse

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="ตัวเลือกการกำหนดค่าเพื่อเปิดใช้งานการแชร์ข้อมูลจาก Azure Data Lake Storage ของคุณเองกับ Microsoft Dataverse":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>ลบการเชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่

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
- [ติดต่อโปรไฟล์](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [การเพิ่มข้อมูลแล้ว](#enrichment)
- [การคาดคะเน](#prediction)
- [การเป็นสมาชิกเซ็กเมนต์](#segment-membership)

### <a name="customerprofile"></a>โปรไฟล์ลูกค้า

ตารางนี้มีโปรไฟล์ลูกค้าแบบรวมจาก Customer Insights Schema สำหรับโปรไฟล์ลูกค้าแบบรวมขึ้นอยู่กับเอนทิตีและแอตทริบิวต์ที่ใช้ในกระบวนการรวมข้อมูล schema โปรไฟล์ลูกค้ามักจะมีชุดย่อยของแอตทริบิวต์จาก [คำนิยาม Common Data Model ของ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) สำหรับสถานการณ์ B-to-B โปรไฟล์ลูกค้าประกอบด้วยบัญชีแบบรวม และสคีมามักจะประกอบด้วยชุดย่อยของแอตทริบิวต์จาก [คำนิยาม Common Data Model ของบัญชี](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account)

### <a name="contactprofile"></a>ติดต่อโปรไฟล์

ContactProfile มีข้อมูลแบบรวมเกี่ยวกับผู้ติดต่อ ผู้ติดต่อคือ [บุคคลที่เชื่อมโยงกับบัญชี](data-unification-contacts.md) ในสถานการณ์ B-to-B

| Column                       | ขนิด                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  วันเกิด            | DateTime       |  วันเกิดของผู้ติดต่อ               |
|  City                 | ข้อความ |  เมืองของที่อยู่ผู้ติดต่อ               |
|  ผู้ติดต่อ            | ข้อความ |  ID ของโปรไฟล์ผู้ติดต่อ               |
|  ContactProfileId     | รหัสเฉพาะ   |  GUID สำหรับผู้ติดต่อ               |
|  CountryOrRegion      | ข้อความ |  ประเทศ/ภูมิภาคของที่อยู่ผู้ติดต่อ               |
|  รหัสลูกค้า           | ข้อความ |  ID ของบัญชีที่ผู้ติดต่อถูกแมป               |
|  EntityName           | ข้อความ |  เอนทิตีที่ข้อมูลมาจาก                |
|  FirstName            | ข้อความ |  ชื่อของผู้ติดต่อ               |
|  เพศ               | ข้อความ |  เพศของผู้ติดต่อ               |
|  รหัส                   | ข้อความ |  GUID เชิงกำหนดตาม `Identifier`               |
|  ตัวระบุ           | ข้อความ |  ID ภายในของโปรไฟล์ผู้ติดต่อ: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | ข้อความ |  ตำแหน่งงานของผู้ติดต่อ               |
|  LastName             | ข้อความ |  นามสกุลของผู้ติดต่อ               |
|  PostalCode           | ข้อความ |  รหัสไปรษณีย์ของที่อยู่ผู้ติดต่อ               |
|  PrimaryEmail         | ข้อความ |  ที่อยู่อีเมลของผู้ติดต่อ               |
|  PrimaryPhone         | ข้อความ |  หมายเลขโทรศัพท์ของผู้ติดต่อ               |
|  รัฐหรือจังหวัด      | ข้อความ |  รัฐหรือจังหวัดของที่อยู่ผู้ติดต่อ               |
|  StreetAddress        | ข้อความ |  ถนนของที่อยู่ผู้ติดต่อ               |

### <a name="alternatekey"></a>AlternateKey

ตาราง AlternateKey ประกอบด้วยคีย์ของเอนทิตี ซึ่งเข้าร่วมในกระบวนการ Unify

|Column  |ขนิด  |Description  |
|---------|---------|---------|
|DataSourceName    |ข้อความ         | ชื่อของแหล่งข้อมูล ตัวอย่าง: `datasource5`        |
|EntityName        | ข้อความ        | ชื่อของเอนทิตีใน Customer Insights ตัวอย่าง: `contact1`        |
|AlternateValue    |ข้อความ         |รหัสแทนที่แมปกับรหัสลูกค้า ตัวอย่าง: `cntid_1078`         |
|KeyRing           | ข้อความ        | ค่า JSON  </br> ตัวอย่าง: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|รหัสลูกค้า         | ข้อความ        | ID ของโปรไฟล์ลูกค้าแบบรวม         |
|AlternateKeyId     | รหัสเฉพาะ        |  GUID เชิงกำหนดของ AlternateKey ตาม `Identifier`      |
|ตัวระบุ |   ข้อความ      |   `DataSourceName|EntityName|AlternateValue`  </br> ตัวอย่าง: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

ตารางนี้มีกิจกรรมโดยผู้ใช้ที่มีอยู่ใน Customer Insights

| Column            | ขนิด        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| รหัสลูกค้า        | ข้อความ      | รหัสโปรไฟล์ลูกค้า                                                                      |
| ActivityId        | ข้อความ      | ID ภายในของกิจกรรมของลูกค้า (คีย์หลัก)                                       |
| SourceEntityName  | ข้อความ      | ชื่อเอนทิตีต้นทาง                                                                |
| SourceActivityId  | ข้อความ      | คีย์หลักจากเอนทิตีต้นทาง                                                       |
| ActivityType      | ข้อความ      | ชนิดกิจกรรมเชิงความหมาย หรือชื่อของกิจกรรมที่กำหนดเอง                                        |
| ActivityTimeStamp | DateTime    | ประทับเวลาของกิจกรรม                                                                      |
| Title             | ข้อความ      | ชื่อเรื่องหรือชื่อกิจกรรม                                                               |
| Description       | ข้อความ      | Description ของกิจกรรม                                                                     |
| URL                | ข้อความ      | ลิงก์ไปยัง URL ภายนอกที่เฉพาะเจาะจงสำหรับกิจกรรม                                         |
| SemanticData      | ข้อความ | รวมรายการของคู่ค่าคีย์สำหรับฟิลด์การแมปเชิงความหมายที่เฉพาะเจาะจงสำหรับชนิดของกิจกรรม |
| RangeIndex        | ข้อความ      | การประทับเวลา Unix ที่ใช้สำหรับเรียงลำดับไทม์ไลน์กิจกรรมและการสืบค้นช่วงที่มีประสิทธิภาพ |
| UnifiedActivityId   | รหัสเฉพาะ | รหัสภายในของกิจกรรมของลูกค้า (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

ตารางนี้ประกอบด้วยข้อมูลผลลัพธ์ของการวัดตามแอตทริบิวต์ของลูกค้า

| Column             | ขนิด             | Description                 |
|--------------------|------------------|-----------------------------|
| รหัสลูกค้า         | ข้อความ           | รหัสโปรไฟล์ลูกค้า        |
| การวัด           | ข้อความ      | รวมรายการของคู่ค่าคีย์สำหรับชื่อการวัดและค่าสำหรับลูกค้าที่กำหนด |
| ตัวระบุ | ข้อความ           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | รหัสเฉพาะ     | รหัสโปรไฟล์ลูกค้า |

### <a name="enrichment"></a>การเพิ่มความสมบูรณ์

ตารางนี้มีผลลัพธ์ของกระบวนการเพิ่มข้อมูล

| Column               | ขนิด             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| รหัสลูกค้า           | ข้อความ           | รหัสโปรไฟล์ลูกค้า                                 |
| EnrichmentProvider   | ข้อความ           | ชื่อของผู้ให้บริการสำหรับการเพิ่มข้อมูล                                  |
| EnrichmentType       | ข้อความ           | ชนิดของการเพิ่มข้อมูล                                      |
| มูลค่า               | ข้อความ      | รายการของแอตทริบิวต์ที่สร้างโดยกระบวนการเพิ่มข้อมูล |
| EnrichmentId | รหัสเฉพาะ            | GUID เชิงกำหนดที่สร้างจาก `Identifier` |
| ตัวระบุ   | ข้อความ           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>การคาดการณ์

ตารางนี้มีผลลัพธ์ของการคาดคะเนแบบจำลอง

| Column               | ขนิด        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| รหัสลูกค้า           | ข้อความ      | รหัสโปรไฟล์ลูกค้า                                  |
| ModelProvider        | ข้อความ      | ชื่อของผู้ให้บริการของแบบจำลอง                                      |
| แบบจำลอง                | ข้อความ      | ชื่อรูปแบบ                                                |
| มูลค่า               | ข้อความ | รายการของแอตทริบิวต์ที่สร้างโดยแบบจำลอง |
| PredictionId | รหัสเฉพาะ       | GUID เชิงกำหนดที่สร้างจาก `Identifier` |
| ตัวระบุ   | ข้อความ      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>การเป็นสมาชิกเซ็กเมนต์

ตารางนี้มีข้อมูลการเป็นสมาชิกเซ็กเมนต์ของโปรไฟล์ลูกค้า

| Column        | ขนิด | Description                        |
|--------------------|--------------|-----------------------------|
| รหัสลูกค้า        | ข้อความ       | รหัสโปรไฟล์ลูกค้า        |
| SegmentProvider      | ข้อความ       | แอปที่เผยแพร่เซ็กเมนต์      |
| SegmentMembershipType | ข้อความ       | ชนิดของลูกค้าสำหรับเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์นี้ รองรับหลายชนิด เช่น ลูกค้า ผู้ติดต่อ หรือลูกค้าองค์กร ค่าเริ่มต้น: ลูกค้า  |
| Segments       | ข้อความ  | รายการเซ็กเมนต์เฉพาะที่โปรไฟล์ลูกค้าเป็นสมาชิก      |
| ตัวระบุ  | ข้อความ   | รหัสเฉพาะของเรกคอร์ดการเป็นสมาชิกเซ็กเมนต์ `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | รหัสเฉพาะ      | GUID เชิงกำหนดที่สร้างจาก `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
