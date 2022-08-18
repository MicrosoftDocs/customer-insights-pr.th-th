---
title: ส่งออกข้อมูลไปยัง Azure Synapse Analytics (พรีวิว)
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Azure Synapse Analytics
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259867"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>ส่งออกข้อมูลไปยัง Azure Synapse Analytics (พรีวิว)

Azure Synapse เป็นบริการวิเคราะห์ที่ช่วยเร่งเวลาไปยังข้อมูลเชิงลึกในคลังข้อมูลและระบบข้อมูลขนาดใหญ่ คุณนำเข้าและใช้ข้อมูล Customer Insights ได้ใน [Azure Synapse](/azure/synapse-analytics/overview-what-is)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

> [!NOTE]
> อย่าลืมตั้งค่า **การกำหนดบทบาท** ทั้งหมดตามที่อธิบายไว้

- ใน Customer Insights บัญชีผู้ใช้ Azure Active Directory (AD) ของคุณต้องมี [บทบาทผู้ดูแลระบบ](permissions.md#add-users)

ใน Azure:

- การสมัครใช้งาน Azure ที่ใช้งานอยู่

- หากใช้บัญชี Azure Data Lake Storage รุ่น2 ใหม่ [บริการหลักสำหรับ Customer Insights](connect-service-principal.md) จะต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลในที่เก็บข้อมูล Blob** Data Lake Storage Gen2 **จำเป็นต้อง** เปิดใช้งาน [เนมสเปซตามลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)

- ในกลุ่มทรัพยากรที่มี Azure Synapse workspace อยู่ *บริการหลัก* และผู้ใช้ *Azure AD ที่มีสิทธิ์ของผู้ดูแลระบบใน Customer Insights* ต้องได้รับการกำหนด [สิทธิ์](/azure/role-based-access-control/role-assignments-portal) **ผู้อ่าน** เป็นอย่างน้อย

- ผู้ใช้ *Azure AD ที่มีสิทธิ์ของผู้ดูแลระบบใน Customer Insights* มีสิทธิ์ **ผู้สนับสนุนข้อมูลในที่เก็บข้อมูล Blob** ในบัญชี Azure Data Lake Storage รุ่น2 ที่มีข้อมูลอยู่และเชื่อมโยงกับ Azure Synapse workspace เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- *[ข้อมูลประจำตัวที่มีการจัดการของ Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* มีสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage รุ่น2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับ Azure Synapse workspace เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- บน Azure Synapse workspace *บริการหลักสำหรับ Customer Insights* มี [บทบาทที่กำหนด](/azure/synapse-analytics/security/how-to-set-up-access-control) เป็น **ผู้ดูแลระบบ Synapse**

- หากสภาพแวดล้อม Customer Insights ของคุณเก็บข้อมูลใน [Azure Data Lake Storage ของตนเอง](own-data-lake-storage.md) ผู้ใช้ที่ตั้งค่าการเชื่อมต่อกับ Azure Synapse Analytics ต้องมีบทบาท **ผู้อ่าน** ในตัวเป็นอย่างน้อยในบัญชี Data Lake Storage สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)

## <a name="set-up-connection-to-azure-synapse"></a>ตั้งค่าการเชื่อมต่อไปยัง Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Synapse Analytics**

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ **ชื่อที่แสดง** ชื่อและชนิดของการเชื่อมต่อจะอธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ โดยค่าเริ่มต้น จะเป็นผู้ดูแลระบบเท่านั้น ดูข้อมูลเพิ่มเติมที่ [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. เลือกหรือค้นหาการสมัครใช้งานที่คุณต้องการใช้ข้อมูล Customer Insights ในนั้น ทันทีที่เลือกการสมัครใช้งาน คุณยังสามารถเลือก **พื้นที่ทำงาน**, **บัญชีที่เก็บข้อมูล** และ **คอนเทนเนอร์** ได้ด้วย

1. ตรวจสอบ [ความเป็นส่วนตัวและการปฏิบัติตามข้อกำหนดของข้อมูล](connections.md#data-privacy-and-compliance) และเลือก **ฉันเห็นด้วย**

1. ให้เลือก **บันทึก** เพื่อทำการเชื่อมต่อให้เสร็จสิ้น

## <a name="configure-an-export"></a>กำหนดค่าการส่งออก

[!INCLUDE [export-permission-include](includes/export-permission.md)] ในการกำหนดค่าการส่งออกด้วยการเชื่อมต่อที่แชร์ คุณต้องมีสิทธิ์ **ผู้สนับสนุน** ใน Customer Insights เป็นอย่างน้อย

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **เพิ่มส่งออก**

1. ในฟิลด์ **การเชื่อมต่อสำหรับการส่งออก** เลือกการเชื่อมต่อจากส่วน Azure Synapse Analytics ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ

1. ระบุ **ชื่อที่แสดง** ที่เป็นที่รู้จักสำหรับการส่งออกของคุณ และ **ชื่อฐานข้อมูล** การส่งออกจะสร้าง [ฐานข้อมูลที่จัดเก็บข้อมูลดิบ Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) ในพื้นที่ทำงานที่กำหนดไว้ในการเชื่อมต่อ

1. เลือกเอนทิตีที่คุณต้องการส่งออกไปยัง Azure Synapse Analytics
   > [!NOTE]
   > ไม่รองรับแหล่งข้อมูลที่อิงตาม [โฟลเดอร์ Common Data Model](connect-common-data-model.md)

1. เลือก **บันทึก**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ในการสอบถามข้อมูลที่ส่งออกไปยัง Synapse Analytics คุณต้องมีสิทธิ์ **ผู้อ่านข้อมูลของ Blob ในพื้นที่จัดเก็บ** เพื่อเข้าถึงที่เก็บข้อมูลปลายทางในพื้นที่ทำงานของการส่งออก

## <a name="update-an-export"></a>อัปเดตการส่งออก

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **แก้ไข** ในการส่งออกที่คุณต้องการอัปเดต

   - **เพิ่ม** หรือ **ลบ** เอนทิตีจากการเลือก หากเอนทิตีถูกลบออกจากการเลือก เอนทิตีจะไม่ถูกลบออกจากฐานข้อมูล Synapse Analytics อย่างไรก็ตาม การรีเฟรชข้อมูลในอนาคตจะไม่อัปเดตเอนทิตีที่ถูกลบออกในฐานข้อมูลนั้น

   - **การเปลี่ยนชื่อฐานข้อมูล** สร้างฐานข้อมูล Synapse Analytics ใหม่ ฐานข้อมูลที่มีชื่อที่กำหนดค่าไว้ก่อน จะไม่ได้รับการอัปเดตใดๆ ในการรีเฟรชในอนาคต

[!INCLUDE [footer-include](includes/footer-banner.md)]
