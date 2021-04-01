---
title: ใช้แหล่งข้อมูลที่จะนำเข้าข้อมูล
description: เรียนรู้วิธีการนำเข้าข้อมูลจากแหล่งต่างๆ
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595970"
---
# <a name="data-sources-overview"></a><span data-ttu-id="463ce-103">ภาพรวมของแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="463ce-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="463ce-104">ความสามารถข้อมูลเชิงลึกกลุ่มเป้าหมายใน Dynamics 365 Customer Insights เชื่อมต่อกับข้อมูลจากแหล่งที่มามากมาย</span><span class="sxs-lookup"><span data-stu-id="463ce-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="463ce-105">การเชื่อมต่อกับแหล่งข้อมูลมักเรียกว่ากระบวนการของ *การส่งผ่านข้อมูล*</span><span class="sxs-lookup"><span data-stu-id="463ce-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="463ce-106">หลังจากนำเข้าข้อมูลแล้ว คุณสามารถ [รวมกัน](data-unification.md) และดำเนินการได้</span><span class="sxs-lookup"><span data-stu-id="463ce-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="463ce-107">เพิ่มแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="463ce-107">Add a data source</span></span>

<span data-ttu-id="463ce-108">ดูบทความโดยละเอียดเกี่ยวกับวิธีเพิ่มแหล่งข้อมูล ซึ่งขึ้นอยู่กับตัวเลือกที่คุณเลือก</span><span class="sxs-lookup"><span data-stu-id="463ce-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="463ce-109">คุณสามารถเพิ่มแหล่งข้อมูลได้สามวิธีหลัก:</span><span class="sxs-lookup"><span data-stu-id="463ce-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="463ce-110">ผ่านตัวเชื่อมต่อ Power Query มากมาย</span><span class="sxs-lookup"><span data-stu-id="463ce-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="463ce-111">จากโฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="463ce-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="463ce-112">จากที่จัดเก็บข้อมูลดิบ Common Data Service ของคุณเอง</span><span class="sxs-lookup"><span data-stu-id="463ce-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="463ce-113">คุณไม่สามารถเพิ่มข้อมูลจากแหล่งข้อมูลในสถานที่ได้</span><span class="sxs-lookup"><span data-stu-id="463ce-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="463ce-114">ตรวจสอบข้อมูลที่นำเข้า</span><span class="sxs-lookup"><span data-stu-id="463ce-114">Review ingested data</span></span>

