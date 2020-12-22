---
title: เอนทิตีและชุดข้อมูล
description: ดูข้อมูลในเพจเอนทิตี
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407129"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="dae65-103">เอนทิตีในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="dae65-103">Entities in audience insights</span></span>

<span data-ttu-id="dae65-104">หลังจาก [ตั้งค่าคอนฟิกแหล่งข้อมูลของคุณ](data-sources.md) ไปที่หน้า **เอนทิตี** เพื่อประเมินคุณภาพของข้อมูลที่ถูกนำไปใช้</span><span class="sxs-lookup"><span data-stu-id="dae65-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="dae65-105">เอนทิตีถือเป็นชุดข้อมูล</span><span class="sxs-lookup"><span data-stu-id="dae65-105">Entities are considered datasets.</span></span> <span data-ttu-id="dae65-106">ความสามารถที่หลากหลายของ Dynamics 365 Customer Insights สร้างมาจากเอนทิตีเหล่านี้</span><span class="sxs-lookup"><span data-stu-id="dae65-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="dae65-107">การตรวจสอบอย่างใกล้ชิดสามารถช่วยให้คุณยืนยันผลลัพธ์ของความสามารถเหล่านั้น</span><span class="sxs-lookup"><span data-stu-id="dae65-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="dae65-108">หน้า **เอนทิตี** จะแสดงรายการเอนทิตีและมีหลายคอลัมน์:</span><span class="sxs-lookup"><span data-stu-id="dae65-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="dae65-109">**ชื่อ**: ชื่อของเอนทิตีข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="dae65-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="dae65-110">ถ้าคุณเห็นสัญลักษณ์คำเตือนถัดจากชื่อเอนทิตี นั่นหมายความว่าข้อมูลสำหรับเอนทิตีนั้นโหลดไม่สำเร็จ</span><span class="sxs-lookup"><span data-stu-id="dae65-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="dae65-111">**ต้นทาง**: ชนิดของแหล่งข้อมูลที่ใช้เอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="dae65-112">**สร้างโดย**: ชื่อของบุคคลที่สร้างเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="dae65-113">**สร้างแล้ว**: วันที่และเวลาของการสร้างเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="dae65-114">**ปรับปรุงโดย**: ชื่อของบุคคลที่ปรับปรุงเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="dae65-115">**ปรับปรุงล่าสุด**: วันที่และเวลาของการปรับปรุงล่าสุดของเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="dae65-116">**รีเฟรชล่าสุด**: วันที่และเวลาของการรีเฟรชข้อมูลครั้งล่าสุด</span><span class="sxs-lookup"><span data-stu-id="dae65-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="dae65-117">การสำรวจข้อมูลของเอนทิตีเฉพาะ</span><span class="sxs-lookup"><span data-stu-id="dae65-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="dae65-118">เลือกเอนทิตีเพื่อสำรวจฟิลด์และเรกคอร์ดต่างๆ ที่รวมอยู่ภายในเอนทิตีนั้น</span><span class="sxs-lookup"><span data-stu-id="dae65-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dae65-119">![เลือกเอนทิตี](media/data-manager-entities-data.png "เลือกเอนทิตี")</span><span class="sxs-lookup"><span data-stu-id="dae65-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="dae65-120">แท็บ **ข้อมูล** จะถูกเลือกโดยค่าเริ่มต้น และแสดงตารางที่แสดงรายละเอียดเกี่ยวกับแต่ละเรกคอร์ดของเอนทิตี</span><span class="sxs-lookup"><span data-stu-id="dae65-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dae65-121">![ตารางฟิลด์](media/data-manager-entities-fields.PNG "ตารางฟิลด์")</span><span class="sxs-lookup"><span data-stu-id="dae65-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="dae65-122">แท็บ **ฟิลด์** จะแสดงตารางเพื่อตรวจทานรายละเอียดสำหรับเอนทิตีที่เลือก เช่น ชื่อฟิลด์ ชนิดข้อมูล และชนิด</span><span class="sxs-lookup"><span data-stu-id="dae65-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="dae65-123">คอลัมน์ **ชนิด** แสดงชนิด Common Data Model ที่เกี่ยวข้อง ซึ่งถูกระบุแบบอัตโนมัติโดยระบบ หรือ [ถูกแม็ปด้วยตนเอง](map-entities.md) โดยผู้ใช้</span><span class="sxs-lookup"><span data-stu-id="dae65-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="dae65-124">รายการเหล่านี้เป็นชนิดความหมายที่สามารถแตกต่างจากชนิดข้อมูลของแอตทริบิวต์ได้—ตัวอย่างเช่น ฟิลด์ *อีเมล* ด้านล่างมี *ข้อความ* ชนิดข้อมูล แต่ชนิด Common Data Model (ความหมาย) อาจเป็น *อีเมล* หรือ *EmailAddress*</span><span class="sxs-lookup"><span data-stu-id="dae65-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="dae65-125">ตารางทั้งสองจะแสดงเฉพาะตัวอย่างของข้อมูลของเอนทิตีของคุณ</span><span class="sxs-lookup"><span data-stu-id="dae65-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="dae65-126">เมื่อต้องการดูชุดข้อมูลแบบเต็ม ให้ไปที่หน้า **แหล่งข้อมูล** ให้เลือกเอนทิตี เลือก **แก้ไข** และจากนั้น ดูข้อมูลของเอนทิตีนี้พร้อมกับตัวแก้ไข Power Query ตามที่อธิบายไว้ใน [แหล่งข้อมูล](data-sources.md)</span><span class="sxs-lookup"><span data-stu-id="dae65-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="dae65-127">เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับข้อมูลที่ถูกนำไปใช้ในเอนทิตี คอลัมน์ **สรุป** จะให้คุณลักษณะที่สำคัญบางอย่างของข้อมูล เช่น nulls ค่าที่ขาดหายไป ค่าที่ไม่ซ้ำ การนับจำนวน และการกระจาย ตามความเหมาะสมกับข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="dae65-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="dae65-128">เลือกไอคอนแผนภูมิเพื่อดูสรุปของข้อมูล</span><span class="sxs-lookup"><span data-stu-id="dae65-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dae65-129">![สัญลักษณ์สรุป](media/data-manager-entities-summary.png "ตารางสรุปข้อมูล")</span><span class="sxs-lookup"><span data-stu-id="dae65-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="dae65-130">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="dae65-130">Next step</span></span>

<span data-ttu-id="dae65-131">ดูหัวข้อ [รวม](data-unification.md) เพื่อเรียนรู้วิธีการ *แม็ป* *จับคู่* และ *ผสาน* ข้อมูลที่ถูกนำไปใช้</span><span class="sxs-lookup"><span data-stu-id="dae65-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
