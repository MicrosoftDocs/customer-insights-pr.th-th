---
title: ขีดจำกัดบริการใน Dynamics 365 Customer Insights
description: ทำความเข้าใจขีดจำกัดและข้อจำกัด
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350430"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>ข้อจำกัดการบริการในความสามารถ Customer Insights

บทความนี้อธิบายถึงขีดจำกัดในตัวของบริการ Customer Insights ซึ่งออกแบบมาเพื่อให้มั่นใจในความน่าเชื่อถือและความเสถียรของบริการ การร้องขอสำหรับการเปลี่ยนแปลงใด ๆ สามารถทำได้ผ่านทาง [ฟอรั่มเกี่ยวกับไอเดีย](https://go.microsoft.com/fwlink/?linkid=2074172) 

## <a name="audience-insights"></a>ข้อมูลเชิงลึกของผู้ชม

| พื้นที่  | ขีดจำกัด  | บันทึกย่อ |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| เซ็กเมนต์ การวัด และการคาดคะเน | 300  | จำนวนทั้งหมดของ [เซ็กเมนต์](audience-insights/segments.md), [การวัด](audience-insights/measures.md) และ [การคาดคะเน](audience-insights/predictions.md) รวมกันได้ต้องไม่เกิน 300  |
| ความสัมพันธ์ | ความลึก 20 ระดับสำหรับความสัมพันธ์ในเส้นทางเอนทิตี | เมื่อสร้าง [เซ็กเมนต์](audience-insights/segments.md) หรือ [การวัด](audience-insights/measures.md) โดยใช้ส่วนติดต่อของตัวสร้าง เส้นทางของเอนทิตีสามารถมีความสัมพันธ์ระหว่างเอนทิตีเริ่มต้นและเอนทิตีเป้าหมายได้สูงสุด 20 ระดับ  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
