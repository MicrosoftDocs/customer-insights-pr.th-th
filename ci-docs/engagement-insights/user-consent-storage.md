---
title: จัดการคุกกี้และความยินยอมของผู้ใช้ในการจัดเก็บข้อมูลผู้ใช้ใน Dynamics 365 Customer Insights
description: ทำความเข้าใจว่าคุกกี้และความยินยอมของผู้ใช้ถูกใช้เพื่อระบุผู้เยี่ยมชมเว็บไซต์อย่างไร
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558894"
---
# <a name="manage-cookies-and-user-consent"></a>จัดการคุกกี้และความยินยอมของผู้ใช้

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ความสามารถข้อมูลเชิงลึกของการมีส่วนร่วมใน Dynamics 365 Customer Insights ใช้คุกกี้และคีย์ (`localStorage`) เพื่อระบุผู้เข้าชมเว็บไซต์

คุกกี้คือไฟล์ขนาดเล็กที่เก็บข้อมูลเล็กน้อยเกี่ยวกับการโต้ตอบของผู้ใช้กับเว็บไซต์ พวกเขาจะถูกเก็บไว้ในเว็บเบราว์เซอร์ เมื่อผู้ใช้เยี่ยมชมเว็บไซต์ที่ผู้ใช้ของคุณเก็บคุกกี้ไว้ เบราว์เซอร์จะส่งข้อมูลนั้นไปยังเซิร์ฟเวอ ร์ซึ่งจะส่งคืนข้อมูลที่ไม่ซ้ำกับผู้ใช้ นี่คือเทคโนโลยีที่ช่วยให้ ตัวอย่าเช่น รถเข็นสินค้าออนไลน์สามารถเก็บรายการที่เลือกไว้ แม้ว่าผู้ใช้จะออกจากเว็บไซต์ก็ตาม

## <a name="user-consent"></a>ความยินยอมของผู้ใช้

[ข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR)](/dynamics365/get-started/gdpr/) เป็นข้อบังคับของสหภาพยุโรป (EU) ที่กำหนดว่าองค์กรต่าง ๆ ควรจัดการกับความเป็นส่วนตัวและความปลอดภัยของผู้ใช้อย่างไร คุกกี้มักจัดเก็บหรือรวบรวม "ข้อมูลส่วนบุคคล" เช่น ตัวระบุออนไลน์ซึ่ง GDPR ครอบคลุม หากธุรกิจของคุณมีพนักงานและ / หรือขายให้กับเจ้าของข้อมูลในสหภาพยุโรป GDPR จะมีผลต่อคุณ [เรียนรู้เพิ่มเติมเกี่ยวกับวิธีที่ Microsoft สามารถช่วยให้คุณปฏิบัติตาม GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs)

ในการอนุญาตให้ SDK ข้อมูลเชิงลึกของการมีส่วนร่วมจัดเก็บคุกกี้หรือข้อมูลที่ละเอียดอ่อนอื่น ๆ คุณต้องระบุว่าผู้ใช้ของคุณยินยอมหรือไม่ การดำเนินการนี้เกิดขึ้นในการเริ่มต้น SDK โดยการตั้งค่าฟิลด์ `userConsent` ในการกำหนดค่า

หากคุณระบุว่าไม่มีความยินยอมของผู้ใช้ SDK จะไม่จัดเก็บข้อมูลใด ๆ และจะไม่ส่งเหตุการณ์ที่สามารถใช้เพื่อติดตามพฤติกรรมของผู้ใช้ ข้อมูลที่เก็บไว้ก่อนหน้านี้จะถูกลบออกจากเบราว์เซอร์

หากไม่มีการระบุค่าความยินยอมของผู้ใช้ SDK จะถือว่าผู้ใช้ยินยอม ซึ่งหมายความว่าหากคุณ (ในฐานะลูกค้าของเรา) ไม่ได้ระบุค่าสำหรับความยินยอมของผู้ใช้ใน SDK ข้อมูลจะถูกรวบรวม อย่างไรก็ตาม หากคุณระบุว่าค่าความยินยอมของผู้ใช้ต้องเป็น "จริง" จะไม่มีการรวบรวมข้อมูลหากผู้ใช้ปฏิเสธหรือไม่ให้ความยินยอมอย่างชัดเจน

ด้านล่างนี้คือส่วนย่อยของโค้ดที่จะเริ่มต้น SDK ของเว็บโดยได้รับความยินยอมจากผู้ใช้:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>การจัดเก็บข้อมูลของผู้เยี่ยมชมในความสามารถในการเข้าถึงข้อมูลเชิงลึกของการมีส่วนร่วม

### <a name="cookies"></a>คุ้กกี้

- _msei
    - เก็บรหัสผู้ใช้ที่ไม่ระบุตัวตน คุกกี้นี้ถูกตั้งค่าในโดเมนของลูกค้าและจะหมดอายุใน 365 วัน

### <a name="local-storage"></a>ที่เก็บข้อมูลในเครื่อง

ความสามารถของข้อมูลเชิงลึกของการมีส่วนร่วมยังใช้ประโยชน์จากคีย์ (`localStorage`) เพื่อติดตามข้อมูลที่ไม่สำคัญ ข้อมูลนี้จะถูกเก็บไว้อย่างสมบูรณ์ในเบราว์เซอร์ โดยไม่มีการรับส่งข้อมูลไปยังหรือจากเซิร์ฟเวอร์ของคุณ

- *EISession.Id*
    - จัดเก็บข้อมูลเกี่ยวกับเซสชันผู้ใช้ที่กำลังดำเนินอยู่ เช่น รหัสเซสชัน เมื่อเริ่มต้น และเมื่อหมดอายุ
- *EISession.Previous*
    - เก็บ URL ของหน้าที่เยี่ยมชมก่อนหน้านี้ในเซสชันปัจจุบัน

คีย์ในที่จัดเก็บในตัวเครื่องจะไม่หมดอายุโดยอัตโนมัติ และจะได้รับการรีเซ็ตในเซสชัน SDK ถัดไป

## <a name="deleting-cookies"></a>การลบคุกกี้

ลูกค้าของคุณสามารถลบคุกกี้และคีย์การจัดเก็บในเครื่องด้วยตนเองได้ตลอดเวลาผ่านการตั้งค่าเบราว์เซอร์ของพวกเขา


[!INCLUDE[footer-include](../includes/footer-banner.md)]
