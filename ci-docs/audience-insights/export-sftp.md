---
title: ส่งออกข้อมูล Customer Insights ไปยังโฮสต์ SFTP
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับโฮสต์ SFTP
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643526"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="382b5-103">ตัวเชื่อมต่อสำหรับ SFTP (การแสดงตัวอย่าง)</span><span class="sxs-lookup"><span data-stu-id="382b5-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="382b5-104">ใช้ข้อมูลลูกค้าของคุณในแอปพลิเคชันของบริษัทภายนอกโดยการส่งออกข้อมูลไปยังโฮสต์ Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="382b5-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="382b5-105">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="382b5-105">Prerequisites</span></span>

- <span data-ttu-id="382b5-106">ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลรับรองที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="382b5-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="382b5-107">เชื่อมต่อกับ SFTP</span><span class="sxs-lookup"><span data-stu-id="382b5-107">Connect to SFTP</span></span>

1. <span data-ttu-id="382b5-108">ไปที่ **ผู้ดูแลระบบ** > **ปลายทางการส่งออก**</span><span class="sxs-lookup"><span data-stu-id="382b5-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="382b5-109">ภายใต้ **SFTP** เลือก **ตั้งค่า**</span><span class="sxs-lookup"><span data-stu-id="382b5-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="382b5-110">ตั้งชื่อที่เป็นที่รู้จักให้ปลายทางของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="382b5-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="382b5-111">ระบุ **ชื่อผู้ใช้**, **รหัสผ่าน** และ **ชื่อโฮสต์** สำหรับบัญชี SFTP ของคุณ</span><span class="sxs-lookup"><span data-stu-id="382b5-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="382b5-112">ตัวอย่าง: หากโฟลเดอร์รากของเซิร์ฟเวอร์ SFTP ของคุณคือ /root/folder และคุณต้องการส่งออกข้อมูลไปยัง /root/folder/ci_export_destination_folder โฮสต์ควรเป็น sftp://<server_address>/ci_export_destination_folder"</span><span class="sxs-lookup"><span data-stu-id="382b5-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="382b5-113">เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="382b5-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="382b5-114">หลังจากการยืนยันสำเร็จ ให้เลือกว่าคุณต้องการส่งออกข้อมูลของคุณเป็น **ที่บีบอัด** หรือ **ที่ไม่ได้บีบอัด** และเลือก **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออก</span><span class="sxs-lookup"><span data-stu-id="382b5-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="382b5-115">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="382b5-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="382b5-116">เลือก **ต่อไป** เพื่อเริ่มการกำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="382b5-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="382b5-117">กำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="382b5-117">Configure the connection</span></span>

1. <span data-ttu-id="382b5-118">เลือก **แอตทริบิวต์ลูกค้า** ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="382b5-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="382b5-119">คุณสามารถส่งออกหนึ่งหรือหลายแอตทริบิวต์</span><span class="sxs-lookup"><span data-stu-id="382b5-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="382b5-120">เลือก **ถัดไป**</span><span class="sxs-lookup"><span data-stu-id="382b5-120">Select **Next**.</span></span>

1. <span data-ttu-id="382b5-121">เลือกเซ็กเมนต์ที่คุณต้องการส่งออก</span><span class="sxs-lookup"><span data-stu-id="382b5-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="382b5-122">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="382b5-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="382b5-123">ส่งออกข้อมูล</span><span class="sxs-lookup"><span data-stu-id="382b5-123">Export the data</span></span>

<span data-ttu-id="382b5-124">คุณมาสารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md)</span><span class="sxs-lookup"><span data-stu-id="382b5-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="382b5-125">นอกจากนี้ การส่งออกยังจะทำงานพร้อมกับ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) ทุกครั้ง</span><span class="sxs-lookup"><span data-stu-id="382b5-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="382b5-126">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="382b5-126">Data privacy and compliance</span></span>

<span data-ttu-id="382b5-127">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="382b5-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="382b5-128">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="382b5-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="382b5-129">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="382b5-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="382b5-130">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณเอาปลายทางการส่งออกเมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="382b5-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
