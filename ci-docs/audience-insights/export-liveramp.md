---
title: ตัวเชื่อมต่อ LiveRamp
description: เรียนรู้วิธีส่งออกข้อมูลไปยัง LiveRamp
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270181"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="1f79e-103">ตัวเชื่อมต่อ LiveRamp&reg; (แสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="1f79e-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="1f79e-104">เริ่มการใช้งานข้อมูลของคุณใน LiveRamp เพื่อเชื่อมต่อกับแพลตฟอร์มมากกว่า 500 ระบบในระบบดิจิทัล สังคม และทีวี</span><span class="sxs-lookup"><span data-stu-id="1f79e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="1f79e-105">ทำงานกับข้อมูลของคุณใน LiveRamp เพื่อกำหนดเป้าหมาย ปราบปราม และปรับแต่งแคมเปญโฆษณา</span><span class="sxs-lookup"><span data-stu-id="1f79e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f79e-106">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="1f79e-106">Prerequisites</span></span>

- <span data-ttu-id="1f79e-107">คุณต้องสมัครใช้งาน LiveRamp เพื่อใช้ตัวเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="1f79e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="1f79e-108">เพื่อรับการสมัครใช้งาน [ติดต่อ LiveRamp](https://liveramp.com/contact/) โดยตรง</span><span class="sxs-lookup"><span data-stu-id="1f79e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="1f79e-109">[เรียนรู้เพิ่มเติมเกี่ยวกับวิธีการเริ่มทำงาน LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="1f79e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="1f79e-110">เชื่อมต่อกับ LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1f79e-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="1f79e-111">ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="1f79e-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1f79e-112">ในไทล์ **LiveRamp** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="1f79e-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="1f79e-113">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="1f79e-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1f79e-114">ใส่ **ชื่อผู้ใช้** และ **รหัสผ่าน** สำหรับบัญชี LiveRamp Secure FTP (SFTP) ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1f79e-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="1f79e-115">ข้อมูลประจำตัวเหล่านี้อาจแตกต่างจากข้อมูลประจำตัววิธีการเริ่มทำงาน LiveRamp ของคุณ</span><span class="sxs-lookup"><span data-stu-id="1f79e-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="1f79e-116">เลือก **ยืนยัน** เพื่อทดสอบการเชื่อมต่อกับ LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1f79e-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="1f79e-117">หลังจากการยืนยันสำเร็จ ให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="1f79e-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="1f79e-118">เลือก **ต่อไป** เพื่อตั้งค่าตัวเชื่อมต่อ LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1f79e-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1f79e-119">กำหนดค่าตัวเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="1f79e-119">Configure the connector</span></span>

1. <span data-ttu-id="1f79e-120">ในฟิลด์ **เลือกตัวระบุคีย์ของคุณ** เลือก **อีเมล**  **ชื่อและที่อยู่** หรือ **โทรศัพท์** เพื่อส่งไปยัง LiveRamp สำหรับการแก้ไขตัวตน</span><span class="sxs-lookup"><span data-stu-id="1f79e-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="1f79e-121">แมปแอตทริบิวต์ที่สอดคล้องกันจากเอนทิตีลูกค้าแบบรวมของคุณสำหรับตัวระบุคีย์ที่เลือก</span><span class="sxs-lookup"><span data-stu-id="1f79e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="1f79e-122">เลือก **เพิ่มแอตทริบิวต์** เพื่อแมปแอตทริบิวต์เพิ่มเติม เพื่อส่งไปยัง LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1f79e-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="1f79e-123">การส่งแอตทริบิวต์ตัวระบุคีย์เพิ่มเติมไปยัง LiveRamp มีแนวโน้มที่จะทำให้คุณได้รับอัตราการจับคู่ที่สูงขึ้น</span><span class="sxs-lookup"><span data-stu-id="1f79e-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="1f79e-124">เลือกเซ็กเมนต์ที่คุณต้องการส่งออกไปยัง LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1f79e-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="1f79e-125">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="1f79e-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f79e-126">![ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์](media/export-liveramp-segments.png "ตัวเชื่อมต่อ LiveRamp พร้อมการแมปแอตทริบิวต์")</span><span class="sxs-lookup"><span data-stu-id="1f79e-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1f79e-127">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1f79e-127">Export the data</span></span>

<span data-ttu-id="1f79e-128">การส่งออกจะเริ่มในไม่ช้า หากข้อกำหนดเบื้องต้นสำหรับการส่งออกเสร็จสมบูรณ์แล้ว</span><span class="sxs-lookup"><span data-stu-id="1f79e-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="1f79e-129">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="1f79e-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="1f79e-130">เมื่อการส่งออกเสร็จสมบูรณ์ คุณสามารถเข้าสู่วิธีการเริ่มทำงาน LiveRamp เพื่อเริ่มการใช้งานและเผยแพร่ข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="1f79e-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1f79e-131">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="1f79e-131">Data privacy and compliance</span></span>

<span data-ttu-id="1f79e-132">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง Liveramp คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="1f79e-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1f79e-133">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า Liveramp ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="1f79e-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1f79e-134">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="1f79e-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1f79e-135">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="1f79e-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]