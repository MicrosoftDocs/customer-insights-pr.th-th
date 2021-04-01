---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Sales
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Sales
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598132"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>ตัวเชื่อมต่อสำหรับ Dynamics 365 Sales (แสดงตัวอย่าง)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

ใช้ข้อมูลลูกค้าของคุณเพื่อสร้างรายชื่อเพื่อทำการตลาด ติดตามลำดับงาน และนำเสนอโปรโมชันด้วย Dynamics 365 Sales

## <a name="prerequisite"></a>ข้อกำหนดเบื้องต้น

1. ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Sales ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Sales ได้ อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Sales โดยใช้ Common Data Services](connect-power-query.md)

   > [!NOTE]
   > การส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Sales จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Sales ต้องนำเข้าเรกคอร์ดผู้ติดต่อจาก Sales ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และต้องใช้เป็นแหล่งข้อมูล นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแม็ปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]