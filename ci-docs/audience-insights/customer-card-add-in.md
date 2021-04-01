---
title: ติดตั้งและกำหนดค่า Add-in การ์ดลูกค้า
description: ติดตั้งและตั้งค่าคอนฟิก Add-in การ์ดลูกค้าสำหรับ Dynamics 365 Customer Insights
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597350"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="a735a-103">Add-in การ์ดลูกค้า (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="a735a-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a735a-104">ดูมุมมอง 360 องศาของลูกค้าของคุณโดยตรงในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a735a-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="a735a-105">ดูข้อมูลประชากร ข้อมูลเชิงลึก และกำหนดเส้นเวลากิจกรรมด้วย Add-in ของการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a735a-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a735a-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="a735a-106">Prerequisites</span></span>

- <span data-ttu-id="a735a-107">แอป Dynamics 365 (เช่น ฮับการขายหรือฮับการบริการลูกค้า) เวอร์ชัน 9.0 และใหม่กว่า ซึ่งมีการเปิดใช้งานส่วนติดต่อแบบรวม</span><span class="sxs-lookup"><span data-stu-id="a735a-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="a735a-108">โปรไฟล์ลูกค้า [ที่นำเข้าจากแอป Dynamics 365 โดยใช้ Common Data Service](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="a735a-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="a735a-109">ผู้ใช้ Add-in การ์ดลูกค้าจำเป็นต้อง [เพิ่มเป็นผู้ใช้](permissions.md) ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="a735a-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="a735a-110">[ความสามารถในการค้นหาและตัวกรองที่กำหนดค่าไว้](search-filter-index.md)</span><span class="sxs-lookup"><span data-stu-id="a735a-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="a735a-111">การควบคุมทางประชากร: ฟิลด์ข้อมูลประชากร (เช่น อายุ หรือเพศ) พร้อมใช้งานในโปรไฟล์ลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="a735a-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="a735a-112">การควบคุมการเพิ่มข้อมูล: ต้องมี [การเพิ่มข้อมูล](enrichment-hub.md) ที่ใช้งานได้ นำไปใช้กับโปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a735a-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="a735a-113">การควบคุมระบบอัจฉริยะ: ต้องการข้อมูลที่สร้างโดยใช้ Azure Machine Learning ([การคาดคะเน](predictions.md) หรือ [โดมเดลที่กำหนดเอง](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="a735a-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="a735a-114">การควบคุมการวัด: ต้องการ [การวัดที่กำหนดค่าไว้](measures.md)</span><span class="sxs-lookup"><span data-stu-id="a735a-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="a735a-115">การควบคุมไทม์ไลน์: ต้องการ [กิจกรรมที่กำหนดค่าไว้](activities.md)</span><span class="sxs-lookup"><span data-stu-id="a735a-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="a735a-116">ติดตั้ง Add-in การ์ดลูกค้า.</span><span class="sxs-lookup"><span data-stu-id="a735a-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="a735a-117">Add-in ของการ์ดลูกค้าเป็นโซลูชันสำหรับแอป Customer Engagement ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a735a-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="a735a-118">ในการติดตั้งโซลูชัน ให้ไปที่ AppSource และค้นหา **การ์ดลูกค้า Dynamics**</span><span class="sxs-lookup"><span data-stu-id="a735a-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="a735a-119">เลือก [Add-in การ์ดลูกค้าบน AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) และเลือก **รับทันที**</span><span class="sxs-lookup"><span data-stu-id="a735a-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="a735a-120">คุณอาจต้องลงชื่อเข้าใช้ด้วยข้อมูลประจำตัวของผู้ดูแลระบบของคุณสำหรับแอป Dynamics 365 เพื่อติดตั้งโซลูชัน</span><span class="sxs-lookup"><span data-stu-id="a735a-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="a735a-121">ซึ่งอาจใช้เวลาสักครู่สำหรับการติดตั้งโซลูชันไปยังสภาพแวดล้อมของคุณ</span><span class="sxs-lookup"><span data-stu-id="a735a-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="a735a-122">กำหนดค่า Add-in การ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a735a-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="a735a-123">ในฐานะผู้ดูแลระบบ ให้ไปที่ส่วน **การตั้งค่า** ใน Dynamics 365 และเลือก **โซลูชัน**</span><span class="sxs-lookup"><span data-stu-id="a735a-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="a735a-124">เลือกลิงก์ **ชื่อที่แสดง** สำหรับโซลูชัน **Add-in การ์ดลูกค้า (ดูตัวอย่าง)Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a735a-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a735a-125">![เลือกชื่อที่แสดง](media/select-display-name.png "เลือกชื่อที่แสดง")</span><span class="sxs-lookup"><span data-stu-id="a735a-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="a735a-126">เลือก **เข้าสู่ระบบ** และป้อนข้อมูลรับรองสำหรับบัญชีผู้ดูแลระบบที่คุณใช้เพื่อกำหนดค่า Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a735a-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a735a-127">ตรวจสอบว่าตัวบล็อกป๊อปอัพของเบราว์เซอร์ไม่บล็อกหน้าต่างการรับรองความถูกต้อง เมื่อคุณเลือกปุ่ม **ลงชื่อเข้าใช้**</span><span class="sxs-lookup"><span data-stu-id="a735a-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="a735a-128">เลือกสภาพแวดล้อมที่คุณต้องการดึงข้อมูลมา</span><span class="sxs-lookup"><span data-stu-id="a735a-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="a735a-129">กำหนดว่ามีการแมปฟิลด์ใดกับเรกคอร์ดในแอป Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a735a-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="a735a-130">หากต้องการแม็ปกับผู้ติดต่อ ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีผู้ติดต่อของคุณ</span><span class="sxs-lookup"><span data-stu-id="a735a-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="a735a-131">หากต้องการแม็ปกับลูกค้าองค์กร ให้เลือกฟิลด์ในเอนทิตีลูกค้าที่ตรงกับรหัสเอนทิตีลูกค้าองค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="a735a-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a735a-132">![ฟิลด์รหัสผู้ติดต่อ](media/contact-id-field.png "ฟิลด์รหัสผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="a735a-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="a735a-133">เลือก **บันทึกการตั้งค่าคอนฟิก** เพื่อบันทึกการตั้งค่า</span><span class="sxs-lookup"><span data-stu-id="a735a-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="a735a-134">ถัดไป คุณต้องกำหนดบทบาทความปลอดภัยใน Dynamics 365 เพื่อให้ผู้ใช้สามารถปรับแต่งเองและดูการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a735a-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="a735a-135">ใน Dynamics 365 ให้ไปที่ **การตั้งค่า** > **บทบาทความปลอดภัย** > **ผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="a735a-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="a735a-136">เลือกผู้ใช้เพื่อแก้ไขบทบาทผู้ใช้และเลือก **จัดการบทบาท**</span><span class="sxs-lookup"><span data-stu-id="a735a-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="a735a-137">กำหนดบทบาท **เครื่องมือปรับแต่งการ์ด Customer Insights** ให้กับผู้ใช้ที่จะปรับแต่งเนื้อหาที่แสดงบนการ์ดสำหรับทั้งองค์กร</span><span class="sxs-lookup"><span data-stu-id="a735a-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="a735a-138">เพิ่มการควบคุมการ์ดลูกค้าลงในฟอร์ม</span><span class="sxs-lookup"><span data-stu-id="a735a-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="a735a-139">ในการเพิ่มการควบคุมการ์ดลูกค้าลงในแบบฟอร์มการติดต่อของคุณ ให้ไปที่ **การตั้งค่า** > **การปรับแต่ง** ใน Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a735a-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="a735a-140">เลือก **กำหนดระบบตามความต้องการ**</span><span class="sxs-lookup"><span data-stu-id="a735a-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="a735a-141">เรียกดูเอนทิตี **ผู้ติดต่อ** ขยายเมนู แล้วเลือก **ฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="a735a-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="a735a-142">เลือกฟอร์มผู้ติดต่อที่คุณต้องการเพิ่มตัวควบคุมการ์ดลูกค้า</span><span class="sxs-lookup"><span data-stu-id="a735a-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a735a-143">![เลือกฟอร์มของผู้ติดต่อ](media/contact-active-forms.png "เลือกฟอร์มของผู้ติดต่อ")</span><span class="sxs-lookup"><span data-stu-id="a735a-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="a735a-144">เมื่อต้องการเพิ่มการควบคุม ในตัวแก้ไขฟอร์ม ให้ลากฟิลด์ใดๆ จาก **ส่วนแสดงรายชื่อฟิลด์** ไปยังตำแหน่งที่คุณต้องการให้การควบคุมแสดงขึ้น</span><span class="sxs-lookup"><span data-stu-id="a735a-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="a735a-145">เลือกฟิลด์บนแบบฟอร์มที่คุณเพิ่งเพิ่ม และจากนั้นเลือก **เปลี่ยนคุณสมบัติ**</span><span class="sxs-lookup"><span data-stu-id="a735a-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="a735a-146">ไปที่แท็บ **การควบคุม** และเลือก **เพิ่มการควบคุม**</span><span class="sxs-lookup"><span data-stu-id="a735a-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="a735a-147">เลือกหนึ่งในคอนโทรลแบบกำหนดเองที่มีอยู่ แล้วเลือก **เพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="a735a-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="a735a-148">ในกล่องโต้ตอบ **คุณสมบัติฟิลด์** ให้ล้างกล่องกาเครื่องหมาย **แสดงป้ายชื่อบนฟอร์ม**</span><span class="sxs-lookup"><span data-stu-id="a735a-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="a735a-149">เลือกตัวเลือก **เว็บ** สำหรับการควบคุม</span><span class="sxs-lookup"><span data-stu-id="a735a-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="a735a-150">สำหรับการควบคุมการเพิ่มข้อมูล ให้เลือกประเภทการเพิ่มข้อมูลที่คุณต้องการแสดง โดยการกำหนดค่าฟิลด์ **enrichmentType**</span><span class="sxs-lookup"><span data-stu-id="a735a-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="a735a-151">เพิ่มการควบคุมการเพิ่มที่แยกต่างหากสำหรับการเพิ่มแต่ละชนิด</span><span class="sxs-lookup"><span data-stu-id="a735a-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="a735a-152">เลือก **บันทึก** และ **เผยแพร่** เพื่อเผยแพร่ฟอร์มผู้ติดต่อที่อัปเดต</span><span class="sxs-lookup"><span data-stu-id="a735a-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="a735a-153">ไปที่ฟอร์มผู้ติดต่อที่เผยแพร่แล้ว</span><span class="sxs-lookup"><span data-stu-id="a735a-153">Go to the published contact form.</span></span> <span data-ttu-id="a735a-154">คุณจะเห็นการควบคุมที่เพิ่งเพิ่มเข้ามา</span><span class="sxs-lookup"><span data-stu-id="a735a-154">You'll see the newly added control.</span></span> <span data-ttu-id="a735a-155">คุณอาจต้องลงชื่อเข้าใช้ในครั้งแรกที่คุณใช้งาน</span><span class="sxs-lookup"><span data-stu-id="a735a-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="a735a-156">เมื่อต้องการปรับแต่งสิ่งที่คุณต้องการให้แสดงบนการควบคุมที่กำหนดเอง ให้เลือกปุ่มแก้ไขที่มุมขวาบน</span><span class="sxs-lookup"><span data-stu-id="a735a-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="a735a-157">อัปเกรด Add-in ของ Customer Card</span><span class="sxs-lookup"><span data-stu-id="a735a-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="a735a-158">Add-in ของ Customer Card จะไม่อัปเกรดโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="a735a-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="a735a-159">หากต้องการอัปเกรดเป็นเวอร์ชันล่าสุด ให้ทำตามกระบวนงานนี้ในแอป Dynamics 365 ที่มีการติดตั้ง Add-in</span><span class="sxs-lookup"><span data-stu-id="a735a-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="a735a-160">ในแอป Dynamics 365 ไปที่ **การตั้งค่า** > **การปรับแต่ง** และเลือก **โซลูชัน**</span><span class="sxs-lookup"><span data-stu-id="a735a-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="a735a-161">ในตารางของ Add-in ให้ค้นหา **CustomerInsightsCustomerCard** แล้วเลือกแถว</span><span class="sxs-lookup"><span data-stu-id="a735a-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="a735a-162">เลือก **ใช้การอัปเกรดโซลูชัน** ในแถบการดำเนินการ</span><span class="sxs-lookup"><span data-stu-id="a735a-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="อัปเกรดโซลูชันในพื้นที่การแก้ไข/ปรับปรุงตามคำสั่งของแอป Dynamics 365":::

1. <span data-ttu-id="a735a-164">หลังจากเริ่มกระบวนการอัปเกรด คุณจะเห็นตัวบ่งชี้การโหลดจนกว่าการอัปเกรดจะเสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="a735a-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="a735a-165">หากไม่มีเวอร์ชันที่ใหม่กว่า การอัปเกรดจะแสดงข้อความแสดงข้อผิดพลาด</span><span class="sxs-lookup"><span data-stu-id="a735a-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]