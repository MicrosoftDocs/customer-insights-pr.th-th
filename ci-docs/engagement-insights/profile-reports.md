---
title: เปิดใช้งานรายงานโปรไฟล์แบบสำเร็จรูป
description: วิธีสร้างรายงานโปรไฟล์สำเร็จรูปที่จัดกลุ่มตามเพศ อายุ และเขตหรือภูมิภาคของแหล่งกำเนิด
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486143"
---
# <a name="out-of-box-profile-reports"></a>รายงานโปรไฟล์แบบสำเร็จรูป

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

รายงานคือชุดของการจัดรูปแบบการแสดงข้อมูลที่ช่วยให้คุณเข้าใจพฤติกรรมของผู้ใช้ ด้วยการเชื่อมต่อกับความสามารถข้อมูลเชิงลึกของผู้ชม Customer Insights ข้อมูลเชิงลึกของการมีส่วนร่วมสามารถแสดงรายงานที่มีข้อมูลเกี่ยวกับโปรไฟล์ลูกค้าแบบรวม รายงานนี้ประกอบด้วยจำนวนโปรไฟล์ที่คุณมี จัดกลุ่มตามเพศ อายุ และตำแหน่งที่ตั้งทางภูมิศาสตร์

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ผู้ชมสภาพแวดล้อมข้อมูลเชิงลึกต้องจัดเก็บข้อมูลในบัญชี Azure Data Lake Storage ที่จัดการโดยลูกค้า

หากคุณใช้ความสามารถข้อมูลเชิงลึกของผู้ชม Customer Insights รุ่นทดลองหรือสภาพแวดล้อมในที่จัดเก็บที่มีการจัดการ Customer Insights [ติดต่อเรา](https://go.microsoft.com/fwlink/?linkid=2145734) สำหรับความช่วยเหลือ  


## <a name="enable-the-customer-profile-report"></a>เปิดใช้งานรายงานโปรไฟล์ลูกค้า

ผู้ดูแลระบบสภาพแวดล้อมต้อง [เชื่อมโยงข้อมูลเชิงลึกของการมีส่วนร่วมและข้อมูลเชิงลึกของผู้ชม](integrate-audience-insights-engagement-insights.md)

หลังจากระบุรายละเอียดการเชื่อมต่อแล้ว ผู้ดูแลระบบสามารถให้สิทธิ์การเข้าถึงแก่บุคคลอื่นในองค์กรเพื่อดูรายงาน ผู้ดูแลระบบสภาพแวดล้อมที่ตั้งค่าการเชื่อมต่อสามารถเข้าถึงรายงานโดยอัตโนมัติ 

หลังจากเสร็จสิ้นการเชื่อมต่อ คุณลักษณะ **โปรไฟล์** จะพร้อมใช้งานในบานหน้าต่างนำทางด้านซ้าย 

- ไปที่ **ค้นหา** > **โปรไฟล์** เพื่อดูรายงาน

รายงาน **โปรไฟล์** ประกอบด้วยการจัดรูปแบบการแสดงเกี่ยวกับเพศ อายุ และตำแหน่งที่ตั้งทางภูมิศาสตร์ของโปรไฟล์ลูกค้าที่เชื่อมต่อ

:::image type="content" source="media/customer-profiles.png" alt-text="รายงานโปรไฟล์ลูกค้า":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]