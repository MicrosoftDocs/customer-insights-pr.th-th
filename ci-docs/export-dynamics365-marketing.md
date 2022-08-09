---
title: ส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Marketing (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Dynamics 365 Marketing
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196647"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Dynamics 365 Marketing (พรีวิว)

ใช้ [เซ็กเมนต์](segments.md) เพื่อสร้างการส่งเสริมการขายและติดต่อกลุ่มเฉพาะของลูกค้าด้วย [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

หากคุณกำลังใช้ความสามารถใหม่ของ Dynamics 365 Marketing สำหรับกระบวนการปฏิบัติการของการเดินทางของลูกค้าแบบเรียลไทม์ในองค์กร Dataverse คุณไม่จำเป็นต้องสร้างการส่งออกมาตรฐานไปยัง Dynamics 365 Marketing ผู้ติดต่อและเซ็กเมนต์จาก Customer Insights สามารถใช้งานได้โดยตรงใน Dynamics 365 Marketing หลังจากเชื่อมต่อ Marketing และ Customer Insights ก่อนที่คุณจะลบการส่งออกที่มีอยู่ ให้ตรวจสอบคู่มือเกี่ยวกับ [วิธีการเชื่อมต่อ Customer Insights และการประสานรวมการเดินทางของลูกค้า Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="prerequisite"></a>ข้อกำหนดเบื้องต้น

ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Marketing ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Marketing ได้ อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Marketing โดยใช้ Microsoft Dataverse](connect-dataverse-managed-lake.md)

> [!NOTE]
> การส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Marketing จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Marketing เรกคอร์ดผู้ติดต่อจาก Marketing ต้องรับเข้ามาใน Customer Insights และใช้เป็นแหล่งข้อมูล นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแมปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้

## <a name="set-up-connection-to-marketing"></a>ตั้งค่าการเชื่อมต่อไปยัง Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Dynamics 365 Marketing**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน URL Marketing ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**

1. ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Marketing

1. แมปฟิลด์รหัสผู้ติดต่อในเอนทิตีลูกค้ากับรหัสผู้ติดต่อของ Dynamics 365

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Dynamics 365 Marketing ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกฟิลด์รหัสผู้ติดต่อในเอนทิตีลูกค้าที่ตรงกับรหัสผู้ติดต่อของ Dynamics 365

1. เลือกเซ็กเมนต์ที่คุณต้องการส่งออก

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
