---
title: เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก
description: ใช้บริการหลัก Azure เพื่อเชื่อมต่อกับ Data Lake ของคุณเอง
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647701"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก Azure

บทความนี้กล่าวถึงวิธีการเชื่อมต่อ Dynamics 365 Customer Insights กับบัญชี Azure Data Lake Storage โดยใช้บริการหลักของ Azure แทนคีย์บัญชีการจัดเก็บ 

เครื่องมืออัตโนมัติที่ใช้บริการ Azure ควรมีสิทธิ์ที่จำกัดไว้เสมอ แทนที่จะให้แอปพลิเคชันลงชื่อเข้าใช้ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานแบบเต็ม Azure จะเสนอบริการหลัก คุณสามารถใช้บริการหลักเพื่อ [เพิ่มหรือแก้ไขโฟลเดอร์ Common Data Model เป็นแหล่งข้อมูล](connect-common-data-model.md) หรือ [สร้างหรือปรับปรุงภาพแวดล้อม](create-environment.md) ได้อย่างปลอดภัย

> [!IMPORTANT]
> - บัญชี Data Lake Storage ที่จะใช้บริการหลักต้องเป็น รุ่น2 และมี [การเปิดใช้งานเนมสเปซแบบแบบลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace) ไม่รองรับบัญชีที่เก็บข้อมูล Azure Data Lake รุ่น1
> - คุณต้องมีสิทธิ์ของผู้ดูแลระบบสำหรับการสมัครใช้งาน Azure เพื่อสร้างบริการหลัก

## <a name="create-an-azure-service-principal-for-customer-insights"></a>สร้างบริการหลัก Azure สำหรับ Customer Insights

ก่อนสร้างบริการหลักใหม่สำหรับ Customer Insights ให้ตรวจสอบว่ามีบริการหลักอยู่แล้วในองค์กรของคุณหรือไม่

### <a name="look-for-an-existing-service-principal"></a>มองหาบริการหลักที่มีอยู่

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

2. จาก **บริการ Azure** เลือก **Azure Active Directory**

3. ภายใต้ **จัดการ** เลือก **แอปพลิเคชัน Enterprise**

4. ค้นหารหัสแอปพลิเคชัน Microsoft `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ที่มีชื่อว่า `Dynamics 365 AI for Customer Insights`

5. หากคุณพบเรกคอร์ดที่ตรงกัน แสดงว่ามีบริการหลักอยู่แล้ว 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="ภาพหน้าจอที่แสดงบริการหลักที่มีอยู่":::
   
6. หากไม่มีการส่งคืนผลลัพธ์ ให้สร้างบริการหลักใหม่

### <a name="create-a-new-service-principal"></a>สร้างบริการหลักใหม่

1. ติดตั้ง Azure Active Directory PowerShell for Graph เวอร์ชันล่าสุด สำหรับรายละเอียดเพิ่มเติม ไปที่ [ติดตั้ง Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)

   1. บนพีซีของคุณ เลือกคีย์ Windows บนแป้นพิมพ์ และค้นหา **Windows PowerShell** และเลือก **เรียกใช้เป็นผู้ดูแลระบบ**
   
   1. ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`

2. สร้างบริการหลักสำหรับ Customer Insights ด้วยโมดูล Azure AD PowerShell

   1. ในหน้าต่าง PowerShell ให้ป้อน `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` แทนที่ *[รหัสไดเรกทอรีของคุณ]* ด้วยรหัสไดเรกทอรีจริงของการสมัครใช้งาน Azure ที่คุณต้องการสร้างบริการหลัก พารามิเตอร์ชื่อสภาพแวดล้อม `AzureEnvironmentName` เป็นตัวเลือก
  
   1. ป้อน `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` คำสั่งนี้จะสร้างบริการหลักสำหรับ Customer Insights ในการสมัครใช้งาน Azure ที่เลือก 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ให้สิทธิ์แก่บริการหลักในการเข้าถึงบัญชีที่เก็บข้อมูล

