---
title: กำหนดการตั้งค่าความปลอดภัย
description: เรียนรู้เกี่ยวกับการตั้งค่าความปลอดภัยใน Dynamics 365 Customer Insights
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246085"
---
# <a name="configure-security-settings"></a>กำหนดการตั้งค่าความปลอดภัย

จัดการคีย์ API, เข้าถึงข้อมูลลูกค้า และตั้งค่า Azure Private Link

## <a name="manage-api-keys"></a>จัดการคีย์ API

ดูและจัดการคีย์ที่จะใช้ [Customer Insights API](apis.md) กับข้อมูลในสภาพแวดล้อมของคุณ

1. ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** และเลือกแท็บ **API**

1. หากไม่ได้ตั้งค่าการเข้าถึงสภาพแวดล้อมของ API ให้เลือก **เปิดใช้งาน** หรือหากต้องการบล็อก API ไม่ให้เข้าถึงสภาพแวดล้อม ให้เลือก **ปิดใช้งาน** และยืนยัน

1. จัดการคีย์ API หลักและรอง:

   1. หากต้องการแสดงคีย์ API หลักหรือรอง ให้เลือกเครื่องหมาย **แสดง**

   1. หากต้องการคัดลอกคีย์ API หลักหรือรอง ให้เลือกเครื่องหมาย **คัดลอก**

   1. หากต้องการสร้างคีย์ API หลักหรือรองใหม่ ให้เลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่**

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>เข้าถึงข้อมูลลูกค้าอย่างปลอดภัยด้วย Customer Lockbox (พรีวิว)

Customer Insights ใช้ความสามารถของ Power Platform Customer Lockbox Customer Lockbox มีส่วนติดต่อเพื่อตรวจสอบและอนุมัติ (หรือปฏิเสธ) คำขอเข้าถึงข้อมูล คำขอเหล่านี้เกิดขึ้นเมื่อจำเป็นต้องเข้าถึงข้อมูลสำหรับข้อมูลลูกค้าเพื่อแก้ไขกรณีการสนับสนุน ในการใช้คุณลักษณะนี้ Customer Insights จะต้องมีการเชื่อมต่อกับสภาพแวดล้อม Microsoft Dataverse ในผู้เช่าของคุณ

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Customer Lockbox โปรดดู [สรุป](/power-platform/admin/about-lockbox#summary) ของ Power Platform Customer Lockbox บทความนี้ยังอธิบายถึง [เวิร์กโฟลว์](/power-platform/admin/about-lockbox#workflow) และ [การติดตั้ง](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) ที่จำเป็นเพื่อเปิดใช้งาน Customer Lockbox

> [!IMPORTANT]
> ผู้ดูแลระบบส่วนกลางสำหรับ Power Platform หรือผู้ดูแลระบบ Power Platform สามารถอนุมัติคำขอ Customer Lockbox ที่ออกให้กับ Customer Insights ได้

## <a name="set-up-an-azure-private-link"></a>ตั้งค่า Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) ให้ Customer Insights เชื่อมต่อกับบัญชี Azure Data Lake Storage ของคุณผ่านปลายทางส่วนตัวในเครือข่ายเสมือนของคุณ สำหรับข้อมูลในบัญชีที่เก็บข้อมูลซึ่งไม่ได้เปิดเผยต่ออินเทอร์เน็ตสาธารณะ Private Link จะเปิดใช้งานการเชื่อมต่อไปยังเครือข่ายที่ถูกจำกัดนั้น

> [!IMPORTANT]
> ข้อกำหนดบทบาทขั้นต่ำในการตั้งค่าการเชื่อมต่อ Private Link:
>
> - Customer Insights: ผู้ดูแลระบบ
> - บทบาทภายในของ Azure: [ผู้สนับสนุนในบัญชีที่เก็บข้อมูล](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - สิทธิ์สำหรับบทบาท Azure ที่กำหนดเอง: [Microsoft.Storage/storageAccounts/read และ Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. ใน Customer Insights ให้ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** และเลือกแท็บ **Private Link**

1. เลือก **เพิ่ม Private Link**

   บานหน้าต่าง **เพิ่ม Private Link** จะแสดงรายการบัญชีที่เก็บข้อมูลจากผู้เช่าของคุณที่คุณมีสิทธิ์ดู

1. เลือก การสมัครใช้งาน กลุ่มทรัพยากร และบัญชีที่เก็บข้อมูล

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. เลือก **บันทึก**

1. ไปที่บัญชี Data Lake Storage ของคุณและเปิดลิงก์ที่แสดงบนหน้าจอ

1. อนุมัติ Private Link


[!INCLUDE [footer-include](includes/footer-banner.md)]
