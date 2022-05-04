---
title: ทำงานกับ API
description: ใช้ API และทำความเข้าใจข้อจำกัด
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: ecc8bb3dbec1d4583c4bf2a58058145343945299
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647656"
---
# <a name="work-with-customer-insights-apis"></a>ทำงานกับ Customer Insights API

Dynamics 365 Customer Insights จัดเตรียม API เพื่อสร้างแอปพลิเคชันของคุณเองตามข้อมูลของคุณใน Customer Insights

> [!IMPORTANT]
> รายละเอียดของ API เหล่านี้แสดงอยู่ใน [ข้อมูลอ้างอิง Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) รวมถึงข้อมูลเพิ่มเติมเกี่ยวกับการดำเนินงาน พารามิเตอร์และการตอบสนอง

บทความนี้อธิบายวิธีเข้าถึง Customer Insights API, สร้างการลงทะเบียนแอป Azure และเริ่มต้นใช้งานไลบรารีของไคลเอ็นต์ที่พร้อมใช้งาน

## <a name="get-started-trying-the-customer-insights-apis"></a>เริ่มต้นใช้งาน Customer Insights API

1. [ลงชื่อเข้าใช้](https://home.ci.ai.dynamics.com) Customer Insights หากคุณยังไม่ได้สมัครใช้งาน [ลงชื่อเข้าใช้ Customer Insights รุ่นทดลองใช้](https://aka.ms/tryci)

1. หากต้องการเปิดใช้ API ในสภาพแวดล้อม Customer Insights ของคุณ ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์** คุณต้องมีสิทธิ์ระดับผู้ดูแลระบบจึงจะทำได้

1. ไปที่แท็บ **API** และเลือกปุ่ม **เปิดใช้งาน**    
 
   การเปิดใช้งาน API จะสร้างคีย์การสมัครใช้งานหลักและรองสำหรับอินสแตนซ์ของคุณที่จะใช้ในคำขอ API คุณสามารถสร้างคีย์ใหม่ได้โดยการเลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่** ใน **ผู้ดูแลระบบ** > **สิทธิ์** > **API**

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. เลือก **สำรวจ API ของเรา** เพื่อ [ทดลองใช้ API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)

1. เลือกการดำเนินงานของ API และเลือก **ลองใช้งาน**

1. ในบานหน้าต่างด้านข้าง ตั้งค่าในเมนูแบบหล่นลง **การอนุญาต** เป็น **โดยนัย** โทเค็นส่วนหัว `Authorization` ถูกเพิ่มด้วยโทเค็นแบบแบเรอร์ คีย์การสมัครใช้งานของคุณจะมีการเติมข้อมูลโดยอัตโนมัติ
  
1. เพิ่มพารามิเตอร์การสอบถามที่จำเป็นทั้งหมดหรือไม่ก็ได้

1. เลื่อนไปที่ด้านล่างสุดของบานหน้าต่างด้านข้าง แล้วเลือก **ส่ง**

การตอบสนอง HTTP จะปรากฏด้านล่างในไม่ช้า

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>สร้างการลงทะเบียนแอปใหม่ในพอร์ทัล Azure

ขั้นตอนเหล่านี้ช่วยคุณในการเริ่มต้นใช้งาน Customer Insights API ในแอปพลิเคชัน Azure โดยใช้สิทธิ์ที่ได้รับมอบ อย่าลืมกรอก [ส่วนการเริ่มต้นใช้งาน](#get-started-trying-the-customer-insights-apis) ก่อน

1. ลงชื่อเข้าใช้ [พอร์ทัล Azure](https://portal.azure.com) ด้วยบัญชีที่สามารถเข้าถึงข้อมูล Customer Insights

1. ทางด้านซ้าย ให้เลือก **การลงทะเบียนแอป**

1. เลือก **การลงทะเบียนใหม่** ระบุชื่อแอปพลิเคชัน และเลือกชนิดบัญชี
 
   หรือเพิ่ม URL การเปลี่ยนเส้นทางก็ได้ http://localhost เพียงพอสำหรับการพัฒนาแอปพลิเคชันบนคอมพิวเตอร์ของคุณ

1. ในการลงทะเบียนแอปใหม่ของคุณ ให้ไปที่ **สิทธิ์ API**

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. เลือก **เพิ่มสิทธิ์** และเลือก **Customer Insights** ในบานหน้าต่างด้านข้าง

1. สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ที่ได้รับมอบ** แล้วจากนั้น เลือกสิทธิ์ **user_impersonation**

1. เลือก **เพิ่มสิทธิ์** หากคุณต้องการเข้าถึง API โดยไม่มีการลงชื่อเข้าใช้ของผู้ใช้ ให้ดูที่ส่วน [สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์](#server-to-server-application-permissions)

1. เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์

คุณสามารถใช้รหัสแอปพลิเคชัน/ไคลเอ็นต์สำหรับการลงทะเบียนแอปนี้กับ Microsoft Authentication Library (MSAL) เพื่อรับโทเค็นแบบแบเรอร์ที่จะส่งคำขอของคุณไปยัง API

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ MSAL โปรดดู [ภาพรวมของ Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการลงทะเบียนแอปใน Azure โปรดดูที่ [ลงทะเบียนแอปพลิเคชัน](/azure/active-directory/develop/quickstart-register-app.md#register-an-application)

สำหรับข้อมูลเกี่ยวกับการใช้ API ในไลบรารีไคลเอนต์ของเรา โปรดดูที่ [ไลบรารีไคลเอนต์ Customer Insights](#customer-insights-client-libraries)

### <a name="server-to-server-application-permissions"></a>สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์

[ส่วนการลงทะเบียนแอป](#create-a-new-app-registration-in-the-azure-portal) สรุปวิธีการลงทะเบียนแอปที่ต้องให้ผู้ใช้ลงชื่อเข้าใช้เพื่อการรับรองความถูกต้อง เรียนรู้วิธีสร้างการลงทะเบียนแอปที่ไม่จำเป็นต้องมีการโต้ตอบกับผู้ใช้และสามารถเรียกใช้บนเซิร์ฟเวอร์ได้

1. การลงทะเบียนแอปของคุณในพอร์ทัล Azure ให้ไปที่ **สิทธิ์ API**

1. เลือก **เพิ่มสิทธิ์** 

1. เลือกแท็บ **API ที่องค์กรของฉันใช้** และเลือก **Dynamics 365 AI สำหรับ Customer Insights** จากรายการ 

1. สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ของแอปพลิเคชัน** แล้วจากนั้น เลือกสิทธิ์ **CustomerInsights.Api.All**

1. เลือก **เพิ่มสิทธิ์**

1. กลับไปที่ **สิทธิ์ API** สำหรับการลงทะเบียนแอปของคุณ

1. เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. สรุปได้ว่าเราต้องเพิ่มชื่อการลงทะเบียนแอปเป็นผู้ใช้ใน Customer Insights  
   
   เปิด Customer Insights ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์** และเลือก **เพิ่มผู้ใช้**

1. ค้นหาชื่อการลงทะเบียนแอปของคุณ เลือกจากผลการค้นหาและเลือก **บันทึก**

## <a name="customer-insights-client-libraries"></a>ไลบรารีไคลเอ็นต์ Customer Insights

ส่วนนี้ช่วยให้คุณเริ่มต้นใช้งานไลบรารีไคลเอ็นต์ที่มีอยู่สำหรับ Customer Insights API ได้ ซอร์สโค้ดไลบรารีทั้งหมดและแอปพลิเคชันตัวอย่างสามารถดูได้ใน [เพจ Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) 

### <a name="c-nuget"></a>C# NuGet

เรียนรู้วิธีเริ่มต้นใช้งานไลบรารีไคลเอ็นต์ C# จาก NuGet.org สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแพคเกจ NuGet โปรดดู [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) ปัจจุบัน แพคเกจนี้กำหนดเป้าหมายเป็นเฟรมเวิร์ก netstandard2.0 และ netcoreapp2.0

#### <a name="add-the-c-client-library-to-a-c-project"></a>เพิ่มไลบรารีไคลเอ็นต์ C# ในโครงการ C#

1. ใน Visual Studio ให้เปิด **ตัวจัดการแพคเกจ NuGet** สำหรับโครงการของคุณ

1. ค้นหา **Microsoft.Dynamics.CustomerInsights.Api**

1. เลือก **ติดตั้ง** เพื่อเพิ่มแพคเกจลงในโครงการ
 
   หรือรันคำสั่งนี้ใน **คอนโซลตัวจัดการแพคเกจ NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>ใช้ไลบรารีไคลเอ็นต์ C#

1. ใช้ [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) เพื่อรับ `AccessToken` โดยใช้ [การลงทะเบียนแอป Azure](#create-a-new-app-registration-in-the-azure-portal) ที่คุณมีอยู่

1. หลังจากรับรองความถูกต้องและรับโทเค็นเรียบร้อยแล้ว ให้สร้าง `HttpClient` ใหม่หรือใช้ที่มีอยู่ด้วยการตั้งค่า **"การอนุญาต" DefaultRequestHeaders** เป็น **"โทเค็นการเข้าถึง" แบบแบเรอร์** และ **Ocp-Apim-Subscription-Key** ตั้งค่าเป็น [**คีย์การสมัครใช้งาน** จากสภาพแวดล้อม Customer Insights ของคุณ](#get-started-trying-the-customer-insights-apis)   
 
   รีเซ็ตส่วนหัว **การอนุญาต** ตามความเหมาะสม ตัวอย่างเช่น เมื่อโทเค็นหมดอายุ

1. ส่งผ่าน `HttpClient` นี้ในโครงสร้างของไคลเอ็นต์ `CustomerInsights`

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. ทำการเรียกด้วยไคลเอ็นต์ไปที่ "วิธีการขยาย"—ตัวอย่างเช่น `GetAllInstancesAsync` หากการเข้าถึง `Microsoft.Rest.HttpOperationResponse` พื้นฐานเป็นวิธีที่ต้องการ ให้ใช้ "วิธีการข้อความ http"—ตัวอย่างเช่น `GetAllInstancesWithHttpMessagesAsync`

1. การตอบสนองน่าจะเป็นชนิด `object` เนื่องจากวิธีการดังกล่าวสามารถส่งคืนได้หลายชนิด (ตัวอย่างเช่น `IList<InstanceInfo>` และ `ApiErrorResult`) การตรวจสอบชนิดการส่งคืน คุณสามารถแปลงออบเจ็กต์เป็นชนิดการตอบสนองที่ระบุไว้ใน [เพจรายละเอียด API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) สำหรับการดำเนินงานนั้นได้อย่างปลอดภัย    
   
   หากต้องการข้อมูลเพิ่มเติมเกี่ยวกับคำขอที่ต้องการ ให้ใช้ **วิธีการข้อความ http** เพื่อเข้าถึงออบเจ็กต์การตอบสนองแบบข้อมูลดิบ

### <a name="nodejs-package"></a>แพคเกจ NodeJS

ใช้ไลบรารีไคลเอ็นต์ NodeJS ที่มีให้ผ่าน NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>แพคเกจ Python

ใช้ไลบรารีไคลเอ็นต์ Python ที่มีให้ผ่าน PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
