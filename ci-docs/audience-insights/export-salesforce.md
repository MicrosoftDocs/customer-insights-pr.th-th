---
title: ส่งออกข้อมูล Customer Insights ไปยัง Salesforce Marketing Cloud
description: เรียนรู้วิธีการตั้งค่าคอนฟิกการเชื่อมต่อและส่งออกไปยัง Salesforce Marketing Cloud
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314684"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="f70a3-103">ส่งออกเซ็กเมนต์และข้อมูลอื่นๆ ไปยัง Salesforce Marketing Cloud (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="f70a3-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="f70a3-104">ใช้ข้อมูลลูกค้าของคุณใน Salesforce Marketing Cloud โดยส่งออกผ่านตำแหน่ง Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="f70a3-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f70a3-105">ข้อกำหนดเบื้องต้นสำหรับการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f70a3-105">Prerequisites for connection</span></span>

- <span data-ttu-id="f70a3-106">ความพร้อมใช้งานของโฮสต์ SFTP และข้อมูลประจำตัวของผู้ดูแลระบบที่เกี่ยวข้อง</span><span class="sxs-lookup"><span data-stu-id="f70a3-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="f70a3-107">วิธีตั้งค่าตำแหน่ง SFTP สำหรับ Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f70a3-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="f70a3-108">ข้อจำกัดที่ทราบ</span><span class="sxs-lookup"><span data-stu-id="f70a3-108">Known limitations</span></span>

- <span data-ttu-id="f70a3-109">รันไทม์ของการส่งออกขึ้นอยู่กับประสิทธิภาพของระบบของคุณ</span><span class="sxs-lookup"><span data-stu-id="f70a3-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="f70a3-110">เราขอแนะนำให้ใช้ CPU core สองรายการและหน่วยความจำ 1 Gb เป็นการตั้งค่าคอนฟิกขั้นต่ำของเซิร์ฟเวอร์ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f70a3-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="f70a3-111">การส่งออกเอนทิตีที่มีโปรไฟล์ลูกค้าสูงถึง 100 ล้านโปรไฟล์อาจใช้เวลา 90 นาที เมื่อใช้การตั้งค่าคอนฟิกขั้นต่ำที่แนะนำ</span><span class="sxs-lookup"><span data-stu-id="f70a3-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="f70a3-112">ตั้งค่าการเชื่อมต่อกับ Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f70a3-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f70a3-113">ไปที่ **การจัดการ** > **การเชื่อมต่อ**</span><span class="sxs-lookup"><span data-stu-id="f70a3-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f70a3-114">เลือก **เพิ่มการเชื่อมต่อ** แล้วเลือก **Salesforce Marketing Cloud** เพื่อตั้งค่าคอนฟิกการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f70a3-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="f70a3-115">ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="f70a3-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f70a3-116">ชื่อและชนิดของการเชื่อมต่ออธิบายการเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="f70a3-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f70a3-117">เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f70a3-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f70a3-118">เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้</span><span class="sxs-lookup"><span data-stu-id="f70a3-118">Choose who can use this connection.</span></span> <span data-ttu-id="f70a3-119">หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ</span><span class="sxs-lookup"><span data-stu-id="f70a3-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f70a3-120">สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)</span><span class="sxs-lookup"><span data-stu-id="f70a3-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f70a3-121">ระบุ **ชื่อผู้ใช้** **รหัสผ่าน** **ชื่อโฮสต์** และ **โฟลเดอร์การส่งออก** สำหรับบัญชี SFTP ของคุณ</span><span class="sxs-lookup"><span data-stu-id="f70a3-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="f70a3-122">เลือก **ตรวจสอบ** เพื่อทดสอบการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f70a3-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f70a3-123">เลือก **ฉันเห็นด้วย** เพื่อยืนยัน **ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ**</span><span class="sxs-lookup"><span data-stu-id="f70a3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f70a3-124">ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น</span><span class="sxs-lookup"><span data-stu-id="f70a3-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f70a3-125">กำหนดค่าการส่งออก</span><span class="sxs-lookup"><span data-stu-id="f70a3-125">Configure an export</span></span>

