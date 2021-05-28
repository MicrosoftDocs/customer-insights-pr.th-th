---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Synapse Analytics
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อไปยัง Azure Synapse Analytics
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977400"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="eba28-103">ส่งออกข้อมูลไปยัง Azure Synapse Analytics (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="eba28-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="eba28-104">Azure Synapse เป็นบริการวิเคราะห์ที่ช่วยเร่งเวลาไปยังข้อมูลเชิงลึกในคลังข้อมูลและระบบข้อมูลขนาดใหญ่</span><span class="sxs-lookup"><span data-stu-id="eba28-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="eba28-105">คุณนำเข้าและใช้ข้อมูล Customer Insights ได้ใน [Azure Synapse](/azure/synapse-analytics/overview-what-is)</span><span class="sxs-lookup"><span data-stu-id="eba28-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eba28-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="eba28-106">Prerequisites</span></span>

<span data-ttu-id="eba28-107">ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้เพื่อตั้งค่าคอนฟิกการเชื่อมต่อจาก Customer Insights ไปยัง Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="eba28-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="eba28-108">อย่าลืมตั้งค่า **การกำหนดบทบาท** ทั้งหมดตามที่อธิบายไว้</span><span class="sxs-lookup"><span data-stu-id="eba28-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="eba28-109">ข้อกำหนดเบื้องต้นใน Customer Insights</span><span class="sxs-lookup"><span data-stu-id="eba28-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="eba28-110">คุณมีบทบาท **ผู้ดูแลระบบ** ในข้อมูลเชิงลึกของผู้ชม</span><span class="sxs-lookup"><span data-stu-id="eba28-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="eba28-111">เรียนรู้เพิ่มเติมเกี่ยวกับ [การตั้งค่าสิทธิ์ผู้ใช้ในข้อมูลเชิงลึกของผู้ชม](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="eba28-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="eba28-112">ใน Azure:</span><span class="sxs-lookup"><span data-stu-id="eba28-112">In Azure:</span></span> 

- <span data-ttu-id="eba28-113">การสมัครใช้งาน Azure ที่ใช้งานอยู่</span><span class="sxs-lookup"><span data-stu-id="eba28-113">An active Azure subscription.</span></span>

- <span data-ttu-id="eba28-114">หากใช้บัญชี Azure Data Lake Storage Gen2 ใหม่ *หลักบริการสำหรับข้อมูลเชิงลึกของผู้ชม* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ**</span><span class="sxs-lookup"><span data-stu-id="eba28-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="eba28-115">เรียนรู้เพิ่มเติมเกี่ยวกับ [การเชื่อมต่อกับบัญชี Azure Data Lake Storage Gen2 ที่มีหลักบริการของ Azure สำหรับข้อมูลเชิงลึกของผู้ชม](connect-service-principal.md)</span><span class="sxs-lookup"><span data-stu-id="eba28-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="eba28-116">Data Lake Storage Gen2 **จำเป็นต้อง** เปิดใช้งาน [เนมสเปซตามลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)</span><span class="sxs-lookup"><span data-stu-id="eba28-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="eba28-117">ในกลุ่มทรัพยากรที่พื้นที่ทำงาน Azure Synapse ตั้งอยู่ *หลักบริการ* และ *ผู้ใช้สำหรับข้อมูลเชิงลึกของผู้ชม* ต้องได้รับมอบหมายสิทธิ์ **ผู้อ่าน** เป็นอย่างน้อย</span><span class="sxs-lookup"><span data-stu-id="eba28-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="eba28-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)</span><span class="sxs-lookup"><span data-stu-id="eba28-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="eba28-119">*ผู้ใช้* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="eba28-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="eba28-120">เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)</span><span class="sxs-lookup"><span data-stu-id="eba28-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="eba28-121">*[ข้อมูลประจำตัวที่มีการจัดการของพื้นที่ทำงาน Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="eba28-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="eba28-122">เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)</span><span class="sxs-lookup"><span data-stu-id="eba28-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="eba28-123">บนพื้นที่ทำงาน Azure Synapse *หลักบริการสำหรับข้อมูลเชิงลึกของผู้ชม* ต้องการบทบาท **ผู้ดูแลระบบ Synapse** ที่ได้รับมอบหมาย</span><span class="sxs-lookup"><span data-stu-id="eba28-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="eba28-124">สำหรับข้อมูลเพิ่มเติม โปรดดู [วิธีตั้งค่าการควบคุมการเข้าถึงสำหรับพื้นที่ทำงาน Synapse ของคุณ](/azure/synapse-analytics/security/how-to-set-up-access-control)</span><span class="sxs-lookup"><span data-stu-id="eba28-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="eba28-125">ตั้งค่าการเชื่อมต่อและส่งออกไปยัง Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="eba28-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="eba28-126">กำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="eba28-126">Configure a connection</span></span>

1. <span data-ttu-id="eba28-127">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="eba28-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eba28-128">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Synapse Analytics** หรือเลือก **การตั้งค่า** บนไทล์ **Azure Synapse Analytics** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="eba28-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="eba28-129">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ ชื่อที่แสดง</span><span class="sxs-lookup"><span data-stu-id="eba28-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="eba28-130">ชื่อและชนิดของการเชื่อมต่อจะอธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="eba28-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="eba28-131">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="eba28-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eba28-132">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="eba28-132">Choose who can use this connection.</span></span> <span data-ttu-id="eba28-133">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="eba28-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="eba28-134">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="eba28-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="eba28-135">เลือกหรือค้นหาการสมัครใช้งานที่คุณต้องการใช้ข้อมูล Customer Insights ในนั้น</span><span class="sxs-lookup"><span data-stu-id="eba28-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="eba28-136">ทันทีที่เลือกการสมัครใช้งาน คุณยังสามารถเลือก **พื้นที่ทำงาน**, **บัญชีที่เก็บข้อมูล** และ **คอนเทนเนอร์** ได้ด้วย</span><span class="sxs-lookup"><span data-stu-id="eba28-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="eba28-137">ให้เลือก **บันทึก** เพื่อบันทึกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="eba28-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="eba28-138">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="eba28-138">Configure an export</span></span>

<span data-ttu-id="eba28-139">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="eba28-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="eba28-140">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการตั้งค่าคอนฟิกการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="eba28-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eba28-141">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="eba28-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eba28-142">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="eba28-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="eba28-143">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน **Azure Synapse Analytics**</span><span class="sxs-lookup"><span data-stu-id="eba28-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="eba28-144">หากคุณไม่เห็นชื่อส่วนนี้ ไม่มี [การเชื่อมต่อ](connections.md) ชนิดนี้ที่พร้อมใช้งานสำหรับคุณ</span><span class="sxs-lookup"><span data-stu-id="eba28-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="eba28-145">ระบุ **ชื่อที่แสดง** ที่เป็นที่รู้จักสำหรับการส่งออกของคุณ และ **ชื่อฐานข้อมูล**</span><span class="sxs-lookup"><span data-stu-id="eba28-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="eba28-146">เลือกเอนทิตีที่คุณต้องการส่งออกไปยัง Azure Synapse Analytics</span><span class="sxs-lookup"><span data-stu-id="eba28-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="eba28-147">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="eba28-147">Select **Save**.</span></span>

<span data-ttu-id="eba28-148">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="eba28-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eba28-149">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="eba28-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eba28-150">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="eba28-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="eba28-151">อัปเดตการส่งออก</span><span class="sxs-lookup"><span data-stu-id="eba28-151">Update an export</span></span>

1. <span data-ttu-id="eba28-152">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="eba28-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eba28-153">เลือก **แก้ไข** ในการส่งออกที่คุณต้องการอัปเดต</span><span class="sxs-lookup"><span data-stu-id="eba28-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="eba28-154">**เพิ่ม** หรือ **ลบ** เอนทิตีจากการเลือก</span><span class="sxs-lookup"><span data-stu-id="eba28-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="eba28-155">หากเอนทิตีถูกลบออกจากการเลือก เอนทิตีจะไม่ถูกลบออกจากฐานข้อมูล Synapse Analytics</span><span class="sxs-lookup"><span data-stu-id="eba28-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="eba28-156">อย่างไรก็ตาม การรีเฟรชข้อมูลในอนาคตจะไม่อัปเดตเอนทิตีที่ถูกลบออกในฐานข้อมูลนั้น</span><span class="sxs-lookup"><span data-stu-id="eba28-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="eba28-157">**การเปลี่ยนชื่อฐานข้อมูล** สร้างฐานข้อมูล Synapse Analytics ใหม่</span><span class="sxs-lookup"><span data-stu-id="eba28-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="eba28-158">ฐานข้อมูลที่มีชื่อที่ตั้งค่าคอนฟิกไว้ก่อน จะไม่ได้รับการอัปเดตใดๆ ในการรีเฟรชในอนาคต</span><span class="sxs-lookup"><span data-stu-id="eba28-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
