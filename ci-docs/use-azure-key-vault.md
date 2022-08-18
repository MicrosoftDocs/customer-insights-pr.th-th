---
title: นำ Azure Key Vault ของคุณมาเอง (พรีวิว)
description: เรียนรู้วิธีการกำหนดค่า Customer Insights เพื่อใช้ Azure Key Vault ของคุณจัดการข้อมูลลับ
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246178"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>นำ Azure Key Vault ของคุณมาเอง (พรีวิว)

การเชื่อมโยง [Azure Key Vault](/azure/key-vault/general/basic-concepts) เฉพาะกับสภาพแวดล้อม Customer Insights ช่วยให้องค์กรมีคุณสมบัติเป็นไปตามข้อกำหนดในการปฏิบัติตาม

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>เชื่อมโยง Key Vault กับสภาพแวดล้อม Customer Insights

ตั้งค่า Key Vault เฉพาะเพื่อจัดเตรียมและใช้ข้อมูลลับในขอบเขตการปฏิบัติตามข้อกำหนดขององค์กร

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- การสมัครใช้งาน Azure ที่ใช้งานอยู่

- บทบาท [ผู้ดูแลระบบ](permissions.md#admin) [ที่กำหนด](permissions.md#add-users) ใน Customer Insights

- บทบาท [ผู้มีส่วนร่วม](/azure/role-based-access-control/built-in-roles#contributor) และ [ผู้ดูแลระบบการเข้าถึงของผู้ใช้](/azure/role-based-access-control/built-in-roles#user-access-administrator) บน key vault หรือกลุ่มทรัพยากรที่ key vault อยู่ สำหรับข้อมูลเพิ่มเติม ไปที่ [เพิ่มหรือลบการกำหนดบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal) หากคุณไม่มีบทบาทผู้ดูแลระบบการเข้าถึงของผู้ใช้ใน key vault ให้ตั้งค่าสิทธิ์ในการควบคุมการเข้าถึงตามบทบาทสำหรับหลักบริการของ Azure สำหรับ Dynamics 365 Customer Insights แยกจากกัน ทำตามขั้นตอนเพื่อ [ใช้หลักบริการของ Azure](connect-service-principal.md) สำหรับ key vault ที่ควรถูกเชื่อมโยง

- Key Vault ต้อง **ปิดใช้งาน** ไฟร์วอลล์ Key Vault

- Key Vault อยู่ใน [ตำแหน่งที่ตั้ง Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) เดียวกันกับสภาพแวดล้อม Customer Insights ใน Customer Insights ให้ไปที่ **ผู้ดูแลระบบ** > **ระบบ** และแท็บ **เกี่ยวกับ** เพื่อดูภูมิภาคของสภาพแวดล้อม

### <a name="recommendations"></a>การแนะนำ

- [ใช้ Key Vault ที่แยกต่างหากหรือเฉพาะ](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) ที่มีเฉพาะข้อมูลลับที่จำเป็นสำหรับ Customer Insights

- ปฏิบัติตาม [แนวทางปฏิบัติที่ดีที่สุดในการใช้ Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) สำหรับตัวเลือกการเข้าถึงการควบคุม, การสำรองข้อมูล, การตรวจสอบ, และการกู้คืน

### <a name="link-a-key-vault-to-the-environment"></a>เชื่อมโยง Key Vault กับสภาพแวดล้อม

1. ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** และเลือกแท็บ **Key Vault**
1. บนไทล์ **Key Vault** เลือก **ตั้งค่า**
1. เลือก **การสมัครใช้งาน**
1. เลือก Key Vault จากรายการแบบหล่นลง **Key Vault** หากมี Key Vault มากเกินไป ให้เลือกกลุ่มทรัพยากรเพื่อจำกัดผลการค้นหา
1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**
1. เลือก **บันทึก**

ไทล์ **Key Vault** แสดงชื่อ key vault ที่เชื่อมโยง การสมัครใช้งาน และกลุ่มทรัพยากร ซึ่งพร้อมที่จะใช้ในการตั้งค่าการเชื่อมต่อ
สำหรับรายละเอียดเกี่ยวกับสิทธิ์สำหรับ key vault ที่ให้กับ Customer Insights ให้ไปที่ [สิทธิ์ที่ให้สำหรับ key vault](#permissions-granted-on-the-key-vault)

## <a name="use-the-key-vault-in-the-connection-setup"></a>ใช้ key vault ในการตั้งค่าการเชื่อมต่อ

เมื่อ [ตั้งค่าการเชื่อมต่อ](connections.md) กับระบบของ [บุคคลที่สามที่รองรับ](#supported-connection-types) ให้ใช้ข้อมูลลับจาก Key Vault ที่เชื่อมโยงเพื่อกำหนดค่าการเชื่อมต่อ

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**
1. เลือก **เพิ่มการเชื่อมต่อ**
1. สำหรับชนิดการเชื่อมต่อที่รองรับ ตัวสลับ **ใช้ Key Vault** พร้อมใช้งาน หากคุณเชื่อมโยง Key Vault
1. แทนที่จะป้อนข้อมูลลับด้วยตนเอง ให้เลือกชื่อข้อมูลลับที่ชี้ไปที่ข้อมูลลับใน key vault ได้

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="บานหน้าต่างการเชื่อมต่อกับการเชื่อมต่อ SFTP ที่ใช้ข้อมูลลับของ Key Vault":::

1. เลือก **บันทึก** เพื่อสร้างการเชื่อมต่อ

## <a name="supported-connection-types"></a>ชนิดการเชื่อมต่อที่สนับสนุน

การเชื่อมต่อ [การส่งออก](export-destinations.md) ต่อไปนี้ได้รับการสนับสนุน:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>สิทธิ์ที่ให้สำหรับ key vault

มีการให้สิทธิ์ต่อไปนี้แก่ Customer Insights สำหรับ key vault ที่มีการเชื่อมโยง หาก [นโยบายการเข้าถึง Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) หรือ [การควบคุมการเข้าถึงตามบทบาท Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ถูกเปิดใช้งาน

### <a name="key-vault-access-policy"></a>นโยบายการเข้าถึง Key Vault

| พิมพ์ข้อความ        | สิทธิการได้รับอนุญาต          |
| ----------- | -------------------- |
| กุญแจ         | [รับคีย์](/rest/api/keyvault/keys/get-keys/get-keys), [รับคีย์](/rest/api/keyvault/keys/get-key/get-key)                                 |
| ข้อมูลลับ      | [รับข้อมูลลับ](/rest/api/keyvault/secrets/get-secrets/get-secrets), [รับข้อมูลลับ](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| ใบรับรอง | [รับใบรับรอง](/rest/api/keyvault/certificates/get-certificates/get-certificates), [รับใบรับรอง](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

ค่าก่อนหน้าเป็นค่าต่ำสุดในการแสดงรายการและอ่านระหว่างการดำเนินการ

### <a name="azure-role-based-access-control"></a>การควบคุมการเข้าถึงตามบทบาท Azure

ระบบจะเพิ่ม [บทบาทผู้อ่าน Key Vault และผู้ใช้ข้อมูลลับ Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ให้กับ Customer Insights

## <a name="frequently-asked-questions"></a>คำถามที่ถามบ่อย

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights สามารถเขียนข้อมูลลับหรือเขียนทับข้อมูลลับลงใน key vault ได้หรือไม่

ไม่ มีการมอบเฉพาะสิทธิ์ในการอ่านและแสดงรายการที่ระบุไว้ใน [สิทธิ์ที่ได้รับมอบ](#permissions-granted-on-the-key-vault) ให้กับ Customer Insights ระบบไม่สามารถเพิ่ม, ลบ, หรือเขียนทับข้อมูลลับใน key vault นอกจากนี้ นั่นคือเหตุผลที่คุณไม่สามารถป้อนข้อมูลประจำตัว เมื่อการเชื่อมต่อใช้ Key Vault

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>ฉันสามารถเปลี่ยนการเชื่อมต่อจากการใช้ข้อมูลลับของ Key Vault เป็นการรับรองความถูกต้องเริ่มต้นได้หรือไม่

ไม่ คุณไม่สามารถเปลี่ยนกลับเป็นการเชื่อมต่อเริ่มต้นได้ หลังจากที่คุณกำหนดค่าโดยใช้ข้อมูลลับจาก Key Vault ที่มีการเชื่อมโยง สร้างการเชื่อมต่อที่แยกต่างหาก และลบการเชื่อมต่อเก่า หากคุณไม่ต้องการอีกต่อไป

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>ฉันจะเพิกถอนการเข้าถึง key vault สำหรับ Customer Insights ได้อย่างไร

หาก [นโยบายการเข้าถึง Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) หรือ [การควบคุมการเข้าถึงตามบทบาท Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ถูกเปิดใช้งาน ให้ลบสิทธิ์สำหรับบริการหลัก `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ที่มีชื่อว่า `Dynamics 365 AI for Customer Insights` การเชื่อมต่อทั้งหมดที่ใช้ key vault จะหยุดทำงาน

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>ข้อมูลลับที่ใช้ในการเชื่อมต่อถูกลบออกจาก key vault ฉันควรทำอย่างไร

การแจ้งเตือนจะปรากฏใน Customer Insights เมื่อไม่สามารถเข้าถึงข้อมูลลับที่กำหนดค่าจาก key vault ได้อีกต่อไป เปิดใช้งาน [ลบออกชั่วคราว](/azure/key-vault/general/soft-delete-overview) บน key vault เพื่อกู้คืนข้อมูลลับ หากถูกลบออกโดยไม่ได้ตั้งใจ

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>การเชื่อมต่อใช้งานไม่ได้ แต่ข้อมูลลับของฉันอยู่ใน Key Vault อะไรอาจเป็นสาเหตุ

การแจ้งเตือนจะปรากฏใน Customer Insights เมื่อไม่สามารถเข้าถึง key vault สาเหตุอาจเป็น:

- สิทธิ์สำหรับบริการหลักของ Customer Insights ถูกลบออก ต้องมีการกู้คืนด้วยตนเอง

- ไฟร์วอลล์บน key vault ถูกเปิดใช้งานอยู่ ต้องปิดใช้งานไฟร์วอลล์เพื่อทำให้ key vault สามารถเข้าถึงได้สำหรับ Customer Insights อีกครั้ง
