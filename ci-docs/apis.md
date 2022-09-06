---
title: ทำงานกับ Customer Insights API
description: ใช้ API และทำความเข้าใจข้อจำกัด
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387363"
---
# <a name="work-with-customer-insights-apis"></a>ทำงานกับ Customer Insights API

Dynamics 365 Customer Insights จัดเตรียม API เพื่อสร้างแอปพลิเคชันของคุณเองตามข้อมูลของคุณใน Customer Insights

> [!IMPORTANT]
> รายละเอียดของ API เหล่านี้แสดงอยู่ใน [ข้อมูลอ้างอิง Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) รวมถึงข้อมูลเพิ่มเติมเกี่ยวกับการดำเนินงาน พารามิเตอร์และการตอบสนอง

API สำหรับ Customer Insights, สร้างการลงทะเบียนแอป Azure และเริ่มต้นใช้งานไลบรารีไคลเอ็นต์

## <a name="get-started-trying-the-customer-insights-apis"></a>เริ่มต้นใช้งาน Customer Insights API

เปิดใช้งาน API สำหรับ Customer Insights และลองใช้ ผู้ดูแลระบบ Customer Insights ต้องเปิดใช้งานการเข้าถึง API เพื่อเข้าถึง Customer Insights เมื่อเปิดใช้งานการเข้าถึงแล้ว ผู้ใช้ทุกคนสามารถใช้ API กับคีย์การสมัครใช้งานได้

