---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Data Lake Storage Gen2
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อกับ Azure Data Lake Storage Gen2
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947253"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>ส่งออกรายการเซ็กเมนต์และข้อมูลอื่นๆ ไปยัง Azure Data Lake Storage Gen2 (ตัวอย่าง)

จัดเก็บข้อมูล Customer Insights ของคุณในบัญชี Data Lake Storage Gen2 หรือใช้ในการย้ายข้อมูลไปยังแอปพลิเคชันอื่น

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

1. สำหรับ Azure Data Lake Storage Gen2 คุณสามารถเลือกระหว่าง [ระดับประสิทธิภาพมาตรฐานและประสิทธิภาพพรีเมียม](/azure/storage/blobs/create-data-lake-storage-account) เมื่อคุณสร้างบัญชีจัดเก็บข้อมูลสำหรับที่จัดเก็บข้อมูลดิบของคุณ หากคุณเลือกระดับประสิทธิภาพพรีเมียม ให้เลือก Blob บล็อกพรีเมียมเป็นชนิดบัญชี

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>ตั้งค่าการเชื่อมต่อ Azure Data Lake Storage Gen2

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Data Lake Gen 2** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับ Azure Data Lake Storage Gen2 ของคุณ
    - หากต้องการเรียนรู้วิธีสร้างบัญชีที่เก็บข้อมูลที่จะใช้กับ Azure Data Lake Storage Gen2 ดู [สร้างบัญชีที่เก็บข้อมูล](/azure/storage/blobs/create-data-lake-storage-account) 
    - หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับชื่อบัญชีที่เก็บข้อมูล Azure Data Lake Gen 2 และรหัสบัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน **Azure Data Lake** หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้

1. เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้

1. เลือก **บันทึก**

การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที

การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)
นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)

ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Azure Data Lake Gen 2 ที่คุณกำหนดค่าไว้

> [!TIP]
> การส่งออกเอนทิตีที่มีข้อมูลจำนวนมากสามารถนำไปยังไฟล์ CSV หลายไฟล์ในโฟลเดอร์เดียวกันสำหรับการส่งออกแต่ละครั้ง การส่งออกแบบแยกส่วนเกิดขึ้นเนื่องจากเหตุผลด้านประสิทธิภาพ เพื่อลดเวลาที่ใช้ในการส่งออกให้เสร็จสมบูรณ์

[!INCLUDE [footer-include](includes/footer-banner.md)]
