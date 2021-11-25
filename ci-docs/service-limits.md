---
title: ขีดจำกัดบริการใน Dynamics 365 Customer Insights
description: ทำความเข้าใจขีดจำกัดและข้อจำกัด
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/10/2021
ms.locfileid: "7792003"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>ข้อจำกัดการบริการในความสามารถ Customer Insights

บทความนี้อธิบายถึงขีดจำกัดในตัวของบริการ Customer Insights ซึ่งออกแบบมาเพื่อให้มั่นใจในความน่าเชื่อถือและความเสถียรของบริการ การร้องขอสำหรับการเปลี่ยนแปลงใด ๆ สามารถทำได้ผ่านทาง [ฟอรั่มเกี่ยวกับไอเดีย](https://go.microsoft.com/fwlink/?linkid=2074172) 

## <a name="audience-insights"></a>ข้อมูลเชิงลึกของผู้ชม

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>ขีดจำกัดบริการในความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights

| พื้นที่  | ขีดจำกัด  | บันทึกย่อ |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| เซ็กเมนต์ การวัด และการคาดคะเน | 300  | จำนวนทั้งหมดของ [เซ็กเมนต์](audience-insights/segments.md), [การวัด](audience-insights/measures.md) และ [การคาดคะเน](audience-insights/predictions.md) รวมกันได้ต้องไม่เกิน 300  |
| ความสัมพันธ์ | ความลึก 20 ระดับสำหรับความสัมพันธ์ในเส้นทางเอนทิตี | เมื่อสร้าง [เซ็กเมนต์](audience-insights/segments.md) หรือ [การวัด](audience-insights/measures.md) โดยใช้ส่วนติดต่อของตัวสร้าง เส้นทางของเอนทิตีสามารถมีความสัมพันธ์ระหว่างเอนทิตีเริ่มต้นและเอนทิตีเป้าหมายได้สูงสุด 20 ระดับ  |


## <a name="engagement-insights"></a>ข้อมูลเชิงลึกของการมีส่วนร่วม

### <a name="workspace-and-event-quotas"></a>โควตาพื้นที่ทำงานและเหตุการณ์

ข้อมูลเชิงลึกของการมีส่วนร่วมเป็นแอปพลิเคชันที่ปรับขนาดได้สูงซึ่งสามารถรองรับเหตุการณ์นับล้านต่อวินาที ในระหว่างการแสดงตัวอย่างสาธารณะ เหตุการณ์จะมีขีดจำกัดปริมาณ นอกจากนี้ยังมีการจำกัดจำนวนพื้นที่ทำงานในองค์กร

### <a name="engagement-insights-limits"></a>ขีดจำกัดข้อมูลเชิงลึกของการมีส่วนร่วม

- ปริมาณเหตุการณ์สูงสุดต่อพื้นที่ทำงาน = 100 เหตุการณ์ต่อวินาที

- จำนวนพื้นที่ทำงานสูงสุดต่อองค์กร = 100

เมื่อเหตุการณ์เกินเกณฑ์ อาจนำไปสู่การสูญเสียข้อมูลในรายงานตามเหตุการณ์เหล่านั้น คุณสามารถ [ติดต่อฝ่ายสนับสนุน](https://go.microsoft.com/fwlink/?linkid=2145734) เพื่อขอเพิ่มปริมาณก่อนที่คุณจะเกินขีดจำกัด เราจะทำงานร่วมกับคุณเพื่อกำหนดความต้องการของคุณในการเพิ่มปริมาณและสนับสนุนคำขอของคุณ


[!INCLUDE[footer-include](includes/footer-banner.md)]
