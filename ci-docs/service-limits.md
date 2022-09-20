---
title: ข้อจำกัดการบริการใน Customer Insights
description: ทำความเข้าใจขีดจำกัดและข้อจำกัดภายในบริการ SaaS ของ Customer Insights
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463242"
---
# <a name="service-limits-in-customer-insights"></a>ข้อจำกัดการบริการใน Customer Insights

 Customer Insights มีขีดจำกัดในตัวซึ่งออกแบบมาเพื่อรับรองความน่าเชื่อถือและความเสถียรของบริการ การร้องขอสำหรับการเปลี่ยนแปลงใด ๆ สามารถทำได้ผ่านทาง [ฟอรั่มเกี่ยวกับไอเดีย](https://go.microsoft.com/fwlink/?linkid=2074172)

## <a name="customer-insights"></a>Customer Insights

| พื้นที่  | ขีดจำกัด  | บันทึกย่อ |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| เซ็กเมนต์ การวัด และการคาดคะเน | 300  | จำนวนทั้งหมดของ [เซ็กเมนต์](segments.md), [การวัด](measures.md) และ [การคาดคะเน](predictions-overview.md) รวมกันได้ต้องไม่เกิน 300  |
| ความสัมพันธ์ | ความลึก 20 ระดับสำหรับความสัมพันธ์ในเส้นทางเอนทิตี | เมื่อสร้าง [เซ็กเมนต์](segments.md) หรือ [การวัด](measures.md) โดยใช้ส่วนติดต่อของตัวสร้าง เส้นทางของเอนทิตีสามารถมีความสัมพันธ์ระหว่างเอนทิตีเริ่มต้นและเอนทิตีเป้าหมายได้สูงสุด 20 ระดับ  |
|การนำเข้าข้อมูล| การประเมินพร้อมกันสำหรับแหล่งข้อมูล Power Query ได้รับการจำกัด | Customer Insights มี [ขีดจำกัดการรีเฟรช เช่น กระแสข้อมูล ใน PowerBI.com](/power-query/power-query-online-limits#refresh-limits) เหมือนกัน |

## <a name="fair-scheduling-of-jobs"></a>การจัดกำหนดการงานอย่างยุติธรรม

Customer Insights เป็นบริการ SaaS ที่ใช้ทรัพยากร Azure ที่ใช้ร่วมกัน ลูกค้ามักจะมีปริมาณงานที่มีระดับผันแปรสูงและตามกำหนดการที่แตกต่างกัน เพื่อให้แน่ใจว่ามีการเข้าถึงทรัพยากรพื้นฐานอย่างยุติธรรม เราตรวจสอบให้แน่ใจว่ากระบวนการของระบบได้รับการดำเนินการอย่างยุติธรรม ตัวอย่างของกระบวนการของระบบ ได้แก่ งานที่เกี่ยวข้องกับการรวมข้อมูล การปรับปรุงเซ็กเมนต์ หรือการคำนวณการวัด การจัดกำหนดการอย่างยุติธรรมจะช่วยปกป้องคุณจากการเข้าคิวสำหรับทรัพยากรหากมีงานที่ร้องขอจำนวนมาก ขณะเดียวกัน Customer Insights ไม่ได้รับประกันว่างานทั้งหมดที่คุณจัดคิวจะได้รับการประมวลผลพร้อมกัน

[!INCLUDE [footer-include](includes/footer-banner.md)]
