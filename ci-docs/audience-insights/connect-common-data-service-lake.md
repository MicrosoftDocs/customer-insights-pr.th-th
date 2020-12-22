---
title: เชื่อมต่อกับเอนทิตีในที่จัดเก็บที่มีการจัดการของ Common Data Service
description: นำเข้าข้อมูลจากที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Common Data Service
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643421"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="11f6e-103">เชื่อมต่อกับข้อมูลใน Data Lake ที่มีการจัดการ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11f6e-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="11f6e-104">บทความนี้ให้ข้อมูลเกี่ยวกับวิธีที่ลูกค้า Dynamics 365 ที่มีอยู่ สามารถเชื่อมต่อกับเอนทิตีเชิงวิเคราะห์ของตนได้อย่างรวดเร็วในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11f6e-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="11f6e-105">คุณต้องเป็นผู้ดูแลระบบในองค์กร Common Data Service เพื่อดำเนินการต่อ และดูรายการของเอนทิตีที่มีอยู่ในที่จัดเก็บข้อมูลดิบที่มีการจัดการ</span><span class="sxs-lookup"><span data-stu-id="11f6e-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="11f6e-106">ข้อควรพิจารณาที่สำคัญ</span><span class="sxs-lookup"><span data-stu-id="11f6e-106">Important considerations</span></span>

<span data-ttu-id="11f6e-107">ข้อมูลที่เก็บไว้ในบริการออนไลน์ เช่น Azure Data Lake Storage อาจถูกเก็บไว้ในตำแหน่งที่แตกต่างจากที่ที่มีการประมวลผลหรือจัดเก็บข้อมูลใน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="11f6e-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="11f6e-108">โดยการนำเข้าหรือการเชื่อมต่อไปยังข้อมูลที่จัดเก็บในบริการออนไลน์ คุณยอมรับว่าสามารถถ่ายโอนข้อมูลและจัดเก็บด้วย Dynamics 365 Customer Insights  [เรียนรู้เพิ่มเติมที่ Microsoft Trust Center](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="11f6e-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="11f6e-109">เชื่อมต่อกับที่จัดเก็บที่มีการจัดการ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11f6e-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="11f6e-110">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="11f6e-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="11f6e-111">เลือก **เพิ่มแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="11f6e-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="11f6e-112">เลือก **เชื่อมต่อกับ Common Data Service** และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="11f6e-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="11f6e-113">ป้อน **ชื่อ** สำหรับแหล่งข้อมูล แล้วเลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="11f6e-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="11f6e-114">ใส่ **ที่อยู่เซิร์ฟเวอร์** สำหรับองค์กร Common Data Service ของคุณ และเลือก **เข้าสู่ระบบ**</span><span class="sxs-lookup"><span data-stu-id="11f6e-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11f6e-115">![กล่องโต้ตอบเพื่อป้อนที่อยู่เซิร์ฟเวอร์ Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="11f6e-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="11f6e-116">เลือกเอนทิตีที่คุณต้องการนำเข้าระบบจากรายการที่มี</span><span class="sxs-lookup"><span data-stu-id="11f6e-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="11f6e-117">หากมีการเลือกเอนทิตีบางตัวไปแล้ว อาจใช้กับโปรแกรมประยุกต์อื่นของ Dynamics 365 (เช่น Dynamics 365 Sales Insights หรือ Customer Service Insights)</span><span class="sxs-lookup"><span data-stu-id="11f6e-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="11f6e-118">คุณไม่สามารถเปลี่ยนการเลือก</span><span class="sxs-lookup"><span data-stu-id="11f6e-118">You can't change the selection.</span></span> <span data-ttu-id="11f6e-119">เอนทิตีเหล่านี้จะพร้อมใช้งาน เมื่อมีการสร้างแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="11f6e-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11f6e-120">![กล่องโต้ตอบแสดงรายการของเอนทิตีในองค์กร Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="11f6e-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="11f6e-121">บันทึกการเลือกของคุณเพื่อเริ่มซิงค์เอนทิตีที่เลือกกับที่จัดเก็บที่มีการจัดการ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11f6e-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="11f6e-122">คุณจะพบการเชื่อมต่อที่เพิ่งเพิ่มเข้าไปในหน้า **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="11f6e-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="11f6e-123">จะเข้าคิวเพื่อรีเฟรชและแสดงเอนทิตีที่นับเป็น 0 จนกว่าจะซิงค์เอนทิตีทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="11f6e-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="11f6e-124">แหล่งข้อมูลของสภาพแวดล้อมเดียวเท่านั้นที่สามารถใช้ที่จัดเก็บที่มีการจัดการ Common Data Service เดียวกันพร้อมกันได้</span><span class="sxs-lookup"><span data-stu-id="11f6e-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="11f6e-125">แก้ไขแหล่งข้อมูลที่จัดเก็บที่มีการจัดการ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="11f6e-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="11f6e-126">คุณแก้ไขการเลือกเอนทิตีหลังจากสร้างแหล่งข้อมูลเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="11f6e-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="11f6e-127">ตัวอย่างเช่น หากมีการเพิ่มเอนทิตีเพิ่มเติมใน Common Data Service และคุณต้องการนำเข้าด้วยเช่นกัน</span><span class="sxs-lookup"><span data-stu-id="11f6e-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="11f6e-128">เมื่อต้องการเชื่อมต่อกับ Common Data Service อื่น [สร้างแหล่งข้อมูลใหม่](#connect-to-a-common-data-service-managed-lake)</span><span class="sxs-lookup"><span data-stu-id="11f6e-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="11f6e-129">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="11f6e-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="11f6e-130">ถัดจากแหล่งข้อมูลที่คุณต้องการอปรับปรุง เลือกจุดไข่ปลา</span><span class="sxs-lookup"><span data-stu-id="11f6e-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="11f6e-131">เลือกตัวเลือก **แก้ไข** จากรายการ</span><span class="sxs-lookup"><span data-stu-id="11f6e-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="11f6e-132">เลือกเอนทิตีเพิ่มเติมจากรายการเอนทิตีที่มีอยู่ และเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="11f6e-132">Select additional entities from the available list of entities and select **Save**.</span></span>
