---
title: เริ่มต้นใช้งาน Android SDK
description: เรียนรู้วิธีปรับแต่งให้เป็นแบบส่วนตัว และเรียกใช้ Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036941"
---
# <a name="get-started-with-the-android-sdk"></a>เริ่มต้นใช้งาน Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

บทช่วยสอนนี้จะแนะนําคุณตลอดกระบวนการใช้เครื่องมือแอปพลิเคชัน Android ของคุณด้วย SDK ข้อมูลเชิงลึกของการมีส่วนร่วมของ Dynamics 365 Customer Insights คุณจะเริ่มเห็นเหตุการณ์ในพอร์ทัลของคุณภายในห้านาทีหรือเร็วกว่านั้น

## <a name="configuration-options"></a>ตัวเลือกการกำหนดค่า
สามารถส่งผ่านตัวเลือกการกำหนดค่าต่อไปนี้ไปยัง SDK:

- **ingestionKey**: คีย์การส่งผ่านข้อมูลถูกใช้เพื่อส่งเหตุการณ์ไปยังพื้นที่ทำงานของคุณ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- Android Studio

- ระดับ Android API ขั้นต่ำ: 16 (Jelly Bean)

- คีย์การส่งผ่านข้อมูล (ดูด้านล่างสำหรับคำแนะนำเกี่ยวกับวิธีการรับ)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>ขั้นตอนที่ 1 รวม SDK ลงในแอปพลิเคชันของคุณ
เริ่มต้นกระบวนการโดยการเลือกพื้นที่ทำงาน เลือกแพลตฟอร์มบนมือถือ Android และดาวน์โหลด Android SDK

- ใช้ตัวสลับพื้นที่ทำงานในบานหน้าต่างนำทางด้านซ้ายเพื่อเลือกพื้นที่ทำงานของคุณ

- หากคุณไม่มีพื้นที่ทำงานอยู่ ให้เลือก **พื้นที่ทำงานใหม่** และทำตามขั้นตอนเพื่อสร้าง [พื้นที่ทำงานใหม่](create-workspace.md)

## <a name="step-2-configure-the-sdk"></a>ขั้นตอนที่ 2 กำหนดค่า SDK

1. หลังจากที่คุณสร้างพื้นที่ทำงานแล้ว ให้ไปที่ **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** แล้วจากนั้น เลือก **คู่มือการติดตั้ง** 

1. ดาวน์โหลด [Android SDK ของข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วม](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) และวางไฟล์ `eiandroidsdk-debug.aar` ในโฟลเดอร์ `libs`

1. เปิดไฟล์ `build.gradle` ระดับโครงการของคุณ และเพิ่มส่วนย่อยต่อไปนี้:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. ตั้งค่าการกำหนดค่า SDK ของข้อมูลเชิงลึกเกี่ยวกับการมีส่วนร่วมผ่านไฟล์ `AndroidManifest.xml` ของคุณที่อยู่ใต้โฟลเดอร์ `manifests` 
1. คัดลอกส่วนย่อย XML จาก **คู่มือการติดตั้ง** `Your-Ingestion-Key` ควรถูกเติมข้อมูลโดยอัตโนมัติ

   > [!NOTE]
   > คุณไม่จำเป็นต้องแทนที่ส่วน `${applicationId}` จะถูกเติมข้อมูลโดยอัตโนมัติ
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. เปิดใช้งานหรือปิดใช้งานการบันทึกอัตโนมัติของเหตุการณ์ `View` โดยการตั้งค่าฟิลด์ `autoCapture` ด้านบนเป็น `true` หรือ `false`

1. (ทางเลือก) การกำหนดค่าอื่นๆ รวมถึงการตั้งค่า URL ตัวรวบรวมจุดสิ้นสุด สามารถเพิ่มได้ภายใต้ข้อมูลเมตาของคีย์การส่งผ่านข้อมูลใน `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>ขั้นตอนที่ 3 เริ่มต้น SDK จากกิจกรรมหลัก 

หลังจากที่คุณเริ่มต้น SDK คุณสามารถทำงานกับเหตุการณ์และคุณสมบัติของเหตุการณ์ในสภาพแวดล้อม MainActivity

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>ตั้งค่าคุณสมบัติสำหรับเหตุการณ์ทั้งหมด (ไม่บังคับ)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

ชนิดต่อไปนี้ได้รับการสนับสนุนสำหรับคุณสมบัติเหตุการณ์บริบท:
- String
- วันที่
- คู่
- Long
- แบบบูลีน
- UUID

### <a name="track-an-event"></a>ติดตามเหตุการณ์

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>กำหนดรายละเอียดผู้ใช้สำหรับเหตุการณ์ของคุณ (ไม่บังคับ)

SDK ช่วยให้คุณสามารถกำหนดข้อมูลผู้ใช้ที่สามารถส่งไปพร้อมกับทุกๆ เหตุการณ์ คุณสามารถระบุข้อมูลผู้ใช้ได้โดยเรียก `setUser(user: User)` API บนระดับ `Analytics`

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

คลาสข้อมูล `User`มีคุณสมบัติสตริงต่อไปนี้:

- **localId**: ID ภายในของผู้ใช้
- **authId**: ID ของผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **authType** : ชนิดการรับรองความถูกต้องที่ใช้เพื่อรับ ID ผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **ชื่อ**: ชื่อของผู้ใช้
- **อีเมล**: ที่อยู่อีเมลของผู้ใช้

[!INCLUDE[footer-include](../includes/footer-banner.md)]
