---
title: สร้างและจัดการสภาพแวดล้อม
description: เรียนรู้วิธีการลงทะเบียนสำหรับบริการและวิธีจัดการสภาพแวดล้อม
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644156"
---
# <a name="manage-environments"></a><span data-ttu-id="1d3cc-103">จัดการสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="1d3cc-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1d3cc-104">บทความนี้อธิบายถึงวิธีการสร้างองค์กรใหม่และวิธีการจัดเตรียมสภาพแวดล้อม</span><span class="sxs-lookup"><span data-stu-id="1d3cc-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="1d3cc-105">ลงทะเบียนและสร้างองค์กร</span><span class="sxs-lookup"><span data-stu-id="1d3cc-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="1d3cc-106">ไปยังเว็บไซต์ [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="1d3cc-107">เลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="1d3cc-108">เลือกสถานการณ์การสมัครที่คุณต้องการและเลือกลิงก์ที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="1d3cc-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="1d3cc-109">ยอมรับข้อกำหนดและเงื่อนไข และเลือก **ดำเนินการต่อ** เพื่อเริ่มสร้างองค์กร</span><span class="sxs-lookup"><span data-stu-id="1d3cc-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="1d3cc-110">หลังจากสร้างสภาพแวดล้อมแล้ว ระบบจะเปลี่ยนเส้นทางไปที่ [Customer Insights](https://home.ci.ai.dynamics.com)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="1d3cc-111">ใช้สภาพแวดล้อมการสาธิตเพื่อสำรวจแอป หรือสร้างสภาพแวดล้อมใหม่โดยทำตามขั้นตอนในส่วนถัดไป</span><span class="sxs-lookup"><span data-stu-id="1d3cc-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="1d3cc-112">หลังจากระบุการตั้งค่าสภาพแวดล้อม ให้เลือก **สร้าง**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="1d3cc-113">คุณจะลงชื่อเข้าใช้หลังจากสร้างสภาพแวดล้อมสำเร็จแล้ว</span><span class="sxs-lookup"><span data-stu-id="1d3cc-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="1d3cc-114">สร้างสภาพแวดล้อมในองค์กรที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="1d3cc-115">มีสองวิธีในการสร้างสภาพแวดล้อมใหม่:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="1d3cc-116">คุณสามารถระบุการตั้งค่าคอนฟิกใหม่ทั้งหมด หรือคุณสามารถคัดลอกการตั้งค่าของการตั้งค่าคอนฟิกบางรายการจากสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="1d3cc-117">เพื่อสร้างสภาพแวดล้อม:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-117">To create an environment:</span></span>

