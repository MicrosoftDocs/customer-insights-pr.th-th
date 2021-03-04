---
title: ส่งออกข้อมูล Customer Insights ไปยังโฮสต์ SFTP
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับโฮสต์ SFTP
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268021"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="46972-103">ตัวเชื่อมต่อสำหรับ SFTP (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="46972-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="46972-104">ใช้ข้อมูลลูกค้าของคุณในแอปพลิเคชันของบริษัทภายนอกโดยการส่งออกข้อมูลไปยังโฮสต์ Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="46972-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46972-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="46972-105">Prerequisites</span></span>

- <span data-ttu-id="46972-106">ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลประจำตัวที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="46972-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="46972-107">เชื่อมต่อกับ SFTP</span><span class="sxs-lookup"><span data-stu-id="46972-107">Connect to SFTP</span></span>

1. <span data-ttu-id="46972-108">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="46972-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46972-109">ภายใต้ **SFTP** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="46972-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="46972-110">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="46972-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="46972-111">ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ</span><span class="sxs-lookup"><span data-stu-id="46972-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="46972-112">เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="46972-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="46972-113">หลังจากการตรวจสอบสำเร็จ ให้เลือกว่าคุณต้องการส่งออกข้อมูลของคุณแบบ **บีบอัดแบบ Gzip แล้ว** หรือ **คลายการบีบอัดแล้ว** และเลือก **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออก</span><span class="sxs-lookup"><span data-stu-id="46972-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="46972-114">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="46972-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46972-115">เลือก **ต่อไป** เพื่อเริ่มการกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="46972-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="46972-116">ตั้งค่าคอนฟิกการส่งออก</span><span class="sxs-lookup"><span data-stu-id="46972-116">Configure the export</span></span>

1. <span data-ttu-id="46972-117">เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="46972-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46972-118">เอนทิตีที่เลือกแต่ละรายการจะมีไฟล์ผลลัพธ์ไม่เกินห้าไฟล์ เมื่อส่งออก</span><span class="sxs-lookup"><span data-stu-id="46972-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="46972-119">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="46972-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="46972-120">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="46972-120">Export the data</span></span>

<span data-ttu-id="46972-121">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="46972-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="46972-122">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="46972-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46972-123">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="46972-123">Known limitations</span></span>

- <span data-ttu-id="46972-124">รันไทม์ของการส่งออกขึ้นอยู่กับประสิทธิภาพของระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="46972-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="46972-125">เราขอแนะนำให้ใช้ CPU core สองรายการและหน่วยความจำ 1 Gb เป็นการตั้งค่าคอนฟิกขั้นต่ำของเซิร์ฟเวอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="46972-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="46972-126">การส่งออกเอนทิตีที่มีโปรไฟล์ลูกค้ามากถึง 100 ล้านโปรไฟล์ อาจใช้เวลา 90 นาทีเมื่อใช้การตั้งค่าคอนฟิกขั้นต่ำที่แนะนำของ CPU core สองรายการและหน่วยความจำ 1 Gb</span><span class="sxs-lookup"><span data-stu-id="46972-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46972-127">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="46972-127">Data privacy and compliance</span></span>

<span data-ttu-id="46972-128">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="46972-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46972-129">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="46972-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="46972-130">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="46972-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46972-131">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="46972-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]