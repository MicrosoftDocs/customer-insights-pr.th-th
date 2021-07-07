---
title: ใช้แหล่งข้อมูลที่จะนำเข้าข้อมูล
description: เรียนรู้วิธีการนำเข้าข้อมูลจากแหล่งต่างๆ
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304719"
---
# <a name="data-sources-overview"></a><span data-ttu-id="1c94b-103">ภาพรวมของแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1c94b-104">ความสามารถข้อมูลเชิงลึกกลุ่มเป้าหมายใน Dynamics 365 Customer Insights เชื่อมต่อกับข้อมูลจากแหล่งที่มามากมาย</span><span class="sxs-lookup"><span data-stu-id="1c94b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="1c94b-105">การเชื่อมต่อกับแหล่งข้อมูลมักเรียกว่ากระบวนการของ *การส่งผ่านข้อมูล*</span><span class="sxs-lookup"><span data-stu-id="1c94b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="1c94b-106">หลังจากนำเข้าข้อมูลแล้ว คุณสามารถ [รวมกัน](data-unification.md) และดำเนินการได้</span><span class="sxs-lookup"><span data-stu-id="1c94b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="1c94b-107">เพิ่มแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-107">Add a data source</span></span>

<span data-ttu-id="1c94b-108">ดูบทความโดยละเอียดเกี่ยวกับวิธีเพิ่มแหล่งข้อมูล ซึ่งขึ้นอยู่กับตัวเลือกที่คุณเลือก</span><span class="sxs-lookup"><span data-stu-id="1c94b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="1c94b-109">คุณสามารถเพิ่มแหล่งข้อมูลได้สามวิธีหลัก:</span><span class="sxs-lookup"><span data-stu-id="1c94b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="1c94b-110">ผ่านตัวเชื่อมต่อ Power Query มากมาย</span><span class="sxs-lookup"><span data-stu-id="1c94b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="1c94b-111">จากโฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="1c94b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="1c94b-112">จากที่จัดเก็บข้อมูลดิบ Microsoft Dataverse ของคุณเอง</span><span class="sxs-lookup"><span data-stu-id="1c94b-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="1c94b-113">เพิ่มข้อมูลจากแหล่งข้อมูลภายในองค์กร</span><span class="sxs-lookup"><span data-stu-id="1c94b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="1c94b-114">การนำเข้าข้อมูลจากแหล่งข้อมูลภายในองค์กรในข้อมูลเชิงลึกของผู้ชมได้รับการสนับสนุนตามโฟลว์ข้อมูล Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="1c94b-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="1c94b-115">สามารถเปิดใช้โฟลว์ข้อมูลใน Customer Insights โดย [ให้ URL สภาพแวดล้อม Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) เมื่อตั้งค่าสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="1c94b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="1c94b-116">แหล่งข้อมูลที่สร้างขึ้นหลังจากเชื่อมโยงสภาพแวดล้อม Dataverse ที่มี Customer Insights จะใช้ [โฟลว์ข้อมูล Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) โดยค่าเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="1c94b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="1c94b-117">โฟลว์ข้อมูลสนับสนุนการเชื่อมต่อภายในองค์กรโดยใช้เกตเวย์ข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="1c94b-118">ลบและสร้างแหล่งข้อมูลใหม่ที่มีอยู่ก่อนหน้าสภาพแวดล้อม Dataverse ที่เชื่อมโยงกับ [ใช้เกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-app.md)</span><span class="sxs-lookup"><span data-stu-id="1c94b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="1c94b-119">เกตเวย์ข้อมูลจากสภาพแวดล้อม Power BI หรือ Power Apps จะมองเห็นและคุณสามารถใช้ซ้ำได้ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1c94b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="1c94b-120">หน้าแหล่งข้อมูลแสดงลิงก์เพื่อไปที่สภาพแวดล้อม Microsoft Power Platform ที่คุณสามารถดูและตั้งค่าคอนฟิกเกตเวย์ข้อมูลภายในองค์กร</span><span class="sxs-lookup"><span data-stu-id="1c94b-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="1c94b-121">ตรวจสอบข้อมูลที่นำเข้า</span><span class="sxs-lookup"><span data-stu-id="1c94b-121">Review ingested data</span></span>

