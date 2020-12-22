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
# <a name="data-unification"></a><span data-ttu-id="fc3f5-103">การรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="fc3f5-103">Data unification</span></span>

<span data-ttu-id="fc3f5-104">หลังจาก [การตั้งค่าแหล่งข้อมูล](data-sources.md) คุณสามารถรวมข้อมูลเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="fc3f5-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="fc3f5-105">การรวมข้อมูลประกอบด้วยสามขั้นตอน **แม็ป** **จับคู่** และ **ผสาน**</span><span class="sxs-lookup"><span data-stu-id="fc3f5-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="fc3f5-106">กระบวนการรวมข้อมูลช่วยให้คุณรวมแหล่งข้อมูลที่แตกต่างกันครั้งเดียวในชุดข้อมูลหลักเดียวที่ให้มุมมองที่เป็นหนึ่งเดียวของลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="fc3f5-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="fc3f5-107">การรวมลำดับขั้นเป็นข้อบังคับและดำเนินการตามลำดับต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="fc3f5-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="fc3f5-108">แม็ป</span><span class="sxs-lookup"><span data-stu-id="fc3f5-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="fc3f5-109">การจับคู่</span><span class="sxs-lookup"><span data-stu-id="fc3f5-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="fc3f5-110">ผสาน</span><span class="sxs-lookup"><span data-stu-id="fc3f5-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="fc3f5-111">หลังจากเสร็จสิ้นการรวมข้อมูล คุณสามารถเลือก</span><span class="sxs-lookup"><span data-stu-id="fc3f5-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="fc3f5-112">[ตั้งค่าความสัมพันธ์ระหว่างเอนทิตี](relationships.md) เพื่อสร้างเซ็กเมนต์ที่ทันสมัย</span><span class="sxs-lookup"><span data-stu-id="fc3f5-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="fc3f5-113">[เพิ่มข้อมูล](enrichment-hub.md) ของคุณ เพื่อให้ได้ข้อมูลเชิงลึกที่หลากหลายเกี่ยวกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="fc3f5-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="fc3f5-114">[กำหนดกิจกรรม](activities.md) จากแอตทริบิวต์ที่นำเข้าบางส่วน</span><span class="sxs-lookup"><span data-stu-id="fc3f5-114">[define activities](activities.md) from some of the ingested attributes</span></span>
