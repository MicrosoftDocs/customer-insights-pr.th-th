---
title: การตั้งค่าความปลอดภัยใน Customer Insights
description: เรียนรู้เกี่ยวกับการตั้งค่าความปลอดภัยใน Dynamics 365 Customer Insights
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947438"
---
# <a name="security-settings-in-customer-insights"></a>การตั้งค่าความปลอดภัยใน Customer Insights

หน้า **ความปลอดภัย** แสดงรายการตัวเลือกเพื่อกำหนดค่าสิทธิ์ของผู้ใช้และคุณลักษณะที่ช่วยทำให้ Dynamics 365 Customer Insights ปลอดภัยยิ่งขึ้น เฉพาะผู้ดูแลระบบเท่านั้นที่สามารถเข้าถึงหน้านี้ได้

ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** เพื่อกำหนดการตั้งค่า

หน้า **ความปลอดภัย** ประกอบด้วยแท็บต่อไปนี้:

- [ผู้ใช้](#users-tab)
- [APIs](#apis-tab)
- [ลิงก์ส่วนตัว](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [เข้าถึงข้อมูลลูกค้าอย่างปลอดภัยด้วย Customer Lockbox (พรีวิว)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>แท็บผู้ใช้

การเข้าถึง Customer Insights จำกัดเฉพาะผู้ใช้ในองค์กรของคุณที่ผู้ดูแลระบบเพิ่มลงในแอปพลิเคชันเท่านั้น แท็บ **ผู้ใช้** ช่วยคุณจัดการการเข้าถึงของผู้ใช้และสิทธิ์ของพวกเขา สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ของผู้ใช้](permissions.md)

## <a name="apis-tab"></a>แท็บ API

ดูและจัดการคีย์ที่จะใช้ [Customer Insights API](apis.md) กับข้อมูลสภาพแวดล้อมของคุณ

คุณสามารถสร้างคีย์หลักและคีย์รองใหม่ได้โดยเลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่** 

ในการบล็อก API ไม่ให้เข้าถึงสภาพแวดล้อม ให้เลือก **ปิดใช้งาน** หากปิดใช้งาน API คุณสามารถเลือก **เปิดใช้งาน** ให้สิทธิ์การเข้าถึงอีกครั้งได้

## <a name="private-links-tab"></a>แท็บลิงก์ส่วนตัว

[Azure Private Link](/azure/private-link/private-link-overview) ให้ Customer Insights เชื่อมต่อกับบัญชี Azure Data Lake Storage ของคุณผ่านปลายทางส่วนตัวในเครือข่ายเสมือนของคุณ สำหรับข้อมูลในบัญชีที่เก็บข้อมูลซึ่งไม่ได้เปิดเผยต่ออินเทอร์เน็ตสาธารณะ ลิงก์ส่วนตัวจะเปิดใช้งานการเชื่อมต่อไปยังเครือข่ายที่ถูกจำกัดนั้น

> [!IMPORTANT]
> ข้อกำหนดบทบาทขั้นต่ำในการตั้งค่าการเชื่อมต่อลิงก์ส่วนตัว:
>
> - Customer Insights: ผู้ดูแลระบบ
> - บทบาทภายในของ Azure: [ผู้สนับสนุนในบัญชีที่เก็บข้อมูล](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - สิทธิ์สำหรับบทบาท Azure ที่กำหนดเอง: [Microsoft.Storage/storageAccounts/read และ Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

การตั้งค่าลิงก์ส่วนตัวใน Customer Insights เป็นกระบวนการแบบสองขั้นตอน ขั้นแรก คุณเริ่มต้นการสร้างลิงก์ส่วนตัวจาก **ผู้ดูแลระบบ** > **ความปลอดภัย** > **ลิงก์ส่วนตัว** ใน Customer Insights บานหน้าต่าง **เพิ่มลิงก์ส่วนตัว** จะแสดงรายการบัญชีที่เก็บข้อมูลจากผู้เช่าของคุณที่คุณมีสิทธิ์ดู เลือกบัญชีที่เก็บข้อมูลและให้ความยินยอมในการสร้างลิงก์ส่วนตัว

ถัดไป คุณต้องอนุมัติลิงก์ส่วนตัวที่ฝั่งบัญชี Data Lake Storage เปิดลิงก์ที่แสดงบนหน้าจอเพื่ออนุมัติลิงก์ส่วนตัวใหม่

## <a name="key-vault-tab"></a>แท็บ Key Vault

แท็บ **Key Vault** ให้คุณสามารถเชื่อมโยงและจัดการ [Azure Key Vault](/azure/key-vault/general/basic-concepts) ของคุณเองกับสภาพแวดล้อมได้
สามารถใช้ Key Vault เฉพาะเพื่อจัดเตรียมและใช้ข้อมูลลับในขอบเขตการปฏิบัติตามข้อกำหนดขององค์กร Customer Insights สามารถใช้ข้อมูลลับใน Azure Key Vault เพื่อ [ตั้งค่าการเชื่อมต่อ](connections.md) กับระบบของบุคคลที่สาม

สำหรับข้อมูลเพิ่มเติม โปรดดู [การใช้ Azure Key Vault ของคุณเอง](use-azure-key-vault.md)

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>เข้าถึงข้อมูลลูกค้าอย่างปลอดภัยด้วย Customer Lockbox (พรีวิว)

Customer Insights กำลังใช้ความสามารถของ Power Platform Customer Lockbox Customer Lockbox มีส่วนติดต่อเพื่อตรวจสอบและอนุมัติ (หรือปฏิเสธ) คำขอเข้าถึงข้อมูล คำขอเหล่านี้เกิดขึ้นเมื่อจำเป็นต้องเข้าถึงข้อมูลสำหรับข้อมูลลูกค้าเพื่อแก้ไขกรณีการสนับสนุน ในการใช้คุณลักษณะนี้ Customer Insights จะต้องมีการเชื่อมต่อกับสภาพแวดล้อม Microsoft Dataverse ในผู้เช่าของคุณ

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Customer Lockbox โปรดดู [สรุป](/power-platform/admin/about-lockbox#summary) ของ Power Platform Customer Lockbox บทความนี้ยังอธิบายถึง [เวิร์กโฟลว์](/power-platform/admin/about-lockbox#workflow) และ [การติดตั้ง](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) ที่จำเป็นเพื่อเปิดใช้งาน Customer Lockbox

> [!IMPORTANT]
> ผู้ดูแลระบบส่วนกลางสำหรับ Power Platform หรือผู้ดูแลระบบ Power Platform สามารถอนุมัติคำขอ Customer Lockbox ที่ออกให้กับ Customer Insights ได้

[!INCLUDE [footer-include](includes/footer-banner.md)]
