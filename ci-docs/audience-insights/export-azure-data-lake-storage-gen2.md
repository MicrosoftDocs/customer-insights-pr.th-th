---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Data Lake Storage Gen2
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ Azure Data Lake Storage Gen2
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596665"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>ตัวเชื่อมต่อสำหรับ Azure Data Lake Storage Gen2 (พรีวิว)

จัดเก็บข้อมูล Customer Insights ของคุณใน Azure Data Lake Storage Gen2 หรือใช้ในการย้ายข้อมูลของคุณไปยังแอปพลิเคชันอื่น

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>ตั้งค่าคอนฟิกตัวเชื่อมต่อสำหรับ Azure Data Lake Storage Gen2

1. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**

1. ภายใต้ **Azure Data Lake Storage Gen2** เลือก **ตั้งค่า**

1. ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับ Azure Data Lake Storage Gen2 ของคุณ
    - หากต้องการเรียนรู้วิธีสร้างบัญชีที่เก็บข้อมูลที่จะใช้กับ Azure Data Lake Storage Gen2 ดู [สร้างบัญชีที่เก็บข้อมูล](/azure/storage/blobs/create-data-lake-storage-account) 
    - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Data Lake Gen2 และรหัสบัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)

1. เลือก **ถัดไป**

1. เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้

1. เลือก **บันทึก**

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#export-data-on-demand) นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง