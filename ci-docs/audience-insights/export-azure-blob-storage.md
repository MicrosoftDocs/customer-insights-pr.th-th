---
title: ส่งออกข้อมูล Customer Insights ไปยังที่เก็บข้อมูล Azure Blob
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596200"
---
# <a name="connector-for-azure-blob-storage-preview"></a>ตัวเชื่อมต่อสำหรับที่เก็บข้อมูล Azure Blob (แสดงตัวอย่าง)

จัดเก็บข้อมูล Customer Insights ในที่เก็บข้อมูล Azure Blob หรือใช้ในการย้ายข้อมูลไปยังแอปพลิเคชันอื่น

## <a name="configure-the-connector-for-azure-blob-storage"></a>กำหนดค่าตัวเชื่อมต่อสำหรับที่เก็บข้อมูล Azure Blob

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **ที่เก็บข้อมูล Azure Blob** เลือก **ติดตั้ง**

1. ป้อน **ชื่อลูกค้าองค์กร** **รหัสลูกค้าองค์กร** และ **คอนเทนเนอร์** สำหรับลูกค้าองค์กรที่เก็บข้อมูล Azure Blob ของคุณ
    - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชี ให้ดูที่ [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
    - หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**

1. เลือก **ถัดไป**

1. เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้

1. เลือก **บันทึก**

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่า เส้นทางโฟลเดอร์ต่อไปนี้จะถูกสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ

- สำหรับเอนทิตีต้นทางและเอนทิตีที่สร้างโดยระบบ: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ %ExportDestinationName%
  - ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#export-data-on-demand) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง


[!INCLUDE[footer-include](../includes/footer-banner.md)]