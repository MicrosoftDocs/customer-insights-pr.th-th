---
title: การเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลด้วยการนําเข้าแบบกําหนดเองของ SFTP
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595878"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="1ec28-103">เพิ่มข้อมูลโปรไฟล์ลูกค้าด้วยข้อมูลแบบกำหนดเอง (พรีวิว)</span><span class="sxs-lookup"><span data-stu-id="1ec28-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="1ec28-104">การนำเข้าแบบกำหนดเองของ Secure File Transfer Protocol (SFTP) ช่วยให้คุณสามารถนำเข้าข้อมูลที่ไม่ต้องผ่านขั้นตอนการรวมข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1ec28-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="1ec28-105">เป็นวิธีที่ยืดหยุ่น ปลอดภัยและง่ายในการนำข้อมูลของคุณ</span><span class="sxs-lookup"><span data-stu-id="1ec28-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="1ec28-106">การนำเข้าแบบกำหนดเองของ SFTP สามารถใช้ร่วมกับ [การส่งออก SFTP](export-sftp.md) ซึ่งช่วยให้คุณสามารถส่งออกข้อมูลโปรไฟล์ลูกค้าที่จำเป็นสำหรับการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1ec28-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="1ec28-107">จากนั้นข้อมูลจะสามารถประมวลผล เพิ่ม และสามารถใช้การนำเข้าแบบกำหนดเองของ SFTP เพื่อนำข้อมูลที่มีการเพิ่มกลับมาที่ความสามารถข้อมูลเชิงลึกกลุ่มเป้าหมายของ Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1ec28-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ec28-108">ข้อกำหนดเบื้องต้น</span><span class="sxs-lookup"><span data-stu-id="1ec28-108">Prerequisites</span></span>

<span data-ttu-id="1ec28-109">การกำหนดค่าการนําเข้าแบบกําหนดเองของ SFTP ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:</span><span class="sxs-lookup"><span data-stu-id="1ec28-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1ec28-110">คุณมีข้อมูลประจำตัวของผู้ใช้ (ชื่อผู้ใช้และรหัสผ่าน) สำหรับตำแหน่งที่ตั้ง SFTP ที่จะนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1ec28-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="1ec28-111">คุณมี URL และหมายเลขพอร์ต (โดยทั่วไปคือ 22) สำหรับโฮสต์ STFP</span><span class="sxs-lookup"><span data-stu-id="1ec28-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="1ec28-112">คุณมีชื่อไฟล์และตำแหน่งที่ตั้งของไฟล์ที่จะนำเข้าบนโฮสต์ SFTP</span><span class="sxs-lookup"><span data-stu-id="1ec28-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="1ec28-113">มีไฟล์ *model.json* ที่ระบุ Schema สำหรับข้อมูลที่จะนำเข้า</span><span class="sxs-lookup"><span data-stu-id="1ec28-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="1ec28-114">ไฟล์นี้ต้องอยู่ในไดเรกทอรีเดียวกับไฟล์ที่จะนำเข้า</span><span class="sxs-lookup"><span data-stu-id="1ec28-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="1ec28-115">คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)</span><span class="sxs-lookup"><span data-stu-id="1ec28-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="1ec28-116">การกำหนดค่า</span><span class="sxs-lookup"><span data-stu-id="1ec28-116">Configuration</span></span>

1. <span data-ttu-id="1ec28-117">ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** และเลือกแท็บ **ค้นหา**</span><span class="sxs-lookup"><span data-stu-id="1ec28-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="1ec28-118">บน **ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP** ให้เลือก **เพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="1ec28-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ec28-119">![ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP](media/SFTP_Custom_Import_tile.png "ไทล์การนำเข้าข้อมูลแบบกำหนดเองของ SFTP")</span><span class="sxs-lookup"><span data-stu-id="1ec28-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="1ec28-120">เลือก **เริ่มต้นใช้งาน** และระบุข้อมูลประจำตัวและที่อยู่สำหรับเซิร์ฟเวอร์ SFTP</span><span class="sxs-lookup"><span data-stu-id="1ec28-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="1ec28-121">ตัวอย่างเช่น sftp: // mysftpserver.com: 22</span><span class="sxs-lookup"><span data-stu-id="1ec28-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="1ec28-122">ป้อนชื่อไฟล์ที่มีข้อมูลและพาธไปยังไฟล์บนเซิร์ฟเวอร์ SFTP หากไม่ได้อยู่ในโฟลเดอร์รูท</span><span class="sxs-lookup"><span data-stu-id="1ec28-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="1ec28-123">ยืนยันข้อมูลที่ป้อนทั้งหมดโดยการเลือก **เชื่อมต่อกับการนำเข้าแบบกำหนดเอง**</span><span class="sxs-lookup"><span data-stu-id="1ec28-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ec28-124">![เมนูลอยการกำหนดค่าการนำเข้าแบบกำหนดเองของ SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "เมนูลอยการกำหนดค่าการนำเข้าแบบกำหนดเองของ SFTP")</span><span class="sxs-lookup"><span data-stu-id="1ec28-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="1ec28-125">การกำหนดการแม็ปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="1ec28-125">Defining field mappings</span></span> 

<span data-ttu-id="1ec28-126">ไดเรกทอรีที่มีไฟล์ที่จะนำเข้าบนเซิร์ฟเวอร์ SFTP ต้องมีไฟล์ *model.json*</span><span class="sxs-lookup"><span data-stu-id="1ec28-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="1ec28-127">ไฟล์นี้กำหนด Schema ที่จะใช้สำหรับการนำเข้าข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1ec28-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="1ec28-128">Schema ต้องใช้ [Common Data Model](/common-data-model/) เพื่อระบุการแมปฟิลด์</span><span class="sxs-lookup"><span data-stu-id="1ec28-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="1ec28-129">ตัวอย่างง่ายๆ ของไฟล์ model.json มีลักษณะดังนี้:</span><span class="sxs-lookup"><span data-stu-id="1ec28-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="1ec28-130">ผลการเพิ่มข้อมูล</span><span class="sxs-lookup"><span data-stu-id="1ec28-130">Enrichment results</span></span>

<span data-ttu-id="1ec28-131">ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง</span><span class="sxs-lookup"><span data-stu-id="1ec28-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1ec28-132">คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab)</span><span class="sxs-lookup"><span data-stu-id="1ec28-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1ec28-133">เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลที่จะนำเข้าและการเชื่อมต่อกับเซิร์ฟเวอร์ SFTP</span><span class="sxs-lookup"><span data-stu-id="1ec28-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="1ec28-134">หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลที่มีการเพิ่มแบบกำหนดเองที่นำเข้าใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน**</span><span class="sxs-lookup"><span data-stu-id="1ec28-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="1ec28-135">นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม</span><span class="sxs-lookup"><span data-stu-id="1ec28-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1ec28-136">คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**</span><span class="sxs-lookup"><span data-stu-id="1ec28-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1ec28-137">ขั้นตอนถัดไป</span><span class="sxs-lookup"><span data-stu-id="1ec28-137">Next steps</span></span>

<span data-ttu-id="1ec28-138">สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ</span><span class="sxs-lookup"><span data-stu-id="1ec28-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1ec28-139">สร้าง [เซ็กเมนต์](segments.md), [การวัด](measures.md) และ [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์แบบส่วนบุคคลให้กับลูกค้าของคุณ</span><span class="sxs-lookup"><span data-stu-id="1ec28-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]