---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Marketing
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Marketing
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643796"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="6bf86-103">ตัวเชื่อมต่อสำหรับ Dynamics 365 Marketing (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="6bf86-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6bf86-104">ใช้ [เซ็กเมนต์](segments.md) เพื่อสร้างการส่งเสริมการขายและติดต่อกลุ่มเฉพาะของลูกค้าด้วย Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="6bf86-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="6bf86-105">สำหรับข้อมูลเพิ่มเติม โปรดดู [ใช้เซ็กเมนต์จาก Dynamics 365 Customer Insights ด้วย Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="6bf86-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="6bf86-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="6bf86-106">Prerequisite</span></span>

<span data-ttu-id="6bf86-107">เรกคอร์ดผู้ติดต่อ [จาก Dynamics 365 Marketing ที่นำเข้า Common Data Service](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="6bf86-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="6bf86-108">กำหนดค่าตัวเชื่อมต่อสำหรับ Marketing</span><span class="sxs-lookup"><span data-stu-id="6bf86-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="6bf86-109">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="6bf86-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6bf86-110">ภายใต้ **Dynamics 365 Marketing** เลือก **ติดตั้ง**</span><span class="sxs-lookup"><span data-stu-id="6bf86-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="6bf86-111">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="6bf86-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6bf86-112">ป้อน URL Marketing ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="6bf86-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6bf86-113">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="6bf86-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="6bf86-114">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6bf86-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6bf86-115">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="6bf86-115">Select **Next**.</span></span>

1. <span data-ttu-id="6bf86-116">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="6bf86-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="6bf86-117">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="6bf86-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6bf86-118">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="6bf86-118">Export the data</span></span>

<span data-ttu-id="6bf86-119">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="6bf86-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6bf86-120">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="6bf86-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
