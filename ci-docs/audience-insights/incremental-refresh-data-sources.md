---
title: การรีเฟรชส่วนเพิ่มสำหรับแหล่งข้อมูลที่ใช้ Power Query
description: รีเฟรชข้อมูลใหม่และข้อมูลที่อัปเดตสำหรับแหล่งข้อมูลขนาดใหญ่ตาม Power Query
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268571"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="d6ece-103">การรีเฟรชแบบเพิ่มหน่วยสำหรับแหล่งข้อมูลที่ใช้ Power Query</span><span class="sxs-lookup"><span data-stu-id="d6ece-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="d6ece-104">การรีเฟรชแบบเพิ่มหน่วยสำหรับแหล่งข้อมูล มีข้อดีดังต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="d6ece-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="d6ece-105">**การรีเฟรชที่เร็วขึ้น** - เฉพาะข้อมูลที่มีการเปลี่ยนแปลงเท่านั้นที่จะได้รับการรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="d6ece-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="d6ece-106">ตัวอย่างเช่น คุณอาจรีเฟรชเพียงห้าวันที่ผ่านมาของชุดข้อมูลในอดีต</span><span class="sxs-lookup"><span data-stu-id="d6ece-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="d6ece-107">**ความน่าเชื่อถือที่เพิ่มขึ้น** - ด้วยการรีเฟรชที่น้อยลง คุณไม่จำเป็นต้องรักษาการเชื่อมต่อกับระบบต้นทางที่ไม่แน่นอนได้นานเท่านาน ซึ่งลดความเสี่ยงของปัญหาการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d6ece-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="d6ece-108">**การใช้ทรัพยากรที่ลดลง** - การรีเฟรชเฉพาะชุดย่อยของข้อมูลทั้งหมดของคุณ นำไปสู่การใช้ทรัพยากรคอมพิวเตอร์ที่มีประสิทธิภาพมากขึ้นและลดผลกระทบต่อสิ่งแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="d6ece-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="d6ece-109">กําหนดค่าการรีเฟรชแบบเพิ่มหน่วย</span><span class="sxs-lookup"><span data-stu-id="d6ece-109">Configure incremental refresh</span></span>

<span data-ttu-id="d6ece-110">ข้อมูลเชิงลึกกลุ่มเป้าหมาย ช่วยให้สามารถรีเฟรชส่วนเพิ่มสำหรับแหล่งข้อมูลที่นำเข้าผ่าน Power Query ที่รองรับการนำเข้าข้อมูลส่วนเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="d6ece-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="d6ece-111">ตัวอย่างเช่น ฐานข้อมูล Azure SQL ที่มีฟิลด์วันที่และเวลา ซึ่งระบุว่าเมื่อใดที่มีการปรับปรุงเรกคอร์ดข้อมูลล่าสุด</span><span class="sxs-lookup"><span data-stu-id="d6ece-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="d6ece-112">[สร้างแหล่งข้อมูลใหม่โดยอิงจาก Power Query](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="d6ece-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="d6ece-113">ระบุชื่อสำหรับแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d6ece-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="d6ece-114">เลือกแหล่งข้อมูลที่รองรับการรีเฟรชส่วนเพิ่ม เช่น ฐานข้อมูล Azure SQL</span><span class="sxs-lookup"><span data-stu-id="d6ece-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="d6ece-115">เลือกเอนทิตีหรือตารางที่จะส่งเข้า</span><span class="sxs-lookup"><span data-stu-id="d6ece-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="d6ece-116">ทำขั้นตอนการแปลงให้เสร็จสมบูรณ์ และเลือก **ต่อไป**</span><span class="sxs-lookup"><span data-stu-id="d6ece-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="d6ece-117">ในกล่องโต้ตอบ **ตั้งค่าการรีเฟรชส่วนเพิ่ม** ให้เลือก **ติดตั้ง** เพื่อเปิด **การตั้งค่ารีเฟรชส่วนเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="d6ece-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="d6ece-118">หากคุณเลือก **ข้าม** แหล่งข้อมูลจะรีเฟรชชุดข้อมูลทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="d6ece-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="d6ece-119">นอกจากนี้ คุณยังสามารถใช้การรีเฟรชส่วนเพิ่มในภายหลังได้โดยแก้ไขแหล่งข้อมูลที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="d6ece-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="d6ece-120">บน **การตั้งค่าการรีเฟรชส่วนเพิ่ม** คุณจะตั้งค่าคอนฟิกการรีเฟรชส่วนเพิ่มสำหรับเอนทิตีทั้งหมดที่คุณเลือก เมื่อสร้างแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d6ece-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6ece-121">![ตั้งค่าคอนฟิกเอนทิตีในแหล่งข้อมูลสำหรับการรีเฟรชส่วนเพิ่ม](media/incremental-refresh-settings.png "ตั้งค่าคอนฟิกเอนทิตีในแหล่งข้อมูลสำหรับการรีเฟรชส่วนเพิ่ม")</span><span class="sxs-lookup"><span data-stu-id="d6ece-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="d6ece-122">เลือกเอนทิตี และระบุรายละเอียดต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="d6ece-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="d6ece-123">**กำหนดคีย์หลัก**: เลือกคีย์หลักสำหรับเอนทิตีหรือตาราง</span><span class="sxs-lookup"><span data-stu-id="d6ece-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="d6ece-124">**กำหนดฟิลด์ "ปรับปรุงล่าสุด"**: ฟิลด์นี้จะแสดงเฉพาะแอตทริบิวต์ของชนิดวันที่และเวลา</span><span class="sxs-lookup"><span data-stu-id="d6ece-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="d6ece-125">เลือกแอตทริบิวต์ที่ระบุว่าเมื่อใดที่มีการปรับปรุงเรคคอร์ดครั้งล่าสุด</span><span class="sxs-lookup"><span data-stu-id="d6ece-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="d6ece-126">จะใช้เพื่อระบุเรกคอร์ดที่อยู่ในกรอบเวลาการรีเฟรชแบบเพิ่มหน่วย</span><span class="sxs-lookup"><span data-stu-id="d6ece-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="d6ece-127">**ตรวจสอบการปรับปรุงทุกๆ**: ระบุระยะเวลาของกรอบเวลาการรีเฟรชส่วนเพิ่มที่คุณต้องการให้เป็น</span><span class="sxs-lookup"><span data-stu-id="d6ece-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="d6ece-128">เลือก **บันทึก** เพื่อดำเนินการสร้างแหล่งข้อมูลให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="d6ece-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="d6ece-129">การรีเฟรชข้อมูลเริ่มต้นจะเป็นการรีเฟรชแบบเต็ม</span><span class="sxs-lookup"><span data-stu-id="d6ece-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="d6ece-130">หลังจากนั้น การรีเฟรชข้อมูลส่วนเพิ่มจะเกิดขึ้นตามที่ตั้งค่าคอนฟิกไว้ในขั้นตอนก่อนหน้า</span><span class="sxs-lookup"><span data-stu-id="d6ece-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]