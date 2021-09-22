---
title: รับรู้เหตุการณ์บนเว็บจากผู้เยี่ยมชมที่มีการตรวจสอบสิทธิ์ก่อนหน้าด้วยเปลี่ยนไม่รู้จักเป็นรู้จัก
description: คุณลักษณะแบบไม่รู้จักเป็นรู้จักช่วยให้คุณสามารถเชื่อมโยงเหตุการณ์บนเว็บไซต์กับผู้เยี่ยมชมที่ตรวจสอบสิทธิ์ก่อนหน้า
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036806"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>รับรู้เหตุการณ์บนเว็บจากผู้เยี่ยมชมที่มีการตรวจสอบสิทธิ์ก่อนหน้า

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

คุณลักษณะ **เปลี่ยนไม่รู้จักเป็นรู้จัก** ในความสามารถของข้อมูลเชิงลึกการมีส่วนร่วมช่วยให้สามารถเชื่อมโยงเหตุการณ์บนเว็บไซต์กับผู้เยี่ยมชมที่ตรวจสอบสิทธิ์ก่อนหน้า หากปิดใช้งานคุณลักษณะนี้ ผู้เข้าชมที่ตรวจสอบสิทธิ์ระหว่างการเยี่ยมชมก่อนหน้าแล้วจากไปจะไม่ถูกระบุหากพวกเขาไม่ตรวจสอบสิทธิ์อีกครั้งเมื่อกลับมา 

ตัวอย่างเช่น มีผู้เยี่ยมชมเว็บไซต์เมื่อสัปดาห์ที่แล้ว พวกเขาลงชื่อเข้าใช้บัญชีผู้ใช้ของตนบนไซต์ และเรียกดูแค็ตตาล็อกผลิตภัณฑ์ บุคคลนั้นกลับมาในสัปดาห์ถัดไปเพื่อเรียกดูผลิตภัณฑ์เพิ่มเติมโดยไม่ลงชื่อเข้าใช้บัญชีของตน เจ้าของไซต์ที่ใช้คุณลักษณะ **เปลี่ยนไม่รู้จักเป็นรู้จัก** จะรู้ว่าบุคคลเดียวกันกลับมาและทราบถึงสิ่งที่พวกเขาทำบนไซต์ ซึ่งช่วยให้การรายงานและวิเคราะห์กิจกรรมของเว็บไซต์ได้แม่นยำยิ่งขึ้น

## <a name="enable-unknown-to-known"></a>เปิดใช้งานเปลี่ยนไม่รู้จักเป็นรู้จัก

คุณต้องเป็น [ผู้ดูแลระบบพื้นที่ทำงาน](user-roles.md) เพื่อเปิดใช้งานคุณลักษณะนี้ 

1. ในข้อมูลเชิงลึกการมีส่วนร่วม ไปที่ **ผู้ดูแลระบบ** > **พื้นที่ทำงาน** 
2. เลือกแท็บ **การตั้งค่า**
3. ในส่วน **เปลี่ยนไม่รู้จักเป็นรู้จัก** ตั้งค่าสลับเป็น **เปิดใช้งาน**

![เปิดใช้งานเปลี่ยนไม่รู้จักเป็นรู้จัก](media/U2Ktoggle.png "เปิดใช้งานเปลี่ยนไม่รู้จักเป็นรู้จัก")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>การเพิ่มโค้ด JavaScript ในส่วนย่อยการติดตามของเว็บไซต์ของคุณ

เว็บไซต์สามารถเก็บบันทึก **authId ของผู้ใช้** พร้อมตัวอย่าง JavaScript ต่อไปนี้โดยใช้ [SDK เว็บข้อมูลเชิงลึกการมีส่วนร่วม](advanced-SDK-implementation.md) เพื่อให้คุณลักษณะ **เปลี่ยนไม่รู้จักเป็นรู้จัก** ทำงาน คุณต้องเก็บบันทึก authId *และ* เปิดใช้งาน userMapping:True ในส่วนย่อย JavaScript ของคุณ ดังตัวอย่างด้านล่าง

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
