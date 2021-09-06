---
title: เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก
description: ใช้บริการหลัก Azure เพื่อเชื่อมต่อกับ Data Lake ของคุณเอง
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461171"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
เครื่องมืออัตโนมัติที่ใช้บริการ Azure ควรมีสิทธิ์ที่จำกัดไว้เสมอ แทนที่จะให้แอปพลิเคชันลงชื่อเข้าใช้ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานแบบเต็ม Azure จะเสนอบริการหลัก อ่านต่อเพื่อเรียนรู้วิธีการเชื่อมต่อ Dynamics 365 Customer Insights กับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก Azure แทนคีย์บัญชีที่เก็บข้อมูล 

คุณสามารถใช้บริการหลักเพื่อ [เพิ่มหรือแก้ไขโฟลเดอร์ Common Data Model เป็นแหล่งข้อมูล](connect-common-data-model.md) หรือ [สร้างหรืออัพเดตสภาพแวดล้อม](get-started-paid.md) ได้อย่างปลอดภัย<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - บัญชี Data Lake Storage ที่จะใช้<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> บริการหลักต้อง [เปิดใช้งานเนมสเปซแบบลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)
> - คุณต้องมีสิทธิ์ระดับผู้ดูแลระบบสำหรับการสมัครใช้งาน Azure ของคุณเพื่อสร้างบริการหลัก

## <a name="create-an-azure-service-principal-for-customer-insights"></a>สร้างบริการหลัก Azure สำหรับ Customer Insights

ก่อนที่จะสร้างบริการหลักใหม่สำหรับข้อมูลเชิงลึกของผู้ชมหรือข้อมูลเชิงลึกของการมีส่วนร่วม ให้ตรวจสอบว่ามีอยู่แล้วในองค์กรของคุณหรือไม่

### <a name="look-for-an-existing-service-principal"></a>มองหาบริการหลักที่มีอยู่

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

2. จาก **บริการ Azure** เลือก **Azure Active Directory**

3. ภายใต้ **จัดการ** เลือก **แอปพลิเคชัน Enterprise**

4. ค้นหา Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> รหัสแอปพลิเคชัน:
   - ข้อมูลเชิงลึกของผู้ชม: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ที่มีชื่อว่า `Dynamics 365 AI for Customer Insights`
   - ข้อมูลเชิงลึกของการมีส่วนร่วม: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` ที่มีชื่อว่า `Dynamics 365 AI for Customer Insights engagement insights`

5. หากคุณพบเรกคอร์ดที่ตรงกัน แสดงว่ามีบริการหลักอยู่แล้ว 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="ภาพหน้าจอที่แสดงบริการหลักที่มีอยู่":::
   
6. หากไม่มีการส่งคืนผลลัพธ์ ให้สร้างบริการหลักใหม่

>[!NOTE]
>เพื่อใช้ Dynamics 365 Customer Insights อย่างเต็มประสิทธิภาพ เราขอแนะนำให้คุณเพิ่มทั้งสองแอปในหลักบริการ<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>สร้างบริการหลักใหม่
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. ติดตั้ง Azure Active Directory PowerShell for Graph เวอร์ชันล่าสุด สำหรับรายละเอียดเพิ่มเติม ไปที่ [ติดตั้ง Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)

   1. บนพีซีของคุณ เลือกคีย์ Windows บนแป้นพิมพ์ และค้นหา **Windows PowerShell** และเลือก **เรียกใช้เป็นผู้ดูแลระบบ**<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`

2. สร้างบริการหลักสำหรับ Customer Insights ด้วยโมดูล Azure AD PowerShell

   1. ในหน้าต่าง PowerShell ให้ป้อน `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` แทนที่ *"[รหัสผู้เช่าของคุณ]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> ด้วยรหัสจริงของผู้เช่าของคุณที่คุณต้องการสร้างบริการหลัก พารามิเตอร์ชื่อสภาพแวดล้อม `AzureEnvironmentName` เป็นตัวเลือก
  
   1. ป้อน `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` คำสั่งนี้สร้างบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเกี่ยวกับผู้เช่าที่เลือก 

   1. ป้อน `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` คำสั่งนี้สร้างบริการหลักสำหรับข้อมูลเชิงลึกของการมีส่วนร่วม<!--note from editor: Edit okay?--> บนผู้เช่าที่เลือก

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ให้สิทธิ์แก่บริการหลักในการเข้าถึงบัญชีที่เก็บข้อมูล

