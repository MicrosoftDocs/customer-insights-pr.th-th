---
title: เชื่อมต่อกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลัก
description: ใช้บริการหลักของ Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อเชื่อมต่อกับที่จัดเก็บข้อมูลดิบของคุณเองเมื่อเชื่อมต่อกับข้อมูลเชิงลึกกลุ่มเป้าหมาย
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644111"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d9304-103">เชื่อมต่อกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลัก Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="d9304-104">เครื่องมืออัตโนมัติที่ใช้บริการ Azure ควรมีสิทธิ์ที่จำกัดไว้เสมอ</span><span class="sxs-lookup"><span data-stu-id="d9304-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="d9304-105">แทนที่จะให้แอปพลิเคชันลงชื่อเข้าใช้ในฐานะผู้ใช้ที่มีสิทธิ์การใช้งานแบบเต็ม Azure จะเสนอบริการหลัก</span><span class="sxs-lookup"><span data-stu-id="d9304-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="d9304-106">อ่านต่อเพื่อเรียนรู้วิธีเชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 โดยใช้บริการหลักของ Azure แทนคีย์บัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="d9304-107">คุณสามารถใช้บริการหลักเพื่อ [เพิ่มหรือแก้ไขโฟลเดอร์ Common Data Model เป็นแหล่งข้อมูล](connect-common-data-model.md) ได้อย่างปลอดภัยหรือ [สร้างใหม่หรือปรับปรุงสภาพแวดล้อมที่มีอยู่](manage-environments.md#create-an-environment-in-an-existing-organization)</span><span class="sxs-lookup"><span data-stu-id="d9304-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="d9304-108">คุณต้องมีสิทธิ์ระดับผู้ดูแลระบบสำหรับการสมัครใช้งาน Azure ของคุณเพื่อสร้างบริการหลัก</span><span class="sxs-lookup"><span data-stu-id="d9304-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d9304-109">สร้างบริการหลักของ Azure สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="d9304-110">ก่อนสร้างบริการหลักใหม่สำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ตรวจสอบว่ามีอยู่แล้วในองค์กรของคุณหรือไม่</span><span class="sxs-lookup"><span data-stu-id="d9304-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="d9304-111">มองหาบริการหลักที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="d9304-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="d9304-112">ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="d9304-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="d9304-113">เลือก **Azure Active Directory** จากบริการ Azure</span><span class="sxs-lookup"><span data-stu-id="d9304-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="d9304-114">ภายใต้ **จัดการ** เลือก **แอปพลิเคชัน Enterprise**</span><span class="sxs-lookup"><span data-stu-id="d9304-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="d9304-115">ค้นหารหัสแอปพลิเคชันบุคคลที่หนึ่ง `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` หรือชื่อ `Dynamics 365 AI for Customer Insights` ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="d9304-116">หากคุณพบเรกคอร์ดที่ตรงกัน แสดงว่ามีบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="d9304-117">คุณไม่ต้องสร้างอีก</span><span class="sxs-lookup"><span data-stu-id="d9304-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="ภาพหน้าจอที่แสดบริการหลักที่มีอยู่":::
   
6. <span data-ttu-id="d9304-119">หากไม่มีการส่งคืนผลลัพธ์ ให้สร้างบริการหลักใหม่</span><span class="sxs-lookup"><span data-stu-id="d9304-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="d9304-120">สร้างบริการหลักใหม่</span><span class="sxs-lookup"><span data-stu-id="d9304-120">Create a new service principal</span></span>

1. <span data-ttu-id="d9304-121">ติดตั้งเวอร์ชันล่าสุดของ **Azure Active Directory PowerShell สำหรับกราฟ**</span><span class="sxs-lookup"><span data-stu-id="d9304-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="d9304-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [ติดตั้ง Azure Active Directory PowerShell สำหรับกราฟ](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)</span><span class="sxs-lookup"><span data-stu-id="d9304-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="d9304-123">บนพีซีของคุณ ให้เลือกแป้น Windows บนแป้นพิมพ์ของคุณและค้นหา **Windows PowerShell** และ **เรียกใช้ในฐานะผู้ดูแลระบบ**</span><span class="sxs-lookup"><span data-stu-id="d9304-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="d9304-124">ในหน้าต่าง PowerShell ที่เปิดขึ้น ให้ป้อน `Install-Module AzureAD`</span><span class="sxs-lookup"><span data-stu-id="d9304-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="d9304-125">สร้างบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายด้วยโมดูล Azure AD PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9304-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="d9304-126">ในหน้าต่าง PowerShell ให้ป้อน `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`</span><span class="sxs-lookup"><span data-stu-id="d9304-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="d9304-127">แทนที่ "รหัสผู้เช่าของคุณ" ด้วยรหัสจริงของผู้เช่าของคุณที่คุณต้องการสร้างบริการหลัก</span><span class="sxs-lookup"><span data-stu-id="d9304-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="d9304-128">พารามิเตอร์ชื่อสภาพแวดล้อม `AzureEnvironmentName` เป็นตัวเลือก</span><span class="sxs-lookup"><span data-stu-id="d9304-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="d9304-129">ป้อน `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`</span><span class="sxs-lookup"><span data-stu-id="d9304-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="d9304-130">คำสั่งนี้สร้างบริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเกี่ยวกับผู้เช่าที่เลือก</span><span class="sxs-lookup"><span data-stu-id="d9304-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="d9304-131">ให้สิทธิ์แก่บริการหลักในการเข้าถึงบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="d9304-132">ไปที่พอร์ทัล Azure เพื่อให้สิทธิ์แก่บริการหลักสำหรับบัญชีที่เก็บข้อมูลที่คุณต้องการใช้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="d9304-133">ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) และลงชื่อเข้าใช้องค์กรของคุณ</span><span class="sxs-lookup"><span data-stu-id="d9304-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="d9304-134">เปิดบัญชีที่เก็บข้อมูลที่คุณต้องการให้บริการหลักสำหรับข้อมูลเชิงลึกกลุ่มเป้าหมายเข้าถึงได้</span><span class="sxs-lookup"><span data-stu-id="d9304-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="d9304-135">เลือก **การควบคุมการเข้าถึง (IAM)** จากบานหน้าต่างนำทาง แล้วเลือก **เพิ่ม** > **เพิ่มการกำหนดบทบาท**</span><span class="sxs-lookup"><span data-stu-id="d9304-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ภาพหน้าจอที่แสดงพอร์ทัล Azure ขณะที่เพิ่มการกำหนดบทบาท":::
   