<span data-ttu-id="f70a3-126">คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="f70a3-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f70a3-127">สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="f70a3-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f70a3-128">ไปที่ **ข้อมูล** > **การส่งออก**</span><span class="sxs-lookup"><span data-stu-id="f70a3-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f70a3-129">หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มปลายทาง**</span><span class="sxs-lookup"><span data-stu-id="f70a3-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f70a3-130">ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน SFTP</span><span class="sxs-lookup"><span data-stu-id="f70a3-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="f70a3-131">หากคุณไม่เห็นชื่อส่วนนี้ แสดงว่าคุณไม่สามารถใช้การเชื่อมต่อชนิดนี้ได้</span><span class="sxs-lookup"><span data-stu-id="f70a3-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f70a3-132">เลือกว่าคุณต้องการส่งออก **บีบอัดแบบ Gzip แล้ว** ข้อมูลของคุณหรือ **คลายการบีบอัดแล้ว** และ **ตัวคั่นฟิลด์** สำหรับไฟล์ที่ส่งออกหรือไม่</span><span class="sxs-lookup"><span data-stu-id="f70a3-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f70a3-133">เลือกเอนทิตีที่คุณต้องการส่งออก ตัวอย่างเช่น เซ็กเมนต์</span><span class="sxs-lookup"><span data-stu-id="f70a3-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f70a3-134">แต่ละเอนทิตีที่เลือกจะถูกแบ่งออกเป็นไฟล์ผลลัพธ์สูงสุดห้าไฟล์เมื่อส่งออก</span><span class="sxs-lookup"><span data-stu-id="f70a3-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="f70a3-135">เลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="f70a3-135">Select **Save**.</span></span>

<span data-ttu-id="f70a3-136">การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที</span><span class="sxs-lookup"><span data-stu-id="f70a3-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f70a3-137">การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="f70a3-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f70a3-138">นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="f70a3-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="f70a3-139">นำเข้าข้อมูล Customer Insights จากตำแหน่ง SFTP ไปยัง Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f70a3-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f70a3-140">สร้าง [ส่วนขยายข้อมูลใน Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) เพื่อนำเข้าไฟล์ข้อมูล Customer Insights จากตำแหน่ง SFTP</span><span class="sxs-lookup"><span data-stu-id="f70a3-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="f70a3-141">[นำเข้าข้อมูลจากตำแหน่ง SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ลงในส่วนขยายข้อมูล Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f70a3-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="f70a3-142">ตั้งค่าระบบอัตโนมัติเพื่อนำเข้าข้อมูลไปยังส่วนขยายข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f70a3-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="f70a3-143">เรียนรู้เพิ่มเติมเกี่ยวกับ [ระบบอัตโนมัติของการวางไฟล์และระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)</span><span class="sxs-lookup"><span data-stu-id="f70a3-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="f70a3-144">กำหนด [ระบบอัตโนมัติของการวางไฟล์](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) หรือ [ระบบอัตโนมัติที่มีการจัดกำหนดการ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)</span><span class="sxs-lookup"><span data-stu-id="f70a3-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="f70a3-145">นี่คือตัวอย่างของ [ระบบอัตโนมัติที่มี SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)</span><span class="sxs-lookup"><span data-stu-id="f70a3-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f70a3-146">ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ</span><span class="sxs-lookup"><span data-stu-id="f70a3-146">Data privacy and compliance</span></span>

<span data-ttu-id="f70a3-147">เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลผ่าน SFTP Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล</span><span class="sxs-lookup"><span data-stu-id="f70a3-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f70a3-148">Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่าปลายทางการส่งออกปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี</span><span class="sxs-lookup"><span data-stu-id="f70a3-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f70a3-149">สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)</span><span class="sxs-lookup"><span data-stu-id="f70a3-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f70a3-150">ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณ สามารถลบปลายทางการส่งออกนี้เมื่อใดก็ได้เพื่อยกเลิกการใช้ฟังก์ชันนี้</span><span class="sxs-lookup"><span data-stu-id="f70a3-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
