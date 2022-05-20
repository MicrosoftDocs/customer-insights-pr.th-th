---
title: สร้างสภาพแวดล้อมใน Customer Insights
description: ขั้นตอนในการสร้างสภาพแวดล้อมด้วยการสมัครใช้งานที่ได้รับสิทธิ์ใช้งานสำหรับ Dynamics 365 Customer Insights
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712925"
---
# <a name="create-an-environment-in-customer-insights"></a>สร้างสภาพแวดล้อมใน Customer Insights

บทความนี้อธิบายวิธีสร้างสภาพแวดล้อมใหม่หลังจากที่องค์กรของคุณซื้อการสมัครใช้งาน Dynamics 365 Customer Insights 

องค์กรต่างๆ สามารถสร้างสภาพแวดล้อมหลายรายการสำหรับทุกสิทธิ์การใช้งาน Customer Insights หากองค์กรของคุณซื้อสิทธิ์การใช้งานมากกว่าหนึ่งสิทธิ์ [ติดต่อทีมสนับสนุนของเรา](https://go.microsoft.com/fwlink/?linkid=2079641) เพื่อเพิ่มจำนวนของสภาพแวดล้อมที่มีอยู่ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับความจุและความจุส่วนเพิ่ม โปรดดู [คู่มือการให้สิทธิ์การใช้งาน Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544)

> [!NOTE]
> หากต้องการลองใช้บริการ โปรดดูที่ [ตั้งค่าสภาพแวดล้อมการทดลองใช้](trial-signup.md)

## <a name="create-a-new-environment"></a>สร้างสภาพแวดล้อมใหม่

หลังจากซื้อสิทธิ์ใช้งานของการสมัครใช้งาน Customer Insights แล้ว ผู้ดูแลระบบส่วนกลางของผู้เช่า Microsoft 365 จะได้รับอีเมลที่เชิญให้พวกเขาสร้างสภาพแวดล้อม ไปที่ [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) เพื่อเริ่มต้นใช้งาน 

ประสบการณ์ที่แนะนำจะช่วยให้คุณทำตามขั้นตอนต่างๆ เพื่อรวบรวมข้อมูลที่จำเป็นทั้งหมดสำหรับสภาพแวดล้อมใหม่ คุณต้องมี [สิทธิ์ของผู้ดูแลระบบ](permissions.md) ใน Customer Insights เพื่อสร้างหรือจัดการสภาพแวดล้อม

1. เปิดตัวเลือกสภาพแวดล้อมและเลือก **+ ใหม่**
  
   :::image type="content" source="media/environment-picker.png" alt-text="เลือกตัวเลือกสภาพแวดล้อม":::

1. ทำตามประสบการณ์ที่แนะนำซึ่งสรุปไว้ในส่วนต่อไปนี้

### <a name="step-1-provide-environment-information"></a>ขั้นตอนที่ 1: ให้ข้อมูลสภาพแวดล้อม

ในขั้นตอน **ข้อมูลพื้นฐาน** เลือกว่าคุณต้องการสร้างสภาพแวดล้อมตั้งแต่เริ่มต้นหรือ [คัดลอกข้อมูลจากสภาพแวดล้อมอื่น](manage-environments.md#copy-the-environment-configuration)

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="กล่องโต้ตอบเพื่อสร้างสภาพแวดล้อม Customer Insights ใหม่":::

ให้รายละเอียดต่อไปนี้:
   - **ชื่อ**: ชื่อสำหรับสภาพแวดล้อมนี้ ฟิลด์นี้ถูกกรอกข้อมูลเรียบร้อยแล้ว หากคุณได้คัดลอกสภาพแวดล้อมที่มีอยู่ แต่คุณสามารถเปลี่ยนแปลงได้
   - **เลือกธุรกิจของคุณ**: เลือกผู้ชมหลักสำหรับสภาพแวดล้อมใหม่ คุณสามารถทำงานกับผู้บริโภครายบุคคล (B-to-C) หรือ [บัญชีธุรกิจ](work-with-business-accounts.md) (B-to-B)
   - **ชนิด**: เลือกว่าคุณต้องการสร้างสภาพแวดล้อมการทำงานจริงหรือสภาพแวดล้อม Sandbox สภาพแวดล้อม Sandbox ไม่อนุญาตให้มีการรีเฟรชข้อมูลตามกำหนดเวลาและมีไว้สำหรับการใช้งานเบื้องต้นและการทดสอบเท่านั้น สภาพแวดล้อม Sandbox ใช้ผู้ชมหลักเดียวกันกับสภาพแวดล้อมการทำงานจริงที่เลือกอยู่ในปัจจุบัน
   - **ภูมิภาค**: ภูมิภาคที่มีการปรับใช้และที่เป็นโฮสต์บริการ

### <a name="step-2-configure-data-storage"></a>ขั้นตอนที่ 2: กำหนดค่าการจัดเก็บข้อมูล

ในขั้นตอน **การจัดเก็บข้อมูล** เลือกตำแหน่งที่จะจัดเก็บข้อมูล Customer Insights

คุณจะมีสองตัวเลือก: **ที่เก็บข้อมูล Customer Insights** (Azure Data Lake ที่จัดการโดยทีม Customer Insights) และ **Azure Data Lake Storage** (Azure Data Lake Storage ของคุณเอง) ตามค่าเริ่มต้น ตัวเลือกที่เก็บข้อมูล Customer Insights จะถูกเลือก

:::image type="content" source="media/data-storage-environment.png" alt-text="เลือก Azure Data Lake Storage เพื่อเก็บข้อมูลของคุณ":::

โดยการบันทึกข้อมูลไปที่ Azure Data Lake Storage คุณตกลงว่าข้อมูลจะถูกโอนไปและเก็บไว้ในที่ตั้งทางภูมิศาสตร์ที่เหมาะสมสำหรับบัญชีที่เก็บข้อมูล Azure นั้น ตำแหน่งนี้อาจแตกต่างจากที่เก็บข้อมูลใน Dynamics 365 Customer Insights เรียนรู้เพิ่มเติมที่ [Microsoft Trust Center](https://www.microsoft.com/trust-center)

> [!NOTE]
> ปัจจุบัน Customer Insights รองรับสิ่งต่อไปนี้:  
> - บัญชี Azure Data Lake Storage จากภูมิภาค Azure เดียวกันกับที่คุณเลือกเมื่อสร้างสภาพแวดล้อม
> - บัญชี Azure Data Lake Storage ที่เป็น รุ่น2 และเปิดใช้งาน *เนมสเปซแบบลำดับชั้น* ไม่รองรับบัญชีที่เก็บข้อมูล Azure Data Lake รุ่น1

สำหรับตัวเลือก Azure Data Lake Storage คุณสามารถเลือกระหว่างตัวเลือกตามทรัพยากรและตัวเลือกตามการสมัครใช้งานสำหรับการรับรองความถูกต้อง ดูข้อมูลเพิ่มเติมได้ที่ [เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก Azure](connect-service-principal.md) คอนเทนเนอร์ชื่อ `customerinsights` ต้องมีอยู่ในบัญชีที่เก็บข้อมูล

เมื่อกระบวนการของระบบ เช่น การนำเข้าข้อมูลเสร็จสิ้น ระบบจะสร้างโฟลเดอร์ที่เกี่ยวข้องในบัญชีการจัดเก็บข้อมูลที่คุณระบุ ระบบจะสร้างไฟล์ข้อมูลและไฟล์ *model.json* และเพิ่มไปยังโฟลเดอร์ตามชื่อกระบวนการ

หากคุณสร้าง Customer Insights หลายสภาพแวดล้อมและเลือกที่จะบันทึกเอนทิตีเอาต์พุตจากสภาพแวดล้อมเหล่านั้นไปยังบัญชีที่เก็บข้อมูลของคุณ Customer Insights จะสร้างโฟลเดอร์แยกต่างหากสำหรับแต่ละสภาพแวดล้อมด้วย `ci_environmentID` ในคอนเทนเนอร์

### <a name="step-3-connect-to-microsoft-dataverse"></a>ขั้นตอนที่ 3: เชื่อมต่อไปยัง Microsoft Dataverse
   
ขั้นตอน **Microsoft Dataverse** ช่วยให้คุณเชื่อมต่อ Customer Insights กับสภาพแวดล้อม Dataverse

เตรียมสภาพแวดล้อม Microsoft Dataverse ของคุณเองเพื่อแชร์ข้อมูล (โปรไฟล์และข้อมูลเชิงลึก) กับแอปพลิเคชันทางธุรกิจที่อยู่บน Dataverse เช่น Dynamics 365 Marketing หรือแอปพลิเคชันแบบจำลองใน Power Apps เว้นฟิลด์นี้งไว้หากคุณไม่มีสภาพแวดล้อม Dataverse ของตนเองและเราจะจัดเตรียมไว้ให้คุณ

การเชื่อมต่อกับสภาพแวดล้อม Dataverse ของคุณยังช่วยให้คุณสามารถ [นำเข้าข้อมูลจากแหล่งข้อมูลในสถานที่โดยใช้กระแสข้อมูล Power Platform และเกตเวย์](data-sources.md#add-data-from-on-premises-data-sources)

> [!IMPORTANT]
> 1. Customer Insights และ Dataverse ต้องอยู่ในภูมิภาคเดียวกันจึงจะสามารถแชร์ข้อมูลได้
> 1. คุณต้องมีบทบาทผู้ดูแลระบบส่วนกลางในสภาพแวดล้อม Dataverse ตรวจสอบว่า [สภาพแวดล้อม Dataverse นี้เชื่อมโยง](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) กับกลุ่มความปลอดภัยที่กำหนดหรือไม่และตรวจสอบว่าคุณได้เพิ่มสภาพแวดล้อมลงในกลุ่มความปลอดภัยเหล่านั้นแล้ว
> 1. ไม่มีสภาพแวดล้อม Customer Insights ที่มีอยู่เชื่อมโยงกับสภาพแวดล้อม Dataverse นั้น เรียนรู้วิธีการ [ลบการเชื่อมต่อกับสภาพแวดล้อม Dataverse ที่มีอยู่](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment)

:::image type="content" source="media/dataverse-provisioning.png" alt-text="การแชร์ข้อมูลกับ Microsoft Dataverse อัตโนมัติเปิดใช้งานสำหรับอินสแตนซ์ใหม่ทั้งหมด":::

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการเปิดใช้งานการแชร์ข้อมูลกับ Microsoft Dataverse จาก Azure Data Lake Storage ของคุณเอง ดูที่ [เชื่อมต่อกับ Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse)

Customer Insights ไม่สนับสนุนสถานการณ์การแบ่งปันข้อมูลต่อไปนี้:
- หากคุณเปิดใช้งานการแบ่งปันข้อมูลด้วยที่จัดเก็บข้อมูลดิบที่จัดการ Dataverse คุณจะไม่สามารถ [สร้างค่าที่คาดคะเนหรือขาดหายไปในเอนทิตี](predictions.md)

### <a name="step-4-finalize-the-settings"></a>ขั้นตอนที่ 4: ดำเนินการตั้งค่าให้เสร็จสมบูรณ์

ในขั้นตอน **ตรวจทาน** ไปที่การตั้งค่าที่ระบุทั้งหมด เมื่อทุกอย่างดูสมบูรณ์ ให้เลือก **สร้าง** เพื่อสร้างสภาพแวดล้อม 

คุณยังสามารถเปลี่ยนการตั้งค่าส่วนใหญ่ได้ในภายหลัง สำหรับข้อมูลเพิ่มเติม ดู [จัดการการสภาพแวดล้อม](manage-environments.md)

## <a name="work-with-your-new-environment"></a>ทำงานกับสภาพแวดล้อมใหม่ของคุณ

ทบทวนทความต่อไปนี้เพื่อช่วยคุณเริ่มต้นใช้งานการกำหนดค่า Customer Insights: 

- [เพิ่มผู้ใช้เพิ่มเติมและกำหนดสิทธิ์](permissions.md)
- [นำเข้าแหล่งข้อมูลของคุณ](data-sources.md) และดำเนินการผ่าน [กระบวนการรวมข้อมูล](data-unification.md) เพื่อให้ได้ [โปรไฟล์ลูกค้าแบบรวม](customer-profiles.md)
- [เพิ่มข้อมูลโปรไฟล์ลูกค้าแบบรวม](enrichment-hub.md) หรือ [เรียกใช้โมเดลเชิงคาดการณ์](predictions-overview.md)
- [สร้างเซ็กเมนต์](segments.md) เพื่อจัดกลุ่มลูกค้าและ [การวัด](measures.md) เพื่อทบทวน KPI
- [ตั้งค่าการเชื่อมต่อ](connections.md) และ [การส่งออก](export-destinations.md) เพื่อประมวลผลชุดย่อยของข้อมูลของคุณในแอปพลิเคชันอื่น
