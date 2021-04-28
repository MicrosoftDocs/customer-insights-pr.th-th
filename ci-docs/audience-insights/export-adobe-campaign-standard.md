---
title: ส่งออกข้อมูล Customer Insights ไปยัง Adobe Campaign Standard
description: เรียนรู้วิธีใช้เซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Campaign Standard
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760304"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="5dd9f-103">ใช้เซ็กเมนต์ Customer Insights ใน Adobe Campaign Standard (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="5dd9f-104">ในฐานะผู้ใช้ข้อมูลเชิงลึกกลุ่มเป้าหมายสำหรับ Dynamics 365 Customer Insights คุณอาจสร้างเซ็กเมนต์เพื่อทำให้แคมเปญการตลาดของคุณมีประสิทธิภาพมากขึ้นโดยกำหนดเป้าหมายไปยังกลุ่มเป้าหมายที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="5dd9f-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="5dd9f-105">หากต้องการใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform และแอปพลิเคชันเช่น Adobe Campaign Standard คุณต้องทำตามขั้นตอนสองสามขั้นตอนที่ระบุไว้ในบทความนี้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="แผนผังกระบวนการของขั้นตอนที่ระบุไว้ในบทความนี้":::

## <a name="prerequisites"></a><span data-ttu-id="5dd9f-107">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="5dd9f-107">Prerequisites</span></span>

-   <span data-ttu-id="5dd9f-108">สิทธิ์การใช้งาน Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5dd9f-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="5dd9f-109">สิทธิ์การใช้งาน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="5dd9f-110">บัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="5dd9f-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="5dd9f-111">ภาพรวมการส่งเสริมการขาย</span><span class="sxs-lookup"><span data-stu-id="5dd9f-111">Campaign Overview</span></span>

<span data-ttu-id="5dd9f-112">เพื่อให้เข้าใจวิธีใช้เซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายใน Adobe Experience Platform ได้ดีขึ้น ลองดูตัวอย่างแคมเปญที่สมมติขึ้น</span><span class="sxs-lookup"><span data-stu-id="5dd9f-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="5dd9f-113">สมมติว่าบริษัทของคุณเสนอบริการแบบสมัครสมาชิกรายเดือนให้กับลูกค้าของคุณในสหรัฐอเมริกา</span><span class="sxs-lookup"><span data-stu-id="5dd9f-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="5dd9f-114">คุณต้องการระบุลูกค้าที่การสมัครสมาชิกถึงกำหนดต่ออายุในแปดวันถัดไป แต่ยังไม่ได้ต่ออายุการสมัครสมาชิก</span><span class="sxs-lookup"><span data-stu-id="5dd9f-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="5dd9f-115">เพื่อรักษาลูกค้าเหล่านี้ไว้ คุณต้องส่งข้อเสนอส่งเสริมการขายทางอีเมลโดยใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="5dd9f-116">ในตัวอย่างนี้ เราต้องการเรียกใช้แคมเปญอีเมลส่งเสริมการขายเพียงครั้งเดียว</span><span class="sxs-lookup"><span data-stu-id="5dd9f-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="5dd9f-117">บทความนี้ไม่ได้กล่าวถึงกรณีการใช้งานของการเรียกใช้แคมเปญมากกว่าหนึ่งครั้ง</span><span class="sxs-lookup"><span data-stu-id="5dd9f-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="5dd9f-118">อย่างไรก็ตาม ข้อมูลเชิงลึกกลุ่มเป้าหมายและ Adobe Campaign Standard สามารถกำหนดค่าให้ทำงานสำหรับสถานการณ์แคมเปญที่เกิดซ้ำได้เช่นกัน</span><span class="sxs-lookup"><span data-stu-id="5dd9f-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="5dd9f-119">ระบุกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-119">Identify your target audience</span></span>

<span data-ttu-id="5dd9f-120">ในสถานการณ์ของเรา เราถือว่าที่อยู่อีเมลของลูกค้ามีอยู่ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และการกำหนดลักษณะการส่งเสริมการขายของพวกเขาจะได้รับการวิเคราะห์เพื่อระบุสมาชิกของเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="5dd9f-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="5dd9f-121">[เซ็กเมนต์ที่คุณกำหนดไว้ในข้อมูลเชิงลึกกลุ่มเป้าหมาย](segments.md) มีชื่อว่า **ChurnProneCustomers** และคุณวางแผนที่จะส่งอีเมลส่งเสริมการขายให้กับลูกค้าเหล่านี้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ภาพหน้าจอของเพจเซ็กเมนต์ที่สร้างเซ็กเมนต์ ChurnProneCustomers":::

<span data-ttu-id="5dd9f-123">อีเมลข้อเสนอที่คุณต้องการส่งจะมีชื่อ นามสกุล และวันที่สิ้นสุดการสมัครสมาชิกของลูกค้า</span><span class="sxs-lookup"><span data-stu-id="5dd9f-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="5dd9f-124">ซึ่งจะแจ้งให้ลูกค้าทราบเกี่ยวกับส่วนลดที่พวกเขาจะได้รับหากพวกเขาต่ออายุการสมัครสมาชิกก่อนที่จะสิ้นสุด</span><span class="sxs-lookup"><span data-stu-id="5dd9f-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="5dd9f-125">ส่งออกกลุ่มเป้าหมายของคุณ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="5dd9f-126">กำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-126">Configure a connection</span></span>