<span data-ttu-id="463ce-115">คุณจะเห็นชื่อของแหล่งข้อมูลที่ส่งผ่านข้อมูลสถานะ และเวลาล่าสุดที่รีเฟรชข้อมูลสำหรับแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="463ce-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="463ce-116">คุณสามารถจัดเรียงรายการแหล่งข้อมูลตามทุกคอลัมน์</span><span class="sxs-lookup"><span data-stu-id="463ce-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="463ce-117">![เพิ่มแหล่งข้อมูลแล้ว](media/configure-data-datasource-added.png "เพิ่มแหล่งข้อมูลแล้ว")</span><span class="sxs-lookup"><span data-stu-id="463ce-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="463ce-118">สถานะ</span><span class="sxs-lookup"><span data-stu-id="463ce-118">Status</span></span>  |<span data-ttu-id="463ce-119">รายละเอียด</span><span class="sxs-lookup"><span data-stu-id="463ce-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="463ce-120">สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="463ce-120">Successful</span></span>   |<span data-ttu-id="463ce-121">แหล่งข้อมูลนำเข้าสำเร็จแล้วหากมีการระบุเวลาไว้ในคอลัมน์ **รีเฟรชแล้ว**</span><span class="sxs-lookup"><span data-stu-id="463ce-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="463ce-122">ยังไม่ได้เริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="463ce-122">Not started</span></span>   |<span data-ttu-id="463ce-123">แหล่งข้อมูลยังไม่มีการนำเข้าข้อมูลหรือยังอยู่ในโหมดร่าง</span><span class="sxs-lookup"><span data-stu-id="463ce-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="463ce-124">กำลังรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="463ce-124">Refreshing</span></span>    |<span data-ttu-id="463ce-125">กำลังดำเนินการนำข้อมูลไปใช้</span><span class="sxs-lookup"><span data-stu-id="463ce-125">Data ingestion is in progress.</span></span> <span data-ttu-id="463ce-126">คุณสามารถยกเลิกการดำเนินการนี้ได้ด้วยการเลือก **หยุดการรีเฟรช** ในคอลัมน์ **การดำเนินการ**</span><span class="sxs-lookup"><span data-stu-id="463ce-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="463ce-127">การหยุดการรีเฟรชของแหล่งข้อมูลจะแปลงกลับเป็นสถานะรีเฟรชล่าสุด</span><span class="sxs-lookup"><span data-stu-id="463ce-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="463ce-128">ไม่สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="463ce-128">Failed</span></span>     |<span data-ttu-id="463ce-129">การใช้ข้อมูลรันไปในข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="463ce-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="463ce-130">เลือกค่าในคอลัมน์ **สถานะ** ของแหล่งข้อมูลใดๆ เพื่อรีวิวรายละเอียดเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="463ce-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="463ce-131">ในบานหน้าต่าง **รายละเอียดความคืบหน้า** ขยาย **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="463ce-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="463ce-132">เลือก **ดูรายละเอียด** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับสถานะการรีเฟรช ซึ่งรวมถึงรายละเอียดข้อผิดพลาดและการปรับปรุงกระบวนการดาวน์สตรีม</span><span class="sxs-lookup"><span data-stu-id="463ce-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="463ce-133">การโหลดข้อมูลอาจใช้เวลาสักครู่</span><span class="sxs-lookup"><span data-stu-id="463ce-133">Loading data can take some time.</span></span> <span data-ttu-id="463ce-134">หลังจากการรีเฟรชที่สำเร็จ จะสามารถตรวจสอบข้อมูลที่ถูกนำไปใช้ได้จากหน้า **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="463ce-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="463ce-135">สำหรับข้อมูลเพิ่มเติม โปรดดู [เอนทิตี](entities.md)</span><span class="sxs-lookup"><span data-stu-id="463ce-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="463ce-136">รีเฟรชแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="463ce-136">Refresh a data source</span></span>

<span data-ttu-id="463ce-137">แหล่งข้อมูลสามารถรีเฟรชตามกำหนดการอัตโนมัติหรือรีเฟรชด้วยตนเองได้ตามต้องการ</span><span class="sxs-lookup"><span data-stu-id="463ce-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="463ce-138">ไปที่ **ผู้ดูแลระบบ** > **ระบบ** > [**กำหนดการ**](system.md#schedule-tab) เพื่อกำหนดค่าการรีเฟรชตามกำหนดการของแหล่งข้อมูลที่นำเข้าทั้งหมดของคุณ</span><span class="sxs-lookup"><span data-stu-id="463ce-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="463ce-139">การรีเฟรชแหล่งข้อมูลตามต้องการ ให้ทำตามขั้นตอนเหล่านี้:</span><span class="sxs-lookup"><span data-stu-id="463ce-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="463ce-140">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="463ce-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="463ce-141">เลือกจุดไข่ปลาแนวตั้งถัดจากแหล่งข้อมูลที่คุณต้องการรีเฟรช และเลือก **รีเฟรช** จากรายการแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="463ce-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="463ce-142">ตอนนี้แหล่งข้อมูลถูกทริกเกอร์สำหรับการรีเฟรชด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="463ce-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="463ce-143">การรีเฟรชแหล่งข้อมูลจะปรับปรุงสคีมาเอนทิตีทั้งคู่ รวมถึงข้อมูลสำหรับเอนทิตีทั้งหมดที่ระบุในแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="463ce-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="463ce-144">เลือก **หยุดการรีเฟรช** หากคุณต้องการยกเลิกการรีเฟรชที่มีอยู่และแหล่งข้อมูลจะเปลี่ยนกลับเป็นสถานะการรีเฟรชล่าสุด</span><span class="sxs-lookup"><span data-stu-id="463ce-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="463ce-145">ลบแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="463ce-145">Delete a data source</span></span>

1. <span data-ttu-id="463ce-146">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="463ce-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="463ce-147">เลือกจุดไข่ปลาแนวตั้งถัดจาก แหล่งข้อมูล ที่คุณต้องการลบและเลือก **ลบ** จากเมนูแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="463ce-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="463ce-148">ยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="463ce-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]