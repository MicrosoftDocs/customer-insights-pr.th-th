---
title: เริ่มต้นใช้งาน iOS SDK
description: เรียนรู้วิธีปรับแต่งให้เป็นแบบส่วนตัว และเรียกใช้ iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226238"
---
# <a name="get-started-with-the-ios-sdk"></a>เริ่มต้นใช้งาน iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

บทช่วยสอนนี้จะแนะนําคุณตลอดการใช้เครื่องมือแอปพลิเคชัน iOS ของคุณด้วย SDK ข้อมูลเชิงลึกของการมีส่วนร่วม Dynamics 365 Customer Insights คุณจะเริ่มเห็นเหตุการณ์ในพอร์ทัลของคุณภายในห้านาทีหรือเร็วกว่านั้น

## <a name="configuration-options"></a>ตัวเลือกการกำหนดค่า

สามารถส่งผ่านตัวเลือกการกำหนดค่าต่อไปนี้ไปยัง SDK ผ่านทางไฟล์ `EIConfig.plist` ที่ให้มา:

- **ingestionKey**: คีย์การส่งผ่านข้อมูลที่ใช้ส่งกิจกรรมไปยังโครงการของคุณ
- **autocollectAction**: ค่าบูลีนเพื่อเปิดใช้งานหรือปิดใช้งานการใช้เครื่องมืออัตโนมัติของเหตุการณ์การดำเนินการ
- **autocollectView**: ค่าบูลีนเพื่อเปิดใช้งานหรือปิดใช้งานการใช้เครื่องมืออัตโนมัติของเหตุการณ์มุมมอง
- **endpointUrl**: URL จุดสิ้นสุดที่เหตุการณ์จะถูกนำไป

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- Xcode รุ่น 9+
- iOS รุ่น 8.2+
- คีย์การส่งผ่านข้อมูล (ดูคำแนะนำด้านล่างเพื่อรับ)

## <a name="integrate-the-sdk-into-your-application"></a>รวม SDK ลงในแอปพลิเคชันของคุณ

เริ่มต้นกระบวนการโดยการเลือกพื้นที่ทำงานเพื่อทำงาน เลือกแพลตฟอร์มบนมือถือ iOS และดาวน์โหลด SDK

- ใช้ตัวสลับพื้นที่ทำงานในบานหน้าต่างนำทางด้านซ้ายเพื่อเลือกพื้นที่ทำงานของคุณ

- หากคุณไม่มีพื้นที่ทำงานอยู่ ให้เลือก **พื้นที่ทำงานใหม่** และทำตามขั้นตอนเพื่อสร้าง [พื้นที่ทำงานใหม่](create-workspace.md)

- หลังจากที่คุณสร้างพื้นที่ทำงานแล้ว ให้ไปที่ **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** แล้วจากนั้น เลือก **คู่มือการติดตั้ง**

## <a name="configure-the-sdk"></a>กำหนดค่า SDK

เมื่อคุณดาวน์โหลด SDK แล้ว คุณสามารถใช้งานใน Xcode เพื่อเปิดใช้งานและกำหนดเหตุการณ์ได้ มีสองวิธีในการดำเนินการ

### <a name="option-1-using-cocoapods-recommended"></a>ตัวเลือกที่ 1: การใช้ CocoaPods (แนะนำ)
CocoaPods เป็นตัวจัดการการขึ้นต่อกันสำหรับโครงการ Swift และ Objective-C Cocoa การใช้ตัวเลือกนี้ทำให้การรวม SDK ข้อมูลเชิงลึกของการมีส่วนร่วมสำหรับ iOS ง่ายขึ้น CocoaPods ยังช่วยให้คุณสามารถอัปเกรด SDK ข้อมูลเชิงลึกของการมีส่วนร่วมเป็นเวอร์ชันล่าสุดได้อีกด้วย วิธีใช้ CocoaPods เพื่อรวม SDK ข้อมูลเชิงลึกของการมีส่วนร่วมเข้ากับโครงการ Xcode ของคุณ 

1. ติดตั้ง CocoaPods 

