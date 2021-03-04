---
title: ส่งออกข้อมูล Customer Insights ไปยัง Facebook Ads Manager
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Facebook Ads Manager
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269997"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="e2420-103">ตัวเชื่อมต่อสำหรับ Facebook Ads Manager (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="e2420-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e2420-104">ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยัง Facebook Ads Manager เพื่อสร้างแคมเปญใน Facebook และ Instagram</span><span class="sxs-lookup"><span data-stu-id="e2420-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2420-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="e2420-105">Prerequisites</span></span>

- <span data-ttu-id="e2420-106">คุณต้องมี [**บัญชี Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ซึ่งรวมถึง [**บัญชี Facebook Business**](https://business.facebook.com/)</span><span class="sxs-lookup"><span data-stu-id="e2420-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e2420-107">คุณต้องเป็นผู้ดูแลระบบใน [**บัญชี Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)</span><span class="sxs-lookup"><span data-stu-id="e2420-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="e2420-108">เชื่อมต่อกับ Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="e2420-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="e2420-109">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="e2420-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e2420-110">ภายใต้ **Facebook Ads Manager** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="e2420-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="e2420-111">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางการส่งออกของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="e2420-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e2420-112">เลือก **ดำเนินการต่อด้วย Facebook** เพื่อเข้าสู่ระบบบัญชี Facebook Ad ของคุณ</span><span class="sxs-lookup"><span data-stu-id="e2420-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="e2420-113">อนุญาตสิทธิ์ **ads_management** หลังจากการรับรองความถูกต้องกับ Facebook</span><span class="sxs-lookup"><span data-stu-id="e2420-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="e2420-114">เลือก **บัญชี Facebook Ads** ที่คุณต้องการใช้งาน</span><span class="sxs-lookup"><span data-stu-id="e2420-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="e2420-115">เลือก **ผู้ชมแบบกำหนดเองที่มีอยู่** จากรายการแบบหล่นลง หรือสร้าง **ผู้ชมแบบกำหนดเองใหม่**</span><span class="sxs-lookup"><span data-stu-id="e2420-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e2420-116">สำหรับข้อมูลเพิ่มเติม โปรดดู [**ผู้ชมใน Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)</span><span class="sxs-lookup"><span data-stu-id="e2420-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="e2420-117">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="e2420-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e2420-118">เลือก **ต่อไป** เพื่อกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="e2420-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e2420-119">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="e2420-119">Configure the connector</span></span>

1. <span data-ttu-id="e2420-120">ใน **เลือกฟิลด์ตัวระบุคีย์ของคุณ** เลือก **อีเมล์** **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไป่ยัง Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="e2420-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="e2420-121">แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="e2420-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e2420-122">[เคล็ดลับ] โอกาสที่ดีที่สุดสำหรับการแข่งขันจะเกิดขึ้นหากคุณเลือก **อีเมล์** เป็นตัวระบุที่สำคัญ</span><span class="sxs-lookup"><span data-stu-id="e2420-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e2420-123">การเพิ่มตัวระบุเพิ่มเติมอาจช่วยปรับปรุงการจับคู่ให้ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="e2420-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e2420-124">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมที่จะส่งไปยัง Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="e2420-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e2420-125">แอตทริบิวต์จาก Facebook Ads Manager กำลังจับคู่กับชื่อที่เป็นมิตรต่อผู้ใช้: **FN** = **ชื่อ** **LN** = **นามสกุล** **FI** = **เริ่มต้นครั้งแรก** **โทรศัพท์** = **โทรศัพท์** **GEN** = **เพศ** **DOB** = **วันเกิด** **ST** = **สถานะ** **CT** = **เมือง** **ZIP** = **รหัสไปรษณีย์/รหัสไปรษณีย์** **ประเทศ** = **ประเทศ ภูมิภาค**</span><span class="sxs-lookup"><span data-stu-id="e2420-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e2420-126">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="e2420-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e2420-127">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="e2420-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e2420-128">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="e2420-128">Export the data</span></span>

<span data-ttu-id="e2420-129">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="e2420-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e2420-130">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="e2420-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e2420-131">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="e2420-131">Known limitations</span></span>

- <span data-ttu-id="e2420-132">โปรไฟล์ลูกค้ามากถึง 10 ล้านโปรไฟล์ต่อการส่งออกไปยังตัวจัดการโฆษณาบน Facebook</span><span class="sxs-lookup"><span data-stu-id="e2420-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="e2420-133">การส่งออกไปยังตัวจัดการโฆษณาบน Facebook ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="e2420-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="e2420-134">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 10 ล้านโปรไฟล์ อาจใช้เวลาถึง 90 นาทีในการทำให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="e2420-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2420-135">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="e2420-135">Data privacy and compliance</span></span>

<span data-ttu-id="e2420-136">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Facebook Ads Manager คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="e2420-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2420-137">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Facebook Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="e2420-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2420-138">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="e2420-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2420-139">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="e2420-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]