ไปที่พอร์ทัล Azure เพื่อให้สิทธิ์แก่บริการหลักสำหรับบัญชีที่เก็บข้อมูลที่คุณต้องการใช้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

1. เปิดบัญชีที่เก็บข้อมูลที่คุณต้องการให้บริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเข้าถึงได้

1. ในบานหน้าต่างด้านซ้าย เลือก **การควบคุมการเข้าถึง (IAM)** แล้วจากนั้น เลือก **เพิ่ม** > **เพิ่มการมอบหมายบทบาท**

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ภาพหน้าจอที่แสดงพอร์ทัล Azure ขณะที่เพิ่มการมอบหมายบทบาท":::

1. บนบานหน้าต่าง **เพิ่มการมอบหมายบทบาท** ตั้งค่าคุณสมบัติต่อไปนี้:
   - บทบาท: **ผู้สนับสนุนข้อมูล Blob ของการจัดเก็บ**
   - กำหนดการเข้าถึง: **ผู้ใช้,กลุ่ม หรือบริการหลัก**
   - เลือก: **Dynamics 365 AI for Customer Insights** และ **ข้อมูลเชิงลึกการมีส่วนร่วมของ Dynamics 365 AI for Customer Insights** ([หลักการบริการ](#create-a-new-service-principal) ทั้งสองรายการที่คุณสร้างไว้ก่อนหน้านี้ในกระบวนงานนี้)

1.  เลือก **บันทึก**

โดยอาจใช้เวลาถึง 15 นาทีในการเผยแพร่การเปลี่ยนแปลง

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>ป้อนรหัสทรัพยากร Azure หรือรายละเอียดการสมัครใช้งาน Azure ในสิ่งที่แนบกับบัญชีที่เก็บข้อมูลกับข้อมูลเชิงลึกของผู้ชม

คุณสามารถ<!--note from editor: Edit suggested only if this section is optional.--> แนบบัญชี Data Lake Storage ในข้อมูลเชิงลึกของผู้ชมไปยัง [เก็บข้อมูลเอาท์พุต](manage-environments.md) หรือ [ใช้เป็นแหล่งข้อมูล](connect-common-data-service-lake.md) ตัวเลือกนี้ทำให้คุณสามารถเลือกระหว่างวิธีการแบบอิงตามทรัพยากรหรือแบบอิงตามการสมัครใช้งาน โดยขึ้นอยู่กับวิธีการที่คุณเลือก ให้ทำตามกระบวนงานในส่วนใดส่วนหนึ่งต่อไปนี้<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามทรัพยากร

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณ และเปิดบัญชีที่เก็บข้อมูล

1. ในบานหน้าต่างด้านซ้าย ไปที่ **การตั้งค่า** > **คุณสมบัติ**

1. คัดลอกค่ารหัสทรัพยากรบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="คัดลอกรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::

1. ในข้อมูลเชิงลึกของผู้ชม ให้แทรกรหัสทรัพยากรในฟิลด์ทรัพยากรที่แสดงบนหน้าจอการเชื่อมต่อบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::   

1. ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล

### <a name="subscription-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามการสมัครใช้งาน

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณ และเปิดบัญชีที่เก็บข้อมูล

1. ในบานหน้าต่างด้านซ้าย ไปที่ **การตั้งค่า** > **คุณสมบัติ**

1. ตรวจสอบ **การสมัครใช้งาน**, **กลุ่มทรัพยากร** และ **ชื่อ** ของบัญชีที่เก็บข้อมูล เพื่อให้แน่ใจว่าคุณเลือกค่าที่ถูกต้องในข้อมูลเชิงลึกกลุ่มเป้าหมาย

1. ในข้อมูลเชิงลึกของผู้ชม เลือกค่าสำหรับฟิลด์ที่เกี่ยวข้อง เมื่อแนบบัญชีที่เก็บข้อมูล

1. ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล


[!INCLUDE[footer-include](../includes/footer-banner.md)]