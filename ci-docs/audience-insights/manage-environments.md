---
title: สร้างและจัดการสภาพแวดล้อม
description: เรียนรู้วิธีการลงทะเบียนสำหรับบริการและวิธีจัดการสภาพแวดล้อม
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304903"
---
# <a name="manage-environments"></a><span data-ttu-id="62f96-103">จัดการสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="62f96-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="62f96-104">บทความนี้อธิบายถึงวิธีการสร้างองค์กรใหม่และวิธีการจัดเตรียมสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="62f96-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="62f96-105">ลงทะเบียนและสร้างองค์กร</span><span class="sxs-lookup"><span data-stu-id="62f96-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="62f96-106">ไปยังเว็บไซต์ [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)</span><span class="sxs-lookup"><span data-stu-id="62f96-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="62f96-107">เลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="62f96-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="62f96-108">เลือกสถานการณ์การสมัครที่คุณต้องการและเลือกลิงก์ที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="62f96-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="62f96-109">ยอมรับข้อกำหนดและเงื่อนไข และเลือก **ดำเนินการต่อ** เพื่อเริ่มสร้างองค์กร</span><span class="sxs-lookup"><span data-stu-id="62f96-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="62f96-110">หลังจากสร้างสภาพแวดล้อมแล้ว ระบบจะเปลี่ยนเส้นทางไปที่ [Customer Insights](https://home.ci.ai.dynamics.com)</span><span class="sxs-lookup"><span data-stu-id="62f96-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="62f96-111">ใช้สภาพแวดล้อมการสาธิตเพื่อสำรวจแอป หรือสร้างสภาพแวดล้อมใหม่โดยทำตามขั้นตอนในส่วนถัดไป</span><span class="sxs-lookup"><span data-stu-id="62f96-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="62f96-112">หลังจากระบุการตั้งค่าสภาพแวดล้อม ให้เลือก **สร้าง**</span><span class="sxs-lookup"><span data-stu-id="62f96-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="62f96-113">คุณจะลงชื่อเข้าใช้หลังจากสร้างสภาพแวดล้อมสำเร็จแล้ว</span><span class="sxs-lookup"><span data-stu-id="62f96-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="62f96-114">สร้างสภาพแวดล้อมในองค์กรที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="62f96-115">มีสองวิธีในการสร้างสภาพแวดล้อมใหม่:</span><span class="sxs-lookup"><span data-stu-id="62f96-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="62f96-116">คุณสามารถระบุการตั้งค่าคอนฟิกใหม่ทั้งหมด หรือคุณสามารถคัดลอกการตั้งค่าของการตั้งค่าคอนฟิกบางรายการจากสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="62f96-117">องค์กรสามารถสร้าง *สอง* สภาพแวดล้อมสำหรับสิทธิ์การใช้งาน Customer Insights ทั้งหมด</span><span class="sxs-lookup"><span data-stu-id="62f96-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="62f96-118">หากองค์กรของคุณซื้อสิทธิ์การใช้งานมากกว่าหนึ่งครั้ง โปรด [ติดต่อทีมสนับสนุนของเรา](https://go.microsoft.com/fwlink/?linkid=2079641) เพื่อเพิ่มจำนวนสภาพแวดล้อมที่พร้อมใช้งาน</span><span class="sxs-lookup"><span data-stu-id="62f96-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="62f96-119">สำหรับข้อมูลเพิ่มเติมเกี่ยวกับความจุและความจุส่วนเสริม ดาวน์โหลด [คู่มือการให้สิทธิ์การใช้งาน Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544)</span><span class="sxs-lookup"><span data-stu-id="62f96-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="62f96-120">เพื่อสร้างสภาพแวดล้อม:</span><span class="sxs-lookup"><span data-stu-id="62f96-120">To create an environment:</span></span>

