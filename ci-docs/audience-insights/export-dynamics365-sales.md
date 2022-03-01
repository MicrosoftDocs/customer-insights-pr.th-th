---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Sales
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Sales
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643841"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>ตัวเชื่อมต่อสำหรับ Dynamics 365 Sales (แสดงตัวอย่าง)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

ใช้ข้อมูลลูกค้าของคุณเพื่อสร้างรายชื่อเพื่อทำการตลาด ติดตามลำดับงาน และนำเสนอโปรโมชันด้วย Dynamics 365 Sales

## <a name="prerequisite"></a>ข้อกำหนดเบื้องต้น

เรกคอร์ดผู้ติดต่อ [จาก Dynamics 365 Sales ที่นำเข้าโดยใช้ Common Data Service](connect-power-query.md)

## <a name="configure-the-connector-for-sales"></a>กำหนดค่าตัวเชื่อมต่อสำหรับ Sales

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Dynamics 365 Sales** เลือก **ติดตั้ง**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**

1. ป้อน URL Sales ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**

1. ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Sales

1. แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365

1. เลือก **ถัดไป**

1. เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง
