---
title: ส่งออกข้อมูล Customer Insights ไปยังที่เก็บข้อมูล Azure Blob
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยังที่เก็บข้อมูล Blob
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976204"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="d198a-103">ส่งออกรายการเซ็กเมนต์และข้อมูลอื่น ๆ ไปยังที่เก็บข้อมูล Azure Blob (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="d198a-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="d198a-104">จัดเก็บข้อมูล Customer Insights ของคุณในที่เก็บข้อมูล Blob หรือใช้ในการย้ายข้อมูลไปยังแอปพลิเคชันอื่น</span><span class="sxs-lookup"><span data-stu-id="d198a-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="d198a-105">ตั้งค่าการเชื่อมต่อกับที่เก็บข้อมูล Blob</span><span class="sxs-lookup"><span data-stu-id="d198a-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="d198a-106">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="d198a-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d198a-107">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **ที่เก็บข้อมูล Azure Blob** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d198a-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="d198a-108">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="d198a-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d198a-109">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d198a-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d198a-110">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d198a-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d198a-111">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d198a-111">Choose who can use this connection.</span></span> <span data-ttu-id="d198a-112">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="d198a-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d198a-113">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="d198a-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d198a-114">ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับบัญชีที่เก็บข้อมูล Blob ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d198a-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="d198a-115">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Blob และรหัสบัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="d198a-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="d198a-116">หากต้องการเรียนรู้วิธีสร้างคอนเทนเนอร์ โปรดดู [สร้างคอนเทนเนอร์](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)</span><span class="sxs-lookup"><span data-stu-id="d198a-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d198a-117">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="d198a-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d198a-118">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="d198a-118">Configure an export</span></span>

<span data-ttu-id="d198a-119">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="d198a-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d198a-120">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="d198a-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d198a-121">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="d198a-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d198a-122">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="d198a-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d198a-123">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วนที่เก็บข้อมูล Azure Blob</span><span class="sxs-lookup"><span data-stu-id="d198a-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="d198a-124">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="d198a-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d198a-125">เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้</span><span class="sxs-lookup"><span data-stu-id="d198a-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="d198a-126">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="d198a-126">Select **Save**.</span></span>

<span data-ttu-id="d198a-127">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="d198a-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d198a-128">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="d198a-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="d198a-129">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="d198a-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="d198a-130">ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Blob ที่คุณกำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="d198a-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="d198a-131">เส้นทางโฟลเดอร์ต่อไปนี้จะถูกสร้างขึ้นโดยอัตโนมัติในคอนเทนเนอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d198a-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="d198a-132">สำหรับเอนทิตีต้นทางและเอนทิตีที่สร้างโดยระบบ: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="d198a-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="d198a-133">ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="d198a-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="d198a-134">model.json สำหรับเอนทิตีที่ส่งออกจะอยู่ที่ระดับ %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="d198a-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="d198a-135">ตัวอย่าง: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="d198a-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
