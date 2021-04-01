---
title: ตัวเชื่อมต่อ Power BI
description: เรียนรู้วิธีการใช้ตัวเชื่อมต่อ Dynamics 365 Customer Insights ใน Power BI
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596062"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="ac20c-103">ตัวเชื่อมต่อสำหรับ Power BI (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="ac20c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="ac20c-104">สร้างการจัดรูปแบบการแสดงสำหรับข้อมูลของคุณด้วย Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="ac20c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="ac20c-105">สร้างข้อมูลเชิงลึกเพิ่มเติมและสร้างรายงานด้วยข้อมูลลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="ac20c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac20c-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="ac20c-106">Prerequisites</span></span>

- <span data-ttu-id="ac20c-107">คุณมีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="ac20c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="ac20c-108">รุ่นล่าสุดของ [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ติดตั้งอยู่บนคอมพิวเตอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="ac20c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="ac20c-109">[เรียนรู้เพิ่มเติมเกี่ยวกับ Power BI Desktop](/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="ac20c-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="ac20c-110">กำหนดค่าตัวเชื่อมต่อสำหรับ Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="ac20c-111">ใน Power BI Desktop เลือก **ไฟล์** > **รับข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="ac20c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="ac20c-112">เลือก **ดูเพิ่มเติม** และค้นหาสำหรับ **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="ac20c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="ac20c-113">เลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="ac20c-113">Select **Connect**.</span></span>

1. <span data-ttu-id="ac20c-114">**เข้าสู่ระบบ** ด้วยบัญชีองค์กรเดียวกันกับที่คุณใช้สำหรับ Customer Insights และเลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="ac20c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ac20c-115">บัญชีที่คุณระบุในขั้นตอนนี้ใช้เพื่อดึงข้อมูลจาก Customer Insights และไม่จำเป็นต้องเป็นบัญชีเดียวกับที่คุณลงชื่อเข้าใช้ Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="ac20c-116">หากต้องการรีเซ็ตบัญชีที่ใช้ในการดึงข้อมูล ให้เปิด Power BI และไปที่ **ไฟล์** > **ตัวเลือก** > **การตั้งค่า** > **การตั้งค่าแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="ac20c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="ac20c-117">ในรายการแหล่งข้อมูล เลือก **เข้าสู่ระบบ Dynamics 365 Customer Insights** และเลือก **ล้างสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="ac20c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="ac20c-118">ในกล่องโต้ตอบ **ตัวนำทาง**</span><span class="sxs-lookup"><span data-stu-id="ac20c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="ac20c-119">คุณจะเห็นรายการสภาพแวดล้อมทั้งหมดที่คุณสามารถเข้าถึงได้</span><span class="sxs-lookup"><span data-stu-id="ac20c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="ac20c-120">ขยายสภาพแวดล้อมและเปิดโฟลเดอร์ใดๆ (เอนทิตี, การวัด, เซ็กเมนต์, การเพิ่มข้อมูล)</span><span class="sxs-lookup"><span data-stu-id="ac20c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="ac20c-121">ตัวอย่างเช่น เปิดโฟลเดอร์ **เอนทิตี** เพื่อดูเอนทิตีทั้งหมดที่คุณสามารถนำเข้าได้</span><span class="sxs-lookup"><span data-stu-id="ac20c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="ac20c-122">![ตัวนำทางตัวเชื่อมต่อ Power BI](media/power-bi-navigator.png "ตัวนำทางตัวเชื่อมต่อ Power BI")</span><span class="sxs-lookup"><span data-stu-id="ac20c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="ac20c-123">เลือกช่องทำเครื่องหมายถัดจากเอนทิตีที่จะรวมและ **โหลด**</span><span class="sxs-lookup"><span data-stu-id="ac20c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="ac20c-124">คุณสามารถเลือกหลายเอนทิตีจากหลายสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="ac20c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="ac20c-125">คุณจะเห็นกล่องโต้ตอบที่กำลังโหลดขณะที่โหลดเอนทิตีของคุณ</span><span class="sxs-lookup"><span data-stu-id="ac20c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="ac20c-126">เมื่อโหลดเอนทิตีที่คุณเลือกทั้งหมดแล้ว คุณสามารถใช้ความสามารถของ Power BI เพื่อแสดงภาพข้อมูล</span><span class="sxs-lookup"><span data-stu-id="ac20c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="ac20c-127">ชุดข้อมูลขนาดใหญ่</span><span class="sxs-lookup"><span data-stu-id="ac20c-127">Large data sets</span></span>

<span data-ttu-id="ac20c-128">ตัวเชื่อมต่อ Customer Insights สำหรับ Power BI ได้รับการออกแบบมาเพื่อทำงานกับชุดข้อมูลที่มีโปรไฟล์ลูกค้ามากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="ac20c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="ac20c-129">การนำเข้าชุดข้อมูลขนาดใหญ่อาจได้ผล แต่ต้องใช้เวลานาน</span><span class="sxs-lookup"><span data-stu-id="ac20c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="ac20c-130">นอกจากนี้ กระบวนการอาจหมดเวลา เนื่องจากข้อจำกัดของ Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="ac20c-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [Power BI: คำแนะนำสำหรับชุดข้อมูลขนาดใหญ่](/power-bi/admin/service-premium-what-is#large-datasets)</span><span class="sxs-lookup"><span data-stu-id="ac20c-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="ac20c-132">ทำงานกับชุดข้อมูลย่อย</span><span class="sxs-lookup"><span data-stu-id="ac20c-132">Work with a subset of data</span></span>

<span data-ttu-id="ac20c-133">ลองทำงานกับชุดย่อยของข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="ac20c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="ac20c-134">ตัวอย่างเช่น คุณสามารถสร้าง [เซ็กเมนต์](segments.md) แทนการส่งออกเรกคอร์ดลูกค้าทั้งหมดไปยัง Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ac20c-135">การแก้ไขปัญหา</span><span class="sxs-lookup"><span data-stu-id="ac20c-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="ac20c-136">สภาพแวดล้อม Customer Insights ไม่ปรากฏใน Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="ac20c-137">สภาพแวดล้อมที่มี [ความสัมพันธ์](relationships.md) มากกว่าหนึ่งรายการที่กำหนดระหว่างเอนทิตีที่เหมือนกันสองรายการในข้อมูลเชิงลึกกลุ่มเป้าหมาย จะไม่พร้อมใช้งานในตัวเชื่อมต่อ Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="ac20c-138">คุณสามารถระบุและลบความสัมพันธ์ที่ซ้ำกันได้</span><span class="sxs-lookup"><span data-stu-id="ac20c-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="ac20c-139">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **ความสัมพันธ์** เกี่ยวกับสภาพแวดล้อมที่คุณไม่มีใน Power BI</span><span class="sxs-lookup"><span data-stu-id="ac20c-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="ac20c-140">ระบุความสัมพันธ์ที่ซ้ำกัน:</span><span class="sxs-lookup"><span data-stu-id="ac20c-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="ac20c-141">ตรวจสอบว่ามีความสัมพันธ์มากกว่าหนึ่งรายการที่กำหนดระหว่างเอนทิตีสองรายการที่เหมือนกันหรือไม่</span><span class="sxs-lookup"><span data-stu-id="ac20c-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="ac20c-142">ตรวจสอบว่ามีความสัมพันธ์ที่สร้างขึ้นระหว่างเอนทิตีสองรายการที่ถูกรวมอยู่ในกระบวนการรวมหรือไม่</span><span class="sxs-lookup"><span data-stu-id="ac20c-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="ac20c-143">มีความสัมพันธ์โดยนัยที่กำหนดไว้ระหว่างเอนทิตีทั้งหมดที่รวมอยู่ในกระบวนการรวม</span><span class="sxs-lookup"><span data-stu-id="ac20c-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="ac20c-144">ลบความสัมพันธ์ที่ซ้ำกันที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="ac20c-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="ac20c-145">หลังจากการลบความสัมพันธ์ที่ซ้ำกันออก ให้ลองตั้งค่าคอนฟิกตัวเชื่อมต่อ Power BI อีกครั้ง</span><span class="sxs-lookup"><span data-stu-id="ac20c-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="ac20c-146">สภาพแวดล้อมควรพร้อมใช้งานในขณะนี้</span><span class="sxs-lookup"><span data-stu-id="ac20c-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]