1. <span data-ttu-id="d9304-137">ในบานหน้าต่าง **เพิ่มการกำหนดบทบาท** ให้ตั้งค่าคุณสมบัติต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="d9304-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="d9304-138">บทบาท: *ผู้สนับสนุนข้อมูล Blob ของการจัดเก็บ*</span><span class="sxs-lookup"><span data-stu-id="d9304-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="d9304-139">กำหนดการเข้าถึง: *ผู้ใช้,กลุ่ม หรือบริการหลัก*</span><span class="sxs-lookup"><span data-stu-id="d9304-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="d9304-140">เลือก: *Dynamics 365 AI for Customer Insights* ([บริการหลักที่คุณสร้างขึ้น](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="d9304-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="d9304-141">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="d9304-141">Select **Save**.</span></span>

<span data-ttu-id="d9304-142">โดยอาจใช้เวลาถึง 15 นาทีในการเผยแพร่การเปลี่ยนแปลง</span><span class="sxs-lookup"><span data-stu-id="d9304-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="d9304-143">ป้อนรหัสทรัพยากร Azure หรือรายละเอียดการสมัครใช้งาน Azure ในสิ่งที่แนบมากับบัญชีที่เก็บข้อมูลกับข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="d9304-144">แนบบัญชีที่เก็บข้อมูล Azure Data Lake ในข้อมูลเชิงลึกกลุ่มเป้าหมาย เพื่อ [จัดเก็บข้อมูลผลลัพธ์](manage-environments.md) หรือ [ใช้เป็นแหล่งข้อมูล](connect-common-data-service-lake.md)</span><span class="sxs-lookup"><span data-stu-id="d9304-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="d9304-145">การเลือกตัวเลือก Azure Data Lake ช่วยให้คุณสามารถเลือกได้ระหว่างแนวทางที่อิงตามทรัพยากรหรือตามการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="d9304-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="d9304-146">ทำตามขั้นตอนด้านล่างเพื่อให้ข้อมูลที่จำเป็นเกี่ยวกับแนวทางที่เลือก</span><span class="sxs-lookup"><span data-stu-id="d9304-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="d9304-147">การเชื่อมต่อบัญชีที่เก็บข้อมูลตามทรัพยากร</span><span class="sxs-lookup"><span data-stu-id="d9304-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="d9304-148">ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณและเปิดบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d9304-149">ไปที่ **การตั้งค่า** > **คุณสมบัติ** บนบานหน้าต่างนำทาง</span><span class="sxs-lookup"><span data-stu-id="d9304-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d9304-150">คัดลอกค่ารหัสทรัพยากรบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="คัดลอกรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::

1. <span data-ttu-id="d9304-152">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ใส่รหัสทรัพยากรในฟิลด์ทรัพยากรที่แสดงในหน้าจอการเชื่อมต่อบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::   
   
1. <span data-ttu-id="d9304-154">ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="d9304-155">การเชื่อมต่อบัญชีที่เก็บข้อมูลตามการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="d9304-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="d9304-156">ไปที่ [พอร์ทัลผู้ดูแลระบบ Azure](https://portal.azure.com) ลงชื่อเข้าใช้การสมัครใช้งานของคุณและเปิดบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d9304-157">ไปที่ **การตั้งค่า** > **คุณสมบัติ** บนบานหน้าต่างนำทาง</span><span class="sxs-lookup"><span data-stu-id="d9304-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d9304-158">ตรวจสอบ **การสมัครใช้งาน**, **กลุ่มทรัพยากร** และ **ชื่อ** ของบัญชีที่เก็บข้อมูล เพื่อให้แน่ใจว่าคุณเลือกค่าที่ถูกต้องในข้อมูลเชิงลึกกลุ่มเป้าหมาย</span><span class="sxs-lookup"><span data-stu-id="d9304-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="d9304-159">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้เลือกค่าหรือสำหรับฟิลด์ที่เกี่ยวข้องเมื่อแนบบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="ป้อนข้อมูลรหัสทรัพยากรบัญชีที่เก็บข้อมูล":::
   
1. <span data-ttu-id="d9304-161">ทำตามขั้นตอนที่เหลือในข้อมูลเชิงลึกกลุ่มเป้าหมายเพื่อแนบบัญชีที่เก็บข้อมูล</span><span class="sxs-lookup"><span data-stu-id="d9304-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
