---
title: เชื่อมต่อกับตารางใน Microsoft Dataverse
description: นำเข้าข้อมูลจากที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011726"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>เชื่อมต่อกับข้อมูลในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse

ผู้ใช้ Microsoft Dataverse สามารถเชื่อมต่อกับเอนทิตีการวิเคราะห์ในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Microsoft Dataverse ได้อย่างรวดเร็ว

> [!NOTE]
> คุณต้องเป็นผู้ดูแลระบบในองค์กร Dataverse เพื่อดำเนินการและดูรายชื่อของเอนทิตีที่มีอยู่ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ

## <a name="important-considerations"></a>ข้อควรพิจารณาที่สำคัญ

1. ข้อมูลที่เก็บไว้ในบริการออนไลน์ เช่น Azure Data Lake Storage อาจถูกเก็บไว้ในตำแหน่งที่แตกต่างจากที่ที่มีการประมวลผลหรือจัดเก็บข้อมูลใน Dynamics 365 Customer Insights การนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ หมายถึงคุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)
2. มองเห็นได้เฉพาะเอนทิตี Dataverse ที่เปิดใช้งาน [การติดตามการเปลี่ยนแปลง](/power-platform/admin/enable-change-tracking-control-data-synchronization) เท่านั้น เอนทิตีเหล่านี้สามารถส่งออกไปยังที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Dataverse และใช้ใน Customer Insights ตาราง Dataverse แบบสำเร็จูปมีการเปิดใช้งานการติดตามการเปลี่ยนแปลงตามค่าเริ่มต้น คุณต้องเปิดการติดตามการเปลี่ยนแปลงสำหรับตารางที่กำหนดเอง การตรวจสอบว่าตาราง Dataverse เปิดใช้งานการติดตามการเปลี่ยนแปลงหรือไม่ ไปที่ [Power Apps](https://make.powerapps.com) > **ข้อมูล** > **ตาราง** ค้นหาตารางที่คุณสนใจและเลือก ไปที่ **การตั้งค่า** > **ตัวเลือกขั้นสูง** และตรวจสอบการตั้งค่า **ติดตามการเปลี่ยนแปลง**

## <a name="connect-to-a-dataverse-managed-lake"></a>เชื่อมต่อกับที่จัดเก็บที่มีการจัดการของ Dataverse

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. เลือก **เพิ่มแหล่งข้อมูล**

1. เลือก **Microsoft Dataverse**

1. ป้อน **ชื่อ** สำหรับแหล่งข้อมูลและ **คำอธิบาย** ที่ระบุหรือไม่ก็ได้

1. ระบุ **ที่อยู่เซิฟเวอร์** สำหรับองค์กร Dataverse และเลือก **ลงชื่อเข้าใช้**

1. เลือกตารางที่คุณต้องการรับเข้าเป็นเอนทิตีใน Customer Insights จากรายการที่มีอยู่

   > [!NOTE]
   > หากมีการเลือกบางตารางไว้อยู่แล้ว แอปพลิเคชัน Dynamics 365 อื่นๆ อาจใช้ตารางเหล่านั้น (เช่น Dynamics 365 Sales Insights หรือ Customer Service Insights) คุณไม่สามารถเปลี่ยนการเลือก ตารางเหล่านี้จะสามารถใช้งานเป็นเอนทิตีเมื่อสร้างแหล่งข้อมูลแล้ว

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="กล่องโต้ตอบที่แสดงรายการเอนทิตีในสภาพแวดล้อม Dataverse":::

1. บันทึกการเลือกของคุณเพื่อเริ่มการซิงค์ตารางที่เลือกจาก Dataverse คุณจะพบการเชื่อมต่อที่เพิ่งเพิ่มเข้าไปในหน้า **แหล่งข้อมูล** ระบบจะจัดคิวเพื่อรีเฟรชและแสดงจำนวนเอนทิตีเป็น 0 จนกว่าตารางที่เลือกทั้งหมดจะถูกซิงค์

แหล่งข้อมูลของสภาพแวดล้อมเดียวเท่านั้นที่สามารถใช้ที่จัดเก็บที่มีการจัดการของ Dataverse เดียวกันพร้อมกันได้

## <a name="edit-a-dataverse-managed-lake-data-source"></a>แก้ไขแหล่งข้อมูลที่จัดเก็บที่มีการจัดการของ Dataverse

คุณแก้ไขการเลือกเอนทิตีหลังจากสร้างแหล่งข้อมูลเท่านั้น ตัวอย่างเช่น หากมีการเพิ่มเอนทิตีเพิ่มเติมใน Dataverse และคุณต้องการนำเข้าด้วยเช่นกัน
หากต้องการเชื่อมต่อกับ Dataverse Data Lake อื่นๆ ให้ [สร้างแหล่งข้อมูลใหม่](#connect-to-a-dataverse-managed-lake)

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. ข้างแหล่งข้อมูลที่คุณต้องการปรับปรุง ให้เลือก **แก้ไข**

1. เลือกเอนทิตีเพิ่มเติมจากรายการเอนทิตีที่มีอยู่ และเลือก **บันทึก**
