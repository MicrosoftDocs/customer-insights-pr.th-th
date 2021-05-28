---
title: เพิ่มข้อมูลโปรไฟล์ลูกค้าแบบรวม
description: ใช้ความสามารถเพื่อเพิ่มข้อมูลลูกค้าของคุณ
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954510"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="5b8ae-103">การเพิ่มข้อมูลสำหรับโปรไฟล์ลูกค้า (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="5b8ae-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="5b8ae-104">ใช้ข้อมูลจากแหล่งต่างๆ เช่น Microsoft และคู่ค้าอื่นๆ เพื่อเพิ่มข้อมูลลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="5b8ae-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="หน้าฮับการเพิ่มข้อมูล":::

<span data-ttu-id="5b8ae-106">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** เพื่อทำงานกับตัวเลือกการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="5b8ae-107">คุณต้องมีสิทธิ์ผู้สนับสนุนหรือผู้ดูแลระบบ เพื่อสร้างหรือแก้ไขการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="5b8ae-108">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์](permissions.md)</span><span class="sxs-lookup"><span data-stu-id="5b8ae-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="5b8ae-109">บนแท็บ **ค้นพบ** คุณจะพบการเพิ่มข้อมูลต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="5b8ae-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="5b8ae-110">[แบรนด์](enrichment-microsoft.md) จัดทำโดย Microsoft</span><span class="sxs-lookup"><span data-stu-id="5b8ae-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5b8ae-111">[ความสนใจ](enrichment-microsoft.md) จัดทำโดย Microsoft</span><span class="sxs-lookup"><span data-stu-id="5b8ae-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5b8ae-112">[ที่อยู่ที่ปรับปรุงแล้ว](enrichment-enhanced-addresses.md) ที่ได้รับจาก Microsoft</span><span class="sxs-lookup"><span data-stu-id="5b8ae-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="5b8ae-113">[ข้อมูลบริษัท](enrichment-leadspace.md) ซึ่งมีให้โดย Leadspace</span><span class="sxs-lookup"><span data-stu-id="5b8ae-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="5b8ae-114">[ประชากรศาสตร์](enrichment-experian.md) นำเสนอโดย Experian</span><span class="sxs-lookup"><span data-stu-id="5b8ae-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="5b8ae-115">[ข้อมูลตำแหน่งที่ตั้ง](enrichment-here.md) ให้บริการโดย HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5b8ae-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="5b8ae-116">[ข้อมูลที่กำหนดเอง](enrichment-SFTP-custom-import.md) ผ่าน Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="5b8ae-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="5b8ae-117">บนแท็บ **การเพิ่มข้อมูลของฉัน** คุณสามารถดูการเพิ่มข้อมูลที่คุณได้ตั้งค่าคอนฟิกและแก้ไขคุณสมบัติได้</span><span class="sxs-lookup"><span data-stu-id="5b8ae-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="5b8ae-118">จัดการการเพิ่มข้อมูลที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="5b8ae-118">Manage existing enrichments</span></span>

<span data-ttu-id="5b8ae-119">ไปที่ **การเพิ่มข้อมูลของฉัน** เพื่อดูการเพิ่มข้อมูลที่กำหนดค่าไว้ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="5b8ae-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="5b8ae-120">การเพิ่มข้อมูลแต่ละรายการจะแสดงเป็นแถวที่มีข้อมูลเพิ่มเติมเกี่ยวกับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="5b8ae-121">เลือกการเพิ่มข้อมูลเพื่อดูตัวเลือกที่มี</span><span class="sxs-lookup"><span data-stu-id="5b8ae-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="5b8ae-122">คุณยังสามารถเลือกจุดไข่ปลา (...) บนรายการเพื่อดูตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="5b8ae-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="ตัวเลือกในการจัดการการเพิ่มข้อมูลในรายการการเพิ่มข้อมูล":::

- <span data-ttu-id="5b8ae-124">**ดู** รายละเอียดการเพิ่มข้อมูลพร้อมจำนวนโปรไฟล์ลูกค้าที่ปรับปรุงแล้ว</span><span class="sxs-lookup"><span data-stu-id="5b8ae-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="5b8ae-125">**แก้ไข** การกำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="5b8ae-126">**รัน** การเพิ่มข้อมูลเพื่ออัปเดตโปรไฟล์ลูกค้าด้วยข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="5b8ae-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="5b8ae-127">**ปิดใช้งาน** การเพิ่มข้อมูลที่มีอยู่เพื่อหยุดการรีเฟรชโดยอัตโนมัติทุกครั้งที่รีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="5b8ae-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="5b8ae-128">ข้อมูลจากการรีเฟรชที่สำเร็จครั้งล่าสุดจะยังคงพร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="5b8ae-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="5b8ae-129">**เปิดใช้งาน** การเพิ่มข้อมูลที่ไม่ใช้งานเพื่อเริ่มการรีเฟรชอัตโนมัติทุกครั้งที่รีเฟรชตามกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="5b8ae-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="5b8ae-130">**ลบ** การเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="5b8ae-131">คุณสามารถเรียกใช้หรือปิดใช้งานการเพิ่มข้อมูลหลายรายการพร้อมกันได้โดยเลือกจากรายการ</span><span class="sxs-lookup"><span data-stu-id="5b8ae-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="5b8ae-132">ตัวเลือกการดูและแก้ไขไม่สามารถใช้ได้เป็นการดำเนินการจำนวนมากและใช้ได้กับการเพิ่มข้อมูลทีละรายการเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="5b8ae-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="5b8ae-133">การเพิ่มข้อมูลและการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5b8ae-133">Enrichments and connections</span></span>

<span data-ttu-id="5b8ae-134">การเพิ่มข้อมูลของบุคคลที่สามได้รับการกำหนดค่าโดยใช้ [การเชื่อมต่อ](connections.md) ซึ่งผู้ดูแลระบบตั้งค่าด้วยข้อมูลประจำตัวและให้ความยินยอมในการถ่ายโอนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="5b8ae-135">การเชื่อมต่อสามารถใช้เพื่อเพิ่มข้อมูลได้ทั้งโดยผู้ดูแลระบบและผู้สนับสนุนเพื่อกำหนดค่าการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="5b8ae-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="5b8ae-136">การเพิ่มข้อมูลหลายรายการในชนิดเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="5b8ae-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="5b8ae-137">มีการระบุเอนทิตีที่จะทำให้สมบูรณ์ในระหว่างการกำหนดค่าการเพิ่มข้อมูล ซึ่งช่วยให้คุณสามารถสร้างโปรไฟล์ของคุณได้เพียงบางส่วนเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="5b8ae-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="5b8ae-138">สำหรับตัวอย่าง ให้เพิ่มข้อมูลสำหรับเซ็กเมนต์เฉพาะเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="5b8ae-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="5b8ae-139">คุณสามารถกำหนดค่าการเพิ่มข้อมูลชนิดเดียวกันหลายรายการและใช้การเชื่อมต่อเดียวกันซ้ำได้</span><span class="sxs-lookup"><span data-stu-id="5b8ae-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="5b8ae-140">การเพิ่มข้อมูลบางอย่างจะมีข้อจำกัดสำหรับจำนวนของการเพิ่มข้อมูลชนิดเดียวกันกับที่สามารถสร้างได้</span><span class="sxs-lookup"><span data-stu-id="5b8ae-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="5b8ae-141">ขีดจำกัดและการใช้งานปัจจุบันสามารถดูได้ที่หน้า **การเพิ่มข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="5b8ae-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
