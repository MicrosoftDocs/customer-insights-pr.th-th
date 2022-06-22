---
title: ใช้บัญชี Azure Data Lake Storage รุ่น2 ของคุณเอง
author: mukeshpo
description: เรียนรู้เกี่ยวกับข้อกำหนดในการใช้บัญชี Azure Data Lake Storage ของคุณเองเพื่อจัดเก็บข้อมูล Customer Insights
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011956"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>ใช้บัญชี Azure Data Lake Storage รุ่น2 ของคุณเอง

Dynamics 365 Customer Insights ให้คุณมีตัวเลือกในการจัดเก็บข้อมูลทั้งหมดของคุณใน [Azure Data Lake Storage รุ่น2](/azure/storage/blobs/data-lake-storage-introduction)

การบันทึกข้อมูลไปที่ Data Lake Storage หมายถึงคุณตกลงว่าข้อมูลจะถูกโอนไปและเก็บไว้ในที่ตั้งทางภูมิศาสตร์ที่เหมาะสมสำหรับบัญชีที่เก็บข้อมูล Azure นั้น สำหรับข้อมูลเพิ่มเติม โปรดดู [ศูนย์ความเชื่อถือของ Microsoft](https://www.microsoft.com/trust-center)

ผู้ดูแลระบบใน Customer Insights สามารถ [สร้างสภาพแวดล้อม](create-environment.md) และ [ระบุตัวเลือกการจัดเก็บข้อมูล](create-environment.md#step-2-configure-data-storage) ในกระบวนการ

## <a name="prerequisites-to-use-your-storage-account"></a>ข้อกำหนดเบื้องต้นในการใช้บัญชีที่เก็บข้อมูลของคุณ

- บัญชี Azure Data Lake Storage ต้องอยู่ในภูมิภาค Azure เดียวกันกับที่คุณเลือกเมื่อสร้างสภาพแวดล้อม Customer Insights คุณสามารถตวรจสอบภูมิภาคของสภาพแวดล้อม Customer Insights ภายใต้ **ผู้ดูแลระบบ** > **ระบบ** > **เกี่ยวกับ**
- Data Lake Storage ต้องเป็นรุ่น2 และ [เปิดใช้งาน Namespace ตามลำดับชั้น](/azure/storage/blobs/create-data-lake-storage-account) ไม่รองรับบัญชีที่เก็บข้อมูลรุ่น1
- คอนเทนเนอร์ชื่อ `customerinsights` ต้องมีอยู่ในบัญชีที่เก็บข้อมูล คุณต้องสร้างคอนเทนเนอร์ก่อนที่จะใช้ Data Lake Storage ของคุณเองใน Customer Insights ผู้ดูแลระบบที่ตั้งค่าสภาพแวดล้อม Customer Insights ต้องการบทบาทผู้สนับสนุนข้อมูลในที่เก็บข้อมูล Blob หรือเจ้าของข้อมูลในที่เก็บข้อมูล Blob ในบัญชีที่เก็บข้อมูลหรือคอนเทนเนอร์ `customerinsights` สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการกำหนดสิทธิ์ในบัญชีที่เก็บข้อมูล โปรดดู [สร้างบัญชีที่เก็บข้อมูล](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal)

## <a name="connect-customer-insights-with-your-storage-account"></a>เชื่อมต่อ Customer Insights กับบัญชีที่เก็บข้อมูลของคุณ

เมื่อคุณสร้างสภาพแวดล้อมใหม่ ตรวจสอบให้แน่ใจว่ามีบัญชี Data Lake Storage และตรงตามข้อกำหนดเบื้องต้นทั้งหมด

1. ในขั้นตอน **การจัดเก็บข้อมูล** ระหว่างการสร้างสภาพแวดล้อม ให้ตั้งค่า **บันทึกข้อมูลผลลัพธ์** ไปยัง **Azure Data Lake Storage รุ่น2**
1. เลือกวิธีการ **เชื่อมต่อที่เก็บข้อมูลของคุณ** คุณสามารถเลือกระหว่างตัวเลือกตามทรัพยากรและตัวเลือกตามการสมัครใช้งานสำหรับการรับรองความถูกต้อง สำหรับข้อมูลเพิ่มเติม โปรดดู [เชื่อมต่อกับบัญชี Azure Data Lake Storage โดยใช้บริการหลัก Azure](connect-service-principal.md)
   - สำหรับ **การสมัครใช้งาน Azure** เลือก **การสมัครใช้งาน**, **กลุ่มทรัพยากร** และ **บัญชีที่เก็บข้อมูล** ที่มีคอนเทนเนอร์ `customerinsights`
   - สำหรับ **คีย์บัญชี** ให้ระบุ **ชื่อบัญชี** และ **คีย์บัญชี** สำหรับบัญชี Data Lake Storage การใช้วิธีการรับรองความถูกต้องนี้หมายความว่าคุณจะได้รับแจ้งหากองค์กรของคุณหมุนเวียนคีย์ คุณต้อง [ปรับปรุงการกำหนดค่าสภาพแวดล้อม](manage-environments.md#edit-an-existing-environment) ด้วยคีย์ใหม่เมื่อมีการหมุนเวียน
1. เลือกว่าคุณต้องการใช้ Azure Private Link เพื่อเชื่อมต่อกับบัญชีที่เก็บข้อมูลและ [สร้างการเชื่อมต่อกับ Private Link](security-overview.md#private-links-tab) ด้วยกระบวนการสองขั้นตอนหรือไม่

เมื่อกระบวนการของระบบ เช่น การนำเข้าข้อมูลเสร็จสิ้น ระบบจะสร้างโฟลเดอร์ที่เกี่ยวข้องในบัญชีที่เก็บข้อมูล ระบบจะสร้างไฟล์ข้อมูลและไฟล์ *model.json* และเพิ่มไปยังโฟลเดอร์ตามชื่อกระบวนการ

หากคุณสร้าง Customer Insights หลายสภาพแวดล้อมและเลือกที่จะบันทึกเอนทิตีเอาต์พุตจากสภาพแวดล้อมเหล่านั้นไปยังบัญชีที่เก็บข้อมูลของคุณ Customer Insights จะสร้างโฟลเดอร์แยกต่างหากสำหรับแต่ละสภาพแวดล้อมด้วย `ci_environmentID` ในคอนเทนเนอร์
