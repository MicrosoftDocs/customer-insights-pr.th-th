---
title: ส่งออกข้อมูล Customer Insights ไปยัง InMobi
description: เรียนรู้วิธีการกำหนดค่าการเชื่อมต่อและส่งออกไปยัง InMobi
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195911"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>ส่งออกข้อมูล Customer Insights ไปยัง InMobi (พรีวิว)

ส่งออกรายการเซ็กเมนต์หรือข้อมูลอื่นๆ จากอินสแตนซ์ Customer Insights ของคุณไปยัง [InMobi](https://www.inmobi.com/)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [บัญชี InMobi](https://www.inmobi.com/) และข้อมูลประจำตัวของผู้ดูแลระบบ
- ชื่อ [บัญชีที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) และรหัสบัญชี หากต้องการค้นหาชื่อและรหัส โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)
- [คอนเทนเนอร์ที่เก็บข้อมูล Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) ที่จะส่งออกข้อมูล InMobi
- InMobi จะสร้างการเชื่อมต่อโดยตรงกับที่เก็บข้อมูล Blob ของคุณและกำหนดค่าการนำเข้าข้อมูลของคุณไปยัง InMobi โดยอัตโนมัติ ติดต่อเจ้าหน้าที่ InMobi ของคุณเพื่อเริ่มกระบวนการ

## <a name="known-limitations"></a>ข้อจำกัดที่ทราบ

- สำหรับที่เก็บข้อมูล Azure Blob เลือกระหว่าง [ระดับประสิทธิภาพมาตรฐานและประสิทธิภาพพรีเมียม](/azure/storage/blobs/storage-blob-performance-tiers) หากคุณเลือกระดับประสิทธิภาพพรีเมียม ให้เลือก [Blob บล็อกพรีเมียมเป็นชนิดบัญชี](/azure/storage/common/storage-account-overview#types-of-storage-accounts)

## <a name="set-up-connection-to-azure-blob-storage"></a>ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob

[ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Azure Blob ของคุณ](export-azure-blob-storage.md)

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[กำหนดค่าการส่งออก](export-azure-blob-storage.md#configure-an-export)

[!INCLUDE [footer-include](includes/footer-banner.md)]
