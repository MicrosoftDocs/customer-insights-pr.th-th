---
title: ส่งออกเซ็กเมนต์ไปยัง Adobe Experience Platform (พรีวิว)
description: เรียนรู้วิธีการใช้เซ็กเมนต์ Customer Insights ใน Adobe Experience Platform
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195313"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>ส่งออกเซ็กเมนต์ไปยัง Adobe Experience Platform (พรีวิว)

ส่งออกเซ็กเมนต์ที่กำหนดเป้าหมายผู้ชมที่เกี่ยวข้องไปยัง Adobe Experience Platform

:::image type="content" source="media/AEP-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- สิทธิ์การใช้งาน Adobe Experience Platform
- สิทธิ์การใช้งาน Adobe Campaign Standard
- ชื่อ [บัญชีที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) และรหัสบัญชี หากต้องการค้นหาชื่อและรหัส โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
- [คอนเทนเนอร์ที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>ภาพรวมการส่งเสริมการขาย

เพื่อให้เข้าใจได้ดียิ่งขึ้นถึงวิธีที่คุณสามารถใช้เซ็กเมนต์จาก Customer Insights ใน Adobe Experience Platform มาดูตัวอย่างการส่งเสริมการขายที่สมมติขึ้นกัน

สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก หากต้องการรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอโปรโมชันผ่านอีเมล โดยใช้ Adobe Experience Platform

ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง

## <a name="identify-your-target-audience"></a>ระบุกลุ่มเป้าหมายของคุณ

ในสถานการณ์ของเรา เราจะถือว่ามีที่อยู่อีเมลของลูกค้าอยู่ใน Customer Insights และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์

[เซ็กเมนต์ที่คุณกำหนดใน Customer Insights](segments.md) เรียกว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งโปรโมชันทางอีเมลให้กับลูกค้าเหล่านี้

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด

## <a name="export-your-target-audience"></a>ส่งออกกลุ่มเป้าหมายของคุณ

เราจะกำหนดค่าการส่งออกจาก Customer Insights ไปยังบัญชีที่เก็บข้อมูล Azure Blob

### <a name="set-up-connection-to-azure-blob-storage"></a>ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **ที่เก็บข้อมูล Azure Blob**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชี Blob Storage ของคุณที่คุณต้องการส่งออกเซ็กเมนต์ไป  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล":::

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

### <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วนที่เก็บข้อมูล Azure Blob ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. เลือกเรกคอร์ดที่คุณต้องการส่งออก ในตัวอย่างนี้ คือ **ChurnProneCustomers**

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> ตรวจสอบให้แน่ใจว่าจำนวนของเรกคอร์ดในเซ็กเมนต์ที่ส่งออกนั้นอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในคอนเทนเนอร์ที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่า เส้นทางโฟลเดอร์ต่อไปนี้จะถูกสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ

- สำหรับเอนทิตีต้นทางและเอนทิตีที่สร้างโดยระบบ:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ *%ExportDestinationName%*

  ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>กำหนด Experience Data Model (XDM) ใน Adobe Experience Platform

ก่อนที่ข้อมูลที่ส่งออกจาก Customer Insights จะสามารถใช้ได้ภายใน Adobe Experience Platform ให้กำหนดแบบแผนแบบจำลองข้อมูลประสบการณ์และ [กำหนดค่าข้อมูลสำหรับโปรไฟล์ลูกค้าแบบเรียลไทม์](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)

เรียนรู้ว่า [XDM คืออะไร](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) และทำความเข้าใจ [พื้นฐานขององค์ประกอบแบบแผน](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)

## <a name="import-data-into-adobe-experience-platform"></a>นำเข้าข้อมูลใน Adobe Experience Platform

นำเข้าข้อมูลผู้ชมที่เตรียมไว้จาก Customer Insights ลงใน Adobe Experience Platform

1. [สร้างการเชื่อมต่อแหล่งกับต้นทางที่เก็บข้อมูล Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)

1. [กำหนดค่ากระแสข้อมูล](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) สำหรับการเชื่อมต่อชุดงานของที่เก็บข้อมูลบนระบบคลาวด์ เพื่อนำเข้าผลลัพธ์เซ็กเมนต์จาก Customer Insights ไปยัง Adobe Experience Platform

## <a name="create-an-audience-in-adobe-campaign-standard"></a>สร้างผู้ชมใน Adobe Campaign Standard

ในการส่งอีเมลสำหรับการส่งเสริมการขายนี้ เราจะใช้ Adobe Campaign Standard

1. [สร้างผู้ชม](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ใน Adobe Campaign Standard โดยใช้ข้อมูลใน Adobe Experience Platform

1. [ใช้เครื่องมือสร้างเซ็กเมนต์](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) ใน Adobe Campaign Standard เพื่อกำหนดผู้ชมตามข้อมูลใน Adobe Experience Platform

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard

สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="อีเมลตัวอย่างพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
