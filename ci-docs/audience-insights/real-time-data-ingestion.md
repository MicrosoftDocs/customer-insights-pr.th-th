---
title: การนำเข้าข้อมูลแบบเรียลไทม์และข้อจำกัด
description: ข้อมูลทั่วไปเกี่ยวกับความสามารถแบบเรียลไทม์ในข้อมูลเชิงลึกกลุ่มเป้าหมาย
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689198"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="653ee-103">การเพิ่มข้อมูลแบบในเวลาจริง (ดูตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="653ee-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="653ee-104">ฟังก์ชันการทำงานแบบในเวลาจริงช่วยให้คุณเห็นการโต้ตอบล่าสุดที่ลูกค้าทำกับผลิตภัณฑ์หรือบริการของคุณภายในไม่กี่วินาที</span><span class="sxs-lookup"><span data-stu-id="653ee-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="653ee-105">[การรีเฟรชตามกำหนดการ](system.md#schedule-tab) มีเรกคอร์ดจำนวนมากและการดำเนินการที่ซับซ้อนหลายอย่าง</span><span class="sxs-lookup"><span data-stu-id="653ee-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="653ee-106">อย่างแรก ข้อมูลจะดึงมาจากแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="653ee-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="653ee-107">จากนั้นข้อมูลจะถูกรวมเข้าด้วยกันและผสานข้อมูลเพิ่มเติมเข้าด้วยกัน</span><span class="sxs-lookup"><span data-stu-id="653ee-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="653ee-108">การดำเนินการทุกขั้นตอนนี้อาจใช้เวลาหลายนาทีถึงหลายชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="653ee-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="653ee-109">ฟังก์ชันเรียลไทม์จะให้ข้อมูลทันทีสำหรับการใช้งานจนกว่าการรีเฟรชตามกำหนดเวลาในภายหลังจะดึงข้อมูลนี้จากแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="653ee-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="653ee-110">การอัปเดตแบบในเวลาจริงมีเวลาหมดอายุหลังจากที่ไม่มีการแทนที่ค่าจากแหล่งข้อมูลอีกต่อไป:</span><span class="sxs-lookup"><span data-stu-id="653ee-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="653ee-111">การอัปเดตโปรไฟล์จะถูกเก็บไว้เป็นเวลา 4 ชั่วโมง</span><span class="sxs-lookup"><span data-stu-id="653ee-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="653ee-112">กิจกรรมจะถูกเก็บไว้เป็นเวลา 30 วัน</span><span class="sxs-lookup"><span data-stu-id="653ee-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="653ee-113">ค่าเหล่านี้คือพารามิเตอร์การโทร API ที่คุณสามารถเปลี่ยนได้</span><span class="sxs-lookup"><span data-stu-id="653ee-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="653ee-114">พวกเขามีจุดมุ่งหมายเพื่อให้แน่ใจว่าข้อมูลต้นฉบับของคุณยังคงเป็นแหล่งความจริงของคุณ</span><span class="sxs-lookup"><span data-stu-id="653ee-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="653ee-115">หากคุณต้องการให้รวมการปรับปรุงแบบเรียลไทม์ให้นานขึ้น คุณต้องเพิ่มการปรับปรุงลงในแหล่งข้อมูล เพื่อที่จะดึงข้อมูลในระหว่างการรีเฟรชตามกำหนดการครั้งถัดไป</span><span class="sxs-lookup"><span data-stu-id="653ee-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="653ee-116">การอัปเดตแบบในเวลาจริงของฟิลด์โปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="653ee-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="653ee-117">โปรไฟล์ที่ปรับปรุงจะแสดงในมุมมองการ์ดลูกค้าหรือการจัดรูปแบบการแสดงข้อมูลอื่นๆ ภายในไม่กี่วินาที</span><span class="sxs-lookup"><span data-stu-id="653ee-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="653ee-118">เนื่องจากการดำเนินการแบบในเวลาจริงเกิดขึ้นหลังจากการรวมข้อมูลเกิดขึ้น จึงมีผลกับโปรไฟล์ลูกค้าแบบรวมเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="653ee-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="653ee-119">ดังนั้นการเปลี่ยนแปลงโปรไฟล์แบบในเวลาจริงจะไม่อัปเดตมาตรการ การเป็นสมาชิกเซ็กเมนต์ หรือการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="653ee-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="653ee-120">ข้อจำกัด</span><span class="sxs-lookup"><span data-stu-id="653ee-120">Limitations</span></span>

