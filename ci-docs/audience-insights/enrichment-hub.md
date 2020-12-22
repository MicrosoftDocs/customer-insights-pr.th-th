---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าแบบรวม
description: ใช้ความสามารถเพื่อเพิ่มข้อมูลลูกค้าของคุณ
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667117"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="5216d-103">การเพิ่มข้อมูลสำหรับโปรไฟล์ลูกค้า (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="5216d-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="5216d-104">ใช้ข้อมูลจากแหล่งต่างๆ เช่น Microsoft และคู่ค้าอื่นๆ เพื่อเพิ่มข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="5216d-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="หน้าฮับการเพิ่มข้อมูล":::

<span data-ttu-id="5216d-106">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** เพื่อทำงานกับตัวเลือกการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5216d-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="5216d-107">คุณต้องมีสิทธิ์ผู้สนับสนุนหรือผู้ดูแลระบบ เพื่อสร้างหรือแก้ไขการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5216d-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="5216d-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์](permissions.md)</span><span class="sxs-lookup"><span data-stu-id="5216d-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="5216d-109">บนแท็บ **ค้นพบ** คุณจะพบการเพิ่มข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="5216d-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="5216d-110">[แบรนด์](enrichment-microsoft-graph.md) ซึ่งมีให้โดย Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5216d-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="5216d-111">[ความสนใจ](enrichment-microsoft-graph.md) ซึ่งมีให้โดย Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="5216d-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="5216d-112">[ข้อมูลบริษัท](enrichment-leadspace.md) ซึ่งมีให้โดย Leadspace</span><span class="sxs-lookup"><span data-stu-id="5216d-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="5216d-113">[ประชากรศาสตร์](enrichment-experian.md) นำเสนอโดย Experian</span><span class="sxs-lookup"><span data-stu-id="5216d-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="5216d-114">[ข้อมูลตำแหน่งที่ตั้ง](enrichment-here.md) ให้บริการโดย HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5216d-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="5216d-115">[ข้อมูลที่กำหนดเอง](enrichment-SFTP-custom-import.md) ผ่าน Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="5216d-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="5216d-116">บนแท็บ **การเพิ่มข้อมูลของฉัน** คุณสามารถดูการเพิ่มข้อมูลที่คุณได้ตั้งค่าคอนฟิกและแก้ไขคุณสมบัติได้</span><span class="sxs-lookup"><span data-stu-id="5216d-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="5216d-117">จัดการการเพิ่มข้อมูลที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="5216d-117">Manage existing enrichments</span></span>

<span data-ttu-id="5216d-118">ไปที่ **การเพิ่มข้อมูลของฉัน** เพื่อดูการเพิ่มข้อมูลที่กำหนดค่าไว้ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="5216d-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="5216d-119">การเพิ่มข้อมูลแต่ละรายการจะแสดงเป็นแถวที่มีข้อมูลเพิ่มเติมเกี่ยวกับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5216d-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="5216d-120">เลือกการเพิ่มข้อมูลเพื่อดูตัวเลือกที่มี</span><span class="sxs-lookup"><span data-stu-id="5216d-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="5216d-121">หรือคุณสามารถเลือกจุดไข่ปลา (...) ในรายการเพื่อดูตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="5216d-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="ตัวเลือกในการจัดการการเพิ่มข้อมูลในรายการการเพิ่มข้อมูล":::

- <span data-ttu-id="5216d-123">**ดู** รายละเอียดการเพิ่มข้อมูลพร้อมจำนวนโปรไฟล์ลูกค้าที่ปรับปรุงแล้ว</span><span class="sxs-lookup"><span data-stu-id="5216d-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="5216d-124">**แก้ไข** การกำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5216d-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="5216d-125">**รัน** การเพิ่มข้อมูลเพื่ออัปเดตโปรไฟล์ลูกค้าด้วยข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="5216d-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="5216d-126">**ปิดใช้งาน** การเพิ่มข้อมูลที่มีอยู่เพื่อหยุดการรีเฟรชโดยอัตโนมัติทุกครั้งที่รีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="5216d-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="5216d-127">ข้อมูลจากการรีเฟรชที่สำเร็จครั้งล่าสุดจะยังคงพร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="5216d-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="5216d-128">**เปิดใช้งาน** การเพิ่มข้อมูลที่ไม่ใช้งานเพื่อเริ่มการรีเฟรชอัตโนมัติทุกครั้งที่รีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="5216d-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="5216d-129">**ลบ** การเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5216d-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="5216d-130">คุณสามารถเรียกใช้หรือปิดใช้งานการเพิ่มข้อมูลหลายรายการพร้อมกันได้โดยเลือกจากรายการ</span><span class="sxs-lookup"><span data-stu-id="5216d-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="5216d-131">ตัวเลือกการดูและแก้ไขไม่สามารถใช้ได้เป็นการดำเนินการจำนวนมากและใช้ได้กับการเพิ่มข้อมูลทีละรายการเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="5216d-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
