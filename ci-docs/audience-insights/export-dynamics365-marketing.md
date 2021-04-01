---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Marketing
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Marketing
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597626"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="aff98-103">ตัวเชื่อมต่อสำหรับ Dynamics 365 Marketing (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="aff98-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="aff98-104">ใช้ [เซ็กเมนต์](segments.md) เพื่อสร้างการส่งเสริมการขายและติดต่อกลุ่มเฉพาะของลูกค้าด้วย Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="aff98-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="aff98-105">สำหรับข้อมูลเพิ่มเติม โปรดดู [ใช้เซ็กเมนต์จาก Dynamics 365 Customer Insights ด้วย Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="aff98-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="aff98-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="aff98-106">Prerequisite</span></span>

- <span data-ttu-id="aff98-107">ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Marketing ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Marketing ได้</span><span class="sxs-lookup"><span data-stu-id="aff98-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="aff98-108">อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Marketing โดยใช้ Common Data Services](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="aff98-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="aff98-109">การส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Marketing จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Marketing</span><span class="sxs-lookup"><span data-stu-id="aff98-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="aff98-110">ต้องนำเข้าเรกคอร์ดผู้ติดต่อจาก Marketing ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และต้องใช้เป็นแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="aff98-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="aff98-111">นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแม็ปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้</span><span class="sxs-lookup"><span data-stu-id="aff98-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="aff98-112">กำหนดค่าตัวเชื่อมต่อสำหรับ Marketing</span><span class="sxs-lookup"><span data-stu-id="aff98-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="aff98-113">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="aff98-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aff98-114">ภายใต้ **Dynamics 365 Marketing** เลือก **ติดตั้ง**</span><span class="sxs-lookup"><span data-stu-id="aff98-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="aff98-115">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="aff98-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="aff98-116">ป้อน URL Marketing ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="aff98-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="aff98-117">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="aff98-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="aff98-118">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="aff98-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="aff98-119">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="aff98-119">Select **Next**.</span></span>

1. <span data-ttu-id="aff98-120">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="aff98-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="aff98-121">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="aff98-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aff98-122">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="aff98-122">Export the data</span></span>

<span data-ttu-id="aff98-123">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="aff98-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aff98-124">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="aff98-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]