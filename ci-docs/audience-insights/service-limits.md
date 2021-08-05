---
title: ขีดจำกัดบริการ
description: ทำความเข้าใจขีดจำกัดและข้อจำกัด
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604392"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>ขีดจำกัดบริการในความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights

บทความนี้อธิบายถึงขีดจำกัดในตัวของบริการ Customer Insights ซึ่งออกแบบมาเพื่อให้มั่นใจในความน่าเชื่อถือและความเสถียรของบริการ การร้องขอสำหรับการเปลี่ยนแปลงใด ๆ สามารถทำได้ผ่านทาง [ฟอรั่มเกี่ยวกับไอเดีย](https://go.microsoft.com/fwlink/?linkid=2074172) 
 
| พื้นที่  | ขีดจำกัด  | บันทึกย่อ |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| เซ็กเมนต์และการวัด | 100 เซ็กเมนต์หรือการวัด | จำนวนทั้งหมดที่ใช้งานอยู่ของ [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) รวมกันไม่เกิน 100  |
| ความสัมพันธ์ | ความลึก 20 ระดับสำหรับความสัมพันธ์ในเส้นทางเอนทิตี | เมื่อสร้าง [เซ็กเมนต์](segments.md) หรือ [การวัด](measures.md) โดยใช้ส่วนติดต่อของตัวสร้าง เส้นทางของเอนทิตีสามารถมีความสัมพันธ์ระหว่างเอนทิตีเริ่มต้นและเอนทิตีเป้าหมายได้สูงสุด 20 ระดับ  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]