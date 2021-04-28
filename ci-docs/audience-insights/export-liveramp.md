---
title: ตัวเชื่อมต่อ LiveRamp
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยัง LiveRamp
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760350"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="d5e0e-103">ส่งออกเซ็กเมนต์ไปยัง LiveRamp&reg; (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="d5e0e-104">เริ่มการใช้งานข้อมูลของคุณใน LiveRamp เพื่อเชื่อมต่อกับแพลตฟอร์มมากกว่า 500 แพลตฟอร์มทั้งดิจิทัล โซเชียล และทีวี</span><span class="sxs-lookup"><span data-stu-id="d5e0e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="d5e0e-105">ทำงานกับข้อมูลของคุณใน LiveRamp เพื่อกำหนดเป้าหมาย ปราบปราม และปรับแต่งแคมเปญโฆษณา</span><span class="sxs-lookup"><span data-stu-id="d5e0e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d5e0e-106">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="d5e0e-107">คุณต้องสมัครใช้งาน LiveRamp เพื่อใช้ตัวเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d5e0e-108">เพื่อรับการสมัครใช้งาน [ติดต่อ LiveRamp](https://liveramp.com/contact/) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="d5e0e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d5e0e-109">[เรียนรู้เพิ่มเติมเกี่ยวกับวิธีการเริ่มทำงาน LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d5e0e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="d5e0e-110">ตั้งค่าการเชื่อมต่อไปยัง LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d5e0e-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="d5e0e-111">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d5e0e-112">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **LiveRamp** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="d5e0e-113">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d5e0e-114">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d5e0e-115">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d5e0e-116">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-116">Choose who can use this connection.</span></span> <span data-ttu-id="d5e0e-117">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d5e0e-118">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d5e0e-119">ใส่ **ชื่อผู้ใช้** และ **รหัสผ่าน** สำหรับบัญชี LiveRamp Secure FTP (SFTP) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d5e0e-120">ข้อมูลประจำตัวเหล่านี้อาจแตกต่างจากข้อมูลประจำตัววิธีการเริ่มทำงาน LiveRamp ของคุณ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d5e0e-121">เลือก **ยืนยัน** เพื่อทดสอบการเชื่อมต่อกับ LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d5e0e-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d5e0e-122">หลังจากการยืนยันสำเร็จ ให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d5e0e-123">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="d5e0e-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d5e0e-124">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="d5e0e-124">Configure an export</span></span>

<span data-ttu-id="d5e0e-125">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d5e0e-126">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d5e0e-127">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d5e0e-128">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d5e0e-129">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d5e0e-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="d5e0e-130">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d5e0e-131">ในฟิลด์ **เลือกตัวระบุคีย์ของคุณ** เลือก **อีเมล**  **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไปยัง LiveRamp สำหรับการแก้ไขตัวตน</span><span class="sxs-lookup"><span data-stu-id="d5e0e-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d5e0e-132">![ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์](media/export-liveramp-segments.png "ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์")</span><span class="sxs-lookup"><span data-stu-id="d5e0e-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="d5e0e-133">แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="d5e0e-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d5e0e-134">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติมเพื่อส่งไปยัง LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d5e0e-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d5e0e-135">การส่งแอตทริบิวต์ตัวระบุคีย์เพิ่มเติมไปยัง LiveRamp มีแนวโน้มที่จะทำให้คุณได้รับอัตราการจับคู่ที่สูงขึ้น</span><span class="sxs-lookup"><span data-stu-id="d5e0e-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d5e0e-136">เลือกเซ็กเมนต์ที่คุณต้องการส่งออกไปยัง LiveRamp</span><span class="sxs-lookup"><span data-stu-id="d5e0e-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d5e0e-137">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="d5e0e-137">Select **Save**.</span></span>

<span data-ttu-id="d5e0e-138">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="d5e0e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d5e0e-139">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d5e0e-140">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d5e0e-141">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="d5e0e-141">Data privacy and compliance</span></span>

<span data-ttu-id="d5e0e-142">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Liveramp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="d5e0e-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d5e0e-143">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Liveramp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="d5e0e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d5e0e-144">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d5e0e-145">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="d5e0e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