ไปที่พอร์ทัล Azure เพื่อให้สิทธิ์กับบริการหลักสำหรับบัญชีที่เก็บข้อมูลที่คุณต้องการใช้ใน Customer Insights

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

1. เปิดบัญชีที่เก็บข้อมูลที่คุณต้องการให้บริการหลักสำหรับ Customer Insights สามารถเข้าถึงได้

1. ในบานหน้าต่างด้านซ้าย เลือก **การควบคุมการเข้าถึง (IAM)** แล้วจากนั้น เลือก **เพิ่ม** > **เพิ่มการกำหนดบทบาท**

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ภาพหน้าจอที่แสดงพอร์ทัล Azure ขณะที่เพิ่มการกำหนดบทบาท":::

1. บนบานหน้าต่าง **เพิ่มการกำหนดบทบาท** ตั้งค่าคุณสมบัติต่อไปนี้:
   - บทบาท: **ผู้สนับสนุนข้อมูล Blob ของการจัดเก็บ**
   - กำหนดการเข้าถึง: **ผู้ใช้,กลุ่ม หรือบริการหลัก**
   - เลือกสมาชิก: **Dynamics 365 AI สำหรับ Customer Insights** ([บริการหลัก](#create-a-new-service-principal) ที่คุณสร้างไว้ก่อนหน้าในขั้นตอนนี้)

1.  เลือก **ตรวจสอบ + กำหนด**

โดยอาจใช้เวลาถึง 15 นาทีในการเผยแพร่การเปลี่ยนแปลง

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>ป้อนรหัสทรัพยากร Azure หรือรายละเอียดการสมัครใช้งาน Azure ในเอกสารแนบบัญชีที่เก็บข้อมูลของ Customer Insights

คุณสามารถแนบบัญชี Data Lake Storage ใน Customer Insights เพื่อ [เก็บข้อมูลเอาต์พุต](manage-environments.md) หรือ [ใช้เป็นแหล่งข้อมูล](connect-dataverse-managed-lake.md) ตัวเลือกนี้ทำให้คุณสามารถเลือกระหว่างวิธีการแบบอิงตามทรัพยากรหรือแบบอิงตามการสมัครใช้งาน โดยขึ้นอยู่กับวิธีการที่คุณเลือก ให้ทำตามกระบวนงานในส่วนใดส่วนหนึ่งต่อไปนี้

### <a name="resource-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามทรัพยากร

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณ และเปิดบัญชีที่เก็บข้อมูล

1. ในบานหน้าต่างด้านซ้าย ไปที่ **การตั้งค่า** > **คุณสมบัติ**

1. คัดลอกค่ารหัสทรัพยากรบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="คัดลอกรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::

1. ใน Customer Insights ให้ใส่รหัสทรัพยากรในฟิลด์ทรัพยากรที่แสดงบนหน้าจอการเชื่อมต่อบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::   

1. ทำตามขั้นตอนที่เหลือใน Customer Insights เพื่อแนบบัญชีที่เก็บข้อมูล

### <a name="subscription-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามการสมัครใช้งาน

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณ และเปิดบัญชีที่เก็บข้อมูล

1. ในบานหน้าต่างด้านซ้าย ไปที่ **การตั้งค่า** > **คุณสมบัติ**

1. ตรวจสอบ **การสมัครใช้งาน**, **กลุ่มทรัพยากร** และ **ชื่อ** ของบัญชีที่เก็บข้อมูล เพื่อให้แน่ใจว่าคุณได้เลือกค่าที่ถูกต้องใน Customer Insights

1. ใน Customer Insights เลือกค่าสำหรับฟิลด์ที่เกี่ยวข้องเมื่อแนบบัญชีที่เก็บข้อมูล

1. ทำตามขั้นตอนที่เหลือใน Customer Insights เพื่อแนบบัญชีที่เก็บข้อมูล


[!INCLUDE [footer-include](includes/footer-banner.md)]