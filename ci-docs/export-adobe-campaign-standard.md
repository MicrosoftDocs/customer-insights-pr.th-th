---
title: ส่งออกเซ็กเมนต์ Customer Insights ไปยัง Adobe Campaign Standard (พรีวิว)
description: เรียนรู้วิธีใช้เซ็กเมนต์ Customer Insights ใน Adobe Campaign Standard
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195543"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>ส่งออกเซ็กเมนต์ Customer Insights ไปยัง Adobe Campaign Standard (พรีวิว)

ส่งออกเซ็กเมนต์ที่กำหนดเป้าหมายผู้ชมที่เกี่ยวข้องไปยัง Adobe Campaign Standard

:::image type="content" source="media/ACS-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สิทธิ์การใช้งาน Adobe Campaign Standard
- ชื่อ [บัญชีที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) และรหัสบัญชี หากต้องการค้นหาชื่อและรหัส โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
- [คอนเทนเนอร์ที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>ภาพรวมการส่งเสริมการขาย

เพื่อให้เข้าใจได้ดียิ่งขึ้นถึงวิธีที่คุณสามารถใช้เซ็กเมนต์จาก Customer Insights ใน Adobe Experience Platform มาดูตัวอย่างการส่งเสริมการขายที่สมมติขึ้นกัน

สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก หากต้องการรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอโปรโมชันผ่านอีเมลโดยใช้ Adobe Campaign Standard

ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง อย่างไรก็ตาม Customer Insights และ Adobe Campaign Standard สามารถกำหนดค่าให้ทำงานในสถานการณ์การส่งเสริมการขายที่เกิดซ้ำได้เช่นกัน

## <a name="identify-your-target-audience"></a>ระบุกลุ่มเป้าหมายของคุณ

ในสถานการณ์ของเรา เราจะถือว่ามีที่อยู่อีเมลของลูกค้าอยู่ใน Customer Insights และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์

[เซ็กเมนต์ที่คุณกำหนดใน Customer Insights](segments.md) เรียกว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งโปรโมชันทางอีเมลให้กับลูกค้าเหล่านี้

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด

## <a name="export-your-target-audience"></a>ส่งออกกลุ่มเป้าหมายของคุณ

### <a name="set-up-connection-to-adobe-campaign"></a>ตั้งค่าการเชื่อมต่อกับ Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Adobe Campaign**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชีที่เก็บข้อมูล Blob ของคุณ  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล":::

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

### <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Adobe Campaign ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกเรกคอร์ดที่คุณต้องการส่งออก ในตัวอย่างนี้ คือ **ChurnProneCustomers**

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. เลือก **ถัดไป**

1. แมปฟิลด์ **ต้นทาง** จากเซ็กเมนต์ Customer Insights ไปยังชื่อฟิลด์ **เป้าหมาย** ในแบบแผนโปรไฟล์ของ Adobe Campaign Standard

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="การแมปฟิลด์สำหรับตัวเชื่อมต่อ Adobe Campaign Standard":::

   หากคุณต้องการเพิ่มแอตทริบิวต์เพิ่มเติม ให้เลือก **เพิ่มแอตทริบิวต์** ชื่อเป้าหมายอาจแตกต่างจากชื่อฟิลด์ต้นทาง ดังนั้นคุณจึงยังสามารถแมปเอาต์พุตของเซ็กเมนต์จาก Customer Insights กับ Adobe Campaign Standard ได้หากฟิลด์มีชื่อไม่เหมือนกันในทั้งสองระบบ

   > [!NOTE]
   > ที่อยู่อีเมลมีการใช้เป็นฟิลด์ข้อมูลประจำตัว แต่คุณสามารถใช้ตัวระบุอื่นๆ จากโปรไฟล์ลูกค้าเพื่อแมปข้อมูลกับ Adobe Campaign Standard ได้

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> ตรวจสอบให้แน่ใจว่าจำนวนของเรกคอร์ดในเซ็กเมนต์ที่ส่งออกนั้นอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในคอนเทนเนอร์ Azure Blob Storage ที่คุณกำหนดค่าไว้ด้านบน เส้นทางโฟลเดอร์ต่อไปนี้จะถูกสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>กำหนดค่า Adobe Campaign Standard

เซ็กเมนต์ที่ส่งออกมีคอลัมน์ที่คุณเลือกไว้ขณะกำหนดค่าการส่งออก ข้อมูลนี้สามารถใช้เพื่อ [สร้างโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)

หากต้องการใช้เซ็กเมนต์ใน Adobe Campaign Standard ให้ [ขยาย schema ของโปรไฟล์](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ใน Adobe Campaign Standard เพื่อรวมฟิลด์เพิ่มเติมสองฟิลด์

ในตัวอย่างของเรา ฟิลด์เหล่านี้คือ ชื่อเซ็กเมนต์และวันที่ของเซ็กเมนต์ เราจะใช้ฟิลด์เหล่านี้เพื่อระบุโปรไฟล์ใน Adobe Campaign Standard ที่เราต้องการกำหนดเป้าหมายสำหรับแคมเปญนี้

หากไม่มีเรกคอร์ดอื่นใน Adobe Campaign Standard นอกเหนือจากสิ่งที่คุณกำลังจะนำเข้า ให้ข้ามขั้นตอนนี้

## <a name="import-data-into-adobe-campaign-standard"></a>นำเข้าข้อมูลไปยัง Adobe Campaign Standard

นำเข้าข้อมูลผู้ชมที่เตรียมไว้จาก Customer Insights ไปยัง Adobe Campaign Standard เพื่อ [สร้างโปรไฟล์โดยใช้เวิร์กโฟลว์](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)

เวิร์กโฟลว์การนำเข้าในรูปภาพด้านล่างได้รับการกำหนดค่าให้ทำงานทุกๆ แปดชั่วโมง และค้นหาเซ็กเมนต์ Customer Insights ที่ส่งออก (ไฟล์ .csv ในที่เก็บข้อมูล Azure Blob) เวิร์กโฟลว์จะแยกเนื้อหาของไฟล์ .csv ตามลำดับคอลัมน์ที่ระบุ เวิร์กโฟลว์นี้ได้ถูกสร้างขึ้นเพื่อดำเนินการจัดการข้อผิดพลาดพื้นฐาน และทำให้แน่ใจว่าแต่ละเรกคอร์ดมีที่อยู่อีเมล ก่อนที่จะเติมข้อมูลใน Adobe Campaign Standard นอกจากนี้ เวิร์กโฟลว์ยังแยกชื่อเซ็กเมนต์ออกจากชื่อไฟล์ ก่อนที่จะเพิ่มลงในข้อมูลโปรไฟล์ Adobe Campaign Standard

:::image type="content" source="media/ACS-import-workflow.png" alt-text="ภาพหน้าจอของเวิร์กโฟลว์การนำเข้าในอินเทอร์เฟซผู้ใช้ของ Adobe Campaign Standard":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>เรียกข้อมูลผู้ชมใน Adobe Campaign Standard

เมื่อนำข้อมูลเข้าสู่ Adobe Campaign Standard ให้ [สร้างเวิร์กโฟลว์](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) และ [สอบถาม](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) ลูกค้า โดยขึ้นอยู่กับ ชื่อเซ็กเมนต์ และ วันที่ของเซ็กเมนต์ เพื่อเลือกโปรไฟล์ที่ถูกระบุสำหรับแคมเปญตัวอย่างของเรา

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard

สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="อีเมลตัวอย่างพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