1. สร้างไฟล์ใหม่ชื่อ Podfile ภายในไดเรกทอรีรากของโครงการของคุณ และเพิ่มคำสั่งต่อไปนี้ แทนที่ YOUR_TARGET_PROJECT_NAME ด้วยชื่อโครงการ Xcode ของคุณ 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
การกำหนดค่า Pod ด้านบนมีทั้ง SDK เวอร์ชันแก้ไขข้อบกพร่องและเผยแพร่ เลือกว่าตัวเลือกใดเหมาะกับโครงการของคุณที่สุด

1. ติดตั้ง Pod โดยการใช้คำสั่งต่อไปนี้: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>ตัวเลือกที่ 2: การใช้ลิงก์ดาวน์โหลด

1. ดาวน์โหลด [iOS SDK ของข้อมูลเชิงลึกของการมีส่วนร่วม](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) และวางไฟล์ `EIObjC.xcframework` ในโฟลเดอร์ `Frameworks`

1. ถ้าไม่มีโฟลเดอร์ `Frameworks` ให้สร้างขึ้นในโฟลเดอร์โครงการ

## <a name="enable-auto-instrumentation"></a>เปิดใช้งานการใช้เครื่องมืออัตโนมัติ
 
คุณสามารถเปิดใช้งานการใช้เครื่องมืออัตโนมัติโดยไม่ต้องเข้ารหัสได้อย่างง่ายดาย เมื่อโครงการทำงาน จะติดตามเหตุการณ์ `view` และ `action` โดยอัตโนมัติโดยใช้คีย์การนำเข้าที่กำหนดค่าไว้ 

1. อัปเดตและรวมไฟล์ `EIConfig.plist` ที่ให้ไว้ในโฟลเดอร์ไดเร็กทอรีโครงการของคุณสำหรับฟิลด์ต่อไปนี้:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ใช่
    - autocollectAction = ใช่

2. จากนั้น เพิ่มไฟล์ `EIConfig.plist` ไปยังโครงการของคุณใน Xcode 



เพื่อปิดใช้งานการใช้เครื่องมืออัตโนมัติ อัปเดตฟิลด์ต่อไปนี้ในไฟล์ `EIConfig.plist` ที่ให้ไว้ในโฟลเดอร์ไดเร็กทอรีโครงการของคุณ 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>ใช้เหตุการณ์ที่กำหนดเอง

1. เปิดโครงการของคุณใน Xcode และนำทางไปยังการตั้งค่า **ทั่วไป** 
1. เพิ่ม `EIObjC.xcframework` ไปยังโครงการภายใต้ส่วน 'กรอบงาน ไลบรารี และเนื้อหาที่ฝังตัว'

1. นําเข้าไฟล์ส่วนหัวของเฟรมเวิร์กใน AppDelegate.m ด้วยส่วนย่อยต่อไปนี้:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. เริ่มต้น SDK ของข้อมูลเชิงลึกของการมีส่วนร่วมจากapplication: didFinishLaunchingWithOptions
1. คัดลอกส่วนย่อย XML จาก **คู่มือการติดตั้ง**

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. ติดตามเหตุการณ์:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>กำหนดรายละเอียดผู้ใช้สำหรับกิจกรรมของคุณ

SDK ช่วยให้คุณสามารถกำหนดข้อมูลผู้ใช้ที่สามารถส่งไปพร้อมกับทุกๆ เหตุการณ์ คุณสามารถระบุข้อมูลผู้ใช้ได้โดยเรียก `setUser:(nonnull EIUser *)user` API บน SDK

การระบุรายละเอียดผู้ใช้บนระดับ `Analytics` หมายความว่าการตรวจวัดระยะไกลทั้งหมดจะมีข้อมูลนี้ อย่างไรก็ตาม หากคุณระบุระดับเหตุการณ์โดยการเรียก `setUser:(nonnull EIUser *)user` API บนวัตถุ EIEvent เฉพาะเหตุการณ์เฉพาะนั้นเท่านั้นที่จะมีข้อมูล

คลาสข้อมูล `EIUser`มีคุณสมบัติ NSString ต่อไปนี้:

- **localId**: ID ภายในของผู้ใช้
- **authId**: ID ของผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **authType**: ชนิดการรับรองความถูกต้องที่ใช้เพื่อรับ ID ของผู้ใช้ที่ได้รับการรับรองความถูกต้อง
- **ชื่อ**: ชื่อของผู้ใช้
- **อีเมล**: ที่อยู่อีเมลของผู้ใช้


[!INCLUDE[footer-include](../includes/footer-banner.md)]
