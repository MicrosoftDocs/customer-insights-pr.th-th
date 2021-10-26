---
title: นำ Azure Key Vault ของคุณมาเองเพื่อจัดการข้อมูลลับ
description: เรียนรู้วิธีการตั้งค่าคอนฟิก Customer Insights เพื่อใช้ Azure key vault ของคุณเอง
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606144"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>นำ Azure Key Vault ของคุณมาเอง (พรีวิว)

การเชื่อมโยง [Azure Key Vault](/azure/key-vault/general/basic-concepts) โดยเฉพาะกับสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชม ช่วยให้องค์กรเป็นไปตามข้อกำหนดในการปฏิบัติตาม
สามารถใช้ Key Vault เฉพาะเพื่อจัดเตรียมและใช้ข้อมูลลับในขอบเขตการปฏิบัติตามข้อกำหนดขององค์กร ข้อมูลเชิงลึกของผู้ชมสามารถใช้ข้อมูลลับใน Azure Key Vault เพื่อ [ตั้งค่าการเชื่อมต่อ](connections.md) กับระบบของบุคคลที่สาม

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>เชื่อมโยง Key Vault กับสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชม

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ในการตั้งค่าคอนฟิก key vault ในข้อมูลเชิงลึกของผู้ชม ต้องเป็นไปตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณต้องมีการสมัครใช้งาน Azure ที่ใช้งานอยู่

