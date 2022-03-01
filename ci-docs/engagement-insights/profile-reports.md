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
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033975"
---
# <a name="out-of-box-profile-reports"></a>รายงานโปรไฟล์แบบสำเร็จรูป

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

รายงานคือชุดของการจัดรูปแบบการแสดงข้อมูลที่ช่วยให้คุณเข้าใจพฤติกรรมของผู้ใช้ ด้วยการเชื่อมต่อกับความสามารถข้อมูลเชิงลึกของผู้ชม Customer Insights ข้อมูลเชิงลึกของการมีส่วนร่วมสามารถแสดงรายงานที่มีข้อมูลเกี่ยวกับโปรไฟล์ลูกค้าแบบรวม รายงานนี้ประกอบด้วยจำนวนโปรไฟล์ที่คุณมี จัดกลุ่มตามเพศ อายุ และตำแหน่งที่ตั้งทางภูมิศาสตร์

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ผู้ชมสภาพแวดล้อมข้อมูลเชิงลึกต้องจัดเก็บข้อมูลในบัญชี Azure Data Lake Storage ที่จัดการโดยลูกค้า

หากคุณใช้ความสามารถข้อมูลเชิงลึกของผู้ชม Customer Insights รุ่นทดลองหรือสภาพแวดล้อมในที่จัดเก็บที่มีการจัดการ Customer Insights [ติดต่อเรา](https://go.microsoft.com/fwlink/?linkid=2145734) สำหรับความช่วยเหลือ  


## <a name="enable-the-customer-profile-report"></a>เปิดใช้งานรายงานโปรไฟล์ลูกค้า

ผู้ดูแลสภาพแวดล้อมต้อง [สร้างการเชื่อมต่อกับข้อมูลเชิงลึกผู้ชม](configure-connections.md)

หลังจากระบุรายละเอียดการเชื่อมต่อแล้ว ผู้ดูแลระบบสามารถให้สิทธิ์การเข้าถึงแก่บุคคลอื่นในองค์กรเพื่อดูรายงาน ผู้ดูแลระบบสภาพแวดล้อมที่ตั้งค่าการเชื่อมต่อสามารถเข้าถึงรายงานโดยอัตโนมัติ 

หลังจากเสร็จสิ้นการเชื่อมต่อ คุณลักษณะ **โปรไฟล์** จะพร้อมใช้งานในบานหน้าต่างนำทางด้านซ้าย 

- ไปที่ **ค้นหา** > **โปรไฟล์** เพื่อดูรายงาน

รายงาน **โปรไฟล์** ประกอบด้วยการจัดรูปแบบการแสดงเกี่ยวกับเพศ อายุ และตำแหน่งที่ตั้งทางภูมิศาสตร์ของโปรไฟล์ลูกค้าที่เชื่อมต่อ

:::image type="content" source="media/customer-profiles.png" alt-text="รายงานโปรไฟล์ลูกค้า":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]