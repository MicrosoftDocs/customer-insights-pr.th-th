---
title: ตัวอย่าง Android SDK
description: โครงการตัวอย่างเพื่อเรียนรู้เกี่ยวกับ Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229941"
---
# <a name="run-the-android-sdk-sample"></a>เรียกใช้ตัวอย่าง Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

โครงการ Android ตัวอย่างนี้ช่วยให้คุณเข้าใจวิธีการทำงานของ SDK ในแอป คุณไม่จำเป็นต้องเขียนรหัส เพียงเพิ่มคีย์การส่งผ่านข้อมูลของคุณ และคุณก็จะสามารถเห็นเหตุการณ์ในพื้นที่ทำงานของคุณได้ทันที

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [Android Studio](https://developer.android.com/studio)
- [คีย์การส่งผ่านข้อมูล](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>ดาวน์โหลดตัวอย่าง Android SDK

1. [ดาวน์โหลดตัวอย่าง Android SDK ของข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip)
1. แตกไฟล์ที่บีบอัด `ei-android-sample.zip`
1. เปิดโฟลเดอร์ที่คลายการบีบอัดแล้วใน Android Studio
1. ในไฟล์ `AndroidManifest.xml` แทนที่สตริง `"Your-Ingestion-Key"` ด้วยคีย์การเพิ่มพื้นที่ทำงานของคุณจากข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมภายใต้ **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** > **คู่มือการติดตั้ง** 

   > [!NOTE]
   > คุณไม่จำเป็นต้องแทนที่ส่วน `${applicationId}` จะถูกเติมข้อมูลโดยอัตโนมัติ

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. เลือก **เรียกใช้** เพื่อเริ่มต้นโครงการตัวอย่าง
1. ดูเหตุการณ์ในพื้นที่ทำงานของคุณ


[!INCLUDE[footer-include](../includes/footer-banner.md)]
