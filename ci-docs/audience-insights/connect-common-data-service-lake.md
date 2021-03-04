---
title: เชื่อมต่อกับเอนทิตีในที่จัดเก็บที่มีการจัดการของ Common Data Service
description: นำเข้าข้อมูลจากที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Common Data Service
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267837"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>เชื่อมต่อกับข้อมูลใน Data Lake ที่มีการจัดการ Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

บทความนี้ให้ข้อมูลเกี่ยวกับวิธีที่ลูกค้า Dynamics 365 ที่มีอยู่ สามารถเชื่อมต่อกับเอนทิตีเชิงวิเคราะห์ของตนได้อย่างรวดเร็วในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Common Data Service คุณต้องเป็นผู้ดูแลระบบในองค์กร Common Data Service เพื่อดำเนินการต่อ และดูรายการของเอนทิตีที่มีอยู่ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ

## <a name="important-considerations"></a>ข้อควรพิจารณาที่สำคัญ

ข้อมูลที่เก็บไว้ในบริการออนไลน์ เช่น Azure Data Lake Storage อาจถูกเก็บไว้ในตำแหน่งที่แตกต่างจากที่ที่มีการประมวลผลหรือจัดเก็บข้อมูลใน Dynamics 365 Customer Insightsโดยการนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ คุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights  [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>เชื่อมต่อกับที่จัดเก็บที่มีการจัดการ Common Data Service

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

2. เลือก **เพิ่มแหล่งข้อมูล**

3. เลือก **เชื่อมต่อกับ Common Data Service** และเลือก **ต่อไป**

4. ป้อน **ชื่อ** สำหรับแหล่งข้อมูล แล้วเลือก **ถัดไป** ตั้งชื่อแนวทาง: 
   - ขึ้นต้นด้วยตัวอักษร
   - ใช้ตัวอักษรและตัวเลขเท่านั้น ไม่อนุญาตให้ใช้อักขระพิเศษและช่องว่าง
   - ใช้ระหว่าง 3 ถึง 64 อักขระ

5. ใส่ **ที่อยู่เซิร์ฟเวอร์** สำหรับองค์กร Common Data Service ของคุณ และเลือก **เข้าสู่ระบบ**

   > [!div class="mx-imgBorder"]
   > ![กล่องโต้ตอบเพื่อป้อนที่อยู่เซิร์ฟเวอร์ Common Data Service](media/enter-CDS-org-details.png)

6. เลือกเอนทิตีที่คุณต้องการนำเข้าระบบจากรายการที่มี    

   > [!NOTE]
   > หากมีการเลือกเอนทิตีบางตัวไปแล้ว อาจใช้กับโปรแกรมประยุกต์อื่นของ Dynamics 365 (เช่น Dynamics 365 Sales Insights หรือ Customer Service Insights) คุณไม่สามารถเปลี่ยนการเลือก เอนทิตีเหล่านี้จะพร้อมใช้งาน เมื่อมีการสร้างแหล่งข้อมูล

   > [!div class="mx-imgBorder"]
   > ![กล่องโต้ตอบแสดงรายการของเอนทิตีในองค์กร Common Data Service](media/select-analytical-entities.png)

7. บันทึกการเลือกของคุณเพื่อเริ่มซิงค์เอนทิตีที่เลือกกับที่จัดเก็บที่มีการจัดการ Common Data Service คุณจะพบการเชื่อมต่อที่เพิ่งเพิ่มเข้าไปในหน้า **แหล่งข้อมูล** จะเข้าคิวเพื่อรีเฟรชและแสดงเอนทิตีที่นับเป็น 0 จนกว่าจะซิงค์เอนทิตีทั้งหมด

แหล่งข้อมูลของสภาพแวดล้อมเดียวเท่านั้นที่สามารถใช้ที่จัดเก็บที่มีการจัดการ Common Data Service เดียวกันพร้อมกันได้

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>แก้ไขแหล่งข้อมูลที่จัดเก็บที่มีการจัดการ Common Data Service

คุณแก้ไขการเลือกเอนทิตีหลังจากสร้างแหล่งข้อมูลเท่านั้น ตัวอย่างเช่น หากมีการเพิ่มเอนทิตีเพิ่มเติมใน Common Data Service และคุณต้องการนำเข้าด้วยเช่นกัน    
เมื่อต้องการเชื่อมต่อกับ Common Data Service อื่น [สร้างแหล่งข้อมูลใหม่](#connect-to-a-common-data-service-managed-lake)

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

2. ถัดจากแหล่งข้อมูลที่คุณต้องการอปรับปรุง เลือกจุดไข่ปลา

3. เลือกตัวเลือก **แก้ไข** จากรายการ

4. เลือกเอนทิตีเพิ่มเติมจากรายการเอนทิตีที่มีอยู่ และเลือก **บันทึก**


[!INCLUDE[footer-include](../includes/footer-banner.md)]