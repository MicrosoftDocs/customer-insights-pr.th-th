---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Data Lake Storage Gen2
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อกับ Azure Data Lake Storage Gen2
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596665"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="4652f-103">ตัวเชื่อมต่อสำหรับ Azure Data Lake Storage Gen2 (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="4652f-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="4652f-104">จัดเก็บข้อมูล Customer Insights ของคุณใน Azure Data Lake Storage Gen2 หรือใช้ในการย้ายข้อมูลของคุณไปยังแอปพลิเคชันอื่น</span><span class="sxs-lookup"><span data-stu-id="4652f-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="4652f-105">ตั้งค่าคอนฟิกตัวเชื่อมต่อสำหรับ Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="4652f-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="4652f-106">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="4652f-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4652f-107">ภายใต้ **Azure Data Lake Storage Gen2** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="4652f-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="4652f-108">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="4652f-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4652f-109">ป้อน **ชื่อบัญชี** **รหัสบัญชี** และ **คอนเทนเนอร์** สำหรับ Azure Data Lake Storage Gen2 ของคุณ</span><span class="sxs-lookup"><span data-stu-id="4652f-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="4652f-110">หากต้องการเรียนรู้วิธีสร้างบัญชีที่เก็บข้อมูลที่จะใช้กับ Azure Data Lake Storage Gen2 ดู [สร้างบัญชีที่เก็บข้อมูล](/azure/storage/blobs/create-data-lake-storage-account)</span><span class="sxs-lookup"><span data-stu-id="4652f-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="4652f-111">หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีค้นหาชื่อบัญชีที่เก็บข้อมูล Azure Data Lake Gen2 และรหัสบัญชี โปรดดู [จัดการการตั้งค่าบัญชีที่เก็บข้อมูลในพอร์ทัล Azure](/azure/storage/common/storage-account-manage)</span><span class="sxs-lookup"><span data-stu-id="4652f-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="4652f-112">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="4652f-112">Select **Next**.</span></span>

1. <span data-ttu-id="4652f-113">เลือกกล่องถัดจากแต่ละเอนทิตีที่คุณต้องการส่งออกไปยังปลายทางนี้</span><span class="sxs-lookup"><span data-stu-id="4652f-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="4652f-114">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="4652f-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4652f-115">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="4652f-115">Export the data</span></span>

<span data-ttu-id="4652f-116">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#export-data-on-demand)</span><span class="sxs-lookup"><span data-stu-id="4652f-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="4652f-117">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="4652f-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>