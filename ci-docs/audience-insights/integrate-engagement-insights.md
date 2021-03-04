---
title: รวมข้อมูลเว็บจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมกับข้อมูลเชิงลึกเกี่ยวกับผู้ชม
description: นำข้อมูลเว็บเกี่ยวกับลูกค้าจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมไปสู่ข้อมูลเชิงลึกเกี่ยวกับผู้ชม
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267699"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="28657-103">รวมข้อมูลเว็บจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมกับข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="28657-104">ลูกค้ามักทำธุรกรรมแบบวันต่อวันทางออนไลน์ โดยใช้เว็บไซต์</span><span class="sxs-lookup"><span data-stu-id="28657-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="28657-105">ความสามารถของข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม ใน Dynamics 365 Customer Insights เป็นโซลูชันที่สะดวกในการรวมข้อมูลเว็บเป็นแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="28657-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="28657-106">นอกจากข้อมูลด้านธุรกรรม ข้อมูลประชากร หรือพฤติกรรมแล้ว เรายังสามารถดูกิจกรรมบนเว็บในโปรไฟล์ลูกค้าแบบรวมได้</span><span class="sxs-lookup"><span data-stu-id="28657-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="28657-107">เราสามารถใช้โปรไฟล์นี้เพื่อรับข้อมูลเชิงลึกเพิ่มเติม เช่น เซ็กเมนต์ การวัด หรือการคาดการณ์ สำหรับการเปิดใช้งานผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="28657-108">บทความนี้อธิบายขั้นตอนในการนำข้อมูลกิจกรรมบนเว็บของลูกค้าของคุรจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม ไปสู่สภาพแวดล้อมข้อมูลเชิงลึกเกี่ยวกับผู้ชมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="28657-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="28657-109">ในตัวอย่างนี้ เราถือว่าสภาพแวดล้อมที่มีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="28657-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="28657-110">โปรไฟล์ถูกรวมเข้าด้วยกันโดยมีแหล่งที่มาจากการสำรวจ การขายปลีก และระบบการออกตั๋ว</span><span class="sxs-lookup"><span data-stu-id="28657-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="28657-111">นอกจากนี้ยังแสดงกิจกรรมที่เกี่ยวข้องของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="28657-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="28657-112">ตอนนี้เราต้องการทราบว่าหากลูกค้าเข้าชมเว็บของเรา และเข้าใจกิจกรรมของพวกเขา</span><span class="sxs-lookup"><span data-stu-id="28657-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="28657-113">กิจกรรมต่างๆ ได้แก่ เยี่ยมชมเว็บไซต์ หรือดูหน้าผลิตภัณฑ์จากลิงก์ที่ได้รับในอีเมล</span><span class="sxs-lookup"><span data-stu-id="28657-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28657-114">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="28657-114">Prerequisites</span></span>