- <span data-ttu-id="653ee-121">สามารถอัปเดตโปรไฟล์ลูกค้า แต่ไม่สามารถสร้างหรือลบได้</span><span class="sxs-lookup"><span data-stu-id="653ee-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="653ee-122">การส่งออกการอัปเดตแบบในเวลาจริงไปยังระบบภายนอก เช่น Power BI ไม่สามารถทำได้ในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="653ee-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="653ee-123">การสร้างกิจกรรมแบบในเวลาจริง</span><span class="sxs-lookup"><span data-stu-id="653ee-123">Real-time creation of activities</span></span>

<span data-ttu-id="653ee-124">API แบบเรียลไทม์ช่วยให้คุณสามารถเผยแพร่กิจกรรมใหม่จากระบบต้นทางของคุณ (เรกคอร์ดต้นทางแต่ละรายการ) ไปยังโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="653ee-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="653ee-125">กิจกรรมใหม่จะพร้อมใช้งานเป็นกิจกรรมแบบรวมในเส้นเวลาของโปรไฟล์ลูกค้าแบบรวมภายในไม่กี่วินาที</span><span class="sxs-lookup"><span data-stu-id="653ee-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="653ee-126">คุณสามารถดูไทม์ไลน์ในมุมมองการ์ดลูกค้าหรือการรวมไทม์ไลน์อื่นๆ ที่คุณกำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="653ee-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="653ee-127">กิจกรรมไม่สามารถเปลี่ยนแปลงได้</span><span class="sxs-lookup"><span data-stu-id="653ee-127">Activities are immutable.</span></span> <span data-ttu-id="653ee-128">จะไม่มีการเปลี่ยนแปลงเมื่อสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="653ee-128">They don't change once created.</span></span>
> - <span data-ttu-id="653ee-129">ขณะนี้เซ็กเมนต์และการวัดจะไม่อัปเดตตามกิจกรรมใหม่</span><span class="sxs-lookup"><span data-stu-id="653ee-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="653ee-130">กิจกรรมที่เพิ่มผ่านเฉพาะ API แบบในเวลาจริงไม่ได้เป็นส่วนหนึ่งของการส่งออกและจะไม่แสดงใน PowerBI</span><span class="sxs-lookup"><span data-stu-id="653ee-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="653ee-131">มีสองวิธีในการเชื่อมต่อกับ API แบบเรียลไทม์:</span><span class="sxs-lookup"><span data-stu-id="653ee-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="653ee-132">[โดยทางอ้อม](#connect-via-the-dynamics-365-customer-insights-connector) ใช้ [ตัวเชื่อมต่อ Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="653ee-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="653ee-133">[โดยทางตรง](#connect-directly-to-the-real-time-api) ด้วยรหัส</span><span class="sxs-lookup"><span data-stu-id="653ee-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="653ee-134">ทั้งสองวิธีมีข้อกำหนดเบื้องต้นต่อไปนี้เหมือนกัน:</span><span class="sxs-lookup"><span data-stu-id="653ee-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="653ee-135">สภาพแวดล้อม Customer Insights</span><span class="sxs-lookup"><span data-stu-id="653ee-135">A Customer Insights environment</span></span>
- <span data-ttu-id="653ee-136">โปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="653ee-136">Unified customer profiles</span></span>
- <span data-ttu-id="653ee-137">กิจกรรมที่กำหนดค่าและเรียกใช้</span><span class="sxs-lookup"><span data-stu-id="653ee-137">Activities configured and run</span></span>
- <span data-ttu-id="653ee-138">สิทธิ์ของผู้มีส่วนร่วมหรือผู้ดูแลระบบเพื่อรับรองความถูกต้องของบัญชีของคุณ</span><span class="sxs-lookup"><span data-stu-id="653ee-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="653ee-139">เชื่อมต่อผ่านตัวเชื่อมต่อ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="653ee-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="653ee-140">API แบบในเวลาจริงสามารถนำเข้าข้อมูลจากตัวเชื่อมต่อเฉพาะของ Power Platform [ตัวเชื่อมต่อ Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/) โดยไม่จำเป็นต้องเขียนและปรับใช้รหัสใดๆ</span><span class="sxs-lookup"><span data-stu-id="653ee-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="653ee-141">ตัวเชื่อมต่อสามารถดำเนินการแบบในเวลาจริงเช่นเดียวกับ API</span><span class="sxs-lookup"><span data-stu-id="653ee-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="653ee-142">คุณต้องมีใบอนุญาตที่ถูกต้องสำหรับตัวเชื่อมต่อแบบพรีเมียม</span><span class="sxs-lookup"><span data-stu-id="653ee-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="653ee-143">สำหรับข้อมูลเพิ่มเติม ดูที่ [คำถามที่พบบ่อยเกี่ยวกับการให้สิทธิ์การใช้งาน Power Apps และ Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)</span><span class="sxs-lookup"><span data-stu-id="653ee-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="653ee-144">Power Platform [Power Apps และ/หรือ Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="653ee-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="653ee-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="653ee-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="653ee-146">สำหรับรายละเอียดเกี่ยวกับการสร้างโฟลว์ ดูที่ [เอกสาร Power Automate](https://docs.microsoft.com/power-automate/)</span><span class="sxs-lookup"><span data-stu-id="653ee-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="653ee-147">เชื่อมต่อโดยตรงกับ API แบบในเวลาจริง</span><span class="sxs-lookup"><span data-stu-id="653ee-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="653ee-148">คุณสามารถใช้ความสามารถแบบเรียลไทม์โดยการสร้างไปป์ไลน์ของคุณเองและเชื่อมต่อโดยตรงกับ API แบบเรียลไทม์</span><span class="sxs-lookup"><span data-stu-id="653ee-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="653ee-149">คุณสามารถโพสต์กิจกรรมในรูปแบบของระบบต้นทางของคุณหรือในรูปแบบ UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="653ee-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="653ee-150">รับรูปแบบโดยการเรียก API ไปที่ /api/instances/{instanceId}/manage/entities/UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="653ee-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="653ee-151">รายละเอียดของ API นี้ รวมถึงพารามิเตอร์และการตอบสนองสามารถดูได้ในส่วน **EntityData** ใน [ข้อมูลอ้างอิง Customer Insights API ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)</span><span class="sxs-lookup"><span data-stu-id="653ee-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="653ee-152">สำหรับข้อมูลเพิ่มเติม โปรดดู [ทำงานกับ Customer Insights API](apis.md)</span><span class="sxs-lookup"><span data-stu-id="653ee-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="653ee-153">ทำความเข้าใจการใช้งานแบบในเวลาจริงด้วยการใช้การตรวจวัดระยะไกล</span><span class="sxs-lookup"><span data-stu-id="653ee-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="653ee-154">ดูภาพรวมของปริมาณคำขอไปยัง API แบบเรียลไทม์และข้อมูลเกี่ยวกับปัญหาที่ระบบอาจพบ</span><span class="sxs-lookup"><span data-stu-id="653ee-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="653ee-155">คุณสามารถ [เข้าถึงการตรวจวัดระยะไกลแบบในเวลาจริง](system.md#api-usage-tab) โดยไปที่ **ผู้ดูแลระบบ** > **ระบบ** > **การใช้งาน API**</span><span class="sxs-lookup"><span data-stu-id="653ee-155">You can [access the real-time telemetry](system.md#api-usage-tab) by going to **Admin** > **System** > **API usage**.</span></span> <span data-ttu-id="653ee-156">ในตาราง **การดำเนินงาน** แถวสำหรับการดำเนินงานของ API ที่ใช้วิธีการแบบเรียลไทม์จะมีปุ่มสำหรับดูการใช้งาน API แบบเรียลไทม์</span><span class="sxs-lookup"><span data-stu-id="653ee-156">In the **Operations** table, rows for API operations which use the real-time methods contain a button to view real-time API usage.</span></span> <span data-ttu-id="653ee-157">ปุ่มนี้แสดงให้เห็นด้วยสัญลักษณ์กล้องส่องทางไกล</span><span class="sxs-lookup"><span data-stu-id="653ee-157">The button is visualized with a binocular symbol.</span></span> <span data-ttu-id="653ee-158">เลือกปุ่มเพื่อเปิดบานหน้าต่างด้านข้างที่มีรายละเอียดการใช้งานสำหรับการใช้งาน API แบบเรียลไทม์ในสภาพแวดล้อมปัจจุบัน</span><span class="sxs-lookup"><span data-stu-id="653ee-158">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>

<span data-ttu-id="653ee-159">ใช้ตัวเลือก **จัดกลุ่มตาม** เพื่อเลือกวิธีการนำเสนอการโต้ตอบแบบในเวลาจริงที่ดีที่สุดของคุณบนไทม์ไลน์ตั้งแต่ 24 ชั่วโมงที่ผ่านมาจนถึง 30 วันที่ผ่านมา</span><span class="sxs-lookup"><span data-stu-id="653ee-159">Use the **Group by** selector to choose how to best present your real-time interactions on a timeline ranging from the last 24 hours to the last 30 days.</span></span> <span data-ttu-id="653ee-160">คุณสามารถจัดกลุ่มข้อมูลตามวิธี API ชื่อเอนทิตีที่ผ่านการรับรอง (เอนทิตีที่รับข้อมูล) สร้างโดย (แหล่งที่มาของเหตุการณ์) ผลลัพธ์ (สำเร็จหรือล้มเหลว) หรือรหัสข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="653ee-160">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="653ee-161">ข้อมูลมีอยู่ในแผนภูมิประวัติ และเป็นตาราง</span><span class="sxs-lookup"><span data-stu-id="653ee-161">The data is available as a history chart and as a table.</span></span>
