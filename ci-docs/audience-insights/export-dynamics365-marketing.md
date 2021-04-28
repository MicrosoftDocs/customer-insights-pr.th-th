---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Marketing
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Dynamics 365 Marketing
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759660"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="0fed0-103">ใช้เซ็กเมนต์ใน Dynamics 365 Marketing (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="0fed0-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0fed0-104">ใช้ [เซ็กเมนต์](segments.md) เพื่อสร้างการส่งเสริมการขายและติดต่อกลุ่มเฉพาะของลูกค้าด้วย Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="0fed0-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="0fed0-105">สำหรับข้อมูลเพิ่มเติม โปรดดู [ใช้เซ็กเมนต์จาก Dynamics 365 Customer Insights ด้วย Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="0fed0-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="0fed0-106">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="0fed0-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="0fed0-107">ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Marketing ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Marketing ได้</span><span class="sxs-lookup"><span data-stu-id="0fed0-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="0fed0-108">อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Marketing โดยใช้ Common Data Services](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="0fed0-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0fed0-109">การส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Marketing จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Marketing</span><span class="sxs-lookup"><span data-stu-id="0fed0-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="0fed0-110">ต้องนำเข้าเรกคอร์ดผู้ติดต่อจาก Marketing ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และต้องใช้เป็นแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="0fed0-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0fed0-111">นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแม็ปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้</span><span class="sxs-lookup"><span data-stu-id="0fed0-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="0fed0-112">ตั้งค่าการเชื่อมต่อไปยัง Marketing</span><span class="sxs-lookup"><span data-stu-id="0fed0-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="0fed0-113">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="0fed0-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0fed0-114">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Dynamics 365 Marketing** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="0fed0-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="0fed0-115">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="0fed0-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0fed0-116">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="0fed0-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0fed0-117">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="0fed0-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0fed0-118">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="0fed0-118">Choose who can use this connection.</span></span> <span data-ttu-id="0fed0-119">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="0fed0-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0fed0-120">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="0fed0-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0fed0-121">ป้อน URL Marketing ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="0fed0-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0fed0-122">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="0fed0-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="0fed0-123">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0fed0-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0fed0-124">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="0fed0-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0fed0-125">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="0fed0-125">Configure an export</span></span>

<span data-ttu-id="0fed0-126">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="0fed0-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0fed0-127">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="0fed0-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0fed0-128">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="0fed0-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0fed0-129">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="0fed0-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0fed0-130">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="0fed0-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="0fed0-131">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="0fed0-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0fed0-132">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="0fed0-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="0fed0-133">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="0fed0-133">Select **Save**.</span></span>

<span data-ttu-id="0fed0-134">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="0fed0-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0fed0-135">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="0fed0-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0fed0-136">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="0fed0-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
