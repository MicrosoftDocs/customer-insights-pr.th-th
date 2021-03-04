---
title: ตัวเชื่อมต่อ Power BI
description: เรียนรู้วิธีการใช้ตัวเชื่อมต่อ Dynamics 365 Customer Insights ใน Power BI
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477111"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="51a79-103">ตัวเชื่อมต่อสำหรับ Power BI (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="51a79-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="51a79-104">สร้างการจัดรูปแบบการแสดงสำหรับข้อมูลของคุณด้วย Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="51a79-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="51a79-105">สร้างข้อมูลเชิงลึกเพิ่มเติมและสร้างรายงานด้วยข้อมูลลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="51a79-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51a79-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="51a79-106">Prerequisites</span></span>

- <span data-ttu-id="51a79-107">คุณมีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="51a79-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="51a79-108">เวอร์ชันล่าสุดของ [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ถูกติดตั้งบนคอมพิวเตอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="51a79-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="51a79-109">[เรียนรู้เพิ่มเติมเกี่ยวกับ Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="51a79-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="51a79-110">กำหนดค่าตัวเชื่อมต่อสำหรับ Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="51a79-111">ใน Power BI Desktop เลือก **ไฟล์** > **รับข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="51a79-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="51a79-112">เลือก **ดูเพิ่มเติม** และค้นหาสำหรับ **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="51a79-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="51a79-113">เลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="51a79-113">Select **Connect**.</span></span>

1. <span data-ttu-id="51a79-114">**เข้าสู่ระบบ** ด้วยบัญชีองค์กรเดียวกันกับที่คุณใช้สำหรับ Customer Insights และเลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="51a79-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="51a79-115">บัญชีที่คุณระบุในขั้นตอนนี้ใช้เพื่อดึงข้อมูลจาก Customer Insights และไม่จำเป็นต้องเป็นบัญชีเดียวกับที่คุณลงชื่อเข้าใช้ Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="51a79-116">หากต้องการรีเซ็ตบัญชีที่ใช้ในการดึงข้อมูล ให้เปิด Power BI และไปที่ **ไฟล์** > **ตัวเลือก** > **การตั้งค่า** > **การตั้งค่าแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="51a79-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="51a79-117">ในรายการแหล่งข้อมูล เลือก **เข้าสู่ระบบ Dynamics 365 Customer Insights** และเลือก **ล้างสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="51a79-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="51a79-118">ในกล่องโต้ตอบ **ตัวนำทาง**</span><span class="sxs-lookup"><span data-stu-id="51a79-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="51a79-119">คุณจะเห็นรายการสภาพแวดล้อมทั้งหมดที่คุณสามารถเข้าถึงได้</span><span class="sxs-lookup"><span data-stu-id="51a79-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="51a79-120">ขยายสภาพแวดล้อมและเปิดโฟลเดอร์ใดๆ (เอนทิตี, การวัด, เซ็กเมนต์, การเพิ่มข้อมูล)</span><span class="sxs-lookup"><span data-stu-id="51a79-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="51a79-121">ตัวอย่างเช่น เปิดโฟลเดอร์ **เอนทิตี** เพื่อดูเอนทิตีทั้งหมดที่คุณสามารถนำเข้าได้</span><span class="sxs-lookup"><span data-stu-id="51a79-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="51a79-122">![ตัวนำทางตัวเชื่อมต่อ Power BI](media/power-bi-navigator.png "ตัวนำทางตัวเชื่อมต่อ Power BI")</span><span class="sxs-lookup"><span data-stu-id="51a79-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="51a79-123">เลือกช่องทำเครื่องหมายถัดจากเอนทิตีที่จะรวมและ **โหลด**</span><span class="sxs-lookup"><span data-stu-id="51a79-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="51a79-124">คุณสามารถเลือกหลายเอนทิตีจากหลายสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="51a79-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="51a79-125">คุณจะเห็นกล่องโต้ตอบที่กำลังโหลดขณะที่โหลดเอนทิตีของคุณ</span><span class="sxs-lookup"><span data-stu-id="51a79-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="51a79-126">เมื่อโหลดเอนทิตีที่คุณเลือกทั้งหมดแล้ว คุณสามารถใช้ความสามารถของ Power BI เพื่อแสดงภาพข้อมูล</span><span class="sxs-lookup"><span data-stu-id="51a79-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="51a79-127">ชุดข้อมูลขนาดใหญ่</span><span class="sxs-lookup"><span data-stu-id="51a79-127">Large data sets</span></span>

<span data-ttu-id="51a79-128">ตัวเชื่อมต่อ Customer Insights สำหรับ Power BI ได้รับการออกแบบมาเพื่อทำงานกับชุดข้อมูลที่มีโปรไฟล์ลูกค้ามากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="51a79-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="51a79-129">การนำเข้าชุดข้อมูลขนาดใหญ่อาจได้ผล แต่ต้องใช้เวลานาน</span><span class="sxs-lookup"><span data-stu-id="51a79-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="51a79-130">นอกจากนี้ กระบวนการอาจหมดเวลา เนื่องจากข้อจำกัดของ Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="51a79-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [Power BI: คำแนะนำสำหรับชุดข้อมูลขนาดใหญ่](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)</span><span class="sxs-lookup"><span data-stu-id="51a79-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="51a79-132">ทำงานกับชุดข้อมูลย่อย</span><span class="sxs-lookup"><span data-stu-id="51a79-132">Work with a subset of data</span></span>

<span data-ttu-id="51a79-133">ลองทำงานกับชุดย่อยของข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="51a79-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="51a79-134">ตัวอย่างเช่น คุณสามารถสร้าง [เซ็กเมนต์](segments.md) แทนการส่งออกเรกคอร์ดลูกค้าทั้งหมดไปยัง Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="51a79-135">การแก้ไขปัญหา</span><span class="sxs-lookup"><span data-stu-id="51a79-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="51a79-136">สภาพแวดล้อม Customer Insights ไม่ปรากฏใน Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="51a79-137">สภาพแวดล้อมที่มี [ความสัมพันธ์](relationships.md) มากกว่าหนึ่งรายการที่กำหนดระหว่างเอนทิตีที่เหมือนกันสองรายการในข้อมูลเชิงลึกกลุ่มเป้าหมาย จะไม่พร้อมใช้งานในตัวเชื่อมต่อ Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="51a79-138">คุณสามารถระบุและลบความสัมพันธ์ที่ซ้ำกันได้</span><span class="sxs-lookup"><span data-stu-id="51a79-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="51a79-139">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **ความสัมพันธ์** เกี่ยวกับสภาพแวดล้อมที่คุณไม่มีใน Power BI</span><span class="sxs-lookup"><span data-stu-id="51a79-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="51a79-140">ระบุความสัมพันธ์ที่ซ้ำกัน:</span><span class="sxs-lookup"><span data-stu-id="51a79-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="51a79-141">ตรวจสอบว่ามีความสัมพันธ์มากกว่าหนึ่งรายการที่กำหนดระหว่างเอนทิตีสองรายการที่เหมือนกันหรือไม่</span><span class="sxs-lookup"><span data-stu-id="51a79-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="51a79-142">ตรวจสอบว่ามีความสัมพันธ์ที่สร้างขึ้นระหว่างเอนทิตีสองรายการที่ถูกรวมอยู่ในกระบวนการรวมหรือไม่</span><span class="sxs-lookup"><span data-stu-id="51a79-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="51a79-143">มีความสัมพันธ์โดยนัยที่กำหนดไว้ระหว่างเอนทิตีทั้งหมดที่รวมอยู่ในกระบวนการรวม</span><span class="sxs-lookup"><span data-stu-id="51a79-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="51a79-144">ลบความสัมพันธ์ที่ซ้ำกันที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="51a79-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="51a79-145">หลังจากการลบความสัมพันธ์ที่ซ้ำกันออก ให้ลองตั้งค่าคอนฟิกตัวเชื่อมต่อ Power BI อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="51a79-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="51a79-146">สภาพแวดล้อมควรพร้อมใช้งานในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="51a79-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

