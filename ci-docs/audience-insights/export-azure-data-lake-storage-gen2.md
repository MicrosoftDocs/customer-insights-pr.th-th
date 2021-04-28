---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Data Lake Storage Gen2
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ Azure Data Lake Storage Gen2
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760074"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1d437-103">ตั้งค่าการเชื่อมต่อกับ Azure Data Lake Storage Gen2 (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="1d437-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="1d437-104">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="1d437-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1d437-105">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Data Lake Gen 2** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1d437-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="1d437-106">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="1d437-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1d437-107">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="1d437-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1d437-108">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1d437-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1d437-109">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="1d437-109">Choose who can use this connection.</span></span> <span data-ttu-id="1d437-110">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="1d437-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1d437-111">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="1d437-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1d437-112">ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับ Azure Data Lake Storage Gen2 ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1d437-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1d437-113">หากต้องการเรียนรู้วิธีสร้างบัญชีที่เก็บข้อมูลที่จะใช้กับ Azure Data Lake Storage Gen2 ดู [สร้างบัญชีที่เก็บข้อมูล](/azure/storage/blobs/create-data-lake-storage-account)</span><span class="sxs-lookup"><span data-stu-id="1d437-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1d437-114">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับชื่อบัญชีที่เก็บข้อมูล Azure Data Lake Gen 2 และรหัสบัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="1d437-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1d437-115">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="1d437-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1d437-116">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="1d437-116">Configure an export</span></span>

<span data-ttu-id="1d437-117">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="1d437-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1d437-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="1d437-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1d437-119">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="1d437-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1d437-120">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="1d437-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1d437-121">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน **Azure Data Lake**</span><span class="sxs-lookup"><span data-stu-id="1d437-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="1d437-122">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="1d437-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1d437-123">เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้</span><span class="sxs-lookup"><span data-stu-id="1d437-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1d437-124">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="1d437-124">Select **Save**.</span></span>

<span data-ttu-id="1d437-125">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="1d437-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1d437-126">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="1d437-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1d437-127">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="1d437-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="1d437-128">ข้อมูลที่ส่งออกจะถูกเก็บไว้ในที่เก็บข้อมูล Azure Data Lake Gen 2 ที่คุณกำหนดค่าไว้</span><span class="sxs-lookup"><span data-stu-id="1d437-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
