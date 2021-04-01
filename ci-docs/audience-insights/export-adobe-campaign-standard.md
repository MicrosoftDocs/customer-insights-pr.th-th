---
title: ส่งออกข้อมูล Customer Insights ไปยัง Adobe Campaign Standard
description: เรียนรู้วิธีใช้เซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Campaign Standard
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596338"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>ใช้เซ็กเมนต์ Customer Insights ใน Adobe Campaign Standard (พรีวิว)

ในฐานะผู้ใช้ข้อมูลเชิงลึกกลุ่มเป้าหมายสำหรับ Dynamics 365 Customer Insights คุณอาจสร้างเซ็กเมนต์เพื่อทำให้แคมเปญการตลาดของคุณมีประสิทธิภาพมากขึ้นโดยกำหนดเป้าหมายไปยังกลุ่มเป้าหมายที่เกี่ยวข้อง หากต้องการใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform และแอปพลิเคชันเช่น Adobe Campaign Standard คุณต้องทำตามขั้นตอนสองสามขั้นตอนที่ระบุไว้ในบทความนี้

:::image type="content" source="media/ACS-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   สิทธิ์การใช้งาน Dynamics 365 Customer Insights
-   สิทธิ์การใช้งาน Adobe Campaign Standard
-   บัญชีที่เก็บข้อมูล Azure Blob

## <a name="campaign-overview"></a>ภาพรวมการส่งเสริมการขาย

เพื่อให้เข้าใจวิธีใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform ได้ดีขึ้น ลองดูตัวอย่างแคมเปญที่สมมติขึ้น

สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก เพื่อรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอส่งเสริมการขายทางอีเมลโดยใช้ Adobe Campaign Standard

ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง อย่างไรก็ตาม ข้อมูลเชิงลึกกลุ่มเป้าหมายและ Adobe Campaign Standard สามารถกำหนดค่าให้ทำงานสำหรับสถานการณ์แคมเปญที่เกิดซ้ำได้เช่นกัน

## <a name="identify-your-target-audience"></a>ระบุกลุ่มเป้าหมายของคุณ

ในสถานการณ์ของเรา เราถือว่าที่อยู่อีเมลของลูกค้ามีอยู่ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาจะได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์

[เซ็กเมนต์ที่คุณกำหนดไว้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย](segments.md) มีชื่อว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งอีเมลส่งเสริมการขายให้กับลูกค้าเหล่านี้

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด

## <a name="export-your-target-audience"></a>ส่งออกกลุ่มเป้าหมายของคุณ

ด้วยการระบุกลุ่มเป้าหมายของเรา เราสามารถกำหนดค่าการส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยังบัญชีที่เก็บข้อมูล Azure Blob

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ในไทล์ **Adobe Campaign** เลือก **ตั้งค่า**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="ไทล์การกำหนดค่าสำหรับ Adobe Campaign Standard":::

1. ระบุ **ชื่อที่แสดง** สำหรับปลายทางการส่งออกใหม่นี้ จากนั้นป้อน **ชื่อบัญชี**, **คีย์บัญชี** และ **คอนเทนเนอร์** ของบัญชีที่เก็บข้อมูล Azure Blob ที่คุณต้องการส่งออกเซ็กเมนต์ไป  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล"::: 

   - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชี ให้ดูที่ [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)

   - หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

1. เลือก **ถัดไป**

1. เลือกเรกคอร์ดที่คุณต้องการส่งออก ในตัวอย่างนี้ คือ **ChurnProneCustomers**

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. เลือก **ถัดไป**

1. ตอนนี้เราแม็ปฟิลด์ **ต้นทาง** จากเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายกับชื่อฟิลด์ **เป้าหมาย** ในแบบแผนโปรไฟล์ Adobe Campaign Standard

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="การแม็ปฟิลด์สำหรับตัวเชื่อมต่อ Adobe Campaign Standard":::

   หากคุณต้องการเพิ่มแอตทริบิวต์เพิ่มเติม ให้เลือก **เพิ่มแอตทริบิวต์** ชื่อเป้าหมายอาจแตกต่างจากชื่อฟิลด์ต้นทางเพื่อให้คุณยังแม็ปผลลัพธ์ของเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายกับ Adobe Campaign Standard ได้ หากฟิลด์ไม่มีชื่อเดียวกันในทั้งสองระบบ

   > [!NOTE]
   > ที่อยู่อีเมลใช้เป็นฟิลด์ข้อมูลประจำตัว แต่คุณสามารถใช้ตัวระบุอื่นใดก็ได้จากโปรไฟล์ลูกค้าข้อมูลเชิงลึกกลุ่มเป้าหมายของคุณเพื่อแม็ปข้อมูลกับ Adobe Campaign Standard