1. <span data-ttu-id="1d3cc-118">เลือกสัญลักษณ์ **การตั้งค่า** ในส่วนหัวของแอป</span><span class="sxs-lookup"><span data-stu-id="1d3cc-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="1d3cc-119">เลือก **สภาพแวดล้อมใหม่**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d3cc-120">![การตั้งค่าสภาพแวดล้อม](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="1d3cc-121">ในกล่องโต้ตอบ **สร้างสภาพแวดล้อมใหม่** เลือก **สภาพแวดล้อมใหม่**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="1d3cc-122">ถ้าคุณต้องการ [คัดลอกข้อมูลจากสภาพแวดล้อมปัจจุบัน](#additional-considerations-for-copy-configuration-preview) เลือก **คัดลอกจากสภาพแวดล้อมที่มีอยู่**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="1d3cc-123">คุณจะเห็นรายการของสภาพแวดล้อมที่พร้อมใช้งานทั้งหมดในองค์กรของคุณ ที่ซึ่งคุณสามารถคัดลอกข้อมูลได้</span><span class="sxs-lookup"><span data-stu-id="1d3cc-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="1d3cc-124">ให้รายละเอียดต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-124">Provide the following details:</span></span>
   - <span data-ttu-id="1d3cc-125">**ชื่อ**: ชื่อสำหรับสภาพแวดล้อมนี้</span><span class="sxs-lookup"><span data-stu-id="1d3cc-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="1d3cc-126">ฟิลด์นี้ถูกกรอกข้อมูลเรียบร้อยแล้ว หากคุณได้คัดลอกสภาพแวดล้อมที่มีอยู่ แต่คุณสามารถเปลี่ยนแปลงได้</span><span class="sxs-lookup"><span data-stu-id="1d3cc-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="1d3cc-127">**ภูมิภาค**: ภูมิภาคที่มีการปรับใช้และที่เป็นโฮสต์บริการ</span><span class="sxs-lookup"><span data-stu-id="1d3cc-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="1d3cc-128">**ชนิด**: เลือกว่าคุณต้องการสร้างสภาพแวดล้อมการผลิตหรือ Sandbox</span><span class="sxs-lookup"><span data-stu-id="1d3cc-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="1d3cc-129">อีกทางเลือกหนึ่ง คุณสามารถเลือก **การตั้งค่าขั้นสูง**:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="1d3cc-130">**บันทึกข้อมูลทั้งหมดไปที่**: ระบุตำแหน่งที่คุณต้องการจัดเก็บข้อมูลเอาต์พุตที่สร้างจาก Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1d3cc-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="1d3cc-131">คุณจะมีตัวเลือกสองตัวเลือก: **ที่เก็บข้อมูล Customer Insights** (Azure Data Lake ที่จัดการโดยทีม Customer Insights) และ **Azure Data Lake Storage Gen2** (Azure Data Lake Storage ของคุณเอง)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="1d3cc-132">ตามค่าเริ่มต้น ตัวเลือกที่เก็บข้อมูล Customer Insights จะถูกเลือก</span><span class="sxs-lookup"><span data-stu-id="1d3cc-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d3cc-133">การบันทึกข้อมูลใน Azure Data Lake Storage หมายถึงคุณยอมรับว่าข้อมูลจะมีการถ่ายโอนไปและเก็บไว้ในที่ตั้งทางภูมิศาสตร์ที่เหมาะสมสำหรับบัญชีที่เก็บข้อมูล Azure ซึ่งอาจแตกต่างจากที่ตั้งที่เก็บข้อมูลใน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1d3cc-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="1d3cc-134">เรียนรู้เพิ่มเติมที่ Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="1d3cc-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="1d3cc-135">ปัจจุบัน เอนทิตีที่ถูกนำมาใช้จะเก็บไว้ใน Data Lake ที่มีการจัดการของ Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1d3cc-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="1d3cc-136">เรารองรับเฉพาะบัญชีที่เก็บข้อมูล Azure Data Lake รุ่น2 จากภูมิภาค Azure เดียวกับที่คุณเลือกเมื่อสร้างสภาพแวดล้อมเท่านั้น</span><span class="sxs-lookup"><span data-stu-id="1d3cc-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="1d3cc-137">เราสนับสนุนเฉพาะบัญชีพื้นที่เก็บข้อมูลลำดับชั้น Azure Data Lake Gen2 Hierarchical Name Space (HNS) ที่เปิดใช้งาน</span><span class="sxs-lookup"><span data-stu-id="1d3cc-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="1d3cc-138">สำหรับตัวเลือก Azure Data Lake Storage รุ่น2 คุณสามารถเลือกระหว่างตัวเลือกตามทรัพยากรและตัวเลือกตามการสมัครใช้งานสำหรับการรับรองความถูกต้อง</span><span class="sxs-lookup"><span data-stu-id="1d3cc-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="1d3cc-139">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1d3cc-140">ชื่อ **คอนเทนเนอร์** ไม่สามารถเปลี่ยนได้ และจะเป็น "customerinsights"</span><span class="sxs-lookup"><span data-stu-id="1d3cc-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="1d3cc-141">หากต้องการใช้ [การคาดการณ์](predictions.md) ให้ป้อน URL ของอินสแตนซ์ Common Data Service ในฟิลด์ **ที่อยู่เซิฟเวอร์** ภายใต้ **ใช้การคาดคะเน**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="1d3cc-142">เมื่อคุณเรียกใช้กระบวนการ เช่น การนำเข้าข้อมูลหรือการสร้างกเซ็กเมนต์ จะมีการสร้างโฟลเดอร์ที่เกี่ยวข้องขึ้นในบัญชีที่เก็บข้อมูลที่คุณระบุไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="1d3cc-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="1d3cc-143">ไฟล์ข้อมูลและไฟล์ model.json จะถูกสร้าง และเพิ่มลงในโฟลเดอร์ย่อยที่เกี่ยวข้องตามกระบวนการที่คุณเรียกใช้</span><span class="sxs-lookup"><span data-stu-id="1d3cc-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="1d3cc-144">หากคุณสร้างสภาพแวดล้อมของ Customer Insights หลาย ๆ รายการและเลือกที่จะบันทึกเอนทิตีผลลัพธ์จากสภาพแวดล้อมเหล่านั้นในบัญชีที่เก็บข้อมูลของคุณ จะมีการสร้างโฟลเดอร์แยกต่างหากขึ้นสำหรับแต่ละสภาพแวดล้อมด้วย ci_<environmentid> ในคอนเทนเนอร์</span><span class="sxs-lookup"><span data-stu-id="1d3cc-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="1d3cc-145">ข้อควรพิจารณาเพิ่มเติมสำหรับการกำหนดค่าการคัดลอก (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="1d3cc-146">การตั้งค่าการกำหนดค่าต่อไปนี้จะถูกคัดลอก:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="1d3cc-147">การตั้งค่าคอนฟิกคุณลักษณะ</span><span class="sxs-lookup"><span data-stu-id="1d3cc-147">Feature configurations</span></span>
- <span data-ttu-id="1d3cc-148">แหล่งข้อมูลที่นำมาใช้/ที่นำเข้า</span><span class="sxs-lookup"><span data-stu-id="1d3cc-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="1d3cc-149">การตั้งค่าคอนฟิกการรวมข้อมูล (แม็ป จับคู่ ผสาน)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="1d3cc-150">เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="1d3cc-150">Segments</span></span>
- <span data-ttu-id="1d3cc-151">การวัด</span><span class="sxs-lookup"><span data-stu-id="1d3cc-151">Measures</span></span>
- <span data-ttu-id="1d3cc-152">ความสัมพันธ์</span><span class="sxs-lookup"><span data-stu-id="1d3cc-152">Relationships</span></span>
- <span data-ttu-id="1d3cc-153">กิจกรรม</span><span class="sxs-lookup"><span data-stu-id="1d3cc-153">Activities</span></span>
- <span data-ttu-id="1d3cc-154">ดัชนีการค้นหาและตัวกรอง</span><span class="sxs-lookup"><span data-stu-id="1d3cc-154">Search & filter Index</span></span>
- <span data-ttu-id="1d3cc-155">ปลายทางการส่งออก</span><span class="sxs-lookup"><span data-stu-id="1d3cc-155">Export destinations</span></span>
- <span data-ttu-id="1d3cc-156">การรีเฟรชที่มีการจัดกำหนดการ</span><span class="sxs-lookup"><span data-stu-id="1d3cc-156">Scheduled refresh</span></span>
- <span data-ttu-id="1d3cc-157">การเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1d3cc-157">Enrichments</span></span>
- <span data-ttu-id="1d3cc-158">การจัดการโมเดล</span><span class="sxs-lookup"><span data-stu-id="1d3cc-158">Model management</span></span>
- <span data-ttu-id="1d3cc-159">การกำหนดบทบาท</span><span class="sxs-lookup"><span data-stu-id="1d3cc-159">Role assignments</span></span>

<span data-ttu-id="1d3cc-160">การตั้งค่าต่อไปนี้จะ *ไม่* ถูกคัดลอก:</span><span class="sxs-lookup"><span data-stu-id="1d3cc-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="1d3cc-161">โปรไฟล์ลูกค้า</span><span class="sxs-lookup"><span data-stu-id="1d3cc-161">Customer profiles.</span></span>
- <span data-ttu-id="1d3cc-162">ข้อมูลประจำตัวของแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1d3cc-162">Data source credentials.</span></span> <span data-ttu-id="1d3cc-163">คุณจะต้องให้ข้อมูลประจำตัวสำหรับทุกแหล่งข้อมูล และรีเฟรชแหล่งข้อมูลด้วยตนเอง</span><span class="sxs-lookup"><span data-stu-id="1d3cc-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="1d3cc-164">แหล่งข้อมูลจากโฟลเดอร์ Common Data Model และ Lake ที่มีการจัดการ Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1d3cc-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="1d3cc-165">คุณจะต้องสร้างแหล่งข้อมูลเหล่านั้นด้วยตนเองด้วยชื่อเดียวกันกับในสภาพแวดล้อมของแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="1d3cc-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="1d3cc-166">เมื่อคุณคัดลอกสภาพแวดล้อม คุณจะเห็นข้อความยืนยันว่าสภาพแวดล้อมใหม่ถูกสร้างขึ้น</span><span class="sxs-lookup"><span data-stu-id="1d3cc-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="1d3cc-167">เลือก **ไปที่แหล่งข้อมูล** เพื่อดูรายการแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1d3cc-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="1d3cc-168">แหล่งข้อมูลทั้งหมดจะแสดงสถานะ **ต้องการข้อมูลประจำตัว**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="1d3cc-169">แก้ไขแหล่งข้อมูล และป้อนข้อมูลประจำตัวเพื่อรีเฟรช</span><span class="sxs-lookup"><span data-stu-id="1d3cc-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d3cc-170">![แหล่งข้อมูลที่คัดลอก](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="1d3cc-171">หลังจากที่รีเฟรชแหล่งข้อมูล ให้ไปที่ **ข้อมูล** > **รวม**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="1d3cc-172">ที่นี่คุณจะพบการตั้งค่าจากสภาพแวดล้อมของแหล่งที่มา</span><span class="sxs-lookup"><span data-stu-id="1d3cc-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="1d3cc-173">แก้ไขได้ตามต้องการ หรือเลือก **เรียกใช้** เพื่อเริ่มกระบวนการรวมข้อมูล และสร้างเอนทิตีลูกค้าแบบรวม</span><span class="sxs-lookup"><span data-stu-id="1d3cc-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="1d3cc-174">เมื่อการรวมข้อมูลเสร็จสมบูรณ์ ให้ไปที่ **การวัด** และ **เซ็กเมนต์** เพื่อรีเฟรชพวกเขาด้วย</span><span class="sxs-lookup"><span data-stu-id="1d3cc-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="1d3cc-175">แก้ไขสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-175">Edit an existing environment</span></span>

<span data-ttu-id="1d3cc-176">คุณสามารถแก้ไขรายละเอียดบางส่วนของสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="1d3cc-177">ไปยัง **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="1d3cc-178">เลือก **แก้ไข**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-178">Select **Edit**.</span></span>

3. <span data-ttu-id="1d3cc-179">คุณสามารถปรับปรุง **ชื่อที่แสดง** ของสภาพแวดล้อม แต่คุณไม่สามารถเปลี่ยน **ภูมิภาค** หรือ **ชนิด**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="1d3cc-180">หากมีการกำหนดค่าสภาพแวดล้อมให้เก็บข้อมูลไว้ใน Azure Data Lake Storage Gen2 คุณสามารถอัปเดต **คีย์บัญชี**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="1d3cc-181">อย่างไรก็ตาม คุณไม่สามารถเปลี่ยน **ชื่อบัญชี** หรือชื่อ **คอนเทนเนอร์**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="1d3cc-182">หรือคุณสามารถเลือกปรับปรุงการเชื่อมต่อคีย์บัญชีกับการเชื่อมต่อตามทรัพยากรหรือการเชื่อมต่อตามการสมัครใช้งาน</span><span class="sxs-lookup"><span data-stu-id="1d3cc-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="1d3cc-183">เมื่ออัปเกรดแล้ว คุณจะไม่สามารถเปลี่ยนกลับเป็นคีย์บัญชีหลังจากการปรับปรุงได้</span><span class="sxs-lookup"><span data-stu-id="1d3cc-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="1d3cc-184">สำหรับข้อมูลเพิ่มเติม ดูที่ [เชื่อมต่อข้อมูลเชิงลึกกลุ่มเป้าหมายกับบัญชี Azure Data Lake Storage รุ่น2 ที่มีบริการหลักของ Azure](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="1d3cc-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1d3cc-185">คุณไม่สามารถเปลี่ยนแปลงข้อมูล **คอนเทนเนอร์** เมื่อปรับปรุงการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1d3cc-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="1d3cc-186">รีเซ็ตสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-186">Reset an existing environment</span></span>

<span data-ttu-id="1d3cc-187">คุณสามารถรีเซ็ตสภาพแวดล้อมเป็นสถานะว่างได้หากคุณต้องการลบการกำหนดค่าทั้งหมดและลบข้อมูลที่นำเข้า</span><span class="sxs-lookup"><span data-stu-id="1d3cc-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="1d3cc-188">ไปยัง **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="1d3cc-189">เลือก **รีเซ็ต**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="1d3cc-190">การยืนยันการลบ ให้ป้อนชื่อสภาพแวดล้อมและเลือก **รีเซ็ต**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="1d3cc-191">ลบสภาพแวดล้อมที่มีอยู่</span><span class="sxs-lookup"><span data-stu-id="1d3cc-191">Delete an existing environment</span></span>

1. <span data-ttu-id="1d3cc-192">ไปยัง **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="1d3cc-193">เลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-193">Select **Delete**.</span></span>

1. <span data-ttu-id="1d3cc-194">หากต้องการยืนยันการลบ ให้ป้อนชื่อสภาพแวดล้อม และเลือก **ลบ**</span><span class="sxs-lookup"><span data-stu-id="1d3cc-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
