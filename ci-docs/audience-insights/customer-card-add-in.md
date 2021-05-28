---
title: Add-in การ์ดลูกค้าสำหรับแอป Dynamics 365
description: แสดงข้อมูลจากข้อมูลเชิงลึกของผู้ชมในแอป Dynamics 365 ด้วย Add-in นี้
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059611"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="7ebc4-103">Add-in การ์ดลูกค้า (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="7ebc4-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7ebc4-104">ดูมุมมอง 360 องศาของลูกค้าของคุณโดยตรงในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7ebc4-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="7ebc4-105">เมื่อติดตั้ง Add-in การ์ดลูกค้าในแอป Dynamics 365 ที่รองรับ คุณสามารถเลือกที่จะแสดงข้อมูลประชากร ข้อมูลเชิงลึก และลำดับเวลากิจกรรมได้</span><span class="sxs-lookup"><span data-stu-id="7ebc4-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="7ebc4-106">Add-in จะดึงข้อมูลจาก Customer Insights โดยไม่ส่งผลกระทบต่อข้อมูลในแอป Dynamics 365 ที่เชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7ebc4-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="7ebc4-107">Prerequisites</span></span>

- <span data-ttu-id="7ebc4-108">Add-in ใช้งานได้เฉพาะกับแอปแบบจำลองของ Dynamics 365 เช่น Sales หรือ Customer Service เวอร์ชัน 9.0 และใหม่กว่า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="7ebc4-109">เพื่อให้ข้อมูล Dynamics 365 ของคุณแม็ปกับโปรไฟล์ลูกค้าข้อมูลเชิงลึกของผู้ชมที่จำเป็นต้องถูก [นำเข้าจากแอป Dynamics 365 โดยใช้ตัวเชื่อมต่อ Common Data Service](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="7ebc4-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="7ebc4-110">ผู้ใช้ Dynamics 365 ทั้งหมดของ Add-in การ์ดลูกค้าต้องถูก [เพิ่มเป็นผู้ใช้](permissions.md) ในข้อมูลเชิงลึกของผู้ชม เพื่อดูข้อมูล</span><span class="sxs-lookup"><span data-stu-id="7ebc4-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="7ebc4-111">[ความสามารถในการค้นหาและตัวกรองที่มีการตั้งค่าคอนฟิก](search-filter-index.md) ในข้อมูลเชิงลึกของผู้ชม เป็นสิ่งจำเป็นสำหรับการค้นหาข้อมูลในการทำงาน</span><span class="sxs-lookup"><span data-stu-id="7ebc4-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="7ebc4-112">การควบคุม Add-in แต่ละรายการอาศัยข้อมูลเฉพาะในข้อมูลเชิงลึกของผู้ชม:</span><span class="sxs-lookup"><span data-stu-id="7ebc4-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="7ebc4-113">การควบคุมการวัด: ต้องการ [การวัดที่กำหนดค่าไว้](measures.md)</span><span class="sxs-lookup"><span data-stu-id="7ebc4-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="7ebc4-114">การควบคุมอัจฉริยะ: ต้องการข้อมูลที่สร้างขึ้นโดยใช้ [การคาดคะเน](predictions.md) หรือ [โมเดลที่กำหนดเอง](custom-models.md)</span><span class="sxs-lookup"><span data-stu-id="7ebc4-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="7ebc4-115">การควบคุมทางประชากร: ฟิลด์ข้อมูลประชากร (เช่น อายุ หรือเพศ) พร้อมใช้งานในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="7ebc4-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="7ebc4-116">การควบคุมการเพิ่มข้อมูล: ต้องมี [การเพิ่มข้อมูล](enrichment-hub.md) ที่ใช้งานได้ นำไปใช้กับโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="7ebc4-117">การควบคุมไทม์ไลน์: ต้องการ [กิจกรรมที่กำหนดค่าไว้](activities.md)</span><span class="sxs-lookup"><span data-stu-id="7ebc4-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="7ebc4-118">ติดตั้ง Add-in การ์ดลูกค้า.</span><span class="sxs-lookup"><span data-stu-id="7ebc4-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="7ebc4-119">Add-in ของการ์ดลูกค้าเป็นโซลูชันสำหรับแอป Customer Engagement ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7ebc4-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="7ebc4-120">ในการติดตั้งโซลูชัน ให้ไปที่ AppSource และค้นหา **การ์ดลูกค้า Dynamics**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="7ebc4-121">เลือก [Add-in การ์ดลูกค้าบน AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) และเลือก **รับทันที**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="7ebc4-122">คุณอาจต้องลงชื่อเข้าใช้ด้วยข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับแอป Dynamics 365 เพื่อติดตั้งโซลูชัน</span><span class="sxs-lookup"><span data-stu-id="7ebc4-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="7ebc4-123">ซึ่งอาจใช้เวลาสักครู่สำหรับการติดตั้งโซลูชันไปยังสภาพแวดล้อมของคุณ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="7ebc4-124">กำหนดค่า Add-in การ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="7ebc4-125">ในฐานะผู้ดูแลระบบ ให้ไปที่ส่วน **การตั้งค่า** ใน Dynamics 365 และเลือก **โซลูชัน**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="7ebc4-126">เลือกลิงก์ **ชื่อที่แสดง** สำหรับโซลูชัน **Add-in การ์ดลูกค้า (ดูตัวอย่าง)Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ebc4-127">![เลือกชื่อที่แสดง](media/select-display-name.png "เลือกชื่อที่แสดง")</span><span class="sxs-lookup"><span data-stu-id="7ebc4-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="7ebc4-128">เลือก **เข้าสู่ระบบ** และป้อนข้อมูลรับรองสำหรับบัญชีผู้ดูแลระบบที่คุณใช้เพื่อกำหนดค่า Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7ebc4-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7ebc4-129">ตรวจสอบว่าตัวบล็อกป๊อปอัพของเบราว์เซอร์ไม่บล็อกหน้าต่างการรับรองความถูกต้อง เมื่อคุณเลือกปุ่ม **ลงชื่อเข้าใช้**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="7ebc4-130">เลือกสภาพแวดล้อม Customer Insights ที่คุณต้องการดึงข้อมูลมา</span><span class="sxs-lookup"><span data-stu-id="7ebc4-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="7ebc4-131">กำหนดการแม็ปฟิลด์กับเรกคอร์ดในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7ebc4-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="7ebc4-132">โดยขึ้นอยู่กับข้อมูลของคุณใน Customer Insights คุณสามารถเลือกที่จะแม็ปตัวเลือกต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="7ebc4-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="7ebc4-133">หากต้องการแม็ปกับผู้ติดต่อ ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีผู้ติดต่อของคุณ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="7ebc4-134">หากต้องการแม็ปกับลูกค้าองค์กร ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีลูกค้าองค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ebc4-135">![ฟิลด์รหัสผู้ติดต่อ](media/contact-id-field.png "ฟิลด์รหัสผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="7ebc4-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="7ebc4-136">เลือก **บันทึกการตั้งค่าคอนฟิก** เพื่อบันทึกการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="7ebc4-137">ถัดไป คุณต้องกำหนดบทบาทความปลอดภัยใน Dynamics 365 เพื่อให้ผู้ใช้สามารถปรับแต่งเองและดูการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="7ebc4-138">ใน Dynamics 365 ให้ไปที่ **การตั้งค่า** > **บทบาทความปลอดภัย** > **ผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="7ebc4-139">เลือกผู้ใช้เพื่อแก้ไขบทบาทผู้ใช้และเลือก **จัดการบทบาท**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="7ebc4-140">กำหนดบทบาท **เครื่องมือปรับแต่งการ์ด Customer Insights** ให้กับผู้ใช้ที่จะปรับแต่งเนื้อหาที่แสดงบนการ์ดสำหรับทั้งองค์กร</span><span class="sxs-lookup"><span data-stu-id="7ebc4-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="7ebc4-141">เพิ่มการควบคุมการ์ดลูกค้าลงในฟอร์ม</span><span class="sxs-lookup"><span data-stu-id="7ebc4-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="7ebc4-142">ในการเพิ่มการควบคุมการ์ดลูกค้าลงในแบบฟอร์มการติดต่อของคุณ ให้ไปที่ **การตั้งค่า** > **การปรับแต่ง** ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7ebc4-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="7ebc4-143">เลือก **กำหนดระบบตามความต้องการ**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="7ebc4-144">เรียกดูเอนทิตี **ผู้ติดต่อ** ขยายเมนู แล้วเลือก **ฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="7ebc4-145">เลือกฟอร์มผู้ติดต่อที่คุณต้องการเพิ่มตัวควบคุมการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="7ebc4-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ebc4-146">![เลือกฟอร์มของผู้ติดต่อ](media/contact-active-forms.png "เลือกฟอร์มของผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="7ebc4-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="7ebc4-147">เมื่อต้องการเพิ่มการควบคุม ในตัวแก้ไขฟอร์ม ให้ลากฟิลด์ใดๆ จาก **ส่วนแสดงรายชื่อฟิลด์** ไปยังตำแหน่งที่คุณต้องการให้การควบคุมแสดงขึ้น</span><span class="sxs-lookup"><span data-stu-id="7ebc4-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="7ebc4-148">เลือกฟิลด์บนแบบฟอร์มที่คุณเพิ่งเพิ่ม และจากนั้นเลือก **เปลี่ยนคุณสมบัติ**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="7ebc4-149">ไปที่แท็บ **การควบคุม** และเลือก **เพิ่มการควบคุม**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="7ebc4-150">เลือกหนึ่งในคอนโทรลแบบกำหนดเองที่มีอยู่ แล้วเลือก **เพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="7ebc4-151">ในกล่องโต้ตอบ **คุณสมบัติฟิลด์** ให้ล้างกล่องกาเครื่องหมาย **แสดงป้ายชื่อบนฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="7ebc4-152">เลือกตัวเลือก **เว็บ** สำหรับการควบคุม</span><span class="sxs-lookup"><span data-stu-id="7ebc4-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="7ebc4-153">สำหรับการควบคุมการเพิ่มข้อมูล ให้เลือกประเภทการเพิ่มข้อมูลที่คุณต้องการแสดง โดยการกำหนดค่าฟิลด์ **enrichmentType**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="7ebc4-154">เพิ่มการควบคุมการเพิ่มที่แยกต่างหากสำหรับการเพิ่มแต่ละชนิด</span><span class="sxs-lookup"><span data-stu-id="7ebc4-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="7ebc4-155">เลือก **บันทึก** และ **เผยแพร่** เพื่อเผยแพร่ฟอร์มผู้ติดต่อที่อัปเดต</span><span class="sxs-lookup"><span data-stu-id="7ebc4-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="7ebc4-156">ไปที่ฟอร์มผู้ติดต่อที่เผยแพร่แล้ว</span><span class="sxs-lookup"><span data-stu-id="7ebc4-156">Go to the published contact form.</span></span> <span data-ttu-id="7ebc4-157">คุณจะเห็นการควบคุมที่เพิ่งเพิ่มเข้ามา</span><span class="sxs-lookup"><span data-stu-id="7ebc4-157">You'll see the newly added control.</span></span> <span data-ttu-id="7ebc4-158">คุณอาจต้องลงชื่อเข้าใช้ในครั้งแรกที่คุณใช้งาน</span><span class="sxs-lookup"><span data-stu-id="7ebc4-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="7ebc4-159">เมื่อต้องการปรับแต่งสิ่งที่คุณต้องการให้แสดงบนการควบคุมที่กำหนดเอง ให้เลือกปุ่มแก้ไขที่มุมขวาบน</span><span class="sxs-lookup"><span data-stu-id="7ebc4-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="7ebc4-160">อัปเกรด Add-in ของ Customer Card</span><span class="sxs-lookup"><span data-stu-id="7ebc4-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="7ebc4-161">Add-in ของ Customer Card จะไม่อัปเกรดโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="7ebc4-162">หากต้องการอัปเกรดเป็นเวอร์ชันล่าสุด ให้ทำตามกระบวนงานนี้ในแอป Dynamics 365 ที่มีการติดตั้ง Add-in</span><span class="sxs-lookup"><span data-stu-id="7ebc4-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="7ebc4-163">ในแอป Dynamics 365 ไปที่ **การตั้งค่า** > **การปรับแต่ง** และเลือก **โซลูชัน**</span><span class="sxs-lookup"><span data-stu-id="7ebc4-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="7ebc4-164">ในตารางของ Add-in ให้ค้นหา **CustomerInsightsCustomerCard** แล้วเลือกแถว</span><span class="sxs-lookup"><span data-stu-id="7ebc4-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="7ebc4-165">เลือก **ใช้การอัปเกรดโซลูชัน** ในแถบการดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="7ebc4-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="อัปเกรดโซลูชันในพื้นที่การแก้ไข/ปรับปรุงตามคำสั่งของแอป Dynamics 365":::

1. <span data-ttu-id="7ebc4-167">หลังจากเริ่มกระบวนการอัปเกรด คุณจะเห็นตัวบ่งชี้การโหลดจนกว่าการอัปเกรดจะเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="7ebc4-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="7ebc4-168">หากไม่มีเวอร์ชันที่ใหม่กว่า การอัปเกรดจะแสดงข้อความแสดงข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="7ebc4-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
