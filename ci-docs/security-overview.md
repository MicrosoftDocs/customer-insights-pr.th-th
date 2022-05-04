---
title: การตั้งค่าความปลอดภัยใน Dynamics 365 Customer Insights
description: เรียนรู้เกี่ยวกับการตั้งค่าความปลอดภัยใน Dynamics 365 Customer Insights
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653758"
---
# <a name="security-overview-page"></a>หน้าภาพรวมของความปลอดภัย

หน้า **ความปลอดภัย** แสดงรายการตัวเลือกเพื่อกำหนดค่าสิทธิ์ของผู้ใช้และคุณลักษณะที่ช่วยทำให้ Dynamics 365 Customer Insights ปลอดภัยยิ่งขึ้น เฉพาะผู้ดูแลระบบเท่านั้นที่สามารถเข้าถึงหน้านี้ได้ 

ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** เพื่อกำหนดการตั้งค่า

หน้า **ความปลอดภัย** ประกอบด้วยแท็บต่อไปนี้:
- [ผู้ใช้](#users-tab)
- [APIs](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>แท็บผู้ใช้

การเข้าถึง Customer Insights จำกัดเฉพาะผู้ใช้ในองค์กรของคุณที่ผู้ดูแลระบบเพิ่มลงในแอปพลิเคชันเท่านั้น แท็บ **ผู้ใช้** ช่วยคุณจัดการการเข้าถึงของผู้ใช้และสิทธิ์ของพวกเขา สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ของผู้ใช้](permissions.md)

## <a name="apis-tab"></a>แท็บ API

ดูและจัดการคีย์ที่จะใช้ [Customer Insights API](apis.md) กับข้อมูลสภาพแวดล้อมของคุณ

คุณสามารถสร้างคีย์หลักและคีย์รองใหม่ได้โดยเลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่** 

ในการบล็อก API ไม่ให้เข้าถึงสภาพแวดล้อม ให้เลือก **ปิดใช้งาน** หากปิดใช้งาน API คุณสามารถเลือก **เปิดใช้งาน** ให้สิทธิ์การเข้าถึงอีกครั้งได้

## <a name="key-vault-tab"></a>แท็บ Key Vault

แท็บ **Key Vault** ให้คุณสามารถเชื่อมโยงและจัดการ [Azure Key Vault](/azure/key-vault/general/basic-concepts) ของคุณเองกับสภาพแวดล้อมได้
สามารถใช้ Key Vault เฉพาะเพื่อจัดเตรียมและใช้ข้อมูลลับในขอบเขตการปฏิบัติตามข้อกำหนดขององค์กร Customer Insights สามารถใช้ข้อมูลลับใน Azure Key Vault เพื่อ [ตั้งค่าการเชื่อมต่อ](connections.md) กับระบบของบุคคลที่สาม

สำหรับข้อมูลเพิ่มเติม โปรดดู [การใช้ Azure Key Vault ของคุณเอง](use-azure-key-vault.md)


[!INCLUDE [footer-include](includes/footer-banner.md)]