1. เลือก **บันทึก**

หลังจากบันทึกปลายทางการส่งออกแล้ว คุณจะดูได้ใน **การดูแล** > **การส่งออก** > **ปลายทางการส่งออกของฉัน**

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="ภาพหน้าจอที่มีรายการของการส่งออกและเซ็กเมนต์ตัวอย่างที่ไฮไลต์":::

ตอนนี้คุณสามารถ [ส่งออกเซ็กเมนต์ตามความต้องการ](export-destinations.md#export-data-on-demand) ได้แล้ว นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md) ทุกครั้ง

> [!NOTE]
> ตรวจสอบให้แน่ใจว่าจำนวนเรกคอร์ดในเซ็กเมนต์ที่ส่งออกอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ

ข้อมูลที่ส่งออกจะเก็บไว้ในที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่าไว้ด้านบน พาธโฟลเดอร์ต่อไปนี้มีการสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>กำหนดค่า Adobe Campaign Standard

เมื่อมีการส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมาย จะมีคอลัมน์ที่คุณเลือกขณะที่กำหนดปลายทางการส่งออกในขั้นตอนก่อนหน้า ข้อมูลนี้สามารถใช้เพื่อ [สร้างโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)

ในการใช้เซ็กเมนต์ใน Adobe Campaign Standard เราจำเป็นต้องขยายแบบแผนโปรไฟล์ใน Adobe Campaign Standard เพื่อรวมฟิลด์เพิ่มเติมสองฟิลด์ เรียนรู้วิธีการ [ขยายทรัพยากรโปรไฟล์](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ด้วยฟิลด์ใหม่ใน Adobe Campaign Standard

ในตัวอย่างของเรา ฟิลด์เหล่านี้คือ *ชื่อเซ็กเมนต์และวันที่ของเซ็กเมนต์ (ไม่บังคับ)*

เราจะใช้ฟิลด์เหล่านี้เพื่อระบุโปรไฟล์ใน Adobe Campaign Standard ที่เราต้องการกำหนดเป้าหมายสำหรับแคมเปญนี้

หากไม่มีเรกคอร์ดอื่นๆ ใน Adobe Campaign Standard นอกเหนือจากสิ่งที่คุณกำลังจะนำเข้า คุณสามารถข้ามขั้นตอนนี้ได้

## <a name="import-data-into-adobe-campaign-standard"></a>นำเข้าข้อมูลลงใน Adobe Campaign Standard

เมื่อทุกอย่างเข้าที่แล้ว เราจำเป็นต้องนำเข้าข้อมูลกลุ่มเป้าหมายที่เตรียมไว้จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Campaign Standard เพื่อสร้างโปรไฟล์ เรียนรู้ [วิธีการนำเข้าโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) โดยใช้เวิร์กโฟลว์

เวิร์กโฟลว์การนำเข้าในรูปภาพด้านล่างได้รับการกำหนดค่าให้ทำงานทุกๆ 8 ชั่วโมง และค้นหาเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายที่ส่งออก (ไฟล์ .csv ในที่เก็บข้อมูล Azure Blob) เวิร์กโฟลว์จะแยกเนื้อหาของไฟล์ .csv ตามลำดับคอลัมน์ที่ระบุ เวิร์กโฟลว์นี้สร้างขึ้นเพื่อดำเนินการจัดการข้อผิดพลาดพื้นฐานและตรวจสอบให้แน่ใจว่าแต่ละเรกคอร์ดมีที่อยู่อีเมลก่อนที่จะไฮเดรทข้อมูลใน Adobe Campaign Standard เวิร์กโฟลว์ยังแยกชื่อเซ็กเมนต์ออกจากชื่อไฟล์ก่อนที่จะเพิ่มลงในข้อมูลโปรไฟล์ ACS

:::image type="content" source="media/ACS-import-workflow.png" alt-text="ภาพหน้าจอของเวิร์กโฟลว์การนำเข้าในส่วนติดต่อผู้ใช้ Adobe Campaign Standard":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>ดึงข้อมูลกลุ่มเป้าหมายใน Adobe Campaign Standard

เมื่อนำเข้าข้อมูลไปยัง Adobe Campaign Standard แล้ว คุณ [สามารถสร้างเวิร์กโฟลว์](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) และ [การสอบถาม](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) ลูกค้าตาม *ชื่อเซ็กเมนต์* และ *วันที่ของเซ็กเมนต์* เพื่อเลือกโปรไฟล์ที่ระบุไว้สำหรับแคมเปญตัวอย่างของเรา

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard

สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="ตัวอย่างอีเมลพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::