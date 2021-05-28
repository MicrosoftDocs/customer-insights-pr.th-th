---
title: ส่งออกข้อมูล Customer Insights ไปยัง Facebook Ads Manager
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยังตัวจัดการโฆษณาบน Facebook
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976065"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="645a3-103">ส่งออกรายการเซ็กเมนต์ไปที่ตัวจัดการโฆษณาบน Facebook (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="645a3-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="645a3-104">ส่งออกส่วนของโปรไฟล์ลูกค้าแบบรวมไปยัง Facebook Ads Manager เพื่อสร้างแคมเปญใน Facebook และ Instagram</span><span class="sxs-lookup"><span data-stu-id="645a3-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="645a3-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="645a3-105">Prerequisites for connection</span></span>

- <span data-ttu-id="645a3-106">คุณจําเป็นต้องมี [**บัญชีโฆษณา Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ซึ่งมี [**บัญชีธุรกิจ Facebook**](https://business.facebook.com/)</span><span class="sxs-lookup"><span data-stu-id="645a3-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="645a3-107">คุณต้องเป็นผู้ดูแลระบบใน [**บัญชี Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)</span><span class="sxs-lookup"><span data-stu-id="645a3-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="645a3-108">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="645a3-108">Known limitations</span></span>

- <span data-ttu-id="645a3-109">โปรไฟล์ลูกค้ามากถึง 10 ล้านโปรไฟล์ต่อการส่งออกไปยังตัวจัดการโฆษณาบน Facebook</span><span class="sxs-lookup"><span data-stu-id="645a3-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="645a3-110">การส่งออกไปยังตัวจัดการโฆษณาบน Facebook ถูกจำกัดเฉพาะเซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="645a3-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="645a3-111">สร้างหรืออัปเดตผู้ชมที่กำหนดเองใน Facebook ของชนิด *รายชื่อลูกค้า* เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="645a3-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="645a3-112">การส่งออกเซ็กเมนต์ที่มีโปรไฟล์ทั้งหมด 10 ล้านโปรไฟล์ อาจใช้เวลาถึง 90 นาทีในการทำให้เสร็จสมบูรณ์</span><span class="sxs-lookup"><span data-stu-id="645a3-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="645a3-113">ตั้งค่าการเชื่อมต่อกับตัวจัดการโฆษณาบน Facebook</span><span class="sxs-lookup"><span data-stu-id="645a3-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="645a3-114">ก่อนที่ผู้ใช้จะสามารถสร้างการส่งออก ผู้ดูแลระบบต้องกำหนดค่าการเชื่อมต่อกับบริการและอนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="645a3-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="645a3-115">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="645a3-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="645a3-116">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **ตัวจัดการโฆษณาบน Facebook** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="645a3-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="645a3-117">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="645a3-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="645a3-118">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="645a3-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="645a3-119">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="645a3-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="645a3-120">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="645a3-120">Choose who can use this connection.</span></span> <span data-ttu-id="645a3-121">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็น **ผู้ดูแลระบบ**</span><span class="sxs-lookup"><span data-stu-id="645a3-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="645a3-122">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="645a3-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="645a3-123">รับรองความถูกต้องด้วยโฆษณา Facebook:</span><span class="sxs-lookup"><span data-stu-id="645a3-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="645a3-124">เลือก **ดำเนินการต่อด้วย Facebook** เพื่อเข้าสู่ระบบบัญชี Facebook Ad ของคุณ</span><span class="sxs-lookup"><span data-stu-id="645a3-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="645a3-125">อนุญาตสิทธิ์ **ads_management** หลังจากการรับรองความถูกต้องกับ Facebook</span><span class="sxs-lookup"><span data-stu-id="645a3-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="645a3-126">เลือก **บัญชี Facebook Ads** ที่คุณต้องการใช้งาน</span><span class="sxs-lookup"><span data-stu-id="645a3-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="645a3-127">เลือก **ผู้ชมแบบกำหนดเองที่มีอยู่** จากรายการแบบหล่นลง หรือสร้าง **ผู้ชมแบบกำหนดเองใหม่**</span><span class="sxs-lookup"><span data-stu-id="645a3-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="645a3-128">สำหรับข้อมูลเพิ่มเติม โปรดดู [**ผู้ชมใน Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)</span><span class="sxs-lookup"><span data-stu-id="645a3-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="645a3-129">คุณสามารถสร้างหรืออัปเดตผู้ชมที่กำหนดเองบน Facebook ของชนิด *รายชื่อลูกค้า* ด้วยการส่งออกนี้เท่านั้น</span><span class="sxs-lookup"><span data-stu-id="645a3-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="645a3-130">ในบางกรณี คุณจะเห็นกลุ่มเป้าหมายที่กำหนดเอชนิดต่าง ๆ ในรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="645a3-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="645a3-131">การเลือกชนิดที่แตกต่างจาก *รายชื่อลูกค้า* จะส่งผลให้การส่งออกล้มเหลว</span><span class="sxs-lookup"><span data-stu-id="645a3-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="645a3-132">ตรวจสอบ **ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล** และเลือก **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="645a3-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="645a3-133">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="645a3-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="645a3-134">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="645a3-134">Configure an export</span></span>

<span data-ttu-id="645a3-135">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="645a3-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="645a3-136">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="645a3-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="645a3-137">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="645a3-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="645a3-138">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="645a3-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="645a3-139">ใน **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน **ตัวจัดการโฆษณาบน Facebook**</span><span class="sxs-lookup"><span data-stu-id="645a3-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="645a3-140">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="645a3-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="645a3-141">ใน **เลือกฟิลด์ตัวระบุคีย์ของคุณ** เลือก **อีเมล์** **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไป่ยัง Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="645a3-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="645a3-142">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="645a3-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="645a3-143">แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="645a3-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="645a3-144">[เคล็ดลับ] โอกาสที่ดีที่สุดสำหรับการแข่งขันจะเกิดขึ้นหากคุณเลือก **อีเมล์** เป็นตัวระบุที่สำคัญ</span><span class="sxs-lookup"><span data-stu-id="645a3-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="645a3-145">การเพิ่มตัวระบุเพิ่มเติมอาจช่วยปรับปรุงการจับคู่ให้ดีขึ้น</span><span class="sxs-lookup"><span data-stu-id="645a3-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="645a3-146">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมเพื่อส่งไปยังตัวจัดการโฆษณาบน Facebook</span><span class="sxs-lookup"><span data-stu-id="645a3-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="645a3-147">แอตทริบิวต์จาก Facebook Ads Manager กำลังจับคู่กับชื่อที่เป็นมิตรต่อผู้ใช้: **FN** = **ชื่อ** **LN** = **นามสกุล** **FI** = **เริ่มต้นครั้งแรก** **โทรศัพท์** = **โทรศัพท์** **GEN** = **เพศ** **DOB** = **วันเกิด** **ST** = **สถานะ** **CT** = **เมือง** **ZIP** = **รหัสไปรษณีย์/รหัสไปรษณีย์** **ประเทศ** = **ประเทศ ภูมิภาค**</span><span class="sxs-lookup"><span data-stu-id="645a3-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="645a3-148">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="645a3-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="645a3-149">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="645a3-149">Select **Save**.</span></span>

<span data-ttu-id="645a3-150">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="645a3-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="645a3-151">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="645a3-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="645a3-152">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="645a3-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="645a3-153">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="645a3-153">Data privacy and compliance</span></span>

<span data-ttu-id="645a3-154">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights เพื่อส่งข้อมูลไปยัง Facebook Ads Manager คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="645a3-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="645a3-155">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Facebook Ads ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="645a3-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="645a3-156">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="645a3-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="645a3-157">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="645a3-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
