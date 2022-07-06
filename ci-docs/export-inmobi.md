---
title: ส่งออกข้อมูล Customer Insights ไปยัง InMobi
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง InMobi
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056553"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>ส่งออกรายการเซ็กเมนต์และข้อมูลอื่นๆ ไปยัง InMobi (พรีวิว)

ส่งออกรายการเซ็กเมนต์หรือข้อมูลอื่นๆ จากอินสแตนซ์ Customer Insights ของคุณไปยัง [InMobi](https://www.inmobi.com/)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

1. คุณมี [บัญชี InMobi](https://www.inmobi.com/) และข้อมูลประจำตัวของผู้ดูแลระบบ
1. คุณมีชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชีที่เกี่ยวข้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage) มีคอนเทนเนอร์ในบัญชีที่เก็บข้อมูลสำหรับส่งออกข้อมูล InMobi สำหรับข้อมูลเพิ่มเติม โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)
1. InMobi จะสร้างการเชื่อมต่อโดยตรงกับที่เก็บข้อมูล Blob ของคุณและกำหนดค่าการนำเข้าข้อมูลของคุณไปยัง InMobi โดยอัตโนมัติ ติดต่อเจ้าหน้าที่ InMobi ของคุณเพื่อเริ่มกระบวนการ

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

1. สำหรับที่เก็บข้อมูล Azure Blob คุณสามารถเลือกได้ระหว่าง [ระดับประสิทธิภาพมาตรฐานและประสิทธิภาพพรีเมียม](/azure/storage/blobs/storage-blob-performance-tiers) หากคุณเลือกระดับประสิทธิภาพพรีเมียม ให้เลือก [Blob บล็อกพรีเมียมเป็นชนิดบัญชี](/azure/storage/common/storage-account-overview#types-of-storage-accounts)

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob และกำหนดค่าการส่งออก

1. ทำตามคำแนะนำเพื่อ [ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob ของคุณ](export-azure-blob-storage.md)
2. ทำตามคำแนะนำเพื่อ [กำหนดค่าการส่งออก](export-azure-blob-storage.md#configure-an-export)

[!INCLUDE [footer-include](includes/footer-banner.md)]