<span data-ttu-id="1c94b-122">คุณจะเห็นชื่อของแหล่งข้อมูลที่ส่งผ่านข้อมูลสถานะ และเวลาล่าสุดที่รีเฟรชข้อมูลสำหรับแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="1c94b-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="1c94b-123">คุณสามารถจัดเรียงรายการแหล่งข้อมูลตามทุกคอลัมน์</span><span class="sxs-lookup"><span data-stu-id="1c94b-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1c94b-124">![เพิ่มแหล่งข้อมูลแล้ว](media/configure-data-datasource-added.png "เพิ่มแหล่งข้อมูลแล้ว")</span><span class="sxs-lookup"><span data-stu-id="1c94b-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="1c94b-125">สถานะ</span><span class="sxs-lookup"><span data-stu-id="1c94b-125">Status</span></span>  |<span data-ttu-id="1c94b-126">รายละเอียด</span><span class="sxs-lookup"><span data-stu-id="1c94b-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1c94b-127">สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="1c94b-127">Successful</span></span>   |<span data-ttu-id="1c94b-128">แหล่งข้อมูลนำเข้าสำเร็จแล้วหากมีการระบุเวลาไว้ในคอลัมน์ **รีเฟรชแล้ว**</span><span class="sxs-lookup"><span data-stu-id="1c94b-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="1c94b-129">ยังไม่ได้เริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="1c94b-129">Not started</span></span>   |<span data-ttu-id="1c94b-130">แหล่งข้อมูลยังไม่มีการนำเข้าข้อมูลหรือยังอยู่ในโหมดร่าง</span><span class="sxs-lookup"><span data-stu-id="1c94b-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="1c94b-131">กำลังรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="1c94b-131">Refreshing</span></span>    |<span data-ttu-id="1c94b-132">กำลังดำเนินการนำข้อมูลไปใช้</span><span class="sxs-lookup"><span data-stu-id="1c94b-132">Data ingestion is in progress.</span></span> <span data-ttu-id="1c94b-133">คุณสามารถยกเลิกการดำเนินการนี้ได้ด้วยการเลือก **หยุดการรีเฟรช** ในคอลัมน์ **การดำเนินการ**</span><span class="sxs-lookup"><span data-stu-id="1c94b-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="1c94b-134">การหยุดการรีเฟรชของแหล่งข้อมูลจะแปลงกลับเป็นสถานะรีเฟรชล่าสุด</span><span class="sxs-lookup"><span data-stu-id="1c94b-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="1c94b-135">ไม่สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="1c94b-135">Failed</span></span>     |<span data-ttu-id="1c94b-136">การใช้ข้อมูลรันไปในข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="1c94b-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="1c94b-137">เลือกค่าในคอลัมน์ **สถานะ** ของแหล่งข้อมูลใดๆ เพื่อรีวิวรายละเอียดเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="1c94b-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="1c94b-138">ในบานหน้าต่าง **รายละเอียดความคืบหน้า** ขยาย **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="1c94b-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="1c94b-139">เลือก **ดูรายละเอียด** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับสถานะการรีเฟรช ซึ่งรวมถึงรายละเอียดข้อผิดพลาดและการปรับปรุงกระบวนการดาวน์สตรีม</span><span class="sxs-lookup"><span data-stu-id="1c94b-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="1c94b-140">การโหลดข้อมูลอาจต้องใช้เวลา</span><span class="sxs-lookup"><span data-stu-id="1c94b-140">Loading data can take time.</span></span> <span data-ttu-id="1c94b-141">หลังจากการรีเฟรชที่สำเร็จ จะสามารถตรวจสอบข้อมูลที่ถูกนำไปใช้ได้จากหน้า **เอนทิตี**</span><span class="sxs-lookup"><span data-stu-id="1c94b-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="1c94b-142">สำหรับข้อมูลเพิ่มเติม โปรดดู [เอนทิตี](entities.md)</span><span class="sxs-lookup"><span data-stu-id="1c94b-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="1c94b-143">รีเฟรชแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-143">Refresh a data source</span></span>

<span data-ttu-id="1c94b-144">แหล่งข้อมูลสามารถรีเฟรชตามกำหนดการอัตโนมัติหรือรีเฟรชด้วยตนเองได้ตามต้องการ</span><span class="sxs-lookup"><span data-stu-id="1c94b-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="1c94b-145">ไปที่ **ผู้ดูแลระบบ** > **ระบบ** > [**กำหนดการ**](system.md#schedule-tab) เพื่อกำหนดค่าการรีเฟรชตามกำหนดการของแหล่งข้อมูลที่นำเข้าทั้งหมดของคุณ</span><span class="sxs-lookup"><span data-stu-id="1c94b-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="1c94b-146">การรีเฟรชแหล่งข้อมูลตามต้องการ ให้ทำตามขั้นตอนเหล่านี้:</span><span class="sxs-lookup"><span data-stu-id="1c94b-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="1c94b-147">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="1c94b-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1c94b-148">เลือกจุดไข่ปลาแนวตั้งถัดจากแหล่งข้อมูลที่คุณต้องการรีเฟรช และเลือก **รีเฟรช** จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1c94b-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="1c94b-149">ตอนนี้แหล่งข้อมูลถูกทริกเกอร์สำหรับการรีเฟรชด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="1c94b-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="1c94b-150">การรีเฟรชแหล่งข้อมูลจะอัปเดตทั้งสคีมาเอนทิตีและข้อมูลสำหรับเอนทิตีทั้งหมดที่ระบุในแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="1c94b-151">เลือก **หยุดการรีเฟรช** หากคุณต้องการยกเลิกการรีเฟรชที่มีอยู่และแหล่งข้อมูลจะเปลี่ยนกลับเป็นสถานะการรีเฟรชล่าสุด</span><span class="sxs-lookup"><span data-stu-id="1c94b-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="1c94b-152">ลบแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1c94b-152">Delete a data source</span></span>

1. <span data-ttu-id="1c94b-153">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="1c94b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1c94b-154">เลือกจุดไข่ปลาแนวตั้งถัดจากแหล่งข้อมูลที่คุณต้องการลบออก และเลือก **ลบ** จากเมนูแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="1c94b-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="1c94b-155">ยืนยันการลบของคุณ</span><span class="sxs-lookup"><span data-stu-id="1c94b-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
