---
title: เชื่อมต่อกับตารางใน Microsoft Dataverse
description: นำเข้าข้อมูลจากที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046448"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>เชื่อมต่อกับข้อมูลใน Data Lake ที่มีการจัดการ Microsoft Dataverse



บทความนี้ให้ข้อมูลเกี่ยวกับวิธีการที่ผู้ใช้ Dataverse สามารถเชื่อมต่อกับเอนทิตีการวิเคราะห์ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ Microsoft Dataverse 

> [!NOTE]
> คุณต้องเป็นผู้ดูแลระบบในองค์กร Dataverse เพื่อดำเนินการและดูรายชื่อของเอนทิตีที่มีอยู่ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ

## <a name="important-considerations"></a>ข้อควรพิจารณาที่สำคัญ

ข้อมูลที่เก็บไว้ในบริการออนไลน์ เช่น Azure Data Lake Storage อาจถูกเก็บไว้ในตำแหน่งที่แตกต่างจากที่ที่มีการประมวลผลหรือจัดเก็บข้อมูลใน Dynamics 365 Customer Insights การนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ หมายถึงคุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>เชื่อมต่อกับที่จัดเก็บที่มีการจัดการของ Dataverse

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

2. เลือก **เพิ่มแหล่งข้อมูล**

3. เลือก **Microsoft Dataverse** และเลือก **ถัดไป**

4. ป้อน **ชื่อ** สำหรับแหล่งข้อมูล แล้วเลือก **ถัดไป** 

5. ระบุ **ที่อยู่เซิฟเวอร์** สำหรับองค์กร Dataverse และเลือก **ลงชื่อเข้าใช้**

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="หน้าจอในขั้นตอนการนำเข้าข้อมูลที่ผู้ใช้สามารถป้อน URL ของสภาพแวดล้อม Dataverse":::

6. เลือกตารางที่คุณต้องการนำเข้าเป็นเอนทิตีไปยังข้อมูลเชิงลึกของผู้ชมจากรายการที่มี    

   > [!NOTE]
   > หากมีการเลือกบางตารางไว้อยู่แล้ว แอปพลิเคชัน Dynamics 365 อื่นๆ อาจใช้ตารางเหล่านั้น (เช่น Dynamics 365 Sales Insights หรือ Customer Service Insights) คุณไม่สามารถเปลี่ยนการเลือก ตารางเหล่านี้จะสามารถใช้งานเป็นเอนทิตีเมื่อสร้างแหล่งข้อมูลแล้ว

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="กล่องโต้ตอบที่แสดงรายการเอนทิตีในสภาพแวดล้อม Dataverse":::

7. บันทึกการเลือกของคุณเพื่อเริ่มการซิงค์ตารางที่เลือกจาก Dataverse คุณจะพบการเชื่อมต่อที่เพิ่งเพิ่มเข้าไปในหน้า **แหล่งข้อมูล** ระบบจะจัดคิวเพื่อรีเฟรชและแสดงจำนวนเอนทิตีเป็น 0 จนกว่าตารางที่เลือกทั้งหมดจะถูกซิงค์

แหล่งข้อมูลของสภาพแวดล้อมเดียวเท่านั้นที่สามารถใช้ที่จัดเก็บที่มีการจัดการของ Dataverse เดียวกันพร้อมกันได้

## <a name="edit-a-dataverse-managed-lake-data-source"></a>แก้ไขแหล่งข้อมูลที่จัดเก็บที่มีการจัดการของ Dataverse

คุณแก้ไขการเลือกเอนทิตีหลังจากสร้างแหล่งข้อมูลเท่านั้น ตัวอย่างเช่น หากมีการเพิ่มเอนทิตีเพิ่มเติมใน Dataverse และคุณต้องการนำเข้าด้วยเช่นกัน    
หากต้องการเชื่อมต่อกับ Dataverse Data Lake อื่นๆ ให้ [สร้างแหล่งข้อมูลใหม่](#connect-to-a-dataverse-managed-lake)

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

2. ถัดจากแหล่งข้อมูลที่คุณต้องการอปรับปรุง เลือกจุดไข่ปลา

3. เลือกตัวเลือก **แก้ไข** จากรายการ

4. เลือกเอนทิตีเพิ่มเติมจากรายการเอนทิตีที่มีอยู่ และเลือก **บันทึก**

[!INCLUDE[footer-include](../includes/footer-banner.md)]
