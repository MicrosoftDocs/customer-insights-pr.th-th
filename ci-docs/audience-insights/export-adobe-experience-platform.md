---
title: ส่งออกข้อมูล Customer Insights ไปยัง Adobe Experience Platform
description: เรียนรู้วิธีใช้เซ็กเมนต์ข้อมูลเชิงลึกของผู้ชมในแพลตฟอร์ม Adobe Experience
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305547"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>ใช้เซ็กเมนต์ Customer Insights ใน Adobe Experience Platform (พรีวิว)

ในฐานะผู้ใช้ของข้อมูลเชิงลึกของผู้ชมใน Dynamics 365 Customer Insights คุณอาจสร้างเซ็กเมนต์เพื่อทำให้การส่งเสริมการขายทางการตลาดของคุณมีประสิทธิภาพมากขึ้นโดยการกำหนดเป้าหมายผู้ชมที่เกี่ยวข้อง หากต้องการใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform และแอปพลิเคชันเช่น Adobe Campaign Standard คุณต้องทำตามขั้นตอนสองสามขั้นตอนที่ระบุไว้ในบทความนี้

:::image type="content" source="media/AEP-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

-   สิทธิ์การใช้งาน Dynamics 365 Customer Insights
-   สิทธิ์การใช้งาน Adobe Experience Platform
-   สิทธิ์การใช้งาน Adobe Campaign Standard
-   บัญชีที่เก็บข้อมูล Azure Blob

## <a name="campaign-overview"></a>ภาพรวมการส่งเสริมการขาย

เพื่อให้เข้าใจวิธีใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform ได้ดีขึ้น ลองดูตัวอย่างแคมเปญที่สมมติขึ้น

สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก เพื่อรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอส่งเสริมการขายทางอีเมลโดยใช้ Adobe Experience Platform

ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง

## <a name="identify-your-target-audience"></a>ระบุกลุ่มเป้าหมายของคุณ

ในสถานการณ์ของเรา เราถือว่าที่อยู่อีเมลของลูกค้ามีอยู่ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาจะได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์

[เซ็กเมนต์ที่คุณกำหนดไว้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย](segments.md) มีชื่อว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งอีเมลส่งเสริมการขายให้กับลูกค้าเหล่านี้

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด

## <a name="export-your-target-audience"></a>ส่งออกกลุ่มเป้าหมายของคุณ

ด้วยการระบุกลุ่มเป้าหมายของเรา เราสามารถกำหนดค่าการส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยังบัญชีที่เก็บข้อมูล Azure Blob

### <a name="configure-a-connection"></a>กำหนดค่าการเชื่อมต่อ

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Blob Storage** หรือเลือก **ตั้งค่า** ในไทล์ **Azure Blob Storage** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="ไทล์การกำหนดค่าสำหรับที่เก็บข้อมูล Azure Blob"::: 

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชี Blob Storage ของคุณที่คุณต้องการส่งออกเซ็กเมนต์ไป  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล"::: 
   
    - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชี Blob Storage และคีย์บัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
    - หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น 

### <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วนที่เก็บข้อมูล Azure Blob หากคุณไม่เห็นชื่อส่วนนี้ การเชื่อมต่อชนิดนี้ไม่พร้อมใช้งานสำหรับคุณ

1. เลือกเรกคอร์ดที่คุณต้องการส่งออก ในตัวอย่างนี้ คือ **ChurnProneCustomers**

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. เลือก **บันทึก**

หลังจากบันทึกปลายทางการส่งออกแล้ว คุณจะพบบน **ข้อมูล** > **การส่งออก**

ตอนนี้คุณสามารถ [ส่งออกเซ็กเมนต์ตามความต้องการ](export-destinations.md#run-exports-on-demand) ได้แล้ว นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md) ทุกครั้ง

> [!NOTE]
> ตรวจสอบให้แน่ใจว่าจำนวนเรกคอร์ดในเซ็กเมนต์ที่ส่งออกอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในคอนเทนเนอร์ Azure Blob Storage ที่คุณตั้งค่าคอนฟิกไว้ด้านบน พาธโฟลเดอร์ต่อไปนี้มีการสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ *%ExportDestinationName%*

ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>กำหนด Experience Data Model (XDM) ใน Adobe Experience Platform

ก่อนที่ข้อมูลที่ส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายจะสามารถใช้ภายใน Adobe Experience Platform ได้ เราจำเป็นต้องกำหนดแบบแผน Experience Data Model และ [กำหนดค่าข้อมูลสำหรับโปรไฟล์ลูกค้าแบบเรียลไทม์](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)

เรียนรู้ว่า [XDM คืออะไร](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) และทำความเข้าใจ [พื้นฐานขององค์ประกอบแบบแผน](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)

## <a name="import-data-into-adobe-experience-platform"></a>นำเข้าข้อมูลไปยัง Adobe Experience Platform

เมื่อทุกอย่างเข้าที่แล้ว เราจำเป็นต้องนำเข้าข้อมูลกลุ่มเป้าหมายที่เตรียมไว้จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Experience Platform

ประการแรก [สร้างการเชื่อมต่อแหล่งกับต้นทางที่เก็บข้อมูล Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)    

หลังจากกำหนดการเชื่อมต่อกับต้นทางแล้ว [กำหนดค่ากระแสข้อมูล](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) สำหรับการเชื่อมต่อชุดงานที่เก็บข้อมูลบนระบบคลาวด์ เพื่อนำเข้าผลลัพธ์ของเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Experience Platform

## <a name="create-an-audience-in-adobe-campaign-standard"></a>สร้างกลุ่มเป้าหมายใน Adobe Campaign Standard

ในการส่งอีเมลสำหรับการส่งเสริมการขายนี้ เราจะใช้ Adobe Campaign Standard หลังจากนำเข้าข้อมูลไปยัง Adobe Experience Platform เราจำเป็นต้อง [สร้างกลุ่มเป้าหมาย](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ใน Adobe Campaign Standard โดยใช้ข้อมูลใน Adobe Experience Platform


เรียนรู้วิธีการ [ใช้ตัวสร้างเซ็กเมนต์](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) ใน Adobe Campaign Standard เพื่อกำหนดกลุ่มเป้าหมายตามข้อมูลใน Adobe Experience Platform

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard

สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="ตัวอย่างอีเมลพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::
