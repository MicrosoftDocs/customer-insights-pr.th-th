---
title: ส่งออกข้อมูลไปยัง Azure Data Lake Storage รุ่น2 (พรีวิว)
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อกับ Azure Data Lake Storage รุ่น2
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196463"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>ส่งออกข้อมูลไปยัง Azure Data Lake Storage รุ่น2 (พรีวิว)

จัดเก็บข้อมูล Customer Insights ของคุณในบัญชี Data Lake Storage รุ่น2 หรือใช้ในการย้ายข้อมูลไปยังแอปพลิเคชันอื่น

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชีที่เก็บข้อมูลที่ใช้กับ Azure Data Lake รุ่น2](/azure/storage/blobs/create-data-lake-storage-account) หากต้องการค้นหาชื่อบัญชีที่เก็บข้อมูลและคีย์ โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
- [คอนเทนเนอร์ที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- สำหรับ Azure Data Lake Storage รุ่น2 เลือกระหว่าง [ระดับประสิทธิภาพมาตรฐานและประสิทธิภาพพรีเมียม](/azure/storage/blobs/create-data-lake-storage-account) หากคุณเลือกระดับประสิทธิภาพพรีเมียม ให้เลือก [Blob บล็อกพรีเมียมเป็นชนิดบัญชี](/azure/storage/common/storage-account-overview#types-of-storage-accounts)

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>ตั้งค่าการเชื่อมต่อกับ Azure Data Lake Storage รุ่น2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Azure Data Lake รุ่น2**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับ Azure Data Lake Storage รุ่น2 ของคุณ

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Azure Data Lake ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ป้อนชื่อสำหรับการส่งออก

1. ป้อนชื่อโฟลเดอร์สำหรับที่เก็บข้อมูล Azure Data Lake Storage รุ่น2

1. เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Azure Data Lake รุ่น 2 ที่คุณกำหนดค่าไว้

> [!TIP]
> การส่งออกเอนทิตีที่มีข้อมูลจำนวนมากสามารถนำไปยังไฟล์ CSV หลายไฟล์ในโฟลเดอร์เดียวกันสำหรับการส่งออกแต่ละครั้ง การส่งออกแบบแยกส่วนเกิดขึ้นเนื่องจากเหตุผลด้านประสิทธิภาพ เพื่อลดเวลาที่ใช้ในการส่งออกให้เสร็จสมบูรณ์

[!INCLUDE [footer-include](includes/footer-banner.md)]
