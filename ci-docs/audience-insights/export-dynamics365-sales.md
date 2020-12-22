---
title: ส่งออกข้อมูล Customer Insights ไปยัง Dynamics 365 Sales
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Dynamics 365 Sales
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643841"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="8cee0-103">ตัวเชื่อมต่อสำหรับ Dynamics 365 Sales (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="8cee0-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8cee0-104">ใช้ข้อมูลลูกค้าของคุณเพื่อสร้างรายชื่อเพื่อทำการตลาด ติดตามลำดับงาน และนำเสนอโปรโมชันด้วย Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="8cee0-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="8cee0-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="8cee0-105">Prerequisite</span></span>

<span data-ttu-id="8cee0-106">เรกคอร์ดผู้ติดต่อ [จาก Dynamics 365 Sales ที่นำเข้าโดยใช้ Common Data Service](connect-power-query.md)</span><span class="sxs-lookup"><span data-stu-id="8cee0-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="8cee0-107">กำหนดค่าตัวเชื่อมต่อสำหรับ Sales</span><span class="sxs-lookup"><span data-stu-id="8cee0-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="8cee0-108">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="8cee0-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8cee0-109">ภายใต้ **Dynamics 365 Sales** เลือก **ติดตั้ง**</span><span class="sxs-lookup"><span data-stu-id="8cee0-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="8cee0-110">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="8cee0-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8cee0-111">ป้อน URL Sales ขององค์กรของคุณในฟิลด์ **ที่อยู่เซิร์ฟเวอร์**</span><span class="sxs-lookup"><span data-stu-id="8cee0-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="8cee0-112">ในส่วน **บัญชีผู้ดูแลระบบเซิร์ฟเวอร์** ให้เลือก **เข้าสู่ระบบ** และเลือกบัญชี Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="8cee0-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="8cee0-113">แมปฟิลด์รหัสลูกค้ากับรหัสผู้ติดต่อ Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8cee0-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="8cee0-114">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="8cee0-114">Select **Next**.</span></span>

1. <span data-ttu-id="8cee0-115">เลือกเซ็กเมนต์อย่างน้อยหนึ่งเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="8cee0-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="8cee0-116">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="8cee0-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8cee0-117">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="8cee0-117">Export the data</span></span>

<span data-ttu-id="8cee0-118">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="8cee0-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8cee0-119">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="8cee0-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
