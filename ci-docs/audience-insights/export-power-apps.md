---
title: ตัวเชื่อมต่อ Power Apps
description: เชื่อมต่อ Power Apps และ Power Automate
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268939"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="64123-103">ตัวเชื่อมต่อ Microsoft Power Apps (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="64123-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="64123-104">นำโปรไฟล์ลูกค้าแบบรวมเข้าไปยังแอปส่วนตัวของคุณด้วย Power Apps</span><span class="sxs-lookup"><span data-stu-id="64123-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="64123-105">เชื่อมต่อ Power Apps และ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="64123-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="64123-106">Customer Insights เป็นหนึ่งในหลายๆ [แหล่งข้อมูลที่มีอยู่ใน Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources)</span><span class="sxs-lookup"><span data-stu-id="64123-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="64123-107">อ้างถึงเอกสาร Power Apps เพื่อเรียนรู้วิธีการ [เพิ่มการเชื่อมต่อข้อมูลไปยังแอป](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)</span><span class="sxs-lookup"><span data-stu-id="64123-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="64123-108">เราขอแนะนำให้คุณตรวจสอบ [Power Apps ใช้การมอบหมายเพื่อจัดการชุดข้อมูลขนาดใหญ่ในแอปพื้นที่ทำงานอย่างไร](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview) ด้วย</span><span class="sxs-lookup"><span data-stu-id="64123-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="64123-109">เอนทิตีที่มี</span><span class="sxs-lookup"><span data-stu-id="64123-109">Available entities</span></span>

<span data-ttu-id="64123-110">หลังจากเพิ่ม Customer Insights เป็นการเชื่อมต่อข้อมูล คุณสามารถเลือกเอนทิตีต่อไปนี้ใน Power Apps:</span><span class="sxs-lookup"><span data-stu-id="64123-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="64123-111">ลูกค้า: เพื่อใช้ข้อมูลจาก [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="64123-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="64123-112">UnifiedActivity: เพื่อแสดง [เส้นเวลากิจกรรม](activities.md) บนแอป</span><span class="sxs-lookup"><span data-stu-id="64123-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="64123-113">ข้อจำกัด</span><span class="sxs-lookup"><span data-stu-id="64123-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="64123-114">เอนทิตีที่ดึงข้อมูลได้</span><span class="sxs-lookup"><span data-stu-id="64123-114">Retrievable entities</span></span>

<span data-ttu-id="64123-115">คุณสามารถดึงข้อมูลเอนทิตี **ลูกค้า** **UnifiedActivity** และ **เซ็กเมนต์** ผ่านตัวเชื่อมต่อ Power Apps</span><span class="sxs-lookup"><span data-stu-id="64123-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="64123-116">เอนทิตีอื่นๆ จะแสดงขึ้น เนื่องจากตัวเชื่อมต่อที่สำคัญรองรับผ่านทริกเกอร์ใน Power Automate</span><span class="sxs-lookup"><span data-stu-id="64123-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="64123-117">การมอบสิทธิ์</span><span class="sxs-lookup"><span data-stu-id="64123-117">Delegation</span></span>

<span data-ttu-id="64123-118">การมอบสิทธิ์ใช้ได้กับเอนทิตีลูกค้าและเอนทิตี UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="64123-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="64123-119">การมอบหมายสำหรับเอนทิตี **ลูกค้า**: การใช้การมอบหมายสำหรับเอนทิตีนี้ จำเป็นต้องมีการจัดทำดัชนีฟิลด์ใน [ค้นหาและกรองดัชนี](search-filter-index.md)</span><span class="sxs-lookup"><span data-stu-id="64123-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="64123-120">การมอบสิทธิ์สำหรับ **UnifiedActivity**: การมอบสิทธิ์สำหรับเอนทิตีนี้ใช้ได้กับฟิลด์ **ActivityId** และ **CustomerId** เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="64123-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="64123-121">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการมอบสิทธิ์ โปรดดู [ฟังก์ชันและการดำเนินการที่มอบสิทธิ์ได้ของ Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)</span><span class="sxs-lookup"><span data-stu-id="64123-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="64123-122">ตัวอย่างการควบคุมแกลเลอรี่</span><span class="sxs-lookup"><span data-stu-id="64123-122">Example gallery control</span></span>

<span data-ttu-id="64123-123">ตัวอย่างเช่น คุณเพิ่มโปรไฟล์ลูกค้าใน [การควบคุมแกลเลอรี](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery)</span><span class="sxs-lookup"><span data-stu-id="64123-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="64123-124">เพิ่มการควบคุม **แกลอรี** ไปยังแอปที่คุณกำลังสร้าง</span><span class="sxs-lookup"><span data-stu-id="64123-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64123-125">![เพิ่มองค์ประกอบของแกลเลอรี](media/connector-powerapps9.png "เพิ่มองค์ประกอบของแกลเลอรี")</span><span class="sxs-lookup"><span data-stu-id="64123-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="64123-126">เลือก **ลูกค้า** เป็นแหล่งข้อมูลสำหรับรายการ</span><span class="sxs-lookup"><span data-stu-id="64123-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64123-127">![เลือกแหล่งข้อมูลหนึ่งแหล่ง](media/choose-datasource-powerapps.png "เลือกแหล่งข้อมูลหนึ่งแหล่ง")</span><span class="sxs-lookup"><span data-stu-id="64123-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="64123-128">คุณสามารถเปลี่ยนแผงข้อมูลทางด้านขวาเพื่อเลือกฟิลด์เอนทิตีลูกค้าที่จะแสดงในแกลเลอรี</span><span class="sxs-lookup"><span data-stu-id="64123-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="64123-129">หากคุณต้องการแสดงฟิลด์ใด ๆ จากลูกค้าที่เลือกในแกลเลอรี่ ให้กรอกคุณสมบัติข้อความของป้ายชื่อ: **{Name_of_the_gallery}.เลือก{property_name}**</span><span class="sxs-lookup"><span data-stu-id="64123-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="64123-130">ตัวอย่าง: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="64123-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="64123-131">ในการแสดงเส้นเวลาแบบรวมสำหรับลูกค้า เพิ่มองค์ประกอบของแกลเลอรีและเพิ่มคุณสมบัติรายการ: **ตัวกรอง('UnifiedActivity' CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="64123-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="64123-132">ตัวอย่าง: ตัวกรอง('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="64123-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]