---
title: การรวมข้อมูล
description: เรียนรู้วิธีการรวมข้อมูลที่นำเข้า
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407126"
---
# <a name="data-unification"></a>การรวมข้อมูล

หลังจาก [การตั้งค่าแหล่งข้อมูล](data-sources.md) คุณสามารถรวมข้อมูลเข้าด้วยกัน การรวมข้อมูลประกอบด้วยสามขั้นตอน **แม็ป** **จับคู่** และ **ผสาน**

กระบวนการรวมข้อมูลช่วยให้คุณรวมแหล่งข้อมูลที่แตกต่างกันครั้งเดียวในชุดข้อมูลหลักเดียวที่ให้มุมมองที่เป็นหนึ่งเดียวของลูกค้าของคุณ การรวมลำดับขั้นเป็นข้อบังคับและดำเนินการตามลำดับต่อไปนี้:

1. [แม็ป](map-entities.md)
2. [การจับคู่](match-entities.md)
3. [ผสาน](merge-entities.md)

หลังจากเสร็จสิ้นการรวมข้อมูล คุณสามารถเลือก

- [ตั้งค่าความสัมพันธ์ระหว่างเอนทิตี](relationships.md) เพื่อสร้างเซ็กเมนต์ที่ทันสมัย
- [เพิ่มข้อมูล](enrichment-hub.md) ของคุณ เพื่อให้ได้ข้อมูลเชิงลึกที่หลากหลายเกี่ยวกับลูกค้าของคุณ
- [กำหนดกิจกรรม](activities.md) จากแอตทริบิวต์ที่นำเข้าบางส่วน
