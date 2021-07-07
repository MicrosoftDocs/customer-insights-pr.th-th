---
title: การเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304673"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f4f40-103">เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยข้อมูลแบบกำหนดเอง (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="f4f40-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f4f40-104">การนำเข้าแบบกำหนดเองของ Secure File Transfer Protocol (SFTP) ช่วยให้คุณสามารถนำเข้าข้อมูลที่ไม่ต้องผ่านขั้นตอนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f4f40-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f4f40-105">เป็นวิธีที่ยืดหยุ่น ปลอดภัยและง่ายในการนำข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="f4f40-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f4f40-106">การนำเข้าแบบกำหนดเองของ SFTP สามารถใช้ร่วมกับ [การส่งออก SFTP](export-sftp.md) ซึ่งช่วยให้คุณสามารถส่งออกข้อมูลโปรไฟล์ลูกค้าที่จำเป็นสำหรับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f4f40-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f4f40-107">จากนั้น สามารถประมวลผลและเพิ่มข้อมูลได้ และการนำเข้าแบบกำหนดเองของ SFTP สามารถใช้เพื่อนำข้อมูลที่เพิ่มแล้วกลับมาที่ความสามารถข้อมูลเชิงลึกของผู้ชมของ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f4f40-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4f40-108">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="f4f40-108">Prerequisites</span></span>

<span data-ttu-id="f4f40-109">การกำหนดค่าการนําเข้าแบบกําหนดเองของ SFTP ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="f4f40-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f4f40-110">คุณมีชื่อไฟล์และตำแหน่ง (พาธ) ของไฟล์ที่จะถูกนำเข้าบนโฮสต์ SFTP</span><span class="sxs-lookup"><span data-stu-id="f4f40-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f4f40-111">มีไฟล์ *model.json* ที่ระบุ [สคีมา Common Data Model](/common-data-model/) สำหรับข้อมูลที่จะนำเข้า</span><span class="sxs-lookup"><span data-stu-id="f4f40-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="f4f40-112">ไฟล์นี้ต้องอยู่ในไดเรกทอรีเดียวกับไฟล์ที่จะนำเข้า</span><span class="sxs-lookup"><span data-stu-id="f4f40-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f4f40-113">การเชื่อมต่อ SFTP ได้รับการกำหนดค่าแล้วโดยผู้ดูแลระบบ *หรือ* คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)</span><span class="sxs-lookup"><span data-stu-id="f4f40-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="f4f40-114">คุณจะต้องมีข้อมูลประจำตัวของผู้ใช้ URL และหมายเลขพอร์ตสำหรับตำแหน่ง SFTP ที่คุณต้องการนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f4f40-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="f4f40-115">กำหนดค่าการนำเข้า</span><span class="sxs-lookup"><span data-stu-id="f4f40-115">Configure the import</span></span>

1. <span data-ttu-id="f4f40-116">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**</span><span class="sxs-lookup"><span data-stu-id="f4f40-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f4f40-117">บน **ไทล์ SFTP Technologies** เลือก **เพิ่มข้อมูลของฉัน** แล้วเลือก **เริ่มต้นใช้งาน**</span><span class="sxs-lookup"><span data-stu-id="f4f40-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP":::

1. <span data-ttu-id="f4f40-119">เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="f4f40-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f4f40-120">ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f4f40-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f4f40-121">หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อโดยเลือก **เพิ่มการเชื่อมต่อ** และเลือก **การนําเข้าแบบกําหนดเองของ SFTP** จากรายการแบบหล่นลง</span><span class="sxs-lookup"><span data-stu-id="f4f40-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="f4f40-122">เลือก **เชื่อมต่อกับการนำเข้าข้อมูลแบบกำหนดเอง** เพื่อยืนยันการเชื่อมต่อที่เลือก</span><span class="sxs-lookup"><span data-stu-id="f4f40-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="f4f40-123">เลือก **ต่อไป** และป้อน **พาธ** และ **ชื่อไฟล์** ของไฟล์ข้อมูลที่คุณต้องการนำเข้า</span><span class="sxs-lookup"><span data-stu-id="f4f40-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="ภาพหน้าจอเมื่อป้อนตำแหน่งข้อมูล":::

1. <span data-ttu-id="f4f40-125">เลือก **ถัดไป** และระบุชื่อสำหรับการเพิ่มข้อมูลและชื่อสำหรับเอนทิตีผลลัพธ์</span><span class="sxs-lookup"><span data-stu-id="f4f40-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="f4f40-126">เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว</span><span class="sxs-lookup"><span data-stu-id="f4f40-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="f4f40-127">กำหนดค่าการเชื่อมต่อสำหรับการนำเข้าแบบกำหนดเองของ SFTP</span><span class="sxs-lookup"><span data-stu-id="f4f40-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="f4f40-128">คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ</span><span class="sxs-lookup"><span data-stu-id="f4f40-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f4f40-129">เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มข้อมูล *หรือ* ไปที่ **การจัดการ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์การนำเข้าแบบกำหนดเอง</span><span class="sxs-lookup"><span data-stu-id="f4f40-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="f4f40-130">ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**</span><span class="sxs-lookup"><span data-stu-id="f4f40-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f4f40-131">ป้อนชื่อผู้ใช้ รหัสผ่าน และ URL โฮสต์ที่ถูกต้องสำหรับเซิร์ฟเวอร์ SFTP ที่มีข้อมูลที่จะถูกนำเข้า</span><span class="sxs-lookup"><span data-stu-id="f4f40-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="f4f40-132">รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**</span><span class="sxs-lookup"><span data-stu-id="f4f40-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f4f40-133">เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="f4f40-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f4f40-134">เมื่อการตรวจสอบเสร็จสิ้น สามารถบันทึกการเชื่อมต่อได้โดยเลือก **บันทึก**</span><span class="sxs-lookup"><span data-stu-id="f4f40-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4f40-135">![หน้าการตั้งค่าคอนฟิกการเชื่อมต่อ Experian](media/enrichment-SFTP-connection.png "หน้าการตั้งค่าคอนฟิกการเชื่อมต่อ Experian")</span><span class="sxs-lookup"><span data-stu-id="f4f40-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="f4f40-136">การกำหนดการแม็ปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="f4f40-136">Defining field mappings</span></span> 

<span data-ttu-id="f4f40-137">ไดเรกทอรีที่มีไฟล์ที่จะนำเข้าบนเซิร์ฟเวอร์ SFTP ต้องมีไฟล์ *model.json*</span><span class="sxs-lookup"><span data-stu-id="f4f40-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f4f40-138">ไฟล์นี้กำหนด Schema ที่จะใช้สำหรับการนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f4f40-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f4f40-139">Schema ต้องใช้ [Common Data Model](/common-data-model/) เพื่อระบุการแม็ปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="f4f40-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f4f40-140">ตัวอย่างง่ายๆ ของไฟล์ model.json มีลักษณะดังนี้:</span><span class="sxs-lookup"><span data-stu-id="f4f40-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="f4f40-141">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="f4f40-141">Enrichment results</span></span>

<span data-ttu-id="f4f40-142">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="f4f40-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f4f40-143">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="f4f40-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4f40-144">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลที่จะนำเข้าและการเชื่อมต่อกับเซิร์ฟเวอร์ SFTP</span><span class="sxs-lookup"><span data-stu-id="f4f40-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f4f40-145">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลที่มีการเพิ่มแบบกำหนดเองที่นำเข้าใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="f4f40-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f4f40-146">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="f4f40-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f4f40-147">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="f4f40-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4f40-148">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="f4f40-148">Next steps</span></span>

<span data-ttu-id="f4f40-149">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="f4f40-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f4f40-150">สร้าง [เซ็กเมนต์](segments.md) และ [การวัด](measures.md) และ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่ปรับให้เป็นแบบส่วนตัวให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="f4f40-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
