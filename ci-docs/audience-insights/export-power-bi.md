---
title: ตัวเชื่อมต่อ Power BI
description: เรียนรู้วิธีการใช้ตัวเชื่อมต่อ Dynamics 365 Customer Insights ใน Power BI
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407123"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="59b7f-103">ตัวเชื่อมต่อสำหรับ Power BI (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="59b7f-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="59b7f-104">สร้างการจัดรูปแบบการแสดงสำหรับข้อมูลของคุณด้วย Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="59b7f-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="59b7f-105">สร้างข้อมูลเชิงลึกเพิ่มเติมและสร้างรายงานด้วยข้อมูลลูกค้าแบบรวมของคุณ</span><span class="sxs-lookup"><span data-stu-id="59b7f-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59b7f-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="59b7f-106">Prerequisites</span></span>

- <span data-ttu-id="59b7f-107">คุณมีโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="59b7f-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="59b7f-108">เวอร์ชันล่าสุดของ [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ถูกติดตั้งบนคอมพิวเตอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="59b7f-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="59b7f-109">[เรียนรู้เพิ่มเติมเกี่ยวกับ Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="59b7f-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="59b7f-110">กำหนดค่าตัวเชื่อมต่อสำหรับ Power BI</span><span class="sxs-lookup"><span data-stu-id="59b7f-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="59b7f-111">ใน Power BI Desktop เลือก **ไฟล์** > **รับข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="59b7f-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="59b7f-112">เลือก **ดูเพิ่มเติม** และค้นหาสำหรับ **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="59b7f-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="59b7f-113">เลือกผลลัพธ์และเลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="59b7f-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="59b7f-114">**เข้าสู่ระบบ** ด้วยบัญชีองค์กรเดียวกันกับที่คุณใช้สำหรับ Customer Insights และเลือก **เชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="59b7f-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="59b7f-115">บัญชีที่คุณระบุในขั้นตอนนี้ใช้เพื่อดึงข้อมูลจาก Customer Insights และไม่จำเป็นต้องเป็นบัญชีเดียวกับที่คุณลงชื่อเข้าใช้ Power BI</span><span class="sxs-lookup"><span data-stu-id="59b7f-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="59b7f-116">หากต้องการรีเซ็ตบัญชีที่ใช้ในการดึงข้อมูล ให้เปิด Power BI และไปที่ **ไฟล์** > **ตัวเลือก** > **การตั้งค่า** > **การตั้งค่าแหล่งข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="59b7f-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="59b7f-117">ในรายการแหล่งข้อมูล เลือก **เข้าสู่ระบบ Dynamics 365 Customer Insights** และเลือก **ล้างสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="59b7f-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="59b7f-118">ในกล่องโต้ตอบ **ตัวนำทาง**</span><span class="sxs-lookup"><span data-stu-id="59b7f-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="59b7f-119">คุณจะเห็นรายการสภาพแวดล้อมทั้งหมดที่คุณสามารถเข้าถึงได้</span><span class="sxs-lookup"><span data-stu-id="59b7f-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="59b7f-120">ขยายสภาพแวดล้อมและเปิดโฟลเดอร์ใดๆ (เอนทิตี, การวัด, เซ็กเมนต์, การเพิ่มข้อมูล)</span><span class="sxs-lookup"><span data-stu-id="59b7f-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="59b7f-121">ตัวอย่างเช่น เปิดโฟลเดอร์ **เอนทิตี** เพื่อดูเอนทิตีทั้งหมดที่คุณสามารถนำเข้าได้</span><span class="sxs-lookup"><span data-stu-id="59b7f-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="59b7f-122">![ตัวนำทางตัวเชื่อมต่อ Power BI](media/power-bi-navigator.png "ตัวนำทางตัวเชื่อมต่อ Power BI")</span><span class="sxs-lookup"><span data-stu-id="59b7f-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="59b7f-123">เลือกช่องทำเครื่องหมายถัดจากเอนทิตีที่จะรวมและ **โหลด**</span><span class="sxs-lookup"><span data-stu-id="59b7f-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="59b7f-124">คุณสามารถเลือกหลายเอนทิตีจากหลายสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="59b7f-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="59b7f-125">คุณจะเห็นกล่องโต้ตอบที่กำลังโหลดขณะที่โหลดเอนทิตีของคุณ</span><span class="sxs-lookup"><span data-stu-id="59b7f-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="59b7f-126">เมื่อโหลดเอนทิตีที่คุณเลือกทั้งหมดแล้ว คุณสามารถใช้ความสามารถของ Power BI เพื่อแสดงภาพข้อมูล</span><span class="sxs-lookup"><span data-stu-id="59b7f-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="59b7f-127">ชุดข้อมูลขนาดใหญ่</span><span class="sxs-lookup"><span data-stu-id="59b7f-127">Large data sets</span></span>

<span data-ttu-id="59b7f-128">ตัวเชื่อมต่อ Customer Insights สำหรับ Power BI ได้รับการออกแบบมาเพื่อทำงานกับชุดข้อมูลที่มีโปรไฟล์ลูกค้ามากถึง 1 ล้านโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="59b7f-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="59b7f-129">การนำเข้าชุดข้อมูลขนาดใหญ่อาจได้ผล แต่ต้องใช้เวลานาน</span><span class="sxs-lookup"><span data-stu-id="59b7f-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="59b7f-130">นอกจากนี้ กระบวนการอาจหมดเวลา เนื่องจากข้อจำกัดของ Power BI</span><span class="sxs-lookup"><span data-stu-id="59b7f-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="59b7f-131">สำหรับข้อมูลเพิ่มเติม โปรดดู [Power BI: คำแนะนำสำหรับชุดข้อมูลขนาดใหญ่](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)</span><span class="sxs-lookup"><span data-stu-id="59b7f-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="59b7f-132">ทำงานกับชุดข้อมูลย่อย</span><span class="sxs-lookup"><span data-stu-id="59b7f-132">Work with a subset of data</span></span>

<span data-ttu-id="59b7f-133">ลองทำงานกับชุดย่อยของข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="59b7f-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="59b7f-134">ตัวอย่างเช่น คุณสามารถสร้าง [เซ็กเมนต์](segments.md) แทนการส่งออกเรกคอร์ดลูกค้าทั้งหมดไปยัง Power BI</span><span class="sxs-lookup"><span data-stu-id="59b7f-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
