---
title: การเชื่อมต่อกับบริการอื่น ๆ จาก Customer Insights
description: แบ่งปันข้อมูลไปยังบริการอื่น ๆ
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896120"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="e4c3c-103">ภาพรวมของการเชื่อมต่อ (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-103">Connections (preview) overview</span></span>

<span data-ttu-id="e4c3c-104">การเชื่อมต่อเป็นกุญแจสำคัญในการเปิดใช้งานการแบ่งปันข้อมูลไปและจาก Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e4c3c-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="e4c3c-105">การเชื่อมต่อแต่ละครั้งจะสร้างการแบ่งปันข้อมูลด้วยบริการเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="e4c3c-106">การเชื่อมต่อเป็นรากฐาน [ในการกำหนดค่าการเพิ่มประสิทธิภาพของบุคคลที่สาม](enrichment-hub.md) และ [กำหนดค่าการส่งออก](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="e4c3c-107">การเชื่อมต่อเดียวกันสามารถใช้ได้หลายครั้ง</span><span class="sxs-lookup"><span data-stu-id="e4c3c-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="e4c3c-108">ตัวอย่างเช่น การเชื่อมต่อกับ Dynamics 365 Marketing หนึ่งรายการทำงานสำหรับการส่งออกหลายรายการและสามารถใช้การเชื่อมต่อ Leadspace หนึ่งรายการสำหรับการปรับปรุงหลายอย่าง</span><span class="sxs-lookup"><span data-stu-id="e4c3c-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="e4c3c-109">ไปที่ **การจัดการ** > **การเชื่อมต่อ** เพื่อสร้างและดูการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="e4c3c-110">แท็บ **การเชื่อมต่อ** แสดงการเชื่อมต่อที่ใช้งานอยู่ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="e4c3c-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="e4c3c-111">รายการจะแสดงแถวสำหรับการเชื่อมต่อแต่ละรายการ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="e4c3c-112">ดูภาพรวมโดยย่อ คำอธิบาย และดูว่าคุณสามารถทำอะไรได้บ้างกับตัวเลือกความสามารถในการขยายแต่ละตัวในแท็บ **ค้นพบ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="e4c3c-113">การส่งออก</span><span class="sxs-lookup"><span data-stu-id="e4c3c-113">Exports</span></span>

<span data-ttu-id="e4c3c-114">เฉพาะผู้ดูแลระบบเท่านั้นที่สามารถกำหนดค่าการเชื่อมต่อใหม่ แต่สามารถให้สิทธิ์การเข้าถึงแก่ผู้ร่วมให้ข้อมูลเพื่อใช้การเชื่อมต่อที่มีอยู่ได้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="e4c3c-115">ผู้ดูแลระบบควบคุมว่าข้อมูลจะไปที่ไหน ผู้สนับสนุนกำหนดส่วนข้อมูลและความถี่ที่เหมาะสมกับความต้องการของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="e4c3c-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="e4c3c-116">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="e4c3c-117">การเพิ่มความสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="e4c3c-117">Enrichments</span></span>

<span data-ttu-id="e4c3c-118">เฉพาะผู้ดูแลระบบเท่านั้นที่สามารถกำหนดค่าการเชื่อมต่อใหม่ แต่การเชื่อมต่อที่สร้างขึ้นจะพร้อมใช้งานสำหรับทั้งผู้ดูแลระบบและผู้สนับสนุนเสมอ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="e4c3c-119">ผู้ดูแลระบบจัดการข้อมูลประจำตัวและให้ความยินยอมในการถ่ายโอนข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e4c3c-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="e4c3c-120">จากนั้นสามารถใช้การเชื่อมต่อเพื่อเพิ่มคุณค่าได้ทั้งโดยผู้ดูแลระบบและผู้สนับสนุน</span><span class="sxs-lookup"><span data-stu-id="e4c3c-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="e4c3c-121">เพิ่มการเชื่อมต่อใหม่</span><span class="sxs-lookup"><span data-stu-id="e4c3c-121">Add a new connection</span></span>

<span data-ttu-id="e4c3c-122">ในการเพิ่มการเชื่อมต่อ คุณต้องมี [สิทธิ์ผู้ดูแลระบบ](permissions.md)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="e4c3c-123">หากคุณเชื่อมต่อกับบริการอื่น ๆ ของ Microsoft เราถือว่าบริการทั้งสองอยู่ในองค์กรเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="e4c3c-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="e4c3c-124">ไปที่ **การจัดการ** > **การเชื่อมต่อ (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e4c3c-125">ไปที่แท็บ **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e4c3c-126">เลือก **เพิ่มการเชื่อมต่อ** เพื่อสร้างการเชื่อมต่อใหม่</span><span class="sxs-lookup"><span data-stu-id="e4c3c-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="e4c3c-127">เลือกจากเมนูแบบหล่นลงว่าคุณต้องการสร้างการเชื่อมต่อชนิดใด</span><span class="sxs-lookup"><span data-stu-id="e4c3c-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="e4c3c-128">ในบานหน้าต่าง **ตั้งค่าการเชื่อมต่อ** ให้รายละเอียดที่จำเป็น</span><span class="sxs-lookup"><span data-stu-id="e4c3c-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="e4c3c-129">**ชื่อที่แสดง** และชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="e4c3c-130">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="e4c3c-131">ฟิลด์ที่แน่นอนขึ้นอยู่กับบริการที่คุณกำลังเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="e4c3c-132">คุณสามารถเรียนรู้เกี่ยวกับรายละเอียดของชนิดการเชื่อมต่อที่เฉพาะเจาะจงได้จากบทความเกี่ยวกับบริการเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="e4c3c-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="e4c3c-133">หากต้องการสร้างการเชื่อมต่อ ให้เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="e4c3c-134">คุณยังสามารถเลือก **ตั้งค่า** บนไทล์บนแท็บ **ค้นพบ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="e4c3c-135">อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก</span><span class="sxs-lookup"><span data-stu-id="e4c3c-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="e4c3c-136">เมื่อตั้งค่าหรือแก้ไขการเชื่อมต่อการส่งออก คุณสามารถเลือกผู้ใช้ที่ได้รับอนุญาตให้ใช้การเชื่อมต่อเฉพาะนี้เพื่อกำหนด [การส่งออก](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="e4c3c-137">โดยค่าเริ่มต้น การเชื่อมต่อจะพร้อมใช้งานสำหรับผู้ใช้ที่มีบทบาทผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="e4c3c-138">คุณสามารถเปลี่ยนการตั้งค่านี้ภายใต้ **เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้** และอนุญาตให้ผู้ใช้ที่มีบทบาทผู้สนับสนุนใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="e4c3c-139">ผู้สนับสนุนจะไม่สามารถดูหรือแก้ไขการเชื่อมต่อได้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="e4c3c-140">พวกเขาจะเห็นชื่อที่แสดงและชนิดเมื่อสร้างการส่งออกเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="e4c3c-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="e4c3c-141">โดยการแบ่งปันการเชื่อมต่อ คุณอนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="e4c3c-142">ผู้สนับสนุนจะเห็นการเชื่อมต่อที่แบ่งปันเมื่อพวกเขาตั้งค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="e4c3c-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="e4c3c-143">พวกเขาสามารถจัดการทุกการส่งออกที่ใช้การเชื่อมต่อเฉพาะนี้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="e4c3c-144">คุณสามารถเปลี่ยนการตั้งค่านี้ได้ในขณะที่ยังคงการส่งออกที่ผู้สนับสนุนกำหนดไว้แล้ว</span><span class="sxs-lookup"><span data-stu-id="e4c3c-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="e4c3c-145">แก้ไขการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-145">Edit a connection</span></span>

1. <span data-ttu-id="e4c3c-146">ไปที่ **การจัดการ** > **การเชื่อมต่อ (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e4c3c-147">ไปที่แท็บ **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e4c3c-148">เลือกจุดไข่ปลาแนวตั้งสำหรับการเชื่อมต่อที่คุณต้องการแก้ไข</span><span class="sxs-lookup"><span data-stu-id="e4c3c-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="e4c3c-149">เลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-149">Select **Edit**.</span></span>

1. <span data-ttu-id="e4c3c-150">เปลี่ยนค่าที่คุณต้องการอัปเดตและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="e4c3c-151">ลบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-151">Remove a connection</span></span>

<span data-ttu-id="e4c3c-152">หากการเชื่อมต่อที่คุณกำลังลบถูกใช้โดยการเพิ่มข้อมูลหรือการส่งออก คุณต้องถอดหรือนำออกก่อน</span><span class="sxs-lookup"><span data-stu-id="e4c3c-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="e4c3c-153">กล่องโต้ตอบการลบจะนำคุณไปสู่การเพิ่มข้อมูลหรือการส่งออกที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="e4c3c-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="e4c3c-154">การเพิ่มข้อมูลและการส่งออกที่แยกออกจากกันกลายเป็นไม่ได้ใช้งาน</span><span class="sxs-lookup"><span data-stu-id="e4c3c-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="e4c3c-155">คุณเปิดใช้งานอีกครั้งโดยเพิ่มการเชื่อมต่ออื่นให้กับพวกเขาในหน้า [การเพิ่มข้อมูล](enrichment-hub.md) หรือ [การส่งออก](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="e4c3c-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="e4c3c-156">ไปที่ **การจัดการ** > **การเชื่อมต่อ (ตัวอย่าง)**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="e4c3c-157">ไปที่แท็บ **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="e4c3c-158">เลือกจุดไข่ปลาแนวตั้งสำหรับการเชื่อมต่อที่คุณต้องการลบ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="e4c3c-159">เลือก **ลบ** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="e4c3c-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="e4c3c-160">กล่องโต้ตอบการยืนยันปรากฏขึ้น</span><span class="sxs-lookup"><span data-stu-id="e4c3c-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="e4c3c-161">หากมีการเพิ่มข้อมูลหรือการส่งออกโดยใช้การเชื่อมต่อนี้ ให้เลือกปุ่มเพื่อดูสิ่งที่ใช้การเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="e4c3c-162">**การส่งออก:** คุณสามารถเลือกที่จะลบหรือยกเลิกการเชื่อมต่อการส่งออกเพื่อให้สามารถลบการเชื่อมต่อได้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="e4c3c-163">ในการยกเลิกการเชื่อมต่อการส่งออก ผู้ดูแลระบบสามารถใช้การดำเนินการ **ยกเลิกการเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="e4c3c-164">การดำเนินการนี้พร้อมใช้งานสำหรับการส่งออกที่เลือกแต่ละรายการและหลายรายการ</span><span class="sxs-lookup"><span data-stu-id="e4c3c-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="e4c3c-165">การยกเลิกการเชื่อมต่อจะทำให้คุณคงการกำหนดค่าการส่งออกไว้ แต่จะไม่ทำงานจนกว่าจะมีการเพิ่มการเชื่อมต่ออื่นเข้ามา</span><span class="sxs-lookup"><span data-stu-id="e4c3c-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="e4c3c-166">**การเพิ่มข้อมูล:** คุณสามารถเลือกที่จะลบหรือปิดการใช้งานการเชื่อมต่อการเพิ่มข้อมูลเพื่อให้สามารถลบการเชื่อมต่อได้</span><span class="sxs-lookup"><span data-stu-id="e4c3c-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="e4c3c-167">เมื่อการเชื่อมต่อไม่มีการอ้างอิงอีกต่อไป ให้กลับไปที่ **การจัดการ** > **การเชื่อมต่อ** แล้วลองลบการเชื่อมต่ออีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="e4c3c-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="e4c3c-168">เพื่อยืนยันการลบ ให้เลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="e4c3c-168">To confirm the deletion select **Remove**.</span></span>

