---
title: ใช้โปรไฟล์แบบรวมใน Dynamics 365 Marketing
description: เรียนรู้วิธีการรวมโปรไฟล์แบบรวมและเซ็กเมนต์เข้ากับ Dynamics 365 Marketing
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054455"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>ใช้ unified customer profile ใน Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) ยกระดับประสบการณ์ของลูกค้า ช่วยให้คุณสามารถประสานการเดินทางส่วนบุคคลในทุกจุดติดต่อเพื่อเสริมสร้างความสัมพันธ์และได้รับความภักดี แอป Dynamics 365 Marketing ทํางานได้อย่างราบรื่นกับ Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams, และผลิตภัณฑ์อื่น ๆ และช่วยให้คุณตัดสินใจได้เร็วขึ้นและดีขึ้นโดยใช้พลังของข้อมูลและ AI

การเชื่อมต่อข้อมูล Customer Insights กับ Marketing ช่วยให้คุณสามารถ:

- กําหนดเป้าหมาย Unified customer profile และเซ็กเมนต์ ซึ่งช่วยให้คุณสามารถดึงดูดลูกค้าทุกคนได้ โดยไม่คํานึงถึงตำแหน่งข้อมูลของลูกค้า
- เนื้อหาแบบไดนามิกพื้นฐาน (เช่น โทเค็นส่วนบุคคล) ในอีเมล, SMS และการแจ้งเตือนแบบพุชเกี่ยวกับการวัดต่างๆ เช่น สถานะสมาชิก วันที่ต่ออายุการสมัครใช้งาน บัญชีหลัก หรือการวัดอื่นๆ ที่คุณบันทึกไว้ในโปรไฟล์ Customer Insights แบบรวม
- โหลดข้อมูลจาก Marketing ลงใน Customer Insights และรวมเข้ากับข้อมูลลูกค้าจากแหล่งข้อมูลอื่นๆ
- ใช้การล้างข้อมูล Customer Insights การเพิ่มความสมบูรณ์ และเครื่องมือการจับคู่แบบคลุมเครือ

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>ใช้โปรไฟล์ลูกค้าที่หลากหลายในการตลาดแบบเรียลไทม์

การตลาดแบบเรียลไทม์ช่วยให้คุณสร้าง[ทริกเกอร์แบบกำหนดเอง](/dynamics365/marketing/real-time-marketing-custom-triggers) ซึ่งเปิดตัวการเดินทางของลูกค้าตามการดำเนินการของลูกค้า ยิ่งข้อมูลของคุณเป็นส่วนตัวมากเท่าไร การเดินทางของคุณก็จะยิ่งมีความเกี่ยวข้องและเป็นส่วนตัวมากขึ้นเท่านั้น นี่คือสิ่งที่ช่วยให้การรวม Marketing และ Customer Insights เข้าด้วยกันมีประสิทธิภาพมากยิ่งขึ้น คุณสามารถ [รวมข้อมูล](data-unification.md) จากแหล่งใดๆ ก็ได้ จากนั้นใช้เพื่อขับเคลื่อนการเดินทางของลูกค้าที่มีความเป็นส่วนตัวสูง

เรียนรู้เพิ่มเติม: [ใช้โปรไฟล์และเซ็กเมนต์ Customer Insights ในการตลาดแบบเรียลไทม์](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>ใช้เซ็กเมนต์แบบครบวงจรกับการเดินทางของลูกค้าขาออก

Customer Insights ช่วยให้คุณสามารถปรับแต่งข้อมูลจากแหล่งที่มาต่างๆ และรวมเข้ากับกลุ่มลูกค้าแบบรวม ด้วย [การเชื่อมต่อ Customer Insights กับการตลาดขาออก](export-dynamics365-marketing.md) เซ็กเมนต์เหล่านี้จะปรากฏขึ้น *และ* รีเฟรชโดยอัตโนมัติในตัวออกแบบการเดินทางของลูกค้า

เรียนรู้เพิ่มเติม: [ใช้เซ็กเมนต์จาก Dynamics 365 Customer Insights กับ Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>ดึงข้อมูลจาก Azure Data Lake Storage ของคุณเอง

คุณจะไม่ถูกจํากัดเฉพาะที่เก็บข้อมูลระบบคลาวด์ หากคุณต้องการใช้ข้อมูล Customer Insights กับ Marketing หากคุณมีการตั้งค่า Azure Data Lake Storage ของคุณเองอยู่แล้ว คุณก็สามารถเชื่อมต่อกับ Customer Insights จากนั้นแบ่งปันข้อมูลกับแอป Marketing เช่นเดียวกับที่คุณทำกับการตั้งค่าบนระบบคลาวด์

เรียนรู้เพิ่มเติม: [เปิดใช้งานการแชร์ข้อมูลกับ Dataverse จาก Azure Data Lake Storage ของคุณเอง](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