<span data-ttu-id="28657-115">ในการรวมข้อมูลจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม จำเป็นต้องปฏิบัติตามข้อกำหนดเบื้องต้นบางประการ:</span><span class="sxs-lookup"><span data-stu-id="28657-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="28657-116">รวม SDK ข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมกับเว็บไซต์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="28657-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="28657-117">สำหรับข้อมูลเพิ่มเติม ดู [เริ่มต้นใช้งาน SDK เว็บ](../engagement-insights/instrument-website.md)</span><span class="sxs-lookup"><span data-stu-id="28657-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="28657-118">การส่งออกกิจกรรมบนเว็บจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม จำเป็นต้องเข้าถึงบัญชีพื้นที่เก็บข้อมูล ADLS Gen 2 ที่จะใช้ในการนำเข้าข้อมูลเหตุการณ์บนเว็บไปยังข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="28657-119">สำหรับข้อมูลเพิ่มเติม โปรดดู [ส่งออกเหตุการณ์](../engagement-insights/export-events.md)</span><span class="sxs-lookup"><span data-stu-id="28657-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="28657-120">กำหนดค่าเหตุการณ์ที่ปรับแต่งในข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม</span><span class="sxs-lookup"><span data-stu-id="28657-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="28657-121">หลังจากผู้ดูแลระบบจัดทำเว็บไซต์ด้วย SDK ข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม *เหตุการณ์พื้นฐาน* จะถูกรวบรวม เมื่อผู้ใช้ดูหน้าเว็บหรือคลิกที่ใดที่หนึ่ง</span><span class="sxs-lookup"><span data-stu-id="28657-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="28657-122">เหตุการณ์พื้นฐานมักจะมีรายละเอียดมากมาย</span><span class="sxs-lookup"><span data-stu-id="28657-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="28657-123">ขึ้นอยู่กับกรณีการใช้งานของคุณ คุณต้องการข้อมูลเพียงบางส่วนในเหตุการณ์พื้นฐาน</span><span class="sxs-lookup"><span data-stu-id="28657-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="28657-124">ข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมช่วยให้คุณสร้าง *เหตุการณ์ที่ปรับปรุง* ที่มีเฉพาะคุณสมบัติของเหตุการณ์พื้นฐานที่คุณเลือก</span><span class="sxs-lookup"><span data-stu-id="28657-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="28657-125">สำหรับข้อมูลเพิ่มเติม ดู [สร้างและแก้ไขเหตุการณ์ที่ปรับปรุง](../engagement-insights/refined-events.md)</span><span class="sxs-lookup"><span data-stu-id="28657-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="28657-126">ข้อควรพิจารณาเมื่อสร้างเหตุการณ์ที่ปรับปรุง:</span><span class="sxs-lookup"><span data-stu-id="28657-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="28657-127">ระบุชื่อที่มีความหมายสำหรับเหตุการณ์ที่ปรับปรุง</span><span class="sxs-lookup"><span data-stu-id="28657-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="28657-128">ใช้เป็นชื่อกิจกรรมในข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="28657-129">เลือกคุณสมบัติต่อไปนี้เป็นอย่างน้อย เพื่อสร้างกิจกรรมในข้อมูลเชิงลึกเกี่ยวกับผู้ชม:</span><span class="sxs-lookup"><span data-stu-id="28657-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="28657-130">Signal.Action.Name - ระบุรายละเอียดกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="28657-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="28657-131">Signal.User.Id - ใช้เพื่อจับคู่กับรหัสลูกค้า</span><span class="sxs-lookup"><span data-stu-id="28657-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="28657-132">Signal.View.Uri - ใช้เป็นที่อยู่เว็บเป็นพื้นฐานสำหรับเซ็กเมนต์หรือการวัด</span><span class="sxs-lookup"><span data-stu-id="28657-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="28657-133">Signal.Export.Id - เพื่อใช้เป็นคีย์หลักสำหรับเหตุการณ์</span><span class="sxs-lookup"><span data-stu-id="28657-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="28657-134">Signal.Timestamp - เพื่อกำหนดวันที่และเวลาสำหรับกิจกรรม</span><span class="sxs-lookup"><span data-stu-id="28657-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="28657-135">เลือกตัวกรองเพื่อมุ่งเน้นไปที่เหตุการณ์และหน้า ที่สำคัญสำหรับกรณีการใช้งานของคุณ</span><span class="sxs-lookup"><span data-stu-id="28657-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="28657-136">ในตัวอย่างนี้ เราจะใช้ชื่อการดำเนินการ "การส่งเสริมการขายทางอีเมล"</span><span class="sxs-lookup"><span data-stu-id="28657-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="28657-137">ส่งออกกิจกรรมบนเว็บที่ปรับปรุง</span><span class="sxs-lookup"><span data-stu-id="28657-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="28657-138">หลังจากกำหนดเหตุการณ์ที่ปรับปรุงแล้ว คุณต้องกำหนดค่าการส่งออกข้อมูลเหตุการณ์ให้กับ Azure Data Lake Storage ซึ่งสามารถตั้งค่าเป็นแหล่งข้อมูล สำหรับการส่งผ่านข้อมูลในข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="28657-139">การส่งออกเกิดขึ้นอย่างต่อเนื่องเมื่อมีโฟล์เหตุการณ์จากคุณสมบัติเว็บ</span><span class="sxs-lookup"><span data-stu-id="28657-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="28657-140">สำหรับข้อมูลเพิ่มเติม โปรดดู [ส่งออกเหตุการณ์](../engagement-insights/export-events.md)</span><span class="sxs-lookup"><span data-stu-id="28657-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="28657-141">นำเข้าข้อมูลเหตุการณ์ไปยังข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="28657-142">ตอนนี้คุณได้กำหนดเหตุการณ์ที่ปรับปรุงและกำหนดค่าการส่งออกแล้ว เราจะดำเนินการต่อเพื่อนำเข้าข้อมูลไปยังข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="28657-143">คุณต้องสร้างแหล่งข้อมูลใหม่ โดยใช้โฟลเดอร์ Common Data Model</span><span class="sxs-lookup"><span data-stu-id="28657-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="28657-144">ป้อนรายละเอียดสำหรับบัญชีพื้นที่เก็บข้อมูลที่คุณส่งออกกิจกรรมไป</span><span class="sxs-lookup"><span data-stu-id="28657-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="28657-145">ในไฟล์ *default.cdm.json* เลือกเหตุการณ์ที่ปรับปรุง เพื่อนำเข้าและสร้างเอนทิตีในข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="28657-146">สำหรับข้อมูลเพิ่มเติม ดู [เชื่อมต่อกับโฟลเดอร์ Common Data Model โดยใช้บัญชี Azure Data Lake](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="28657-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="28657-147">เชื่อมโยงข้อมูลเหตุการณ์ที่ปรับปรุงแล้วเป็นกิจกรรมของโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="28657-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="28657-148">หลังจากเสร็จสิ้นการนำเข้าเอนทิตี คุณสามารถกำหนดค่ากิจกรรมสำหรับโปรไฟล์ลูกค้าได้</span><span class="sxs-lookup"><span data-stu-id="28657-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="28657-149">สำหรับข้อมูลเพิ่มเติม ดู [กิจกรรมของลูกค้า](activities.md)</span><span class="sxs-lookup"><span data-stu-id="28657-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="หน้ากิจกรรมที่มีบานหน้าต่างแก้ไขกิจกรรมแบบขยาย และกรอกข้อมูลในฟิลด์":::

