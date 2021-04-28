---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Sales
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและส่งออกไปยัง Dynamics 365 Sales
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759627"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="729c4-103">ใช้เซ็กเมนต์ใน Dynamics 365 Sales (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="729c4-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="729c4-104">ใช้ข้อมูลลูกค้าของคุณเพื่อสร้างรายชื่อเพื่อทำการตลาด ติดตามลำดับงาน และนำเสนอโปรโมชันด้วย Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="729c4-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="729c4-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="729c4-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="729c4-106">ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Sales ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Sales ได้</span><span class="sxs-lookup"><span data-stu-id="729c4-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="729c4-107">อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Sales โดยใช้ Common Data Services](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="729c4-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="729c4-108">การส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Sales จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Sales</span><span class="sxs-lookup"><span data-stu-id="729c4-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="729c4-109">ต้องนำเข้าเรกคอร์ดผู้ติดต่อจาก Sales ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และต้องใช้เป็นแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="729c4-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="729c4-110">นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแม็ปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้</span><span class="sxs-lookup"><span data-stu-id="729c4-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="729c4-111">ตั้งค่าการเชื่อมต่อไปยัง Sales</span><span class="sxs-lookup"><span data-stu-id="729c4-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="729c4-112">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="729c4-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="729c4-113">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Dynamics 365 Sales** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="729c4-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="729c4-114">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="729c4-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="729c4-115">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="729c4-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="729c4-116">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="729c4-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="729c4-117">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="729c4-117">Choose who can use this connection.</span></span> <span data-ttu-id="729c4-118">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="729c4-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="729c4-119">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="729c4-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="729c4-120">ป้อน URL Sales ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="729c4-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="729c4-121">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="729c4-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="729c4-122">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="729c4-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="729c4-123">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="729c4-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="729c4-124">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="729c4-124">Configure an export</span></span>

<span data-ttu-id="729c4-125">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="729c4-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="729c4-126">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="729c4-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="729c4-127">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="729c4-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="729c4-128">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="729c4-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="729c4-129">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="729c4-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="729c4-130">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="729c4-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="729c4-131">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="729c4-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="729c4-132">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="729c4-132">Select **Save**</span></span>

<span data-ttu-id="729c4-133">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="729c4-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="729c4-134">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="729c4-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="729c4-135">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="729c4-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
