---
title: ตัวเชื่อมต่อ Power Automate | Microsoft Docs
description: สร้างโฟลว์ใน Microsoft Power Automate จาก Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407118"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="eb2ac-103">ตัวเชื่อมต่อ Power Automate (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="eb2ac-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="eb2ac-104">ทริกเกอร์เหตุการณ์เฉพาะที่จะเกิดขึ้นโดยอัตโนมัติเมื่อข้อมูลของคุณมีการเปลี่ยนแปลง และจัดการโฟลว์ที่ซับซ้อนมากขึ้นโดยตรงใน [Power Automate](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="eb2ac-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="eb2ac-105">ทริกเกอร์ Power Automate</span><span class="sxs-lookup"><span data-stu-id="eb2ac-105">Power Automate triggers</span></span>

<span data-ttu-id="eb2ac-106">คุณสามารถใช้ทริกเกอร์ที่หลากหลายที่อนุญาตให้คุณสร้างโฟลว์เพื่อทำงานซ้ำอัตโนมัติ เช่น การแจ้งเตือน หรือการดำเนินการขั้นสูงอื่นๆ</span><span class="sxs-lookup"><span data-stu-id="eb2ac-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="eb2ac-107">ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="eb2ac-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="eb2ac-108">ทริกเกอร์เมื่อการรีเฟรชแหล่งข้อมูลสำเร็จ</span><span class="sxs-lookup"><span data-stu-id="eb2ac-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="eb2ac-109">ทริกเกอร์เมื่อข้ามขีดจำกัดในเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="eb2ac-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="eb2ac-110">ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด</span><span class="sxs-lookup"><span data-stu-id="eb2ac-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="eb2ac-111">ทริกเกอร์เมื่อข้ามขีดจำกัดในการวัดของธุรกิจ</span><span class="sxs-lookup"><span data-stu-id="eb2ac-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="eb2ac-112">ทริกเกอร์จะถูกจำกัดการข้ามผ่านขีดจำกัด</span><span class="sxs-lookup"><span data-stu-id="eb2ac-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="eb2ac-113">ทริกเกอร์เมื่อการรีเฟรชทั้งหมด (แหล่งข้อมูล, เซ็กเมนต์, การวัด...) เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="eb2ac-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="eb2ac-114">ทริกเกอร์เมื่อการรีเฟรชของกระบวนการรวม (แผนที่ จับคู่ ผสาน) เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="eb2ac-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="eb2ac-115">[กำหนดค่าทริกเกอร์ของคุณใน Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)</span><span class="sxs-lookup"><span data-stu-id="eb2ac-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="eb2ac-116">การดำเนินการ Power Automate</span><span class="sxs-lookup"><span data-stu-id="eb2ac-116">Power Automate actions</span></span>
<span data-ttu-id="eb2ac-117">ตัวเชื่อมต่อ Power Automate ให้การดำเนินการอื่นๆ นอกเหนือจากทริกเกอร์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="eb2ac-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="eb2ac-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="eb2ac-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="eb2ac-119">สร้างโฟลว์ Power Automate ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="eb2ac-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="eb2ac-120">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ระบบ**</span><span class="sxs-lookup"><span data-stu-id="eb2ac-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="eb2ac-121">บนหน้า **ระบบ** เลือกแท็บ **สถานะ**.</span><span class="sxs-lookup"><span data-stu-id="eb2ac-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="eb2ac-122">ในส่วน **แหล่งข้อมูล** ให้เลือก **โฟลว์** และเลือก **สร้างโฟลว์** จากรายการแบบเลื่อนลง</span><span class="sxs-lookup"><span data-stu-id="eb2ac-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eb2ac-123">![ตัวเชื่อมต่อ Power Automate ที่แสดงการสร้างการดำเนินการของโฟลว์](media/power-automate-connector-create-flow.png "ตัวเชื่อมต่อ Power Automate แสดงการสร้างการดำเนินการของโฟลว์")</span><span class="sxs-lookup"><span data-stu-id="eb2ac-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="eb2ac-124">ใน Power Automate เลือกหนึ่งในทริกเกอร์ที่มีอยู่เพื่อสร้างโฟลว์ที่คุณต้องการ</span><span class="sxs-lookup"><span data-stu-id="eb2ac-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="eb2ac-125">หากคุณกำลังสร้างโฟลว์แรก คุณต้องรับรองความถูกต้องด้วยตัวเชื่อมต่อ Power Automate ก่อน</span><span class="sxs-lookup"><span data-stu-id="eb2ac-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