1. <span data-ttu-id="62f96-121">เลือกตัวเลือก **สภาพแวดล้อม** ในส่วนหัวของแอป</span><span class="sxs-lookup"><span data-stu-id="62f96-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="62f96-122">เลือก **สร้าง**</span><span class="sxs-lookup"><span data-stu-id="62f96-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="62f96-123">![การตั้งค่าสภาพแวดล้อม](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="62f96-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="62f96-124">ในกล่องโต้ตอบ **สร้างสภาพแวดล้อม** เลือก **สภาพแวดล้อมใหม่**</span><span class="sxs-lookup"><span data-stu-id="62f96-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="62f96-125">ถ้าคุณต้องการ [คัดลอกข้อมูลจากสภาพแวดล้อมปัจจุบัน](#considerations-for-copy-configuration-preview) เลือก **คัดลอกจากสภาพแวดล้อมที่มีอยู่**</span><span class="sxs-lookup"><span data-stu-id="62f96-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="62f96-126">คุณจะเห็นรายการของสภาพแวดล้อมที่พร้อมใช้งานทั้งหมดในองค์กรของคุณ ที่ซึ่งคุณสามารถคัดลอกข้อมูลได้</span><span class="sxs-lookup"><span data-stu-id="62f96-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="62f96-127">ให้รายละเอียดต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="62f96-127">Provide the following details:</span></span>
   - <span data-ttu-id="62f96-128">**ชื่อ**: ชื่อสำหรับสภาพแวดล้อมนี้</span><span class="sxs-lookup"><span data-stu-id="62f96-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="62f96-129">ฟิลด์นี้ถูกกรอกข้อมูลเรียบร้อยแล้ว หากคุณได้คัดลอกสภาพแวดล้อมที่มีอยู่ แต่คุณสามารถเปลี่ยนแปลงได้</span><span class="sxs-lookup"><span data-stu-id="62f96-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="62f96-130">**ชนิด**: เลือกว่าคุณต้องการสร้างสภาพแวดล้อมการผลิตหรือ Sandbox</span><span class="sxs-lookup"><span data-stu-id="62f96-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="62f96-131">**ภูมิภาค**: ภูมิภาคที่มีการปรับใช้และที่เป็นโฮสต์บริการ</span><span class="sxs-lookup"><span data-stu-id="62f96-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="62f96-132">อีกทางเลือกหนึ่ง คุณสามารถเลือก **การตั้งค่าขั้นสูง**:</span><span class="sxs-lookup"><span data-stu-id="62f96-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="62f96-133">**บันทึกข้อมูลทั้งหมดไปที่**: ระบุตำแหน่งที่คุณต้องการจัดเก็บข้อมูลเอาต์พุตที่สร้างจาก Customer Insights</span><span class="sxs-lookup"><span data-stu-id="62f96-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="62f96-134">คุณจะมีสองตัวเลือก: **ที่เก็บข้อมูล Customer Insights** (Azure Data Lake ที่จัดการโดยทีม Customer Insights) และ **Azure Data Lake Storage** (Azure Data Lake Storage ของคุณเอง)</span><span class="sxs-lookup"><span data-stu-id="62f96-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="62f96-135">ตามค่าเริ่มต้น ตัวเลือกที่เก็บข้อมูล Customer Insights จะถูกเลือก</span><span class="sxs-lookup"><span data-stu-id="62f96-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="62f96-136">การบันทึกข้อมูลใน Azure Data Lake Storage หมายถึงคุณยอมรับว่าข้อมูลจะมีการถ่ายโอนไปและเก็บไว้ในที่ตั้งทางภูมิศาสตร์ที่เหมาะสมสำหรับบัญชีที่เก็บข้อมูล Azure ซึ่งอาจแตกต่างจากที่ตั้งที่เก็บข้อมูลใน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="62f96-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="62f96-137">เรียนรู้เพิ่มเติมที่ Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="62f96-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="62f96-138">ปัจจุบัน เอนทิตีที่ถูกนำมาใช้จะถูกเก็บไว้ใน Data Lake ที่มีการจัดการของ Customer Insights เสมอ</span><span class="sxs-lookup"><span data-stu-id="62f96-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="62f96-139">เราสนับสนุนบัญชี Azure Data Lake Storage จากภูมิภาค Azure เดียวกันกับที่คุณเลือกเมื่อสร้างสภาพแวดล้อมเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="62f96-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="62f96-140">เราสนับสนุนบัญชี Azure Data Lake Storage ที่เปิดใช้งานเนมสเปซตามลำดับชั้นเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="62f96-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="62f96-141">สำหรับตัวเลือก Azure Data Lake Storage คุณสามารถเลือกระหว่างตัวเลือกตามทรัพยากรและตัวเลือกตามการสมัครใช้งานสำหรับการรับรองความถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="62f96-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="62f96-142">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="62f96-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="62f96-143">ไม่สามารถเปลี่ยนชื่อ **คอนเทนเนอร์** ได้ และจะเป็น `customerinsights`</span><span class="sxs-lookup"><span data-stu-id="62f96-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="62f96-144">หากคุณต้องการใช้ [การคาดคะเน](predictions.md) ตั้งค่าคอนฟิกการแบ่งปันข้อมูลกับ Microsoft Dataverse หรือเปิดใช้งานการนำเข้าข้อมูลจากแหล่งข้อมูลภายในองค์กร ให้ระบุ URL สภาพแวดล้อม Microsoft Dataverse ภายใต้ **ตั้งค่าคอนฟิกการแบ่งปันข้อมูลกับ Microsoft Dataverse และเปิดใช้งานความสามารถเพิ่มเติม**</span><span class="sxs-lookup"><span data-stu-id="62f96-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="62f96-145">เลือก **เปิดใช้งานการแชร์ข้อมูล** เพื่อแชร์ข้อมูลผลลัพธ์ Customer Insights กับ Microsoft Dataverse Data Lake แบบจัดการได้</span><span class="sxs-lookup"><span data-stu-id="62f96-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="62f96-146">ขณะนี้ การแชร์ข้อมูลกับ Microsoft Dataverse Data Lake แบบจัดการได้ ไม่รองรับ เมื่อคุณบันทึกข้อมูลทั้งหมดไปยัง Azure Data Lake Storage ของคุณเอง</span><span class="sxs-lookup"><span data-stu-id="62f96-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="62f96-147">[การคาดการณ์ของค่าที่ขาดหายไปในเอนทิตี](predictions.md) ขณะนี้ยังไม่รองรับ เมื่อคุณเปิดใช้งานการแชร์ข้อมูลกับ Microsoft Dataverse Data Lake แบบจัดการได้</span><span class="sxs-lookup"><span data-stu-id="62f96-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="62f96-148">![ตัวเลือกการกำหนดค่าเพื่อเปิดใช้งานการแบ่งปันข้อมูลกับ Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="62f96-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="62f96-149">เมื่อคุณเรียกใช้กระบวนการ เช่น การนำเข้าข้อมูลหรือการสร้างกเซ็กเมนต์ จะมีการสร้างโฟลเดอร์ที่เกี่ยวข้องขึ้นในบัญชีที่เก็บข้อมูลที่คุณระบุไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="62f96-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="62f96-150">ไฟล์ข้อมูลและไฟล์ model.json จะถูกสร้างและเพิ่มลงในโฟลเดอร์ตามชื่อกระบวนการ</span><span class="sxs-lookup"><span data-stu-id="62f96-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="62f96-151">หากคุณสร้างสภาพแวดล้อมของ Customer Insights หลาย ๆ รายการและเลือกที่จะบันทึกเอนทิตีผลลัพธ์จากสภาพแวดล้อมเหล่านั้นในบัญชีที่เก็บข้อมูลของคุณ จะมีการสร้างโฟลเดอร์แยกต่างหากขึ้นสำหรับแต่ละสภาพแวดล้อมด้วย ci_<environmentid> ในคอนเทนเนอร์</span><span class="sxs-lookup"><span data-stu-id="62f96-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="62f96-152">ข้อควรพิจารณาสำหรับการกำหนดค่าการคัดลอก (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="62f96-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="62f96-153">การตั้งค่าการกำหนดค่าต่อไปนี้จะถูกคัดลอก:</span><span class="sxs-lookup"><span data-stu-id="62f96-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="62f96-154">การตั้งค่าคอนฟิกคุณลักษณะ</span><span class="sxs-lookup"><span data-stu-id="62f96-154">Feature configurations</span></span>
- <span data-ttu-id="62f96-155">แหล่งข้อมูลที่ รับเข้า/นำเข้า</span><span class="sxs-lookup"><span data-stu-id="62f96-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="62f96-156">การตั้งค่าคอนฟิกการรวมข้อมูล (แม็ป จับคู่ ผสาน)</span><span class="sxs-lookup"><span data-stu-id="62f96-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="62f96-157">เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="62f96-157">Segments</span></span>
- <span data-ttu-id="62f96-158">การวัด</span><span class="sxs-lookup"><span data-stu-id="62f96-158">Measures</span></span>
- <span data-ttu-id="62f96-159">ความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="62f96-159">Relationships</span></span>
- <span data-ttu-id="62f96-160">กิจกรรม</span><span class="sxs-lookup"><span data-stu-id="62f96-160">Activities</span></span>
- <span data-ttu-id="62f96-161">ดัชนีการค้นหาและตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="62f96-161">Search & filter Index</span></span>
- <span data-ttu-id="62f96-162">ปลายทางการส่งออก</span><span class="sxs-lookup"><span data-stu-id="62f96-162">Export destinations</span></span>
- <span data-ttu-id="62f96-163">การรีเฟรชที่มีการจัดกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="62f96-163">Scheduled refresh</span></span>
- <span data-ttu-id="62f96-164">การเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="62f96-164">Enrichments</span></span>
- <span data-ttu-id="62f96-165">การจัดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="62f96-165">Model management</span></span>
- <span data-ttu-id="62f96-166">การกำหนดบทบาท</span><span class="sxs-lookup"><span data-stu-id="62f96-166">Role assignments</span></span>

<span data-ttu-id="62f96-167">การตั้งค่าต่อไปนี้จะ *ไม่* ถูกคัดลอก:</span><span class="sxs-lookup"><span data-stu-id="62f96-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="62f96-168">โปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="62f96-168">Customer profiles.</span></span>
- <span data-ttu-id="62f96-169">ข้อมูลประจำตัวของแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="62f96-169">Data source credentials.</span></span> <span data-ttu-id="62f96-170">คุณจะต้องให้ข้อมูลประจำตัวสำหรับทุกแหล่งข้อมูล และรีเฟรชแหล่งข้อมูลด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="62f96-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="62f96-171">แหล่งข้อมูลจากโฟลเดอร์ Common Data Model และ Data Lake ที่มีการจัดการของ Dataverse</span><span class="sxs-lookup"><span data-stu-id="62f96-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="62f96-172">คุณจะต้องสร้างแหล่งข้อมูลเหล่านั้นด้วยตนเองด้วยชื่อเดียวกันกับในสภาพแวดล้อมของแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="62f96-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="62f96-173">เมื่อคุณคัดลอกสภาพแวดล้อม คุณจะเห็นข้อความยืนยันว่าสภาพแวดล้อมใหม่ถูกสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="62f96-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="62f96-174">เลือก **ไปที่แหล่งข้อมูล** เพื่อดูรายการแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="62f96-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="62f96-175">แหล่งข้อมูลทั้งหมดจะแสดงสถานะ **ต้องการข้อมูลประจำตัว**</span><span class="sxs-lookup"><span data-stu-id="62f96-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="62f96-176">แก้ไขแหล่งข้อมูล และป้อนข้อมูลประจำตัวเพื่อรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="62f96-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62f96-177">![คัดลอกแหล่งข้อมูลแล้ว](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="62f96-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="62f96-178">หลังจากที่รีเฟรชแหล่งข้อมูล ให้ไปที่ **ข้อมูล** > **รวม**</span><span class="sxs-lookup"><span data-stu-id="62f96-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="62f96-179">ที่นี่คุณจะพบการตั้งค่าจากสภาพแวดล้อมของแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="62f96-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="62f96-180">แก้ไขได้ตามต้องการ หรือเลือก **เรียกใช้** เพื่อเริ่มกระบวนการรวมข้อมูล และสร้างเอนทิตีลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="62f96-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="62f96-181">เมื่อการรวมข้อมูลเสร็จสมบูรณ์ ให้ไปที่ **การวัด** และ **เซ็กเมนต์** เพื่อรีเฟรชพวกเขาด้วย</span><span class="sxs-lookup"><span data-stu-id="62f96-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="62f96-182">แก้ไขสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-182">Edit an existing environment</span></span>

<span data-ttu-id="62f96-183">คุณสามารถแก้ไขรายละเอียดบางส่วนของสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="62f96-184">เลือกตัวเลือก **สภาพแวดล้อม** ในส่วนหัวของแอป</span><span class="sxs-lookup"><span data-stu-id="62f96-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="62f96-185">เลือกไอคอน **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="62f96-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="62f96-186">ในกล่อง **แก้ไขสภาพแวดล้อม** คุณสามารถอัปเดต **ชื่อที่แสดง** ของสภาพแวดล้อมได้ แต่คุณไม่สามารถเปลี่ยน **ภูมิภาค** หรือ **ชนิด** ได้</span><span class="sxs-lookup"><span data-stu-id="62f96-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="62f96-187">หากสภาพแวดล้อมได้รับการตั้งค่าคอนฟิกให้จัดเก็บข้อมูลใน Azure Data Lake Storage คุณสามารถอัปเดต **คีย์บัญชี**</span><span class="sxs-lookup"><span data-stu-id="62f96-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="62f96-188">อย่างไรก็ตาม คุณไม่สามารถเปลี่ยน **ชื่อบัญชี** หรือชื่อ **คอนเทนเนอร์**</span><span class="sxs-lookup"><span data-stu-id="62f96-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="62f96-189">หรือคุณสามารถอัปเดตจากการเชื่อมต่อตามคีย์บัญชีเป็นการเชื่อมต่อตามทรัพยากรหรือการเชื่อมต่อตามการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="62f96-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="62f96-190">เมื่ออัปเกรดแล้ว คุณจะไม่สามารถเปลี่ยนกลับเป็นคีย์บัญชีหลังจากการปรับปรุงได้</span><span class="sxs-lookup"><span data-stu-id="62f96-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="62f96-191">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="62f96-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="62f96-192">คุณไม่สามารถเปลี่ยนแปลงข้อมูล **คอนเทนเนอร์** เมื่อปรับปรุงการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="62f96-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="62f96-193">คุณสามารถระบุ URL สภาพแวดล้อม Microsoft Dataverse ภายใต้ **กำหนดค่าการแบ่งปันข้อมูลด้วย Microsoft Dataverse และเปิดใช้งานความสามารถเพิ่มเติม**</span><span class="sxs-lookup"><span data-stu-id="62f96-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="62f96-194">ความสามารถเหล่านี้รวมถึงการแบ่งปันข้อมูลกับแอปพลิเคชันและโซลูชันที่อิงตาม Microsoft Dataverse, การนำเข้าข้อมูลจากแหล่งข้อมูลภายในองค์กร หรือ [การคาดคะเน](predictions.md) การใช้งาน</span><span class="sxs-lookup"><span data-stu-id="62f96-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="62f96-195">เลือก **เปิดใช้งานการแชร์ข้อมูล** เพื่อแชร์ข้อมูลผลลัพธ์ Customer Insights กับ Microsoft Dataverse Managed Data lake</span><span class="sxs-lookup"><span data-stu-id="62f96-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="62f96-196">ขณะนี้ การแชร์ข้อมูลกับ Microsoft Dataverse Data Lake แบบจัดการได้ ไม่รองรับ เมื่อคุณบันทึกข้อมูลทั้งหมดไปยัง Azure Data Lake Storage ของคุณเอง</span><span class="sxs-lookup"><span data-stu-id="62f96-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="62f96-197">[การคาดคะเนของค่าที่ขาดหายไปในเอนทิตี](predictions.md) ขณะนี้ยังไม่รองรับเมื่อคุณเปิดใช้งานการแบ่งปันข้อมูลด้วย Microsoft Dataverse Managed Data Lake</span><span class="sxs-lookup"><span data-stu-id="62f96-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="62f96-198">หลังจากที่เปิดใช้งานการแบ่งปันข้อมูลกับ Microsoft Dataverse การรีเฟรชอย่างเต็มรูปแบบของแหล่งข้อมูลและกระบวนการอื่นๆ ของคุณจะเริ่มต้น</span><span class="sxs-lookup"><span data-stu-id="62f96-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="62f96-199">หากกระบวนการกำลังทำงานในขณะนี้ คุณไม่เห็นตัวเลือกในการเปิดใช้งานการแบ่งปันข้อมูลกับ Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="62f96-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="62f96-200">รอให้กระบวนการเหล่านั้นเสร็จสมบูรณ์ หรือยกเลิกเพื่อเปิดใช้งานการแบ่งปันข้อมูล</span><span class="sxs-lookup"><span data-stu-id="62f96-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="ตัวเลือกการกำหนดค่าเพื่อเปิดใช้งานการแบ่งปันข้อมูลกับ Microsoft Dataverse":::
   
   <span data-ttu-id="62f96-202">เมื่อคุณเรียกใช้กระบวนการ เช่น การนำเข้าข้อมูลหรือการสร้างกเซ็กเมนต์ จะมีการสร้างโฟลเดอร์ที่เกี่ยวข้องขึ้นในบัญชีที่เก็บข้อมูลที่คุณระบุไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="62f96-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="62f96-203">ไฟล์ข้อมูลและไฟล์ model.json จะถูกสร้างและเพิ่มลงในโฟลเดอร์ย่อยตามลำดับขึ้นอยู่กับกระบวนการที่คุณเรียกใช้</span><span class="sxs-lookup"><span data-stu-id="62f96-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="62f96-204">รีเซ็ตสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-204">Reset an existing environment</span></span>

<span data-ttu-id="62f96-205">ในฐานะผู้ดูแลระบบ คุณสามารถรีเซ็ตสภาพแวดล้อมเป็นสถานะว่างได้ หากคุณต้องการลบการกำหนดค่าทั้งหมดและลบข้อมูลที่นำเข้า</span><span class="sxs-lookup"><span data-stu-id="62f96-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="62f96-206">เลือกตัวเลือก **สภาพแวดล้อม** ในส่วนหัวของแอป</span><span class="sxs-lookup"><span data-stu-id="62f96-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="62f96-207">เลือกสภาพแวดล้อมที่คุณต้องการรีเซ็ต และเลือกจุดไข่ปลา (**...**)</span><span class="sxs-lookup"><span data-stu-id="62f96-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="62f96-208">เลือกตัวเลือก **รีเซ็ต**</span><span class="sxs-lookup"><span data-stu-id="62f96-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="62f96-209">การยืนยันการลบ ให้ป้อนชื่อสภาพแวดล้อมและเลือก **รีเซ็ต**</span><span class="sxs-lookup"><span data-stu-id="62f96-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="62f96-210">ลบสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="62f96-210">Delete an existing environment</span></span>

<span data-ttu-id="62f96-211">ในฐานะผู้ดูแลระบบ คุณสามารถลบสภาพแวดล้อมที่คุณดูแลได้</span><span class="sxs-lookup"><span data-stu-id="62f96-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="62f96-212">เลือกตัวเลือก **สภาพแวดล้อม** ในส่วนหัวของแอป</span><span class="sxs-lookup"><span data-stu-id="62f96-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="62f96-213">เลือกสภาพแวดล้อมที่คุณต้องการรีเซ็ต และเลือกจุดไข่ปลา (**...**)</span><span class="sxs-lookup"><span data-stu-id="62f96-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="62f96-214">เลือกตัวเลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="62f96-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="62f96-215">หากต้องการยืนยันการลบ ให้ป้อนชื่อสภาพแวดล้อม และเลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="62f96-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
