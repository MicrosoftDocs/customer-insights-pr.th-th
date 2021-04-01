---
title: ส่งออกข้อมูล Customer Insights ไปยังโฮสต์ SFTP
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับโฮสต์ SFTP
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598408"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="69407-103">ตัวเชื่อมต่อสำหรับ SFTP (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="69407-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="69407-104">ใช้ข้อมูลลูกค้าของคุณในแอปพลิเคชันของบริษัทภายนอกโดยการส่งออกข้อมูลไปยังโฮสต์ Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="69407-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69407-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="69407-105">Prerequisites</span></span>

- <span data-ttu-id="69407-106">ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลประจำตัวที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="69407-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="69407-107">เชื่อมต่อกับ SFTP</span><span class="sxs-lookup"><span data-stu-id="69407-107">Connect to SFTP</span></span>

1. <span data-ttu-id="69407-108">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="69407-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="69407-109">ภายใต้ **SFTP** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="69407-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="69407-110">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="69407-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="69407-111">ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ</span><span class="sxs-lookup"><span data-stu-id="69407-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="69407-112">เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="69407-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="69407-113">หลังจากการตรวจสอบสำเร็จ ให้เลือกว่าคุณต้องการส่งออกข้อมูลของคุณแบบ **บีบอัดแบบ Gzip แล้ว** หรือ **คลายการบีบอัดแล้ว** และเลือก **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออก</span><span class="sxs-lookup"><span data-stu-id="69407-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="69407-114">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="69407-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="69407-115">เลือก **ต่อไป** เพื่อเริ่มการกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="69407-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="69407-116">ตั้งค่าคอนฟิกการส่งออก</span><span class="sxs-lookup"><span data-stu-id="69407-116">Configure the export</span></span>

1. <span data-ttu-id="69407-117">เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="69407-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="69407-118">เอนทิตีที่เลือกแต่ละรายการจะมีไฟล์ผลลัพธ์ไม่เกินห้าไฟล์ เมื่อส่งออก</span><span class="sxs-lookup"><span data-stu-id="69407-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="69407-119">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="69407-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="69407-120">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="69407-120">Export the data</span></span>

<span data-ttu-id="69407-121">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="69407-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="69407-122">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="69407-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="69407-123">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="69407-123">Known limitations</span></span>

- <span data-ttu-id="69407-124">รันไทม์ของการส่งออกขึ้นอยู่กับประสิทธิภาพของระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="69407-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="69407-125">เราขอแนะนำให้ใช้ CPU core สองรายการและหน่วยความจำ 1 Gb เป็นการตั้งค่าคอนฟิกขั้นต่ำของเซิร์ฟเวอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="69407-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="69407-126">การส่งออกเอนทิตีที่มีโปรไฟล์ลูกค้ามากถึง 100 ล้านโปรไฟล์ อาจใช้เวลา 90 นาทีเมื่อใช้การตั้งค่าคอนฟิกขั้นต่ำที่แนะนำของ CPU core สองรายการและหน่วยความจำ 1 Gb</span><span class="sxs-lookup"><span data-stu-id="69407-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="69407-127">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="69407-127">Data privacy and compliance</span></span>

<span data-ttu-id="69407-128">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="69407-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="69407-129">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="69407-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="69407-130">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="69407-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="69407-131">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="69407-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]