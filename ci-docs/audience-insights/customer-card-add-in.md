---
title: ติดตั้งและกำหนดค่า Add-in การ์ดลูกค้า
description: ติดตั้งและตั้งค่าคอนฟิก Add-in การ์ดลูกค้าสำหรับ Dynamics 365 Customer Insights
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644066"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="15123-103">Add-in การ์ดลูกค้า (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="15123-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="15123-104">ดูมุมมอง 360 องศาของลูกค้าของคุณโดยตรงในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15123-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="15123-105">ดูข้อมูลประชากร ข้อมูลเชิงลึก และกำหนดเส้นเวลากิจกรรมด้วย Add-in ของการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="15123-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15123-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="15123-106">Prerequisites</span></span>

- <span data-ttu-id="15123-107">แอป Dynamics 365 (เช่น ฮับการขายหรือฮับการบริการลูกค้า) เวอร์ชัน 9.0 และใหม่กว่า ซึ่งมีการเปิดใช้งานส่วนติดต่อแบบรวม</span><span class="sxs-lookup"><span data-stu-id="15123-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="15123-108">โปรไฟล์ลูกค้า [ที่นำเข้าจากแอป Dynamics 365 โดยใช้ Common Data Service](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="15123-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="15123-109">ผู้ใช้ Add-in การ์ดลูกค้าจำเป็นต้อง [เพิ่มเป็นผู้ใช้](permissions.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="15123-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="15123-110">[ความสามารถในการค้นหาและตัวกรองที่กำหนดค่าไว้](search-filter-index.md)</span><span class="sxs-lookup"><span data-stu-id="15123-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="15123-111">การควบคุมข้อมูลพื้นฐาน: ฟิลด์ข้อมูลพื้นฐาน เช่น อายุหรือเพศมีอยู่ในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="15123-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="15123-112">การควบคุมการเพิ่มข้อมูล: ต้องมี [การเพิ่มข้อมูล](enrichment-hub.md) ที่ใช้งานได้ นำไปใช้กับโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="15123-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="15123-113">การควบคุมระบบอัจฉริยะ: ต้องการข้อมูลที่สร้างโดยใช้ Azure Machine Learning ([การคาดคะเน](predictions.md) หรือ [โดมเดลที่กำหนดเอง](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="15123-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="15123-114">การควบคุมการวัด: ต้องการ [การวัดที่กำหนดค่าไว้](measures.md)</span><span class="sxs-lookup"><span data-stu-id="15123-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="15123-115">การควบคุมไทม์ไลน์: ต้องการ [กิจกรรมที่กำหนดค่าไว้](activities.md)</span><span class="sxs-lookup"><span data-stu-id="15123-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="15123-116">ติดตั้ง Add-in การ์ดลูกค้า.</span><span class="sxs-lookup"><span data-stu-id="15123-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="15123-117">Add-in ของการ์ดลูกค้าเป็นโซลูชันสำหรับแอป Customer Engagement ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15123-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="15123-118">ในการติดตั้งโซลูชัน ให้ไปที่ AppSource และค้นหา **การ์ดลูกค้า Dynamics**</span><span class="sxs-lookup"><span data-stu-id="15123-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="15123-119">เลือก [Add-in การ์ดลูกค้าบน AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) และเลือก **รับทันที**</span><span class="sxs-lookup"><span data-stu-id="15123-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="15123-120">คุณอาจต้องลงชื่อเข้าใช้ด้วยข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับแอป Dynamics 365 เพื่อติดตั้งโซลูชัน</span><span class="sxs-lookup"><span data-stu-id="15123-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="15123-121">ซึ่งอาจใช้เวลาสักครู่สำหรับการติดตั้งโซลูชันไปยังสภาพแวดล้อมของคุณ</span><span class="sxs-lookup"><span data-stu-id="15123-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="15123-122">กำหนดค่า Add-in การ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="15123-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="15123-123">ในฐานะผู้ดูแลระบบ ให้ไปที่ส่วน **การตั้งค่า** ใน Dynamics 365 และเลือก **โซลูชัน**</span><span class="sxs-lookup"><span data-stu-id="15123-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="15123-124">เลือกลิงก์ **ชื่อที่แสดง** สำหรับโซลูชัน **Add-in การ์ดลูกค้า (ดูตัวอย่าง)Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="15123-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15123-125">![เลือกชื่อที่แสดง](media/select-display-name.png "เลือกชื่อที่แสดง")</span><span class="sxs-lookup"><span data-stu-id="15123-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="15123-126">เลือก **เข้าสู่ระบบ** และป้อนข้อมูลรับรองสำหรับบัญชีผู้ดูแลระบบที่คุณใช้เพื่อกำหนดค่า Customer Insights</span><span class="sxs-lookup"><span data-stu-id="15123-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="15123-127">ตรวจสอบว่าตัวบล็อกป๊อปอัพของเบราว์เซอร์ไม่บล็อกหน้าต่างการรับรองความถูกต้อง เมื่อคุณเลือกปุ่ม **ลงชื่อเข้าใช้**</span><span class="sxs-lookup"><span data-stu-id="15123-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="15123-128">เลือกสภาพแวดล้อมที่คุณต้องการดึงข้อมูลมา</span><span class="sxs-lookup"><span data-stu-id="15123-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="15123-129">กำหนดว่ามีการแมปฟิลด์ใดกับเรกคอร์ดในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15123-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="15123-130">หากต้องการแม็ปกับผู้ติดต่อ ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีผู้ติดต่อของคุณ</span><span class="sxs-lookup"><span data-stu-id="15123-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="15123-131">หากต้องการแม็ปกับลูกค้าองค์กร ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีลูกค้าองค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="15123-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15123-132">![ฟิลด์รหัสผู้ติดต่อ](media/contact-id-field.png "ฟิลด์รหัสผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="15123-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="15123-133">เลือก **บันทึกการตั้งค่าคอนฟิก** เพื่อบันทึกการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="15123-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="15123-134">ถัดไป คุณต้องกำหนดบทบาทความปลอดภัยใน Dynamics 365 เพื่อให้ผู้ใช้สามารถปรับแต่งเองและดูการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="15123-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="15123-135">ใน Dynamics 365 ให้ไปที่ **การตั้งค่า** > **บทบาทความปลอดภัย** > **ผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="15123-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="15123-136">เลือกผู้ใช้เพื่อแก้ไขบทบาทผู้ใช้และเลือก **จัดการบทบาท**</span><span class="sxs-lookup"><span data-stu-id="15123-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="15123-137">กำหนดบทบาท **เครื่องมือปรับแต่งการ์ด Customer Insights** ให้กับผู้ใช้ที่จะปรับแต่งเนื้อหาที่แสดงบนการ์ดสำหรับทั้งองค์กร</span><span class="sxs-lookup"><span data-stu-id="15123-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="15123-138">เพิ่มการควบคุมการ์ดลูกค้าลงในฟอร์ม</span><span class="sxs-lookup"><span data-stu-id="15123-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="15123-139">ในการเพิ่มการควบคุมการ์ดลูกค้าลงในแบบฟอร์มการติดต่อของคุณ ให้ไปที่ **การตั้งค่า** > **การปรับแต่ง** ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15123-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="15123-140">เลือก **กำหนดระบบตามความต้องการ**</span><span class="sxs-lookup"><span data-stu-id="15123-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="15123-141">เรียกดูเอนทิตี **ผู้ติดต่อ** ขยายเมนู แล้วเลือก **ฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="15123-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="15123-142">เลือกฟอร์มผู้ติดต่อที่คุณต้องการเพิ่มตัวควบคุมการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="15123-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="15123-143">![เลือกฟอร์มของผู้ติดต่อ](media/contact-active-forms.png "เลือกฟอร์มของผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="15123-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="15123-144">เมื่อต้องการเพิ่มการควบคุม ในตัวแก้ไขฟอร์ม ให้ลากฟิลด์ใดๆ จาก **ส่วนแสดงรายชื่อฟิลด์** ไปยังตำแหน่งที่คุณต้องการให้การควบคุมแสดงขึ้น</span><span class="sxs-lookup"><span data-stu-id="15123-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="15123-145">เลือกฟิลด์บนแบบฟอร์มที่คุณเพิ่งเพิ่ม และจากนั้นเลือก **เปลี่ยนคุณสมบัติ**</span><span class="sxs-lookup"><span data-stu-id="15123-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="15123-146">ไปที่แท็บ **การควบคุม** และเลือก **เพิ่มการควบคุม**</span><span class="sxs-lookup"><span data-stu-id="15123-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="15123-147">เลือกหนึ่งในคอนโทรลแบบกำหนดเองที่มีอยู่ แล้วเลือก **เพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="15123-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="15123-148">ในกล่องโต้ตอบ **คุณสมบัติฟิลด์** ให้ล้างกล่องกาเครื่องหมาย **แสดงป้ายชื่อบนฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="15123-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="15123-149">เลือกตัวเลือก **เว็บ** สำหรับการควบคุม</span><span class="sxs-lookup"><span data-stu-id="15123-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="15123-150">สำหรับการควบคุมการเพิ่มข้อมูล ให้เลือกประเภทการเพิ่มข้อมูลที่คุณต้องการแสดง โดยการกำหนดค่าฟิลด์ **enrichmentType**</span><span class="sxs-lookup"><span data-stu-id="15123-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="15123-151">คุณจำเป็นต้องเพิ่มการควบคุมการเพิ่มข้อมูลแบบแยกสำหรับแต่ละประเภทการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="15123-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="15123-152">เลือก **บันทึก** และ **เผยแพร่** เพื่อเผยแพร่ฟอร์มผู้ติดต่อที่อัปเดต</span><span class="sxs-lookup"><span data-stu-id="15123-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="15123-153">ไปที่ฟอร์มผู้ติดต่อที่เผยแพร่แล้ว</span><span class="sxs-lookup"><span data-stu-id="15123-153">Go to the published contact form.</span></span> <span data-ttu-id="15123-154">คุณจะเห็นการควบคุมที่เพิ่งเพิ่มเข้ามา</span><span class="sxs-lookup"><span data-stu-id="15123-154">You'll see the newly added control.</span></span> <span data-ttu-id="15123-155">คุณอาจต้องลงชื่อเข้าใช้ในครั้งแรกที่คุณใช้งาน</span><span class="sxs-lookup"><span data-stu-id="15123-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="15123-156">เมื่อต้องการปรับแต่งสิ่งที่คุณต้องการให้แสดงบนการควบคุมที่กำหนดเอง ให้เลือกปุ่มแก้ไขที่มุมขวาบน</span><span class="sxs-lookup"><span data-stu-id="15123-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
