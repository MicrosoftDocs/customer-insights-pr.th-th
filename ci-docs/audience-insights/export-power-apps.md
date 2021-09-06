---
title: ตัวเชื่อมต่อ Power Apps
description: เชื่อมต่อ Power Apps และ Power Automate
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031818"
---
# <a name="microsoft-power-apps-connector-preview"></a>ตัวเชื่อมต่อ Microsoft Power Apps (ตัวอย่าง)

นำโปรไฟล์ลูกค้าแบบรวมเข้าไปยังแอปส่วนตัวของคุณด้วย Power Apps

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>เชื่อมต่อ Power Apps และ Dynamics 365 Customer Insights

Customer Insights เป็นหนึ่งในหลายๆ [แหล่งข้อมูลที่มีอยู่ใน Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources)

อ้างถึงเอกสาร Power Apps เพื่อเรียนรู้วิธีการ [เพิ่มการเชื่อมต่อข้อมูลไปยังแอป](/powerapps/maker/canvas-apps/add-data-connection) เราขอแนะนำให้คุณตรวจสอบ [Power Apps ใช้การมอบหมายเพื่อจัดการชุดข้อมูลขนาดใหญ่ในแอปพื้นที่ทำงานอย่างไร](/powerapps/maker/canvas-apps/delegation-overview) ด้วย

## <a name="available-entities"></a>เอนทิตีที่มี

หลังจากเพิ่ม Customer Insights เป็นการเชื่อมต่อข้อมูล คุณสามารถเลือกเอนทิตีต่อไปนี้ใน Power Apps:

- ลูกค้า: เพื่อใช้ข้อมูลจาก [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md)
- UnifiedActivity: เพื่อแสดง [เส้นเวลากิจกรรม](activities.md) บนแอป

## <a name="limitations"></a>ข้อจำกัด

### <a name="retrievable-entities"></a>เอนทิตีที่ดึงข้อมูลได้

คุณสามารถดึงข้อมูลเอนทิตี **ลูกค้า** **UnifiedActivity** และ **เซ็กเมนต์** ผ่านตัวเชื่อมต่อ Power Apps เอนทิตีอื่นๆ จะแสดงขึ้น เนื่องจากตัวเชื่อมต่อที่สำคัญรองรับผ่านทริกเกอร์ใน Power Automate  

### <a name="delegation"></a>การมอบสิทธิ์

การมอบสิทธิ์ใช้ได้กับเอนทิตีลูกค้าและเอนทิตี UnifiedActivity 

- การมอบหมายสำหรับเอนทิตี **ลูกค้า**: การใช้การมอบหมายสำหรับเอนทิตีนี้ จำเป็นต้องมีการจัดทำดัชนีฟิลด์ใน [ค้นหาและกรองดัชนี](search-filter-index.md)  

- การมอบสิทธิ์สำหรับ **UnifiedActivity**: การมอบสิทธิ์สำหรับเอนทิตีนี้ใช้ได้กับฟิลด์ **ActivityId** และ **CustomerId** เท่านั้น  

- สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการมอบสิทธิ์ โปรดดู [ฟังก์ชันและการดำเนินการที่มอบสิทธิ์ได้ของ Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) 

## <a name="example-gallery-control"></a>ตัวอย่างการควบคุมแกลเลอรี่

ตัวอย่างเช่น คุณเพิ่มโปรไฟล์ลูกค้าใน [การควบคุมแกลเลอรี](/powerapps/maker/canvas-apps/add-gallery)

1. เพิ่มการควบคุม **แกลอรี** ไปยังแอปที่คุณกำลังสร้าง

> [!div class="mx-imgBorder"]
> ![เพิ่มองค์ประกอบของแกลเลอรี](media/connector-powerapps9.png "เพิ่มองค์ประกอบของแกลเลอรี")

1. เลือก **ลูกค้า** เป็นแหล่งข้อมูลสำหรับรายการ

    > [!div class="mx-imgBorder"]
    > ![เลือกแหล่งข้อมูล](media/choose-datasource-powerapps.png "เลือกแหล่งข้อมูลหนึ่งแหล่ง")

1. คุณสามารถเปลี่ยนแผงข้อมูลทางด้านขวาเพื่อเลือกฟิลด์เอนทิตีลูกค้าที่จะแสดงในแกลเลอรี

1. หากคุณต้องการแสดงฟิลด์ใด ๆ จากลูกค้าที่เลือกในแกลเลอรี่ ให้กรอกคุณสมบัติข้อความของป้ายชื่อ: **{Name_of_the_gallery}.เลือก{property_name}**

    ตัวอย่าง: Gallery1.Selected.address1_city

1. ในการแสดงเส้นเวลาแบบรวมสำหรับลูกค้า เพิ่มองค์ประกอบของแกลเลอรีและเพิ่มคุณสมบัติรายการ: **ตัวกรอง('UnifiedActivity' CustomerId = {Customer_Id})**

    ตัวอย่าง: ตัวกรอง('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]