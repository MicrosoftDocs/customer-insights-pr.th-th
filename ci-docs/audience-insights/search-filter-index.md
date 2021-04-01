---
title: ค้นหาและกรองโปรไฟล์ลูกค้า
description: ค้นหาข้อมูลเกี่ยวกับโปรไฟล์ลูกค้าแบบรวมและตัวกรองสำหรับแอตทริบิวต์ที่ระบุได้อย่างรวดเร็ว
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597166"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="aed95-103">โปรไฟล์ลูกค้า: ดัชนีการค้นหาและตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="aed95-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="aed95-104">ผลลัพธ์ของการรวมข้อมูลลูกค้าของคุณคือ เอนทิตีโปรไฟล์ลูกค้าที่ให้มุมมองแบบรวมลงในฐานลูกค้ารวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="aed95-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="aed95-105">เมื่อต้องการ [ค้นหาข้อมูลเกี่ยวกับลูกค้าหรือกลุ่มของลูกค้าเฉพาะ](customer-profiles.md) อย่างรวดเร็ว คุณสามารถตั้งค่าคอนฟิกความสามารถ **ค้นหา** และ **กรอง** ในหน้า **ลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="aed95-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="aed95-106">อ่านต่อไปเพื่อเรียนรู้วิธีที่ผู้ดูแลระบบสามารถแก้ไขแอตทริบิวต์บนหน้า **ดัชนีการค้นหาและตัวกรอง** ซึ่งพร้อมใช้งานสำหรับผู้ใช้สำหรับการค้นหาและการกรอง</span><span class="sxs-lookup"><span data-stu-id="aed95-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aed95-107">![ตัวกรองการค้นหา](media/search-filter.png "ตัวกรองการค้นหา")</span><span class="sxs-lookup"><span data-stu-id="aed95-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="aed95-108">เพิ่มฟิลด์และระบุแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="aed95-108">Add fields and specify attributes</span></span>