1. [ลงชื่อเข้าใช้](https://home.ci.ai.dynamics.com) Customer Insights หากคุณยังไม่ได้สมัครใช้งาน [ลงชื่อเข้าใช้ Customer Insights รุ่นทดลองใช้](https://aka.ms/tryci)

1. ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** และเลือกแท็บ **API**

1. หากไม่ได้ตั้งค่าการเข้าถึงสภาพแวดล้อมของ API ให้เลือก **เปิดใช้งาน**

   การเปิดใช้งาน API จะสร้างคีย์การสมัครใช้งานหลักและรองสำหรับอินสแตนซ์ของคุณที่จะใช้ในคำขอ API ในการสร้างคีย์ใหม่ ให้เลือก **สร้างคีย์หลักใหม่** หรือ **สร้างคีย์รองใหม่** บนแท็บ **API**

1. เลือก [**สำรวจ API ของเรา**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) เพื่อทดลองใช้ API

1. ค้นหาและเลือกการดำเนินการของ API แล้วเลือก **ทดลองใช้**

   :::image type="content" source="media/try-api.png" alt-text="วิธีทดสอบ API":::

1. ในบานหน้าต่างด้านข้าง ตั้งค่าในเมนูแบบหล่นลง **การอนุญาต** เป็น **โดยนัย** โทเค็นส่วนหัว `Authorization` ถูกเพิ่มด้วยโทเค็นแบบแบเรอร์ คีย์การสมัครใช้งานของคุณมีการเติมข้อมูลโดยอัตโนมัติ
  
1. เพิ่มพารามิเตอร์การสอบถามที่จำเป็นทั้งหมดหรือไม่ก็ได้

1. เลื่อนไปที่ด้านล่างสุดของบานหน้าต่างด้านข้าง แล้วเลือก **ส่ง**

   การตอบสนองของ HTTP แสดงที่ด้านล่างของบานหน้าต่าง

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>สร้างการลงทะเบียนแอปใหม่ในพอร์ทัล Azure

สร้าง [การลงทะเบียนแอป](/graph/auth-register-app-v2) ใหม่เพื่อใช้ API สำหรับ Customer Insights ในแอปพลิเคชัน Azure โดยใช้สิทธิ์ที่ได้รับมอบหมาย

1. กรอกข้อมูลใน [ส่วนการเริ่มต้นใช้งาน](#get-started-trying-the-customer-insights-apis)

1. ลงชื่อเข้าใช้ [พอร์ทัล Azure](https://portal.azure.com) ด้วยบัญชีที่สามารถเข้าถึงข้อมูล Customer Insights

1. ค้นหาและเลือก **การลงทะเบียนแอป**

1. เลือก **การลงทะเบียนใหม่** ระบุชื่อแอปพลิเคชัน และเลือกชนิดบัญชี

   หรือเพิ่ม URL การเปลี่ยนเส้นทางก็ได้ http://localhost เพียงพอสำหรับการพัฒนาแอปพลิเคชันบนคอมพิวเตอร์ของคุณ

1. เลือก **ลงทะเบียน**

1. ในการลงทะเบียนแอปใหม่ของคุณ ให้ไปที่ **สิทธิ์ API**

1. เลือก **เพิ่มสิทธิ์** และเลือก **Dynamics 365 AI สำหรับ Customer Insights** ในบานหน้าต่างด้านข้าง

1. สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ที่ได้รับมอบ** แล้วจากนั้น เลือกสิทธิ์ **user_impersonation**

1. เลือก **เพิ่มสิทธิ์**

1. เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์

1. ในการเข้าถึง API โดยไม่มีการลงชื่อเข้าใช้ของผู้ใช้ ให้ไปที่ [สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์](#server-to-server-application-permissions)

คุณสามารถใช้รหัสแอปพลิเคชัน/ไคลเอ็นต์สำหรับการลงทะเบียนแอปนี้กับ [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) เพื่อรับโทเค็นแบบแบเรอร์ที่จะส่งคำขอของคุณไปยัง API

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

สำหรับข้อมูลเกี่ยวกับการใช้ API ในไลบรารีไคลเอนต์ของเรา โปรดดูที่ [ไลบรารีไคลเอนต์ Customer Insights](#customer-insights-client-libraries)

### <a name="server-to-server-application-permissions"></a>สิทธิ์ของแอปพลิเคชันแบบเซิร์ฟเวอร์ต่อเซิร์ฟเวอร์

สร้างการลงทะเบียนแอปที่ไม่ต้องการการโต้ตอบของผู้ใช้และสามารถเรียกใช้บนเซิร์ฟเวอร์ได้

1. การลงทะเบียนแอปของคุณในพอร์ทัล Azure ให้ไปที่ **สิทธิ์ API**

1. เลือก **เพิ่มสิทธิ์**

1. เลือกแท็บ **API ที่องค์กรของฉันใช้** และเลือก **Dynamics 365 AI สำหรับ Customer Insights** จากรายการ

1. สำหรับ **ชนิดสิทธิ์** เลือก **สิทธิ์ของแอปพลิเคชัน** แล้วจากนั้น เลือกสิทธิ์ **CustomerInsights.Api.All**

1. เลือก **เพิ่มสิทธิ์**

1. กลับไปที่ **สิทธิ์ API** สำหรับการลงทะเบียนแอปของคุณ

1. เลือก **ให้ความยินยอมของผู้ดูแลระบบสำหรับ...** เพื่อลงทะเบียนแอปให้เสร็จสมบูรณ์

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. เพิ่มชื่อการลงทะเบียนแอปเป็นผู้ใช้ใน Customer Insights

   1. เปิด Customer Insights ไปที่ **ผู้ดูแลระบบ** > **ความปลอดภัย** และเลือก **เพิ่มผู้ใช้**

   1. ค้นหาชื่อการลงทะเบียนแอปของคุณ เลือกจากผลการค้นหาและเลือก **บันทึก**

## <a name="sample-queries"></a>การสอบถามตัวอย่าง

สำหรับรายการสั้นๆ ของการสอบถามตัวอย่าง OData เพื่อทำงานกับ API โปรดดู [ตัวอย่างการสอบถาม OData](odata-examples.md)

## <a name="customer-insights-client-libraries"></a>ไลบรารีไคลเอ็นต์ Customer Insights

เริ่มต้นใช้งานโดยใช้ไลบรารีไคลเอ็นต์ที่มีอยู่ของ API สำหรับ Customer Insights ซอร์สโค้ดไลบรารีทั้งหมดและแอปพลิเคชันตัวอย่างสามารถดูได้ใน [เพจ Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)

### <a name="c-nuget"></a>C# NuGet

ใช้ไลบรารีไคลเอ็นต์ C# จาก NuGet.org ปัจจุบัน แพคเกจนี้กำหนดเป้าหมายเป็นเฟรมเวิร์ก netstandard2.0 และ netcoreapp2.0 สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแพคเกจ NuGet โปรดดู [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)

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

1. ทำการเรียกไคลเอ็นต์ด้วย "วิธีการขยาย" ตัวอย่างเช่น `GetAllInstancesAsync` หากการเข้าถึง `Microsoft.Rest.HttpOperationResponse` พื้นฐานเป็นวิธีที่ต้องการ ให้ใช้ "วิธีการข้อความ http" ตัวอย่างเช่น `GetAllInstancesWithHttpMessagesAsync`

1. การตอบสนองน่าจะเป็นชนิด `object` เนื่องจากวิธีการดังกล่าวสามารถส่งคืนได้หลายชนิด (ตัวอย่างเช่น `IList<InstanceInfo>` และ `ApiErrorResult`) หากต้องการตรวจสอบชนิดการส่งคืน ให้ใช้ออบเจ็กต์ในชนิดการตอบสนองที่ระบุใน [หน้ารายละเอียด API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) สำหรับการดำเนินการนั้น

   หากต้องการข้อมูลเพิ่มเติมเกี่ยวกับคำขอที่ต้องการ ให้ใช้ **วิธีการข้อความ http** เพื่อเข้าถึงออบเจ็กต์การตอบสนองแบบข้อมูลดิบ

### <a name="nodejs-package"></a>แพคเกจ NodeJS

ใช้ไลบรารีไคลเอ็นต์ NodeJS ที่มีให้ผ่าน NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>แพคเกจ Python

ใช้ไลบรารีไคลเอ็นต์ Python ที่มีให้ผ่าน PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
