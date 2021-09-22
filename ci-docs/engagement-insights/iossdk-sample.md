---
title: เรียกใช้ตัวอย่าง iOS SDK
description: โครงการตัวอย่างเพื่อเรียนรู้เกี่ยวกับ iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036851"
---
# <a name="run-the-ios-sdk-sample"></a>เรียกใช้ตัวอย่าง iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

โครงการ iOS ตัวอย่างนี้ช่วยให้คุณเข้าใจวิธีการทำงานของ SDK ในแอป คุณไม่จำเป็นต้องเขียนรหัส เพียงเพิ่มคีย์การส่งผ่านข้อมูลของคุณ และคุณก็จะสามารถเห็นเหตุการณ์ในพื้นที่ทำงานของคุณได้ทันที

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [Xcode รุ่น 9+](https://developer.apple.com/xcode/downloads/)
- [คีย์การส่งผ่านข้อมูล](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>ดาวน์โหลดตัวอย่าง iOS SDK

1. [ดาวน์โหลดตัวอย่าง iOS SDK ของข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip)
1. แตกไฟล์ที่บีบอัด `ei-ios-sample.zip`
1. เปิดโครงการแอปตัวอย่างใน Xcode
1. ในไฟล์ `EIConfig.plist` แทนที่สตริง `“YOUR-INGESTION-KEY”` ในฟิลด์ `ingestionKey` ด้วยคีย์การเพิ่มพื้นที่ทำงานของคุณจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมภายใต้ **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** > **คู่มือการติดตั้ง**
1. เลือก **เรียกใช้** เพื่อเริ่มต้นโครงการตัวอย่าง
1. ดูเหตุการณ์ในพื้นที่ทำงานของคุณ

[!INCLUDE[footer-include](../includes/footer-banner.md)]
