---
title: ส่งออกข้อมูล Customer Insights ไปยังโฮสต์ SFTP
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อและการส่งออกไปยังสถานที่ SFTP
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760442"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="55da8-103">ส่งออกรายการเซ็กเมนต์และข้อมูลอื่น ๆ ไปยัง SFTP (ตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="55da8-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="55da8-104">ใช้ข้อมูลลูกค้าของคุณในโปรแกรมประยุกต์ของบุคคลที่สามโดยส่งออกไปยังสถานที่ Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="55da8-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="55da8-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="55da8-105">Prerequisites for connection</span></span>

- <span data-ttu-id="55da8-106">ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลประจำตัวที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="55da8-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="55da8-107">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="55da8-107">Known limitations</span></span>

- <span data-ttu-id="55da8-108">รันไทม์ของการส่งออกขึ้นอยู่กับประสิทธิภาพของระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="55da8-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="55da8-109">เราขอแนะนำให้ใช้ CPU core สองรายการและหน่วยความจำ 1 Gb เป็นการตั้งค่าคอนฟิกขั้นต่ำของเซิร์ฟเวอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="55da8-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="55da8-110">การส่งออกเอนทิตีที่มีโปรไฟล์ลูกค้ามากถึง 100 ล้านโปรไฟล์ อาจใช้เวลา 90 นาทีเมื่อใช้การตั้งค่าคอนฟิกขั้นต่ำที่แนะนำของ CPU core สองรายการและหน่วยความจำ 1 Gb</span><span class="sxs-lookup"><span data-stu-id="55da8-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="55da8-111">ตั้งค่าการเชื่อมต่อไปยัง SFTP</span><span class="sxs-lookup"><span data-stu-id="55da8-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="55da8-112">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="55da8-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="55da8-113">เลือก **เพิ่มการเชื่อมต่อ** และเลือก **SFTP** เพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="55da8-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="55da8-114">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="55da8-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="55da8-115">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="55da8-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="55da8-116">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="55da8-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="55da8-117">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="55da8-117">Choose who can use this connection.</span></span> <span data-ttu-id="55da8-118">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="55da8-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="55da8-119">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="55da8-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="55da8-120">ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ</span><span class="sxs-lookup"><span data-stu-id="55da8-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="55da8-121">เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="55da8-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="55da8-122">เลือกว่าคุณต้องการส่งออก **บีบอัดแบบ Gzip แล้ว** ข้อมูลของคุณหรือ **คลายการบีบอัดแล้ว** และ **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออกหรือไม่</span><span class="sxs-lookup"><span data-stu-id="55da8-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="55da8-123">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="55da8-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="55da8-124">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="55da8-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="55da8-125">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="55da8-125">Configure an export</span></span>

<span data-ttu-id="55da8-126">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="55da8-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="55da8-127">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="55da8-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="55da8-128">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="55da8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="55da8-129">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="55da8-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="55da8-130">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SFTP</span><span class="sxs-lookup"><span data-stu-id="55da8-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="55da8-131">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="55da8-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="55da8-132">เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="55da8-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="55da8-133">แต่ละเอนทิตีที่เลือกจะถูกแบ่งออกเป็นไฟล์ผลลัพธ์สูงสุดห้าไฟล์เมื่อส่งออก</span><span class="sxs-lookup"><span data-stu-id="55da8-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="55da8-134">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="55da8-134">Select **Save**.</span></span>

<span data-ttu-id="55da8-135">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="55da8-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="55da8-136">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="55da8-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="55da8-137">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="55da8-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="55da8-138">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="55da8-138">Data privacy and compliance</span></span>

<span data-ttu-id="55da8-139">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="55da8-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="55da8-140">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="55da8-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="55da8-141">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="55da8-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="55da8-142">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="55da8-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
