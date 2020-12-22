---
title: ตัวเชื่อมต่อ Power BI
description: เรียนรู้วิธีการใช้ตัวเชื่อมต่อ Dynamics 365 Customer Insights ใน Power BI
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407123"
---
# <a name="connector-for-power-bi-preview"></a>ตัวเชื่อมต่อสำหรับ Power BI (การแสดงตัวอย่าง)

สร้างการจัดรูปแบบการแสดงสำหรับข้อมูลของคุณด้วย Power BI Desktop สร้างข้อมูลเชิงลึกเพิ่มเติมและสร้างรายงานด้วยข้อมูลลูกค้าแบบรวมของคุณ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- คุณมีโปรไฟล์ลูกค้าแบบรวม
- เวอร์ชันล่าสุดของ [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ถูกติดตั้งบนคอมพิวเตอร์ของคุณ [เรียนรู้เพิ่มเติมเกี่ยวกับ Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>กำหนดค่าตัวเชื่อมต่อสำหรับ Power BI

1. ใน Power BI Desktop เลือก **ไฟล์** > **รับข้อมูล**

1. เลือก **ดูเพิ่มเติม** และค้นหาสำหรับ **Dynamics 365 Customer Insights**

1. เลือกผลลัพธ์และเลือก **เชื่อมต่อ**

1. **เข้าสู่ระบบ** ด้วยบัญชีองค์กรเดียวกันกับที่คุณใช้สำหรับ Customer Insights และเลือก **เชื่อมต่อ**
   > [!NOTE]
   > บัญชีที่คุณระบุในขั้นตอนนี้ใช้เพื่อดึงข้อมูลจาก Customer Insights และไม่จำเป็นต้องเป็นบัญชีเดียวกับที่คุณลงชื่อเข้าใช้ Power BI หากต้องการรีเซ็ตบัญชีที่ใช้ในการดึงข้อมูล ให้เปิด Power BI และไปที่ **ไฟล์** > **ตัวเลือก** > **การตั้งค่า** > **การตั้งค่าแหล่งข้อมูล** ในรายการแหล่งข้อมูล เลือก **เข้าสู่ระบบ Dynamics 365 Customer Insights** และเลือก **ล้างสิทธิ์**  

1. ในกล่องโต้ตอบ **ตัวนำทาง** คุณจะเห็นรายการสภาพแวดล้อมทั้งหมดที่คุณสามารถเข้าถึงได้ ขยายสภาพแวดล้อมและเปิดโฟลเดอร์ใดๆ (เอนทิตี, การวัด, เซ็กเมนต์, การเพิ่มข้อมูล) ตัวอย่างเช่น เปิดโฟลเดอร์ **เอนทิตี** เพื่อดูเอนทิตีทั้งหมดที่คุณสามารถนำเข้าได้

   ![ตัวนำทางตัวเชื่อมต่อ Power BI](media/power-bi-navigator.png "ตัวนำทางตัวเชื่อมต่อ Power BI")

1. เลือกช่องทำเครื่องหมายถัดจากเอนทิตีที่จะรวมและ **โหลด** คุณสามารถเลือกหลายเอนทิตีจากหลายสภาพแวดล้อม

1. คุณจะเห็นกล่องโต้ตอบที่กำลังโหลดขณะที่โหลดเอนทิตีของคุณ เมื่อโหลดเอนทิตีที่คุณเลือกทั้งหมดแล้ว คุณสามารถใช้ความสามารถของ Power BI เพื่อแสดงภาพข้อมูล

## <a name="large-data-sets"></a>ชุดข้อมูลขนาดใหญ่

ตัวเชื่อมต่อ Customer Insights สำหรับ Power BI ได้รับการออกแบบมาเพื่อทำงานกับชุดข้อมูลที่มีโปรไฟล์ลูกค้ามากถึง 1 ล้านโปรไฟล์ การนำเข้าชุดข้อมูลขนาดใหญ่อาจได้ผล แต่ต้องใช้เวลานาน นอกจากนี้ กระบวนการอาจหมดเวลา เนื่องจากข้อจำกัดของ Power BI สำหรับข้อมูลเพิ่มเติม โปรดดู [Power BI: คำแนะนำสำหรับชุดข้อมูลขนาดใหญ่](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets) 

### <a name="work-with-a-subset-of-data"></a>ทำงานกับชุดข้อมูลย่อย

ลองทำงานกับชุดย่อยของข้อมูลของคุณ ตัวอย่างเช่น คุณสามารถสร้าง [เซ็กเมนต์](segments.md) แทนการส่งออกเรกคอร์ดลูกค้าทั้งหมดไปยัง Power BI