<span data-ttu-id="28657-151">กำหนดค่ากิจกรรมใหม่ด้วยการแมปต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="28657-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="28657-152">**คีย์หลัก:** Signal.Export.Id รหัสเฉพาะที่พร้อมใช้งานสำหรับทุกเรกคอร์ดเหตุการณ์ในข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม</span><span class="sxs-lookup"><span data-stu-id="28657-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="28657-153">คุณสมบัตินี้ถูกสร้างขึ้นโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="28657-153">This property is automatically generated.</span></span>

- <span data-ttu-id="28657-154">**การประทับเวลา:** Signal.Timestamp ในคุณสมบัติเหตุการณ์</span><span class="sxs-lookup"><span data-stu-id="28657-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="28657-155">**เหตุการณ์:** Signal.Name ชื่อเหตุการณ์ที่คุณต้องการติดตาม</span><span class="sxs-lookup"><span data-stu-id="28657-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="28657-156">**ที่อยู่เว็บ:** Signal.View.Uri หมายถึง uri ของเพจที่สร้างเหตุการณ์</span><span class="sxs-lookup"><span data-stu-id="28657-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="28657-157">**รายละเอียด:** Signal.Action.Name เพื่อแสดงข้อมูลเพื่อเชื่อมโยงกับเหตุการณ์</span><span class="sxs-lookup"><span data-stu-id="28657-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="28657-158">คุณสมบัติที่เลือกในกรณีนี้ บ่งชี้ว่าเหตุการณ์นั้นมีไว้สำหรับการส่งเสริมการขายทางอีเมล</span><span class="sxs-lookup"><span data-stu-id="28657-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="28657-159">**ชนิดกิจกรรม:** ในตัวอย่างนี้ เราเลือก WebLog ชนิดกิจกรรมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="28657-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="28657-160">การเลือกนี้เป็นตัวเลือกตัวกรองที่มีประโยชน์ในการรันโมเดลการคาดการณ์ หรือสร้างเซ็กเมนต์ตามชนิดกิจกรรมนี้</span><span class="sxs-lookup"><span data-stu-id="28657-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="28657-161">**ตั้งค่าความสัมพันธ์:** การตั้งค่าที่สำคัญนี้เชื่อมโยงกิจกรรมกับโปรไฟล์ลูกค้าที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="28657-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="28657-162">**Signal.User.Id** คือตัวระบุที่กำหนดค่าใน SDK ที่จะรวบรวมและเกี่ยวข้องกับรหัสผู้ใช้ในแหล่งข้อมูลอื่น ที่กำหนดค่าในข้อมูลเชิงลึกเกี่ยวกับผู้ชม</span><span class="sxs-lookup"><span data-stu-id="28657-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="28657-163">ในตัวอย่างนี้ เรากำหนดค่าความสัมพันธ์ระหว่าง Signal.User.Id และ RetailCustomers: CustomerRetailId ซึ่งเป็นคีย์หลักที่ถูกกำหนด ในขั้นตอนการแม็ปของกระบวนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="28657-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="28657-164">หลังจากประมวลผลกิจกรรม คุณสามารถตรวจสอบเรกคอร์ดลูกค้า และเปิดบัตรลูกค้าเพื่อดูกิจกรรมจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมในไทม์ไลน์</span><span class="sxs-lookup"><span data-stu-id="28657-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="28657-165">หากต้องการค้นหารหัสลูกค้าที่มีกิจกรรมข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม ให้ไปที่ **เอนทิตี** และดูตัวอย่างข้อมูลสำหรับเอนทิตี UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="28657-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="28657-166">ActivityTypeDisplay = WebLog มีกิจกรรมข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมที่กำหนดค่าไว้ในตัวอย่างด้านบน</span><span class="sxs-lookup"><span data-stu-id="28657-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="28657-167">คัดลอกรหัสลูกค้าสำหรับหนึ่งในเรกคอร์ดเหล่านั้น และสำหรับรหัสนั้นบนหน้า **ลูกค้า**</span><span class="sxs-lookup"><span data-stu-id="28657-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="28657-168">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="28657-168">Next Steps</span></span>

<span data-ttu-id="28657-169">ตอนนี้คุณสามารถสร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และ [การคาดการณ์](predictions.md) เพื่อสร้างความสัมพันธ์ที่มีความหมายกับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="28657-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]