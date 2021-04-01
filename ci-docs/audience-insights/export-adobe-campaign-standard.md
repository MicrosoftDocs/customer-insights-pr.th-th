---
title: ส่งออกข้อมูล Customer Insights ไปยัง Adobe Campaign Standard
description: เรียนรู้วิธีใช้เซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Campaign Standard
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596338"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="fa78a-103">ใช้เซ็กเมนต์ Customer Insights ใน Adobe Campaign Standard (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="fa78a-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="fa78a-104">ในฐานะผู้ใช้ข้อมูลเชิงลึกกลุ่มเป้าหมายสำหรับ Dynamics 365 Customer Insights คุณอาจสร้างเซ็กเมนต์เพื่อทำให้แคมเปญการตลาดของคุณมีประสิทธิภาพมากขึ้นโดยกำหนดเป้าหมายไปยังกลุ่มเป้าหมายที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="fa78a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="fa78a-105">หากต้องการใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform และแอปพลิเคชันเช่น Adobe Campaign Standard คุณต้องทำตามขั้นตอนสองสามขั้นตอนที่ระบุไว้ในบทความนี้</span><span class="sxs-lookup"><span data-stu-id="fa78a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a><span data-ttu-id="fa78a-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="fa78a-107">Prerequisites</span></span>

-   <span data-ttu-id="fa78a-108">สิทธิ์การใช้งาน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fa78a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="fa78a-109">สิทธิ์การใช้งาน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="fa78a-110">บัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="fa78a-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="fa78a-111">ภาพรวมการส่งเสริมการขาย</span><span class="sxs-lookup"><span data-stu-id="fa78a-111">Campaign Overview</span></span>

<span data-ttu-id="fa78a-112">เพื่อให้เข้าใจวิธีใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform ได้ดีขึ้น ลองดูตัวอย่างแคมเปญที่สมมติขึ้น</span><span class="sxs-lookup"><span data-stu-id="fa78a-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="fa78a-113">สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="fa78a-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="fa78a-114">คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="fa78a-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="fa78a-115">เพื่อรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอส่งเสริมการขายทางอีเมลโดยใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="fa78a-116">ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว</span><span class="sxs-lookup"><span data-stu-id="fa78a-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="fa78a-117">บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง</span><span class="sxs-lookup"><span data-stu-id="fa78a-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="fa78a-118">อย่างไรก็ตาม ข้อมูลเชิงลึกกลุ่มเป้าหมายและ Adobe Campaign Standard สามารถกำหนดค่าให้ทำงานสำหรับสถานการณ์แคมเปญที่เกิดซ้ำได้เช่นกัน</span><span class="sxs-lookup"><span data-stu-id="fa78a-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="fa78a-119">ระบุกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="fa78a-119">Identify your target audience</span></span>

<span data-ttu-id="fa78a-120">ในสถานการณ์ของเรา เราถือว่าที่อยู่อีเมลของลูกค้ามีอยู่ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาจะได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="fa78a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="fa78a-121">[เซ็กเมนต์ที่คุณกำหนดไว้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย](segments.md) มีชื่อว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งอีเมลส่งเสริมการขายให้กับลูกค้าเหล่านี้</span><span class="sxs-lookup"><span data-stu-id="fa78a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

<span data-ttu-id="fa78a-123">อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="fa78a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="fa78a-124">ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด</span><span class="sxs-lookup"><span data-stu-id="fa78a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="fa78a-125">ส่งออกกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="fa78a-125">Export your target audience</span></span>

<span data-ttu-id="fa78a-126">ด้วยการระบุกลุ่มเป้าหมายของเรา เราสามารถกำหนดค่าการส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยังบัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="fa78a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="fa78a-127">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="fa78a-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fa78a-128">ในไทล์ **Adobe Campaign** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="fa78a-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="ไทล์การกำหนดค่าสำหรับ Adobe Campaign Standard":::

1. <span data-ttu-id="fa78a-130">ระบุ **ชื่อที่แสดง** สำหรับปลายทางการส่งออกใหม่นี้ จากนั้นป้อน **ชื่อบัญชี**, **คีย์บัญชี** และ **คอนเทนเนอร์** ของบัญชีที่เก็บข้อมูล Azure Blob ที่คุณต้องการส่งออกเซ็กเมนต์ไป</span><span class="sxs-lookup"><span data-stu-id="fa78a-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล"::: 

   - <span data-ttu-id="fa78a-132">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชี ให้ดูที่ [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="fa78a-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="fa78a-133">หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)</span><span class="sxs-lookup"><span data-stu-id="fa78a-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fa78a-134">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="fa78a-134">Select **Next**.</span></span>

1. <span data-ttu-id="fa78a-135">เลือกเรกคอร์ดที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="fa78a-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="fa78a-136">ในตัวอย่างนี้ คือ **ChurnProneCustomers**</span><span class="sxs-lookup"><span data-stu-id="fa78a-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. <span data-ttu-id="fa78a-138">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="fa78a-138">Select **Next**.</span></span>

1. <span data-ttu-id="fa78a-139">ตอนนี้เราแม็ปฟิลด์ **ต้นทาง** จากเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายกับชื่อฟิลด์ **เป้าหมาย** ในแบบแผนโปรไฟล์ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="การแม็ปฟิลด์สำหรับตัวเชื่อมต่อ Adobe Campaign Standard":::

   <span data-ttu-id="fa78a-141">หากคุณต้องการเพิ่มแอตทริบิวต์เพิ่มเติม ให้เลือก **เพิ่มแอตทริบิวต์**</span><span class="sxs-lookup"><span data-stu-id="fa78a-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="fa78a-142">ชื่อเป้าหมายอาจแตกต่างจากชื่อฟิลด์ต้นทางเพื่อให้คุณยังแม็ปผลลัพธ์ของเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายกับ Adobe Campaign Standard ได้ หากฟิลด์ไม่มีชื่อเดียวกันในทั้งสองระบบ</span><span class="sxs-lookup"><span data-stu-id="fa78a-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fa78a-143">ที่อยู่อีเมลใช้เป็นฟิลด์ข้อมูลประจำตัว แต่คุณสามารถใช้ตัวระบุอื่นใดก็ได้จากโปรไฟล์ลูกค้าข้อมูลเชิงลึกกลุ่มเป้าหมายของคุณเพื่อแม็ปข้อมูลกับ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="fa78a-144">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="fa78a-144">Select **Save**.</span></span>

<span data-ttu-id="fa78a-145">หลังจากบันทึกปลายทางการส่งออกแล้ว คุณจะดูได้ใน **การดูแล** > **การส่งออก** > **ปลายทางการส่งออกของฉัน**</span><span class="sxs-lookup"><span data-stu-id="fa78a-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="ภาพหน้าจอที่มีรายการของการส่งออกและเซ็กเมนต์ตัวอย่างที่ไฮไลต์":::

<span data-ttu-id="fa78a-147">ตอนนี้คุณสามารถ [ส่งออกเซ็กเมนต์ตามความต้องการ](export-destinations.md#export-data-on-demand) ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="fa78a-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fa78a-148">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="fa78a-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa78a-149">ตรวจสอบให้แน่ใจว่าจำนวนเรกคอร์ดในเซ็กเมนต์ที่ส่งออกอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ</span><span class="sxs-lookup"><span data-stu-id="fa78a-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="fa78a-150">ข้อมูลที่ส่งออกจะเก็บไว้ในที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่าไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="fa78a-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="fa78a-151">พาธโฟลเดอร์ต่อไปนี้มีการสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ:</span><span class="sxs-lookup"><span data-stu-id="fa78a-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="fa78a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="fa78a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="fa78a-153">ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="fa78a-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="fa78a-154">กำหนดค่า Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="fa78a-155">เมื่อมีการส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมาย จะมีคอลัมน์ที่คุณเลือกขณะที่กำหนดปลายทางการส่งออกในขั้นตอนก่อนหน้า</span><span class="sxs-lookup"><span data-stu-id="fa78a-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="fa78a-156">ข้อมูลนี้สามารถใช้เพื่อ [สร้างโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)</span><span class="sxs-lookup"><span data-stu-id="fa78a-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="fa78a-157">ในการใช้เซ็กเมนต์ใน Adobe Campaign Standard เราจำเป็นต้องขยายแบบแผนโปรไฟล์ใน Adobe Campaign Standard เพื่อรวมฟิลด์เพิ่มเติมสองฟิลด์</span><span class="sxs-lookup"><span data-stu-id="fa78a-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="fa78a-158">เรียนรู้วิธีการ [ขยายทรัพยากรโปรไฟล์](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ด้วยฟิลด์ใหม่ใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="fa78a-159">ในตัวอย่างของเรา ฟิลด์เหล่านี้คือ *ชื่อเซ็กเมนต์และวันที่ของเซ็กเมนต์ (ไม่บังคับ)*</span><span class="sxs-lookup"><span data-stu-id="fa78a-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="fa78a-160">เราจะใช้ฟิลด์เหล่านี้เพื่อระบุโปรไฟล์ใน Adobe Campaign Standard ที่เราต้องการกำหนดเป้าหมายสำหรับแคมเปญนี้</span><span class="sxs-lookup"><span data-stu-id="fa78a-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="fa78a-161">หากไม่มีเรกคอร์ดอื่นๆ ใน Adobe Campaign Standard นอกเหนือจากสิ่งที่คุณกำลังจะนำเข้า คุณสามารถข้ามขั้นตอนนี้ได้</span><span class="sxs-lookup"><span data-stu-id="fa78a-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="fa78a-162">นำเข้าข้อมูลลงใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="fa78a-163">เมื่อทุกอย่างเข้าที่แล้ว เราจำเป็นต้องนำเข้าข้อมูลกลุ่มเป้าหมายที่เตรียมไว้จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Campaign Standard เพื่อสร้างโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="fa78a-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="fa78a-164">เรียนรู้ [วิธีการนำเข้าโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) โดยใช้เวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="fa78a-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="fa78a-165">เวิร์กโฟลว์การนำเข้าในรูปภาพด้านล่างได้รับการกำหนดค่าให้ทำงานทุกๆ 8 ชั่วโมง และค้นหาเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายที่ส่งออก (ไฟล์ .csv ในที่เก็บข้อมูล Azure Blob)</span><span class="sxs-lookup"><span data-stu-id="fa78a-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="fa78a-166">เวิร์กโฟลว์จะแยกเนื้อหาของไฟล์ .csv ตามลำดับคอลัมน์ที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="fa78a-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="fa78a-167">เวิร์กโฟลว์นี้สร้างขึ้นเพื่อดำเนินการจัดการข้อผิดพลาดพื้นฐานและตรวจสอบให้แน่ใจว่าแต่ละเรกคอร์ดมีที่อยู่อีเมลก่อนที่จะไฮเดรทข้อมูลใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="fa78a-168">เวิร์กโฟลว์ยังแยกชื่อเซ็กเมนต์ออกจากชื่อไฟล์ก่อนที่จะเพิ่มลงในข้อมูลโปรไฟล์ ACS</span><span class="sxs-lookup"><span data-stu-id="fa78a-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="ภาพหน้าจอของเวิร์กโฟลว์การนำเข้าในส่วนติดต่อผู้ใช้ Adobe Campaign Standard":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="fa78a-170">ดึงข้อมูลกลุ่มเป้าหมายใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="fa78a-171">เมื่อนำเข้าข้อมูลไปยัง Adobe Campaign Standard แล้ว คุณ [สามารถสร้างเวิร์กโฟลว์](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) และ [การสอบถาม](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) ลูกค้าตาม *ชื่อเซ็กเมนต์* และ *วันที่ของเซ็กเมนต์* เพื่อเลือกโปรไฟล์ที่ระบุไว้สำหรับแคมเปญตัวอย่างของเรา</span><span class="sxs-lookup"><span data-stu-id="fa78a-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="fa78a-172">สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fa78a-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="fa78a-173">สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ</span><span class="sxs-lookup"><span data-stu-id="fa78a-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="ตัวอย่างอีเมลพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::