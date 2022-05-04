---
title: ตัวเชื่อมต่อ Power Apps
description: เชื่อมต่อ Power Apps และ Power Automate
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648006"
---
# <a name="microsoft-power-apps-connector-preview"></a>ตัวเชื่อมต่อ Microsoft Power Apps (ตัวอย่าง)

นำโปรไฟล์ลูกค้าแบบรวมเข้าไปยังแอปส่วนตัวของคุณด้วย Power Apps

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>เชื่อมต่อ Power Apps และ Dynamics 365 Customer Insights

Customer Insights เป็นหนึ่งในหลายๆ [แหล่งข้อมูลที่มีอยู่ใน Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources)

อ้างถึงเอกสาร Power Apps เพื่อเรียนรู้วิธีการ [เพิ่มการเชื่อมต่อข้อมูลไปยังแอป](/powerapps/maker/canvas-apps/add-data-connection) เราขอแนะนำให้คุณตรวจสอบ [Power Apps ใช้การมอบหมายเพื่อจัดการชุดข้อมูลขนาดใหญ่ในแอปพื้นที่ทำงานอย่างไร](/powerapps/maker/canvas-apps/delegation-overview) ด้วย

## <a name="available-entities"></a>เอนทิตีที่มี

หลังจากเพิ่ม Customer Insights เป็นการเชื่อมต่อข้อมูล คุณสามารถเลือกเอนทิตีต่อไปนี้ใน Power Apps:

- **ลูกค้า**: เพื่อใช้ข้อมูลจาก [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md)
- **UnifiedActivity**: เพื่อแสดง [เส้นเวลากิจกรรม](activities.md) ในแอป
- **ContactProfile**: เพื่อแสดงข้อมูลผู้ติดต่อของลูกค้า เอนทิตีนี้สามารถใช้งานเฉพาะในสภาพแวดล้อม Customer Insights สำหรับบัญชีธุรกิจเท่านั้น

## <a name="limitations"></a>ข้อจำกัด

### <a name="retrievable-entities"></a>เอนทิตีที่ดึงข้อมูลได้

คุณสามารถดึงข้อมูลเอนทิตี **ลูกค้า** **UnifiedActivity** **เซ็กเมนต์** และ **ContactProfile** ผ่านตัวเชื่อมต่อ Power Apps เท่านั้น ContactProfile สามารถใช้งานเฉพาะในอินสแตนซ์ Customer Insights สำหรับบัญชีธุรกิจเท่านั้น เอนทิตีอื่นๆ จะแสดงขึ้น เนื่องจากตัวเชื่อมต่อที่สำคัญรองรับผ่านทริกเกอร์ใน Power Automate

คุณสามารถโทรได้สูงสุด 100 สายต่อ 60 วินาที คุณสามารถเรียกตำแหน่งข้อมูล API ได้หลายครั้งโดยใช้พารามิเตอร์ $skip [เรียนรู้เพิ่มเติมเกี่ยวกับพารามิเตอร์ $skip](/connectors/customerinsights/#get-items-from-an-entity)

### <a name="delegation"></a>การมอบสิทธิ์

การมอบสิทธิ์ใช้ได้กับเอนทิตี **ลูกค้า** และเอนทิตี **UnifiedActivity** 

- การมอบหมายสำหรับเอนทิตี **ลูกค้า**: การใช้การมอบหมายสำหรับเอนทิตีนี้ จำเป็นต้องมีการจัดทำดัชนีฟิลด์ใน [ค้นหาและกรองดัชนี](search-filter-index.md)  
- การมอบสิทธิ์สำหรับ **UnifiedActivity**: การมอบสิทธิ์สำหรับเอนทิตีนี้ใช้ได้กับฟิลด์ **ActivityId** และ **CustomerId** เท่านั้น  
- การมอบสิทธิ์สำหรับ **ContactProfile**: การมอบสิทธิ์สำหรับเอนทิตีนี้ใช้ได้กับฟิลด์ **ContactId** และ **CustomerId** เท่านั้น ContactProfile สามารถใช้งานเฉพาะในสภาพแวดล้อม Customer Insights สำหรับบัญชีธุรกิจเท่านั้น

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการมอบสิทธิ์ ไปที่ [ฟังก์ชันและการดำเนินงานที่สามารถมอบสิทธิ์ของ Power Apps](/powerapps/maker/canvas-apps/delegation-overview) 

## <a name="example-gallery-control"></a>ตัวอย่างการควบคุมแกลเลอรี่

คุณสามารถเพิ่มโปรไฟล์ลูกค้าใน [การควบคุมแกลเลอรี](/powerapps/maker/canvas-apps/add-gallery)

1. เพิ่มการควบคุม **แกลอรี** ไปยังแอปที่คุณกำลังสร้าง

    > [!div class="mx-imgBorder"]
    > ![เพิ่มองค์ประกอบของแกลเลอรี](media/connector-powerapps9.png "เพิ่มองค์ประกอบของแกลเลอรี")

2. เลือก **ลูกค้า** เป็นแหล่งข้อมูลสำหรับรายการ

    > [!div class="mx-imgBorder"]
    > ![เลือกแหล่งข้อมูล](media/choose-datasource-powerapps.png "เลือกแหล่งข้อมูล")

3. คุณสามารถเปลี่ยนแผงข้อมูลทางด้านขวาเพื่อเลือกฟิลด์เอนทิตีลูกค้าที่จะแสดงในแกลเลอรี

4. หากคุณต้องการแสดงฟิลด์ใด ๆ จากลูกค้าที่เลือกในแกลเลอรี่ ให้กรอกคุณสมบัติ **ข้อความ** ของป้ายชื่อโดยใช้ **{Name_of_the_gallery}.Selected.{property_name}**  
    - ตัวอย่าง: _Gallery1.Selected.address1_city_

5. ในการแสดงเส้นเวลาแบบรวมสำหรับลูกค้า เพิ่มองค์ประกอบของแกลเลอรี และเพิ่มคุณสมบัติ **รายการ** โดยใช้ **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - ตัวอย่าง: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
