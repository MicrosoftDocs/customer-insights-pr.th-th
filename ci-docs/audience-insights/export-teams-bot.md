---
title: บอทสำหรับ Microsoft Teams
description: ค้นหาโปรไฟล์ลูกค้าแบบรวมใน Microsoft Teams ด้วยความช่วยเหลือของบอท
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267975"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="218b7-103">บอท Teams สำหรับ Dynamics 365 Customer Insights (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="218b7-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="218b7-104">เชื่อมต่อ Microsoft Teams เพื่อให้บอทค้นหาโปรไฟล์ลูกค้าแบบรวมในช่องทาง Teams</span><span class="sxs-lookup"><span data-stu-id="218b7-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="218b7-105">![บอทของ Teams แสดงเรกคอร์ดลูกค้า](media/teams-bot.png "บอทของ Teams แสดงเรกคอร์ดลูกค้า")</span><span class="sxs-lookup"><span data-stu-id="218b7-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="218b7-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="218b7-106">Prerequisites</span></span>

<span data-ttu-id="218b7-107">ในการตั้งค่าและกำหนดค่าบอท ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="218b7-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="218b7-108">มีอย่างน้อยหนึ่ง [แหล่งข้อมูลถูกเพิ่ม](data-sources.md)</span><span class="sxs-lookup"><span data-stu-id="218b7-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="218b7-109">[กระบวนการรวมข้อมูล](data-unification.md) เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="218b7-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="218b7-110">ฟิลด์จะถูกเพิ่มไปยัง [ดัชนีการค้นหาและตัวกรอง](search-filter-index.md)</span><span class="sxs-lookup"><span data-stu-id="218b7-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="218b7-111">Customer Insights และ Teams อยู่ในองค์กรเดียวกัน</span><span class="sxs-lookup"><span data-stu-id="218b7-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="218b7-112">ตั้งค่าคอนฟิกบอท</span><span class="sxs-lookup"><span data-stu-id="218b7-112">Configure the bot</span></span>

1. <span data-ttu-id="218b7-113">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="218b7-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="218b7-114">บนไทล์ Microsoft Teams เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="218b7-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="218b7-115">คุณถูกเปลี่ยนเส้นทางไปยังพื้นที่ **แอป** ใน Teams</span><span class="sxs-lookup"><span data-stu-id="218b7-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="218b7-116">คุณสามารถเปิด Teams และเลือก **แอป** ที่มุมล่างซ้ายหรือ [รับจาก AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="218b7-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="218b7-117">ค้นหา **Customer Insights** และเลือกแอป</span><span class="sxs-lookup"><span data-stu-id="218b7-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="218b7-118">เลือก **เพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="218b7-118">Select **Add**.</span></span>
1. <span data-ttu-id="218b7-119">หลังจากลงชื่อเข้าใช้ Customer Insights ใน Teams คุณจะเห็นข้อความต้อนรับและสามารถเริ่มต้นได้</span><span class="sxs-lookup"><span data-stu-id="218b7-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="218b7-120">สิ่งที่คุณสามารถทำได้ด้วยบอท</span><span class="sxs-lookup"><span data-stu-id="218b7-120">Things you can do with the bot</span></span>

<span data-ttu-id="218b7-121">บอทให้ความสามารถในการค้นหาสำหรับโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="218b7-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="218b7-122">ป้อน **ค้นหา** ตามด้วยชื่อ ที่อยู่อีเมล หรือฟิลด์อื่นๆ ในโปรไฟล์ลูกค้าแบบรวมที่ถูกเพิ่มไปยังดัชนีการค้นหาและตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="218b7-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="218b7-123">คุณจะได้รับบัตรที่มีมากถึง 15 ฟิลด์จากโปรไฟล์ลูกค้าที่เป็นผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="218b7-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="218b7-124">รายการที่ตรงกันหลายรายการส่งคืนรายการผลลัพธ์ที่คุณสามารถเลือกโปรไฟล์ได้</span><span class="sxs-lookup"><span data-stu-id="218b7-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="218b7-125">คุณสามารถเพิ่มคำที่ใช้ค้นหาในเครื่องหมายคำพูดคู่เพื่อค้นหาการจับคู่ที่ตรงกัน</span><span class="sxs-lookup"><span data-stu-id="218b7-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="218b7-126">หากองค์กรของคุณดูแลสภาพแวดล้อม Customer Insights หลายแห่งในองค์กรเดียวกัน คุณสามารถป้อน **switchinstance** เพื่อเลือกว่าสภาพแวดล้อมใดที่คุณต้องการเชื่อมต่อกับบอท</span><span class="sxs-lookup"><span data-stu-id="218b7-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="218b7-127">ป้อน **วิธีใช้** เพื่อดูรายการคำสั่งที่มีสำหรับบอท</span><span class="sxs-lookup"><span data-stu-id="218b7-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]