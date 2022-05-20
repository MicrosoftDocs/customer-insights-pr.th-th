---
title: ส่งออกข้อมูล Customer Insights ไปยังที่เก็บข้อมูล Azure Blob
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยังที่เก็บข้อมูล Blob
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3d573a6c83b7f0b0c33e656eb383e20a96856b0b
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757409"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>ส่งออกรายการเซ็กเมนต์และข้อมูลอื่น ๆ ไปยังที่เก็บข้อมูล Azure Blob (ตัวอย่าง)

จัดเก็บข้อมูล Customer Insights ของคุณในที่เก็บข้อมูล Blob หรือใช้ในการย้ายข้อมูลไปยังแอปพลิเคชันอื่น

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

1. สำหรับที่เก็บข้อมูล Azure Blob คุณสามารถเลือกได้ระหว่าง [ระดับประสิทธิภาพมาตรฐานและประสิทธิภาพพรีเมียม](/azure/storage/blobs/storage-blob-performance-tiers) หากคุณเลือกระดับประสิทธิภาพพรีเมียม ให้เลือก [Blob บล็อกพรีเมียมเป็นชนิดบัญชี](/azure/storage/common/storage-account-overview#types-of-storage-accounts)

## <a name="set-up-the-connection-to-blob-storage"></a>ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Blob

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **ที่เก็บข้อมูล Azure Blob** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชีที่เก็บข้อมูล Blob ของคุณ
    - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชี Blob Storage และคีย์บัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
    - หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น 

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

> [!IMPORTANT]
> หากคุณเปิดการตั้งค่าการลบแบบชั่วคราวสำหรับบัญชีที่เก็บข้อมูล Azure Blob การส่งออกจะล้มเหลว ปิดการลบแบบชั่วคราวเพื่อส่งออกข้อมูลไปยัง Blob ดูข้อมูลเพิ่มเติมได้ที่ [เปิดใช้งานการลบแบบชั่วคราวของ Blob](/azure/storage/blobs/soft-delete-blob-enable)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วนที่เก็บข้อมูล Azure Blob หากคุณไม่เห็นชื่อส่วนนี้ การเชื่อมต่อชนิดนี้ไม่พร้อมใช้งานสำหรับคุณ

1. เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้

1. เลือก **บันทึก**

การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที

การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)     

นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand) 

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Blob ที่คุณกำหนดค่าไว้ เส้นทางโฟลเดอร์ต่อไปนี้จะถูกสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ

- สำหรับเอนทิตีต้นทางและเอนทิตีที่สร้างโดยระบบ:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- model.json สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ %ExportDestinationName%  
  - ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
