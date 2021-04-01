---
title: ทำงานกับ API
description: ใช้ API และทำความเข้าใจข้อจำกัด
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710483"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8acc1-103">ทำงานกับ Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="8acc1-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8acc1-104">Dynamics 365 Customer Insights เตรียม API เพื่อสร้างแอปพลิเคชันของคุณเองโดยใช้ข้อมูลของคุณใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8acc1-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8acc1-105">รายละเอียดของ API เหล่านี้แสดงอยู่ใน [ข้อมูลอ้างอิง Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)</span><span class="sxs-lookup"><span data-stu-id="8acc1-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8acc1-106">รวมถึงข้อมูลเพิ่มเติมเกี่ยวกับการดำเนินงาน พารามิเตอร์และการตอบสนอง</span><span class="sxs-lookup"><span data-stu-id="8acc1-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8acc1-107">บทความนี้แนะนำให้คุณเข้าถึง Customer Insights API, สร้างการลงทะเบียนแอป Azure และช่วยคุณเริ่มต้นใช้งานไลบรารีไคลเอ็นต์ที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="8acc1-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8acc1-108">เริ่มต้นใช้งาน Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="8acc1-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8acc1-109">[ลงชื่อเข้าใช้](https://home.ci.ai.dynamics.com) Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8acc1-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8acc1-110">หากคุณยังไม่ได้สมัครใช้งาน [ลงชื่อเข้าใช้ Customer Insights รุ่นทดลองใช้](https://aka.ms/tryci)</span><span class="sxs-lookup"><span data-stu-id="8acc1-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8acc1-111">หากต้องการเปิดใช้ API ในสภาพแวดล้อม Customer Insights ของคุณ ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="8acc1-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8acc1-112">คุณต้องมีสิทธิ์ระดับผู้ดูแลระบบจึงจะทำได้</span><span class="sxs-lookup"><span data-stu-id="8acc1-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8acc1-113">ไปที่แท็บ **API** และเลือกปุ่ม **เปิดใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="8acc1-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="8acc1-114">การเปิดใช้งาน API จะสร้างคีย์การสมัครใช้งานหลักและรองสำหรับอินสแตนซ์ของคุณที่จะใช้ในคำขอ API</span><span class="sxs-lookup"><span data-stu-id="8acc1-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8acc1-115">คุณสามารถสร้างคีย์ใหม่ได้โดยการเลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่** ใน **ผู้ดูแลระบบ** > **สิทธิ์** > **API**</span><span class="sxs-lookup"><span data-stu-id="8acc1-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="เปิดใช้งาน Customer Insights API":::

1. <span data-ttu-id="8acc1-117">เลือก **สำรวจ API ของเรา** เพื่อ [ทดลองใช้ API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)</span><span class="sxs-lookup"><span data-stu-id="8acc1-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="8acc1-118">เลือกการดำเนินงานของ API และเลือก **ลองใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="8acc1-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8acc1-119">ในบานหน้าต่างด้านข้าง ตั้งค่าในเมนูแบบเลื่อนลง **การอนุญาต** ไปที่ **ทางอ้อม**</span><span class="sxs-lookup"><span data-stu-id="8acc1-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="8acc1-120">ส่วนหัว `Authorization` ได้รับพร้อมกับโทเค็นแบบแบเรอร์ที่เพิ่ม</span><span class="sxs-lookup"><span data-stu-id="8acc1-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="8acc1-121">คีย์การสมัครใช้งานของคุณจะมีการเติมข้อมูลโดยอัตโนมัติ</span><span class="sxs-lookup"><span data-stu-id="8acc1-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8acc1-122">เพิ่มพารามิเตอร์การสอบถามที่จำเป็นทั้งหมดหรือไม่ก็ได้</span><span class="sxs-lookup"><span data-stu-id="8acc1-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8acc1-123">เลื่อนไปที่ด้านล่างสุดของบานหน้าต่างด้านข้าง แล้วเลือก **ส่ง**</span><span class="sxs-lookup"><span data-stu-id="8acc1-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8acc1-124">การตอบสนอง HTTP จะปรากฏด้านล่างในไม่ช้า</span><span class="sxs-lookup"><span data-stu-id="8acc1-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="gif แบบเคลื่อนไหวที่แสดงวิธีการเลือกทดสอบ API":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8acc1-126">สร้างการลงทะเบียนแอปใหม่ในพอร์ทัล Azure</span><span class="sxs-lookup"><span data-stu-id="8acc1-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8acc1-127">ขั้นตอนเหล่านี้ช่วยให้คุณเริ่มต้นใช้งาน Customer Insights API ในแอปพลิเคชัน Azure โดยใช้สิทธิ์ที่ได้รับมอบหมาย</span><span class="sxs-lookup"><span data-stu-id="8acc1-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8acc1-128">ตรวจสอบให้แน่ใจว่า [ส่วนเริ่มต้นใช้งาน](#get-started-trying-the-customer-insights-apis) เสร็จสมบูรณ์ก่อน</span><span class="sxs-lookup"><span data-stu-id="8acc1-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8acc1-129">ลงชื่อเข้าใช้ [พอร์ทัล Azure](https://portal.azure.com) ด้วยบัญชีที่สามารถเข้าถึงข้อมูล Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8acc1-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8acc1-130">ทางด้านซ้าย ให้เลือก **การลงทะเบียนแอป**</span><span class="sxs-lookup"><span data-stu-id="8acc1-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8acc1-131">เลือก **การลงทะเบียนใหม่** ระบุชื่อแอปพลิเคชันและเลือกชนิดบัญชี</span><span class="sxs-lookup"><span data-stu-id="8acc1-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="8acc1-132">หรือเพิ่ม URL การเปลี่ยนเส้นทางก็ได้</span><span class="sxs-lookup"><span data-stu-id="8acc1-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8acc1-133">http://localhost เพียงพอสำหรับการพัฒนาแอปพลิเคชันบนคอมพิวเตอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="8acc1-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8acc1-134">ในการลงทะเบียนแอปใหม่ของคุณ ให้ไปที่ **สิทธิ์ API**</span><span class="sxs-lookup"><span data-stu-id="8acc1-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="gif แบบเคลื่อนไหวเพื่อตั้งค่าสิทธิ์ API ในการลงทะเบียนแอป":::

1. <span data-ttu-id="8acc1-136">เลือก **เพิ่มสิทธิ์** และเลือก **Customer Insights** ในบานหน้าต่างด้านข้าง</span><span class="sxs-lookup"><span data-stu-id="8acc1-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8acc1-137">สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ที่ได้รับมอบหมาย** และเลือกสิทธิ์ **user_impersonation**</span><span class="sxs-lookup"><span data-stu-id="8acc1-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8acc1-138">เลือก **เพิ่มสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="8acc1-138">Select **Add permissions**.</span></span> <span data-ttu-id="8acc1-139">หากคุณต้องการเข้าถึง API โดยไม่มีการลงชื่อเข้าใช้ของผู้ใช้ ให้ดูที่ส่วน [สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์](#server-to-server-application-permissions)</span><span class="sxs-lookup"><span data-stu-id="8acc1-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8acc1-140">เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="8acc1-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8acc1-141">คุณสามารถใช้รหัสแอปพลิเคชัน/ไคลเอ็นต์สำหรับการลงทะเบียนแอปนี้กับ Microsoft Authentication Library (MSAL) เพื่อรับโทเค็นแบบแบเรอร์ที่จะส่งคำขอของคุณไปยัง API</span><span class="sxs-lookup"><span data-stu-id="8acc1-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="gif แบบเคลื่อนไหวเพื่อให้ความยินยอมของผู้ดูแลระบบ":::

<span data-ttu-id="8acc1-143">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ MSAL โปรดดู [ภาพรวมของ Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)</span><span class="sxs-lookup"><span data-stu-id="8acc1-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8acc1-144">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการลงทะเบียนแอปใน Azure โปรดดู [ประสบการณ์การลงทะเบียนแอปในพอร์ทัล Azure ใหม่](/azure/active-directory/develop/app-registration-portal-training-guide)</span><span class="sxs-lookup"><span data-stu-id="8acc1-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="8acc1-145">สำหรับข้อมูลเกี่ยวกับการใช้ API ไลบรารีไคลเอ็นต์ของเรา โปรดดู [ไลบรารีไคลเอ็นต์ Customer Insights](#customer-insights-client-libraries)</span><span class="sxs-lookup"><span data-stu-id="8acc1-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8acc1-146">สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์</span><span class="sxs-lookup"><span data-stu-id="8acc1-146">Server-to-server application permissions</span></span>

<span data-ttu-id="8acc1-147">[ส่วนการลงทะเบียนแอป](#create-a-new-app-registration-in-the-azure-portal) สรุปวิธีการลงทะเบียนแอปที่ต้องให้ผู้ใช้ลงชื่อเข้าใช้เพื่อการรับรองความถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="8acc1-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8acc1-148">เรียนรู้วิธีสร้างการลงทะเบียนแอปที่ไม่จำเป็นต้องมีการโต้ตอบกับผู้ใช้และสามารถเรียกใช้บนเซิร์ฟเวอร์ได้</span><span class="sxs-lookup"><span data-stu-id="8acc1-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8acc1-149">การลงทะเบียนแอปของคุณในพอร์ทัล Azure ให้ไปที่ **สิทธิ์ API**</span><span class="sxs-lookup"><span data-stu-id="8acc1-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8acc1-150">เลือก **เพิ่มสิทธิ์** และเลือก **Customer Insights** ในบานหน้าต่างด้านข้าง</span><span class="sxs-lookup"><span data-stu-id="8acc1-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8acc1-151">สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ของแอปพลิเคชัน** และเลือกสิทธิ์ **CustomerInsights.Api.All**</span><span class="sxs-lookup"><span data-stu-id="8acc1-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8acc1-152">เลือก **เพิ่มสิทธิ์**</span><span class="sxs-lookup"><span data-stu-id="8acc1-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8acc1-153">การให้ความยินยอมของผู้ดูแลระบบเกี่ยวกับสิทธิ์ของแอปพลิเคชันนี้ คุณต้องเพิ่มบริการหลัก</span><span class="sxs-lookup"><span data-stu-id="8acc1-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="8acc1-154">ติดตั้งโมดูล Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="8acc1-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="8acc1-155">เชื่อมต่อกับบัญชี AD ของคุณ: `Connect-AzureAD -TenantId <your tenant id>`</span><span class="sxs-lookup"><span data-stu-id="8acc1-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="8acc1-156">คุณสามารถค้นหารหัสผู้เช่าของคุณได้ที่ **ภาพรวม** > **Azure Active Directory**</span><span class="sxs-lookup"><span data-stu-id="8acc1-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="8acc1-157">รันคำสั่งต่อไปนี้เพื่อเพิ่มบริการหลัก Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` พารามิเตอร์ AppId เกี่ยวข้องกับแอป Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="8acc1-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="ตัวอย่างบริการหลัก":::

1. <span data-ttu-id="8acc1-159">กลับไปที่ **สิทธิ์ API** สำหรับการลงทะเบียนแอปของคุณ</span><span class="sxs-lookup"><span data-stu-id="8acc1-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8acc1-160">เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="8acc1-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="gif แบบเคลื่อนไหวเพื่อให้ความยินยอมของผู้ดูแลระบบ":::

1. <span data-ttu-id="8acc1-162">สรุปได้ว่าเราต้องเพิ่มชื่อการลงทะเบียนแอปเป็นผู้ใช้ใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8acc1-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="8acc1-163">เปิด Customer Insights ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์** และเลือก **เพิ่มผู้ใช้**</span><span class="sxs-lookup"><span data-stu-id="8acc1-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8acc1-164">ค้นหาชื่อการลงทะเบียนแอปของคุณ เลือกจากผลการค้นหาและเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="8acc1-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8acc1-165">ไลบรารีไคลเอ็นต์ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8acc1-165">Customer Insights client libraries</span></span>

<span data-ttu-id="8acc1-166">ส่วนนี้ช่วยให้คุณเริ่มต้นใช้งานไลบรารีไคลเอ็นต์ที่มีอยู่สำหรับ Customer Insights API ได้</span><span class="sxs-lookup"><span data-stu-id="8acc1-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="8acc1-167">ซอร์สโค้ดไลบรารีทั้งหมดและแอปพลิเคชันตัวอย่างสามารถดูได้ใน [เพจ Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)</span><span class="sxs-lookup"><span data-stu-id="8acc1-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="8acc1-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8acc1-168">C# NuGet</span></span>

<span data-ttu-id="8acc1-169">เรียนรู้วิธีเริ่มต้นใช้งานไลบรารีไคลเอ็นต์ C# จาก NuGet.org สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแพคเกจ NuGet โปรดดู [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)</span><span class="sxs-lookup"><span data-stu-id="8acc1-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8acc1-170">ปัจจุบัน แพคเกจนี้กำหนดเป้าหมายเป็นเฟรมเวิร์ก netstandard2.0 และ netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="8acc1-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8acc1-171">เพิ่มไลบรารีไคลเอ็นต์ C# ในโครงการ C#</span><span class="sxs-lookup"><span data-stu-id="8acc1-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8acc1-172">ใน Visual Studio ให้เปิด **ตัวจัดการแพคเกจ NuGet** สำหรับโครงการของคุณ</span><span class="sxs-lookup"><span data-stu-id="8acc1-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8acc1-173">ค้นหา **Microsoft.Dynamics.CustomerInsights.Api**</span><span class="sxs-lookup"><span data-stu-id="8acc1-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8acc1-174">เลือก **ติดตั้ง** เพื่อเพิ่มแพคเกจลงในโครงการ</span><span class="sxs-lookup"><span data-stu-id="8acc1-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="8acc1-175">หรือรันคำสั่งนี้ใน **คอนโซลตัวจัดการแพคเกจ NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8acc1-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="เพิ่มแพคเกจ NuGet ในโครงการ Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8acc1-177">ใช้ไลบรารีไคลเอ็นต์ C#</span><span class="sxs-lookup"><span data-stu-id="8acc1-177">Use the C# client library</span></span>

1. <span data-ttu-id="8acc1-178">ใช้ [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) เพื่อรับ `AccessToken` โดยใช้ [การลงทะเบียนแอป Azure](#create-a-new-app-registration-in-the-azure-portal) ที่คุณมีอยู่</span><span class="sxs-lookup"><span data-stu-id="8acc1-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8acc1-179">หลังจากการรับรองความถูกต้องและรับโทเค็นสำเร็จแล้ว ให้สร้าง `HttpClient` ใหม่หรือใช้ที่มีอยู่โดยตั้งค่า **DefaultRequestHeaders "การอนุญาต"** เป็น **<access token> แบบแบเรอร์** และ **Ocp-Apim-Subscription-Key** ตั้งค่าเป็น [**คีย์การสมัครใช้งาน** จากสภาพแวดล้อม Customer Insights ของคุณ](#get-started-trying-the-customer-insights-apis)</span><span class="sxs-lookup"><span data-stu-id="8acc1-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="8acc1-180">รีเซ็ตส่วนหัว **การอนุญาต** ตามความเหมาะสม</span><span class="sxs-lookup"><span data-stu-id="8acc1-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8acc1-181">ตัวอย่างเช่น เมื่อโทเค็นหมดอายุ</span><span class="sxs-lookup"><span data-stu-id="8acc1-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="8acc1-182">ส่งผ่าน `HttpClient` นี้ในโครงสร้างของไคลเอ็นต์ `CustomerInsights`</span><span class="sxs-lookup"><span data-stu-id="8acc1-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="ตัวอย่างของ httpclient":::

1. <span data-ttu-id="8acc1-184">ทำการเรียกไคลเอ็นต์ด้วย "วิธีการขยาย" ตัวอย่างเช่น `GetAllInstancesAsync`</span><span class="sxs-lookup"><span data-stu-id="8acc1-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8acc1-185">หากการเข้าถึง `Microsoft.Rest.HttpOperationResponse` พื้นฐานเป็นวิธีที่ต้องการ ให้ใช้ "วิธีการข้อความ http" ตัวอย่างเช่น `GetAllInstancesWithHttpMessagesAsync`</span><span class="sxs-lookup"><span data-stu-id="8acc1-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8acc1-186">การตอบสนองน่าจะเป็นชนิด `object` เนื่องจากวิธีการดังกล่าวสามารถส่งคืนได้หลายชนิด (ตัวอย่างเช่น `IList<InstanceInfo>` และ `ApiErrorResult`)</span><span class="sxs-lookup"><span data-stu-id="8acc1-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8acc1-187">การตรวจสอบชนิดการส่งคืน คุณสามารถแปลงออบเจ็กต์เป็นชนิดการตอบสนองที่ระบุไว้ใน [เพจรายละเอียด API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) สำหรับการดำเนินงานนั้นได้อย่างปลอดภัย</span><span class="sxs-lookup"><span data-stu-id="8acc1-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="8acc1-188">หากต้องการข้อมูลเพิ่มเติมเกี่ยวกับคำขอที่ต้องการ ให้ใช้ **วิธีการข้อความ http** เพื่อเข้าถึงออบเจ็กต์การตอบสนองแบบข้อมูลดิบ</span><span class="sxs-lookup"><span data-stu-id="8acc1-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="8acc1-189">แพคเกจ NodeJS</span><span class="sxs-lookup"><span data-stu-id="8acc1-189">NodeJS package</span></span>

<span data-ttu-id="8acc1-190">ใช้ไลบรารีไคลเอ็นต์ NodeJS ที่มีให้ผ่าน NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="8acc1-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="8acc1-191">แพคเกจ Python</span><span class="sxs-lookup"><span data-stu-id="8acc1-191">Python package</span></span>

<span data-ttu-id="8acc1-192">ใช้ไลบรารีไคลเอ็นต์ Python ที่มีให้ผ่าน PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="8acc1-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