<span data-ttu-id="5dd9f-127">ด้วยการระบุกลุ่มเป้าหมายของเรา เราสามารถกำหนดค่าการส่งออกจากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยังบัญชีที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="5dd9f-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="5dd9f-128">ในข้อมูลเชิงลึกของผู้ชม ให้ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5dd9f-129">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Adobe Campaign** เพื่อกำหนดค่าการเชื่อมต่อหรือเลือก **ตั้งค่า** ในไทล์ **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="ไทล์การกำหนดค่าสำหรับ Adobe Campaign Standard":::

1. <span data-ttu-id="5dd9f-131">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5dd9f-132">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5dd9f-133">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5dd9f-134">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-134">Choose who can use this connection.</span></span> <span data-ttu-id="5dd9f-135">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5dd9f-136">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5dd9f-137">ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชีที่เก็บข้อมูล Azure Blob ที่คุณต้องการส่งออกเซ็กเมนต์ไป</span><span class="sxs-lookup"><span data-stu-id="5dd9f-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ภาพหน้าจอของการกำหนดค่าบัญชีที่เก็บข้อมูล"::: 

   - <span data-ttu-id="5dd9f-139">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Blob และคีย์บัญชี ให้ดูที่ [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="5dd9f-140">หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="5dd9f-141">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="5dd9f-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="5dd9f-142">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="5dd9f-142">Configure an export</span></span>

<span data-ttu-id="5dd9f-143">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5dd9f-144">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5dd9f-145">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dd9f-146">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="5dd9f-147">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Adobe Campaign</span><span class="sxs-lookup"><span data-stu-id="5dd9f-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="5dd9f-148">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5dd9f-149">เลือกเรกคอร์ดที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="5dd9f-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="5dd9f-150">ในตัวอย่างนี้ คือ **ChurnProneCustomers**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ภาพหน้าจอของส่วนติดต่อผู้ใช้สำหรับการเลือกเซ็กเมนต์ที่เลือกเซ็กเมนต์ ChurnProneCustomers ไว้":::

1. <span data-ttu-id="5dd9f-152">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-152">Select **Next**.</span></span>

1. <span data-ttu-id="5dd9f-153">ตอนนี้เราแม็ปฟิลด์ **ต้นทาง** จากเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายกับชื่อฟิลด์ **เป้าหมาย** ในแบบแผนโปรไฟล์ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="การแม็ปฟิลด์สำหรับตัวเชื่อมต่อ Adobe Campaign Standard":::

   <span data-ttu-id="5dd9f-155">หากคุณต้องการเพิ่มแอตทริบิวต์เพิ่มเติม ให้เลือก **เพิ่มแอตทริบิวต์**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="5dd9f-156">ชื่อเป้าหมายอาจแตกต่างจากชื่อฟิลด์ต้นทางเพื่อให้คุณยังแม็ปผลลัพธ์ของเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายกับ Adobe Campaign Standard ได้ หากฟิลด์ไม่มีชื่อเดียวกันในทั้งสองระบบ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5dd9f-157">ที่อยู่อีเมลใช้เป็นฟิลด์ข้อมูลประจำตัว แต่คุณสามารถใช้ตัวระบุอื่นใดก็ได้จากโปรไฟล์ลูกค้าข้อมูลเชิงลึกกลุ่มเป้าหมายของคุณเพื่อแม็ปข้อมูลกับ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="5dd9f-158">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-158">Select **Save**.</span></span>

<span data-ttu-id="5dd9f-159">หลังจากบันทึกปลายทางการส่งออกแล้ว คุณจะพบบน **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="5dd9f-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="5dd9f-160">ตอนนี้คุณสามารถ [ส่งออกเซ็กเมนต์ตามความต้องการ](export-destinations.md#run-exports-on-demand) ได้แล้ว</span><span class="sxs-lookup"><span data-stu-id="5dd9f-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5dd9f-161">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="5dd9f-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5dd9f-162">ตรวจสอบให้แน่ใจว่าจำนวนเรกคอร์ดในเซ็กเมนต์ที่ส่งออกอยู่ภายในขีดจำกัดที่อนุญาตของสิทธิ์การใช้งาน Adobe Campaign Standard ของคุณ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="5dd9f-163">ข้อมูลที่ส่งออกจะเก็บไว้ในที่เก็บข้อมูล Azure Blob ที่คุณกำหนดค่าไว้ด้านบน</span><span class="sxs-lookup"><span data-stu-id="5dd9f-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="5dd9f-164">พาธโฟลเดอร์ต่อไปนี้มีการสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ:</span><span class="sxs-lookup"><span data-stu-id="5dd9f-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="5dd9f-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="5dd9f-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="5dd9f-166">ตัวอย่าง: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="5dd9f-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="5dd9f-167">กำหนดค่า Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="5dd9f-168">เมื่อมีการส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมาย จะมีคอลัมน์ที่คุณเลือกขณะที่กำหนดปลายทางการส่งออกในขั้นตอนก่อนหน้า</span><span class="sxs-lookup"><span data-stu-id="5dd9f-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="5dd9f-169">ข้อมูลนี้สามารถใช้เพื่อ [สร้างโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="5dd9f-170">ในการใช้เซ็กเมนต์ใน Adobe Campaign Standard เราจำเป็นต้องขยายแบบแผนโปรไฟล์ใน Adobe Campaign Standard เพื่อรวมฟิลด์เพิ่มเติมสองฟิลด์</span><span class="sxs-lookup"><span data-stu-id="5dd9f-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="5dd9f-171">เรียนรู้วิธีการ [ขยายทรัพยากรโปรไฟล์](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) ด้วยฟิลด์ใหม่ใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="5dd9f-172">ในตัวอย่างของเรา ฟิลด์เหล่านี้คือ *ชื่อเซ็กเมนต์และวันที่ของเซ็กเมนต์ (ไม่บังคับ)*</span><span class="sxs-lookup"><span data-stu-id="5dd9f-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="5dd9f-173">เราจะใช้ฟิลด์เหล่านี้เพื่อระบุโปรไฟล์ใน Adobe Campaign Standard ที่เราต้องการกำหนดเป้าหมายสำหรับแคมเปญนี้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="5dd9f-174">หากไม่มีเรกคอร์ดอื่นๆ ใน Adobe Campaign Standard นอกเหนือจากสิ่งที่คุณกำลังจะนำเข้า คุณสามารถข้ามขั้นตอนนี้ได้</span><span class="sxs-lookup"><span data-stu-id="5dd9f-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="5dd9f-175">นำเข้าข้อมูลลงใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="5dd9f-176">เมื่อทุกอย่างเข้าที่แล้ว เราจำเป็นต้องนำเข้าข้อมูลกลุ่มเป้าหมายที่เตรียมไว้จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Adobe Campaign Standard เพื่อสร้างโปรไฟล์</span><span class="sxs-lookup"><span data-stu-id="5dd9f-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="5dd9f-177">เรียนรู้ [วิธีการนำเข้าโปรไฟล์ใน Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) โดยใช้เวิร์กโฟลว์</span><span class="sxs-lookup"><span data-stu-id="5dd9f-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="5dd9f-178">เวิร์กโฟลว์การนำเข้าในรูปภาพด้านล่างได้รับการกำหนดค่าให้ทำงานทุกๆ 8 ชั่วโมง และค้นหาเซ็กเมนต์ข้อมูลเชิงลึกกลุ่มเป้าหมายที่ส่งออก (ไฟล์ .csv ในที่เก็บข้อมูล Azure Blob)</span><span class="sxs-lookup"><span data-stu-id="5dd9f-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="5dd9f-179">เวิร์กโฟลว์จะแยกเนื้อหาของไฟล์ .csv ตามลำดับคอลัมน์ที่ระบุ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="5dd9f-180">เวิร์กโฟลว์นี้สร้างขึ้นเพื่อดำเนินการจัดการข้อผิดพลาดพื้นฐานและตรวจสอบให้แน่ใจว่าแต่ละเรกคอร์ดมีที่อยู่อีเมลก่อนที่จะไฮเดรทข้อมูลใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="5dd9f-181">เวิร์กโฟลว์ยังแยกชื่อเซ็กเมนต์ออกจากชื่อไฟล์ก่อนที่จะเพิ่มลงในข้อมูลโปรไฟล์ ACS</span><span class="sxs-lookup"><span data-stu-id="5dd9f-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="ภาพหน้าจอของเวิร์กโฟลว์การนำเข้าในส่วนติดต่อผู้ใช้ Adobe Campaign Standard":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="5dd9f-183">ดึงข้อมูลกลุ่มเป้าหมายใน Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="5dd9f-184">เมื่อนำเข้าข้อมูลไปยัง Adobe Campaign Standard แล้ว คุณ [สามารถสร้างเวิร์กโฟลว์](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) และ [การสอบถาม](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) ลูกค้าตาม *ชื่อเซ็กเมนต์* และ *วันที่ของเซ็กเมนต์* เพื่อเลือกโปรไฟล์ที่ระบุไว้สำหรับแคมเปญตัวอย่างของเรา</span><span class="sxs-lookup"><span data-stu-id="5dd9f-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="5dd9f-185">สร้างและส่งอีเมลโดยใช้ Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5dd9f-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="5dd9f-186">สร้างเนื้อหาอีเมลจากนั้น [ทดสอบและส่ง](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) อีเมลของคุณ</span><span class="sxs-lookup"><span data-stu-id="5dd9f-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="ตัวอย่างอีเมลพร้อมข้อเสนอการต่ออายุจาก Adobe Campaign Standard":::