<span data-ttu-id="aed95-109">ถ้าเป็นครั้งแรกที่คุณกำหนดแอตทริบิวต์ที่สามารถค้นหาได้เป็นผู้ดูแลระบบ คุณจำเป็นต้องกำหนดฟิลด์ที่ทำดัชนีเป็นอันดับแรก</span><span class="sxs-lookup"><span data-stu-id="aed95-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="aed95-110">เราขอแนะนำให้คุณเลือกแอตทริบิวต์ทั้งหมดที่ผู้ใช้สามารถค้นหาและกรองได้ในหน้า **ลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="aed95-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="aed95-111">คุณสามารถระบุได้เฉพาะแอตทริบิวต์ที่มีอยู่ในเอนทิตีของโปรไฟล์ลูกค้าที่คุณสร้างขึ้นในระหว่างกระบวนการรวมตัวของข้อมูล</span><span class="sxs-lookup"><span data-stu-id="aed95-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="aed95-112">เปิดหน้า **ลูกค้า** และเลือก **ดัชนีการค้นหาและตัวกรอง**</span><span class="sxs-lookup"><span data-stu-id="aed95-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="aed95-113">เลือก **+ เพิ่ม** เพื่อระบุฟิลด์ดัชนี</span><span class="sxs-lookup"><span data-stu-id="aed95-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="aed95-114">เลือกแอตทริบิวต์ในรายการที่คุณต้องการเพิ่มเป็นฟิลด์ที่จัดทำดัชนี</span><span class="sxs-lookup"><span data-stu-id="aed95-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="aed95-115">คุณสามารถเพิ่มแอตทริบิวต์เพิ่มเติมได้เสมอโดยการเลือก **เพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="aed95-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="aed95-116">คุณยังสามารถลบแอตทริบิวต์ที่เลือกได้โดยเลือกสัญลักษณ์ **ลบ**</span><span class="sxs-lookup"><span data-stu-id="aed95-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="aed95-117">สำรวจตารางฟิลด์ลูกค้าที่จัดทำดัชนี</span><span class="sxs-lookup"><span data-stu-id="aed95-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="aed95-118">ข้อมูลต่อไปนี้ถูกแสดงในตาราง</span><span class="sxs-lookup"><span data-stu-id="aed95-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="aed95-119">**ชื่อ**: แสดงชื่อของแอตทริบิวต์ตามที่ปรากฏในเอนทิตีโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="aed95-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="aed95-120">**ชนิดข้อมูล**: ระบุว่าชนิดข้อมูลเป็นสตริง หมายเลข หรือวันที่</span><span class="sxs-lookup"><span data-stu-id="aed95-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="aed95-121">**ถูกรวมอยู่ในการค้นหา**: ระบุว่าสามารถใช้แอตทริบิวต์นี้สำหรับการค้นหาลูกค้าในหน้า **ลูกค้า** โดยใช้ฟิลด์ **การค้นหา** หรือไม่</span><span class="sxs-lookup"><span data-stu-id="aed95-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="aed95-122">**เพิ่มตัวกรอง**: ตัวควบคุมเพื่อกำหนดว่าแอตทริบิวต์นี้สามารถใช้สำหรับการกรองบนหน้า **ลูกค้า** ได้อย่างไร</span><span class="sxs-lookup"><span data-stu-id="aed95-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="aed95-123">การแก้ไขตัวเลือกการกรองสำหรับแอตทริบิวต์ที่กำหนด</span><span class="sxs-lookup"><span data-stu-id="aed95-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="aed95-124">เมนู **ตัวกรอง** บนหน้า **ลูกค้า** สามารถมีจำนวนของระดับแอตทริบิวต์ที่แตกต่างกัน (ตัวอย่างเช่น กลุ่มอายุต่างๆ ในการกรองลูกค้า)</span><span class="sxs-lookup"><span data-stu-id="aed95-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="aed95-125">เลือก **เพิ่มตัวกรอง** สำหรับแอตทริบิวต์ที่กำหนดบนหน้า **ดัชนีการค้นหาและตัวกรอง**</span><span class="sxs-lookup"><span data-stu-id="aed95-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="aed95-126">คุณสามารถกำหนดจำนวนผลลัพธ์และลำดับที่จะจัดระเบียบ</span><span class="sxs-lookup"><span data-stu-id="aed95-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="aed95-127">โดยขึ้นอยู่กับชนิดข้อมูลของแอตทริบิวต์ หนึ่งในบานหน้าต่างต่อไปนี้จะปรากฏขึ้น</span><span class="sxs-lookup"><span data-stu-id="aed95-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="aed95-128">แอตทริบิวต์ชนิดสตริง: ระบุจำนวนผลลัพธ์ที่ต้องการในแผง **ตัวเลือกตัวกรองสตริง** และนโยบายใบสั่งที่จะถูกจัดระเบียบ</span><span class="sxs-lookup"><span data-stu-id="aed95-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="aed95-129">แอตทริบิวต์ชนิดตัวเลข: ระบุช่วงเวลาที่รวมอยู่ในแผง **ตัวเลือกตัวกรองตัวเลข** และนโยบายใบสั่งที่จะถูกจัดระเบียบ</span><span class="sxs-lookup"><span data-stu-id="aed95-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="aed95-130">แอตทริบิวต์ชนิดวันที่: ระบุช่วงเวลาที่รวมอยู่ในแผง **ตัวเลือกตัวกรองวันที่** และนโยบายใบสั่งที่จะถูกจัดระเบียบ</span><span class="sxs-lookup"><span data-stu-id="aed95-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="aed95-131">เลือก **บันทึก** เพื่อนำการเปลี่ยนแปลงของคุณมาใช้</span><span class="sxs-lookup"><span data-stu-id="aed95-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="aed95-132">เลือก **เรียกใช้** เมื่อคุณพร้อมที่จะใช้การตั้งค่าของคุณ</span><span class="sxs-lookup"><span data-stu-id="aed95-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aed95-133">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="aed95-133">Next steps</span></span>

<span data-ttu-id="aed95-134">ไปที่หน้า **ลูกค้า** เพื่อค้นหาโปรไฟล์ลูกค้าหรือใช้ฟิลด์ที่จัดทำดัชนีเพื่อดูชุดย่อยของโปรไฟล์ลูกค้าทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="aed95-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]