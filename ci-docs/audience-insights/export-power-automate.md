---
title: ตัวเชื่อมต่อ Power Automate | Microsoft Docs
description: สร้างโฟลว์ใน Microsoft Power Automate จาก Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268847"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="f8ea9-103">ตัวเชื่อมต่อ Power Automate (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="f8ea9-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="f8ea9-104">ทริกเกอร์เหตุการณ์เฉพาะที่จะเกิดขึ้นโดยอัตโนมัติเมื่อข้อมูลของคุณมีการเปลี่ยนแปลง และจัดการโฟลว์ที่ซับซ้อนมากขึ้นโดยตรงใน [Power Automate](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f8ea9-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="f8ea9-105">ทริกเกอร์ Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8ea9-105">Power Automate triggers</span></span>

<span data-ttu-id="f8ea9-106">ใช้ทริกเกอร์เพื่อสร้างโฟลว์ระบบคลาวด์ และทำให้งานซ้ำๆ เป็นแบบอัตโนมัติ เช่น การแจ้งเตือน หรือการดำเนินการขั้นสูงเพิ่มเติม</span><span class="sxs-lookup"><span data-stu-id="f8ea9-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="f8ea9-107">ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="f8ea9-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="f8ea9-108">ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="f8ea9-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="f8ea9-109">ทริกเกอร์เมื่อข้ามขีดจำกัดในเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="f8ea9-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="f8ea9-110">ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด</span><span class="sxs-lookup"><span data-stu-id="f8ea9-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f8ea9-111">ทริกเกอร์เมื่อข้ามขีดจำกัดในการวัดของธุรกิจ</span><span class="sxs-lookup"><span data-stu-id="f8ea9-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="f8ea9-112">ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด</span><span class="sxs-lookup"><span data-stu-id="f8ea9-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="f8ea9-113">ทริกเกอร์เมื่อการรีเฟรชทั้งหมด (แหล่งข้อมูล, เซ็กเมนต์, การวัด...) เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="f8ea9-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="f8ea9-114">ทริกเกอร์เมื่อการรีเฟรชของกระบวนการรวม (แผนที่ จับคู่ ผสาน) เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="f8ea9-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="f8ea9-115">[กำหนดค่าทริกเกอร์ของคุณใน Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)</span><span class="sxs-lookup"><span data-stu-id="f8ea9-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="f8ea9-116">การดำเนินการ Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8ea9-116">Power Automate actions</span></span>
<span data-ttu-id="f8ea9-117">ตัวเชื่อมต่อ Power Automate ให้การดำเนินการอื่นๆ นอกเหนือจากทริกเกอร์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="f8ea9-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="f8ea9-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="f8ea9-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="f8ea9-119">สร้างโฟลว์ Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8ea9-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="f8ea9-120">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="f8ea9-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8ea9-121">บนไทล์ **Power Automate** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="f8ea9-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f8ea9-122">Customer Insights Connector (พรีวิว) ใน Power Automate เปิดขึ้น</span><span class="sxs-lookup"><span data-stu-id="f8ea9-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="f8ea9-123">**ลงชื่อเข้าใช้** ไปยัง Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8ea9-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="f8ea9-124">เลือกหนึ่งในทริกเกอร์ที่พร้อมใช้งาน และเพิ่มขั้นตอนเพิ่มเติมในโฟลว์ใหม่ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f8ea9-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="f8ea9-125">สำหรับข้อมูลเพิ่มเติม โปรดดู [สร้างโฟลว์ระบบคลาวด์ใน Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow)</span><span class="sxs-lookup"><span data-stu-id="f8ea9-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="f8ea9-126">ตัวอย่างวิธีใช้โฟลว์:</span><span class="sxs-lookup"><span data-stu-id="f8ea9-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="f8ea9-127">โพสต์ข้อความไปยังช่องทาง Microsoft Teams หากการรีเฟรชแหล่งข้อมูลล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="f8ea9-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="f8ea9-128">ส่งอีเมลไปยังเจ้าของข้อมูล เมื่อมีการข้ามขีดจำกัดในเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="f8ea9-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]