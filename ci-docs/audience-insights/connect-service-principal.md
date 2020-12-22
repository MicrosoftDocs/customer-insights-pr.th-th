---
title: เชื่อมต่อกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลัก
description: ใช้บริการหลักของ Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อเชื่อมต่อกับที่จัดเก็บข้อมูลดิบของคุณเองเมื่อเชื่อมต่อกับข้อมูลเชิงลึกกลุ่มเป้าหมาย
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644111"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>เชื่อมต่อกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลัก Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย

เครื่องมืออัตโนมัติที่ใช้บริการ Azure ควรมีสิทธิ์ที่จำกัดไว้เสมอ แทนที่จะให้แอปพลิเคชันลงชื่อเข้าใช้ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานแบบเต็ม Azure จะเสนอบริการหลัก อ่านต่อเพื่อเรียนรู้วิธีเชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 โดยใช้บริการหลักของ Azure แทนคีย์บัญชีที่เก็บข้อมูล 

คุณสามารถใช้บริการหลักเพื่อ [เพิ่มหรือแก้ไขโฟลเดอร์ Common Data Model เป็นแหล่งข้อมูล](connect-common-data-model.md) ได้อย่างปลอดภัยหรือ [สร้างใหม่หรือปรับปรุงสภาพแวดล้อมที่มีอยู่](manage-environments.md#create-an-environment-in-an-existing-organization)

คุณต้องมีสิทธิ์ระดับผู้ดูแลระบบสำหรับการสมัครใช้งาน Azure ของคุณเพื่อสร้างบริการหลัก

## <a name="create-azure-service-principal-for-audience-insights"></a>สร้างบริการหลักของ Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย

ก่อนสร้างบริการหลักใหม่สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ตรวจสอบว่ามีอยู่แล้วในองค์กรของคุณหรือไม่

### <a name="look-for-an-existing-service-principal"></a>มองหาบริการหลักที่มีอยู่

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

2. เลือก **Azure Active Directory** จากบริการ Azure

3. ภายใต้ **จัดการ** เลือก **แอปพลิเคชัน Enterprise**

4. ค้นหารหัสแอปพลิเคชันบุคคลที่หนึ่ง `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` หรือชื่อ `Dynamics 365 AI for Customer Insights` ในข้อมูลเชิงลึกกลุ่มเป้าหมาย

5. หากคุณพบเรกคอร์ดที่ตรงกัน แสดงว่ามีบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย คุณไม่ต้องสร้างอีก
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="ภาพหน้าจอที่แสดบริการหลักที่มีอยู่":::
   
6. หากไม่มีการส่งคืนผลลัพธ์ ให้สร้างบริการหลักใหม่

### <a name="create-a-new-service-principal"></a>สร้างบริการหลักใหม่

1. ติดตั้งเวอร์ชันล่าสุดของ **Azure Active Directory PowerShell สำหรับกราฟ** สำหรับข้อมูลเพิ่มเติม โปรดดู [ติดตั้ง Azure Active Directory PowerShell สำหรับกราฟ](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)
   - บนพีซีของคุณ ให้เลือกแป้น Windows บนแป้นพิมพ์ของคุณและค้นหา **Windows PowerShell** และ **เรียกใช้ในฐานะผู้ดูแลระบบ**
   
   - ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`

2. สร้างบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายด้วยโมดูล Azure AD PowerShell
   - ในหน้าต่าง PowerShell ให้ป้อน `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` แทนที่ "รหัสผู้เช่าของคุณ" ด้วยรหัสจริงของผู้เช่าของคุณที่คุณต้องการสร้างบริการหลัก พารามิเตอร์ชื่อสภาพแวดล้อม `AzureEnvironmentName` เป็นตัวเลือก
  
   - ป้อน `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` คำสั่งนี้สร้างบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเกี่ยวกับผู้เช่าที่เลือก  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ให้สิทธิ์แก่บริการหลักในการเข้าถึงบัญชีที่เก็บข้อมูล

ไปที่พอร์ทัล Azure เพื่อให้สิทธิ์แก่บริการหลักสำหรับบัญชีที่เก็บข้อมูลที่คุณต้องการใช้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ

1. เปิดบัญชีที่เก็บข้อมูลที่คุณต้องการให้บริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเข้าถึงได้

1. เลือก **การควบคุมการเข้าถึง (IAM)** จากบานหน้าต่างนำทาง แล้วเลือก **เพิ่ม** > **เพิ่มการกำหนดบทบาท**
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ภาพหน้าจอที่แสดงพอร์ทัล Azure ขณะที่เพิ่มการกำหนดบทบาท":::
   
1. ในบานหน้าต่าง **เพิ่มการกำหนดบทบาท** ให้ตั้งค่าคุณสมบัติต่อไปนี้:
   - บทบาท: *ผู้สนับสนุนข้อมูล Blob ของการจัดเก็บ*
   - กำหนดการเข้าถึง: *ผู้ใช้,กลุ่ม หรือบริการหลัก*
   - เลือก: *Dynamics 365 AI for Customer Insights* ([บริการหลักที่คุณสร้างขึ้น](#create-a-new-service-principal))

1.  เลือก **บันทึก**

โดยอาจใช้เวลาถึง 15 นาทีในการเผยแพร่การเปลี่ยนแปลง

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>ป้อนรหัสทรัพยากร Azure หรือรายละเอียดการสมัครใช้งาน Azure ในสิ่งที่แนบมากับบัญชีที่เก็บข้อมูลกับข้อมูลเชิงลึกกลุ่มเป้าหมาย

แนบบัญชีที่เก็บข้อมูล Azure Data Lake ในข้อมูลเชิงลึกกลุ่มเป้าหมาย เพื่อ [จัดเก็บข้อมูลผลลัพธ์](manage-environments.md) หรือ [ใช้เป็นแหล่งข้อมูล](connect-common-data-service-lake.md) การเลือกตัวเลือก Azure Data Lake ช่วยให้คุณสามารถเลือกได้ระหว่างแนวทางที่อิงตามทรัพยากรหรือตามการสมัครใช้งาน

ทำตามขั้นตอนด้านล่างเพื่อให้ข้อมูลที่จำเป็นเกี่ยวกับแนวทางที่เลือก

### <a name="resounce-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามทรัพยากร

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณและเปิดบัญชีที่เก็บข้อมูล

1. ไปที่ **การตั้งค่า** > **คุณสมบัติ** บนบานหน้าต่างนำทาง

1. คัดลอกค่ารหัสทรัพยากรบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="คัดลอกรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ใส่รหัสทรัพยากรในฟิลด์ทรัพยากรที่แสดงในหน้าจอการเชื่อมต่อบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::   
   
1. ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล

### <a name="subscription-based-storage-account-connection"></a>การเชื่อมต่อบัญชีที่เก็บข้อมูลตามการสมัครใช้งาน

1. ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณและเปิดบัญชีที่เก็บข้อมูล

1. ไปที่ **การตั้งค่า** > **คุณสมบัติ** บนบานหน้าต่างนำทาง

1. ตรวจสอบ **การสมัครใช้งาน**, **กลุ่มทรัพยากร** และ **ชื่อ** ของบัญชีที่เก็บข้อมูล เพื่อให้แน่ใจว่าคุณเลือกค่าที่ถูกต้องในข้อมูลเชิงลึกกลุ่มเป้าหมาย

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้เลือกค่าหรือสำหรับฟิลด์ที่เกี่ยวข้องเมื่อแนบบัญชีที่เก็บข้อมูล

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::
   
1. ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล
