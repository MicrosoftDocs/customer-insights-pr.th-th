---
title: ส่งออกข้อมูล Customer Insights ไปยัง Adobe Experience Platform
description: เรียนรู้วิธีใช้เซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596292"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="93d8f-103">ใช้เซ็กเมนต์ Customer Insights ใน Adobe Experience Platform (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="93d8f-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="93d8f-104">ในฐานะผู้ใช้ข้อมูลเชิงลึกกลุ่มเป้าหมายสำหรับ Dynamics 365 Customer Insights คุณอาจสร้างเซ็กเมนต์เพื่อทำให้แคมเปญการตลาดของคุณมีประสิทธิภาพมากขึ้นโดยกำหนดเป้าหมายไปยังกลุ่มเป้าหมายที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="93d8f-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="93d8f-105">หากต้องการใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform และแอปพลิเคชันเช่น Adobe Campaign Standard คุณต้องทำตามขั้นตอนสองสามขั้นตอนที่ระบุไว้ในบทความนี้</span><span class="sxs-lookup"><span data-stu-id="93d8f-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a><span data-ttu-id="93d8f-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="93d8f-107">Prerequisites</span></span>

-   <span data-ttu-id="93d8f-108">สิทธิ์การใช้งาน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="93d8f-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="93d8f-109">สิทธิ์การใช้งาน Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="93d8f-110">สิทธิ์การใช้งาน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93d8f-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="93d8f-111">บัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="93d8f-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="93d8f-112">ภาพรวมการส่งเสริมการขาย</span><span class="sxs-lookup"><span data-stu-id="93d8f-112">Campaign Overview</span></span>

<span data-ttu-id="93d8f-113">เพื่อให้เข้าใจวิธีใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform ได้ดีขึ้น ลองดูตัวอย่างแคมเปญที่สมมติขึ้น</span><span class="sxs-lookup"><span data-stu-id="93d8f-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="93d8f-114">สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="93d8f-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="93d8f-115">คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="93d8f-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="93d8f-116">เพื่อรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอส่งเสริมการขายทางอีเมลโดยใช้ Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="93d8f-117">ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว</span><span class="sxs-lookup"><span data-stu-id="93d8f-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="93d8f-118">บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง</span><span class="sxs-lookup"><span data-stu-id="93d8f-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="93d8f-119">ระบุกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="93d8f-119">Identify your target audience</span></span>

<span data-ttu-id="93d8f-120">ในสถานการณ์ของเรา เราถือว่าที่อยู่อีเมลของลูกค้ามีอยู่ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาจะได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="93d8f-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="93d8f-121">[เซ็กเมนต์ที่คุณกำหนดไว้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย](segments.md) มีชื่อว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งอีเมลส่งเสริมการขายให้กับลูกค้าเหล่านี้</span><span class="sxs-lookup"><span data-stu-id="93d8f-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

<span data-ttu-id="93d8f-123">อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="93d8f-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="93d8f-124">ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด</span><span class="sxs-lookup"><span data-stu-id="93d8f-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="93d8f-125">ส่งออกกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="93d8f-125">Export your target audience</span></span>

<span data-ttu-id="93d8f-126">ด้วยการระบุกลุ่มเป้าหมายของเรา เราสามารถกำหนดค่าการส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยังบัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="93d8f-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="93d8f-127">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="93d8f-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="93d8f-128">ในไทล์ **ที่เก็บข้อมูล Azure Blob** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="93d8f-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="ไทล์การกำหนดค่าสำหรับที่เก็บข้อมูล Azure Blob":::

1. <span data-ttu-id="93d8f-130">ระบุ **ชื่อที่แสดง** สำหรับปลายทางการส่งออกใหม่นี้ จากนั้นป้อน **ชื่อบัญชี**, **คีย์บัญชี** และ **คอนเทนเนอร์** ของบัญชีที่เก็บข้อมูล Azure Blob ที่คุณต้องการส่งออกเซ็กเมนต์ไป</span><span class="sxs-lookup"><span data-stu-id="93d8f-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล"::: 

   - <span data-ttu-id="93d8f-132">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชี ให้ดูที่ [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="93d8f-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="93d8f-133">หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)</span><span class="sxs-lookup"><span data-stu-id="93d8f-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="93d8f-134">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="93d8f-134">Select **Next**.</span></span>

1. <span data-ttu-id="93d8f-135">เลือกเรกคอร์ดที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="93d8f-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="93d8f-136">ในตัวอย่างนี้ คือ **ChurnProneCustomers**</span><span class="sxs-lookup"><span data-stu-id="93d8f-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. <span data-ttu-id="93d8f-138">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="93d8f-138">Select **Save**.</span></span>

<span data-ttu-id="93d8f-139">หลังจากบันทึกปลายทางการส่งออกแล้ว คุณจะดูได้ใน **การดูแล** > **การส่งออก** > **ปลายทางการส่งออกของฉัน**</span><span class="sxs-lookup"><span data-stu-id="93d8f-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="ภาพหน้าจอที่มีรายการของการส่งออกและเซ็กเมนต์ตัวอย่างที่ไฮไลต์":::

<span data-ttu-id="93d8f-141">ตอนนี้คุณสามารถ [ส่งออกเซ็กเมนต์ตามความต้องการ](export-destinations.md#export-data-on-demand) ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="93d8f-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="93d8f-142">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="93d8f-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="93d8f-143">ตรวจสอบให้แน่ใจว่าจำนวนเรกคอร์ดในเซ็กเมนต์ที่ส่งออกอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ</span><span class="sxs-lookup"><span data-stu-id="93d8f-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="93d8f-144">ข้อมูลที่ส่งออกจะเก็บไว้ในที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่าไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="93d8f-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="93d8f-145">พาธโฟลเดอร์ต่อไปนี้มีการสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ:</span><span class="sxs-lookup"><span data-stu-id="93d8f-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="93d8f-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="93d8f-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="93d8f-147">ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="93d8f-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="93d8f-148">*model.json* สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ *%ExportDestinationName%*</span><span class="sxs-lookup"><span data-stu-id="93d8f-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="93d8f-149">ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="93d8f-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="93d8f-150">กำหนด Experience Data Model (XDM) ใน Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="93d8f-151">ก่อนที่ข้อมูลที่ส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายจะสามารถใช้ภายใน Adobe Experience Platform ได้ เราจำเป็นต้องกำหนดแบบแผน Experience Data Model และ [กำหนดค่าข้อมูลสำหรับโปรไฟล์ลูกค้าแบบเรียลไทม์](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)</span><span class="sxs-lookup"><span data-stu-id="93d8f-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="93d8f-152">เรียนรู้ว่า [XDM คืออะไร](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) และทำความเข้าใจ [พื้นฐานขององค์ประกอบแบบแผน](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)</span><span class="sxs-lookup"><span data-stu-id="93d8f-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="93d8f-153">นำเข้าข้อมูลไปยัง Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="93d8f-154">เมื่อทุกอย่างเข้าที่แล้ว เราจำเป็นต้องนำเข้าข้อมูลกลุ่มเป้าหมายที่เตรียมไว้จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="93d8f-155">ประการแรก [สร้างการเชื่อมต่อแหล่งกับต้นทางที่เก็บข้อมูล Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started)</span><span class="sxs-lookup"><span data-stu-id="93d8f-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="93d8f-156">หลังจากกำหนดการเชื่อมต่อกับต้นทางแล้ว [กำหนดค่ากระแสข้อมูล](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) สำหรับการเชื่อมต่อชุดงานที่เก็บข้อมูลบนระบบคลาวด์ เพื่อนำเข้าผลลัพธ์ของเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="93d8f-157">สร้างกลุ่มเป้าหมายใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93d8f-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="93d8f-158">ในการส่งอีเมลสำหรับแคมเปญนี้ เราจะใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93d8f-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="93d8f-159">หลังจากนำเข้าข้อมูลไปยัง Adobe Experience Platform เราจำเป็นต้อง [สร้างกลุ่มเป้าหมาย](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ใน Adobe Campaign Standard โดยใช้ข้อมูลใน Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="93d8f-160">เรียนรู้วิธีการ [ใช้ตัวสร้างเซ็กเมนต์](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) ใน Adobe Campaign Standard เพื่อกำหนดกลุ่มเป้าหมายตามข้อมูลใน Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="93d8f-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="93d8f-161">สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93d8f-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="93d8f-162">สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ</span><span class="sxs-lookup"><span data-stu-id="93d8f-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="ตัวอย่างอีเมลพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::