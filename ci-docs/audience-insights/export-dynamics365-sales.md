---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Sales
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Sales
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598132"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="156b7-103">ตัวเชื่อมต่อสำหรับ Dynamics 365 Sales (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="156b7-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="156b7-104">ใช้ข้อมูลลูกค้าของคุณเพื่อสร้างรายชื่อเพื่อทำการตลาด ติดตามลำดับงาน และนำเสนอโปรโมชันด้วย Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="156b7-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="156b7-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="156b7-105">Prerequisite</span></span>

1. <span data-ttu-id="156b7-106">ต้องมีเรกคอร์ดผู้ติดต่อใน Dynamics 365 Sales ก่อนที่คุณจะสามารถส่งออกเซ็กเมนต์จาก Customer Insights ไปยัง Sales ได้</span><span class="sxs-lookup"><span data-stu-id="156b7-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="156b7-107">อ่านเพิ่มเติมเกี่ยวกับวิธีการนำเข้าผู้ติดต่อใน [Dynamics 365 Sales โดยใช้ Common Data Services](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="156b7-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="156b7-108">การส่งออกเซ็กเมนต์จากข้อมูลเชิงลึกกลุ่มเป้าหมายไปยัง Sales จะไม่สร้างเรกคอร์ดผู้ติดต่อใหม่ในอินสแตนซ์ Sales</span><span class="sxs-lookup"><span data-stu-id="156b7-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="156b7-109">ต้องนำเข้าเรกคอร์ดผู้ติดต่อจาก Sales ในข้อมูลเชิงลึกกลุ่มเป้าหมาย และต้องใช้เป็นแหล่งข้อมูล</span><span class="sxs-lookup"><span data-stu-id="156b7-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="156b7-110">นอกจากนี้ ยังต้องรวมอยู่ในเอนทิตีลูกค้าแบบรวมเพื่อแม็ปรหัสลูกค้ากับรหัสผู้ติดต่อ ก่อนที่จะสามารถส่งออกเซ็กเมนต์ได้</span><span class="sxs-lookup"><span data-stu-id="156b7-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="156b7-111">กำหนดค่าตัวเชื่อมต่อสำหรับ Sales</span><span class="sxs-lookup"><span data-stu-id="156b7-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="156b7-112">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="156b7-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="156b7-113">ภายใต้ **Dynamics 365 Sales** เลือก **ติดตั้ง**</span><span class="sxs-lookup"><span data-stu-id="156b7-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="156b7-114">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="156b7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="156b7-115">ป้อน URL Sales ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="156b7-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="156b7-116">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="156b7-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="156b7-117">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="156b7-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="156b7-118">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="156b7-118">Select **Next**.</span></span>

1. <span data-ttu-id="156b7-119">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="156b7-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="156b7-120">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="156b7-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="156b7-121">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="156b7-121">Export the data</span></span>

<span data-ttu-id="156b7-122">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="156b7-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="156b7-123">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="156b7-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]