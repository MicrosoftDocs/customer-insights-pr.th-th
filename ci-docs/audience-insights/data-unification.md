---
title: สร้างมุมมองแบบรวมของลูกค้าของคุณ
description: ทำตามขั้นตอนการรวมข้อมูลกับข้อมูลของคุณเพื่อสร้างชุดข้อมูลหลักเดียวของโปรไฟล์ลูกค้า
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648094"
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