- คุณมีบทบาท [ผู้ดูแลระบบ](permissions.md#administrator) ในข้อมูลเชิงลึกของผู้ชม เรียนรู้เพิ่มเติมเกี่ยวกับ [สิทธิ์ของผู้ใช้ในข้อมูลเชิงลึกของผู้ชม](permissions.md#assign-roles-and-permissions).

- คุณมีบทบาท [ผู้มีส่วนร่วม](/azure/role-based-access-control/built-in-roles#contributor) และ [ผู้ดูแลระบบการเข้าถึงของผู้ใช้](/azure/role-based-access-control/built-in-roles#user-access-administrator) บน key vault หรือกลุ่มทรัพยากรที่ key vault อยู่ สำหรับข้อมูลเพิ่มเติม ไปที่ [เพิ่มหรือลบการกำหนดบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal) หากคุณไม่มีบทบาทผู้ดูแลระบบการเข้าถึงของผู้ใช้ใน key vault คุณต้องตั้งค่าสิทธิ์ในการควบคุมการเข้าถึงตามบทบาทสำหรับหลักบริการของ Azure สำหรับ Dynamics 365 Customer Insights โดยแยกจากกัน ทำตามขั้นตอนเพื่อ [ใช้หลักบริการของ Azure](connect-service-principal.md) สำหรับ key vault ที่ควรถูกเชื่อมโยง

- Key Vault ต้อง **ปิดใช้งาน** ไฟร์วอลล์ Key Vault

- Key Vault อยู่ใน [ตำแหน่งที่ตั้ง Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) เดียวกันกับสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชม ภูมิภาคของสภาพแวดล้อมในข้อมูลเชิงลึกของผู้ชมถูกแสดงรายการอยู่ภายใต้ **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ** > **ภูมิภาค**

### <a name="link-a-key-vault-to-the-environment"></a>เชื่อมโยง Key Vault กับสภาพแวดล้อม

1. ไปที่ **ผู้ดูแลระบบ** > **ระบบ** และจากนั้น เลือกแท็บ **การรักษาความปลอดภัย**
1. บนไทล์ **Key Vault** เลือก **ตั้งค่า**
1. เลือก **การสมัครใช้งาน**
1. เลือก Key Vault จากรายการแบบหล่นลง **Key Vault** หากมีการแสดง Key Vault มากเกินไป ให้เลือกกลุ่มทรัพยากรเพื่อจำกัดผลการค้นหา
1. ยอมรับคำชี้แจง **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**
1. เลือก **บันทึก**

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="ขั้นตอนในการตั้งค่า Key Vault ที่เชื่อมโยงในข้อมูลเชิงลึกของผู้ชม":::

ขณะนี้ไทล์ **Key Vault** แสดงชื่อ key vault ที่เชื่อมโยง, กลุ่มทรัพยากร, และการสมัครใช้งาน ซึ่งพร้อมที่จะใช้ในการตั้งค่าการเชื่อมต่อ
สำหรับรายละเอียดเกี่ยวกับสิทธิ์บน key vault ที่ให้กับข้อมูลเชิงลึกของผู้ชม ให้ไปที่ [สิทธิ์บน key vault ที่ให้กับข้อมูลเชิงลึกของผู้ชม](#permissions-granted-on-the-key-vault-to-audience-insights) ในบทความนี้ภายหลัง

## <a name="use-the-key-vault-in-the-connection-setup"></a>ใช้ key vault ในการตั้งค่าการเชื่อมต่อ

เมื่อ [ตั้งค่าการเชื่อมต่อ](connections.md) กับระบบของบุคคลที่สาม คุณสามารถใช้ข้อมูลลับจาก Key Vault ที่เชื่อมโยงเพื่อตั้งค่าคอนฟิกการเชื่อมต่อได้

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**
1. เลือก **เพิ่มการเชื่อมต่อ**
1. สำหรับชนิดการเชื่อมต่อที่รองรับ ตัวสลับ **ใช้ Key Vault** พร้อมใช้งาน หากคุณเชื่อมโยง Key Vault
1. แทนที่จะป้อนข้อมูลลับด้วยตนเอง คุณสามารถเลือกชื่อข้อมูลลับที่ชี้ไปที่ข้อมูลลับใน key vault ได้

:::image type="content" source="media/use-key-vault-secret.png" alt-text="บานหน้าต่างการเชื่อมต่อกับการเชื่อมต่อ SFTP ที่ใช้ข้อมูลลับของ Key Vault":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>ให้สิทธิ์บน key vault แก่ข้อมูลเชิงลึกของผู้ชม

มีการให้สิทธิ์ต่อไปนี้แก่ข้อมูลเชิงลึกของผู้ชม บน key vault ที่มีการเชื่อมโยง หาก [นโยบายการเข้าถึง Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) หรือ [การควบคุมการเข้าถึงตามบทบาท Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ถูกเปิดใช้งาน

### <a name="key-vault-access-policy"></a>นโยบายการเข้าถึง Key Vault

| พิมพ์ข้อความ        | สิทธิการได้รับอนุญาต          |
| ----------- | -------------------- |
| กุญแจ         | [รับคีย์](/rest/api/keyvault/get-keys), [รับคีย์](/rest/api/keyvault/get-key)                                 |
| ข้อมูลลับ      | [รับข้อมูลลับ](/rest/api/keyvault/get-secrets), [รับข้อมูลลับ](/rest/api/keyvault/get-secret)                     |
| ใบรับรอง | [รับใบรับรอง](/rest/api/keyvault/get-certificates), [รับใบรับรอง](/rest/api/keyvault/get-certificate) |

ค่าก่อนหน้าเป็นค่าต่ำสุดในการแสดงรายการและอ่านระหว่างการดำเนินการ

### <a name="azure-role-based-access-control"></a>การควบคุมการเข้าถึงตามบทบาท Azure

บทบาทผู้ใช้ Key Vault Reader และ Key Vault Secrets จะถูกเพิ่มสำหรับข้อมูลเชิงลึกของผู้ชม สำหรับรายละเอียดเกี่ยวกับบทบาทเหล่านี้ ไปที่ [บทบาทในตัวของ Azure สำหรับการดำเนินการระนาบข้อมูล Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli)

## <a name="recommendations"></a>การแนะนำ

- ใช้ Key Vault ที่แยกต่างหากหรือโดยเฉพาะที่มีเฉพาะข้อมูลลับที่จำเป็นสำหรับข้อมูลเชิงลึกของผู้ชม อ่านเพิ่มเติมเกี่ยวกับเหตุผลที่ [Key Vault ที่แยกต่างหากได้รับการแนะนำ](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)

- ปฏิบัติตาม [แนวทางปฏิบัติที่ดีที่สุดในการใช้ Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) สำหรับตัวเลือกการเข้าถึงการควบคุม, การสำรองข้อมูล, การตรวจสอบ, และการกู้คืน

## <a name="frequently-asked-questions"></a>คำถามที่ถามบ่อย

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>ข้อมูลเชิงลึกของผู้ชมสามารถเขียนข้อมูลลับหรือเขียนทับข้อมูลลับลงใน key vault ได้หรือไม่

ไม่ มีการมอบเฉพาะสิทธิ์ในการอ่านและแสดงรายการที่ระบุไว้ในส่วน [สิทธิ์ที่ได้รับมอบ](#permissions-granted-on-the-key-vault-to-audience-insights) ก่อนหน้าในบทความนี้แก่ข้อมูลเชิงลึกของผู้ชม ระบบไม่สามารถเพิ่ม, ลบ, หรือเขียนทับข้อมูลลับใน key vault นอกจากนี้ นั่นคือเหตุผลที่คุณไม่สามารถป้อนข้อมูลประจำตัว เมื่อการเชื่อมต่อใช้ Key Vault

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>ฉันสามารถเปลี่ยนการเชื่อมต่อจากการใช้ข้อมูลลับของ Key Vault เป็นการรับรองความถูกต้องเริ่มต้นได้หรือไม่

ไม่ คุณไม่สามารถเปลี่ยนกลับเป็นการเชื่อมต่อเริ่มต้นได้ หลังจากที่คุณตั้งค่าคอนฟิกโดยใช้ข้อมูลลับจาก Key Vault ที่มีการเชื่อมโยง สร้างการเชื่อมต่อที่แยกต่างหาก และลบการเชื่อมต่อเก่า หากคุณไม่ต้องการอีกต่อไป

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>ฉันจะเพิกถอนการเข้าถึง key vault สำหรับข้อมูลเชิงลึกของผู้ชมได้อย่างไร

โดยขึ้นอยู่กับว่า [นโยบายการเข้าถึง Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) หรือ [การควบคุมการเข้าถึงตามบทบาท Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) ถูกเปิดใช้งานอยู่หรือไม่ คุณต้องลบสิทธิ์สำหรับบริการหลัก `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ที่มีชื่อว่า `Dynamics 365 AI for Customer Insights` การเชื่อมต่อทั้งหมดที่ใช้ key vault จะหยุดทำงาน

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>ข้อมูลลับที่ใช้ในการเชื่อมต่อถูกลบออกจาก key vault ฉันควรทำอย่างไร

การแจ้งเตือนจะปรากฏในข้อมูลเชิงลึกของผู้ชม เมื่อไม่สามารถเข้าถึงข้อมูลลับที่ตั้งค่าคอนฟิกจาก key vault ได้อีกต่อไป เปิดใช้งาน [ลบออกชั่วคราว](/azure/key-vault/general/soft-delete-overview) บน key vault เพื่อกู้คืนข้อมูลลับ หากถูกลบออกโดยไม่ได้ตั้งใจ

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>การเชื่อมต่อใช้งานไม่ได้ แต่ข้อมูลลับของฉันอยู่ใน Key Vault อะไรอาจเป็นสาเหตุ

การแจ้งเตือนจะปรากฏในข้อมูลเชิงลึกของผู้ชม เมื่อไม่สามารถเข้าถึง key vault สาเหตุอาจเป็น:

- สิทธิ์สำหรับบริการหลักของข้อมูลเชิงลึกของผู้ชมถูกลบออก ต้องมีการกู้คืนด้วยตนเอง

- ไฟร์วอลล์บน key vault ถูกเปิดใช้งานอยู่ ต้องปิดใช้งานไฟร์วอลล์เพื่อทำให้ key vault สามารถเข้าถึงได้สำหรับข้อมูลเชิงลึกของผู้ชมอีกครั้ง
