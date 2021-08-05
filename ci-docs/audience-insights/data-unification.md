---
title: การรวมข้อมูล
description: เรียนรู้วิธีการรวมข้อมูลที่นำเข้า
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539092"
---
# <a name="data-unification-overview"></a>ภาพรวมการรวมข้อมูล

หลังจาก [การตั้งค่าแหล่งข้อมูล](data-sources.md) คุณสามารถรวมข้อมูลเข้าด้วยกัน การรวมข้อมูลประกอบด้วยสามขั้นตอน **แม็ป** **จับคู่** และ **ผสาน**

กระบวนการรวมข้อมูลช่วยให้คุณรวมแหล่งข้อมูลที่แตกต่างกันครั้งเดียวในชุดข้อมูลหลักเดียวที่ให้มุมมองที่เป็นหนึ่งเดียวของลูกค้าของคุณ การรวมลำดับขั้นเป็นข้อบังคับและดำเนินการตามลำดับต่อไปนี้:

1. [แม็ป](map-entities.md)
2. [การจับคู่](match-entities.md)
3. [ผสาน](merge-entities.md)

หลังจากเสร็จสิ้นการรวมข้อมูล คุณสามารถเลือก

- [ตั้งค่าความสัมพันธ์ระหว่างเอนทิตี](relationships.md) เพื่อสร้างเซ็กเมนต์ที่ทันสมัย
- [เพิ่มข้อมูล](enrichment-hub.md) ของคุณ เพื่อให้ได้ข้อมูลเชิงลึกที่หลากหลายเกี่ยวกับลูกค้าของคุณ
- [กำหนดกิจกรรม](activities.md) จากแอตทริบิวต์ที่นำเข้าบางส่วน


[!INCLUDE[footer-include](../includes/footer-banner.md)]