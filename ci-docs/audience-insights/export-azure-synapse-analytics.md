---
title: ส่งออกข้อมูล Customer Insights ไปยัง Azure Synapse Analytics
description: เรียนรู้วิธีกำหนดค่าการเชื่อมต่อกับ Azure Synapse Analytics
ms.date: 01/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 289c8d545f057b3f70679b485cf4350545c0587b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231335"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>ส่งออกข้อมูลไปยัง Azure Synapse Analytics (พรีวิว)

Azure Synapse เป็นบริการวิเคราะห์ที่ช่วยเร่งเวลาไปยังข้อมูลเชิงลึกในคลังข้อมูลและระบบข้อมูลขนาดใหญ่ คุณนำเข้าและใช้ข้อมูล Customer Insights ได้ใน [Azure Synapse](/azure/synapse-analytics/overview-what-is)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้เพื่อกำหนดค่าการเชื่อมต่อจาก Customer Insights ไปยัง Azure Synapse

> [!NOTE]
> อย่าลืมตั้งค่า **การกำหนดบทบาท** ทั้งหมดตามที่อธิบายไว้  

## <a name="prerequisites-in-customer-insights"></a>ข้อกำหนดเบื้องต้นใน Customer Insights

* คุณมีบทบาท **ผู้ดูแลระบบ** ในข้อมูลเชิงลึกของผู้ชม เรียนรู้เพิ่มเติมเกี่ยวกับ [การตั้งค่าสิทธิ์ผู้ใช้ในข้อมูลเชิงลึกของผู้ชม](permissions.md#assign-roles-and-permissions)

ใน Azure: 

- การสมัครใช้งาน Azure ที่ใช้งานอยู่

- หากใช้บัญชี Azure Data Lake Storage Gen2 ใหม่ *หลักบริการสำหรับข้อมูลเชิงลึกของผู้ชม* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** เรียนรู้เพิ่มเติมเกี่ยวกับ [การเชื่อมต่อกับบัญชี Azure Data Lake Storage Gen2 ที่มีหลักบริการของ Azure สำหรับข้อมูลเชิงลึกของผู้ชม](connect-service-principal.md) Data Lake Storage Gen2 **จำเป็นต้อง** เปิดใช้งาน [เนมสเปซตามลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)

- ในกลุ่มทรัพยากรที่พื้นที่ทำงาน Azure Synapse ตั้งอยู่ *หลักบริการ* และ *ผู้ใช้สำหรับข้อมูลเชิงลึกของผู้ชม* ต้องได้รับมอบหมายสิทธิ์ **ผู้อ่าน** เป็นอย่างน้อย สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)

- *ผู้ใช้* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- *[ข้อมูลประจำตัวที่มีการจัดการของพื้นที่ทำงาน Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- บนพื้นที่ทำงาน Azure Synapse *หลักบริการสำหรับข้อมูลเชิงลึกของผู้ชม* ต้องการบทบาท **ผู้ดูแลระบบ Synapse** ที่ได้รับมอบหมาย สำหรับข้อมูลเพิ่มเติม โปรดดู [วิธีตั้งค่าการควบคุมการเข้าถึงสำหรับพื้นที่ทำงาน Synapse ของคุณ](/azure/synapse-analytics/security/how-to-set-up-access-control)

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>ตั้งค่าการเชื่อมต่อและส่งออกไปยัง Azure Synapse

### <a name="configure-a-connection"></a>กำหนดค่าการเชื่อมต่อ

ในการสร้างการเชื่อมต่อ บริการหลักและบัญชีผู้ใช้ใน Customer Insights จำเป็นต้องมีสิทธิ์ **ผู้อ่าน** ใน *กลุ่มทรัพยากร* ที่มี Synapse Analytics workspace ตั้งอยู่ นอกจากนี้ บริการหลักและผู้ใช้บน Synapse Analytics workspace จำเป็นมีสิทธิ์ **ผู้ดูแลระบบ Synapse** ด้วย 

1. ไปที่ **การจัดการ** > **การเชื่อมต่อ**

1. เลือก **เพิ่มการเชื่อมต่อ** และเลือก **Azure Synapse Analytics** หรือเลือก **ตั้งค่า** บนไทล์ **Azure Synapse Analytics** เพื่อกำหนดค่าการเชื่อมต่อ

1. ตั้งชื่อที่เป็นที่รู้จักให้การเชื่อมต่อของคุณในฟิลด์ ชื่อที่แสดง ชื่อและชนิดของการเชื่อมต่อจะอธิบายการเชื่อมต่อนี้ เราขอแนะนำให้เลือกชื่อที่อธิบายวัตถุประสงค์และเป้าหมายของการเชื่อมต่อ

1. เลือกผู้ที่สามารถใช้การเชื่อมต่อนี้ หากคุณไม่ดำเนินการใด ๆ ค่าเริ่มต้นจะเป็นผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดู [อนุญาตให้ผู้สนับสนุนใช้การเชื่อมต่อสำหรับการส่งออก](connections.md#allow-contributors-to-use-a-connection-for-exports)

1. เลือกหรือค้นหาการสมัครใช้งานที่คุณต้องการใช้ข้อมูล Customer Insights ในนั้น ทันทีที่เลือกการสมัครใช้งาน คุณยังสามารถเลือก **พื้นที่ทำงาน**, **บัญชีที่เก็บข้อมูล** และ **คอนเทนเนอร์** ได้ด้วย

1. ให้เลือก **บันทึก** เพื่อบันทึกการเชื่อมต่อ

### <a name="configure-an-export"></a>กำหนดค่าการส่งออก

คุณสามารถกำหนดค่าการส่งออกนี้ได้หากคุณสามารถเข้าถึงการเชื่อมต่อชนิดนี้ได้ ในการกำหนดค่าการส่งออกด้วยการเชื่อมต่อที่แชร์ คุณต้องมีสิทธิ์ **ผู้สนับสนุน** ใน Customer Insights เป็นอย่างน้อย สำหรับข้อมูลเพิ่มเติม โปรดดู [สิทธิ์ที่จำเป็นในการกำหนดค่าการส่งออก](export-destinations.md#set-up-a-new-export)

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. หากต้องการสร้างการส่งออกใหม่ เลือก **เพิ่มการส่งออก**

1. ในฟิลด์ **การเชื่อมต่อที่จะส่งออก** ให้เลือกการเชื่อมต่อจากส่วน **Azure Synapse Analytics** หากคุณไม่เห็นชื่อส่วนนี้ ไม่มี [การเชื่อมต่อ](connections.md) ชนิดนี้ที่พร้อมใช้งานสำหรับคุณ

1. ระบุ **ชื่อที่แสดง** ที่เป็นที่รู้จักสำหรับการส่งออกของคุณ และ **ชื่อฐานข้อมูล**

1. เลือกเอนทิตีที่คุณต้องการส่งออกไปยัง Azure Synapse Analytics
   > [!NOTE]
   > ไม่รองรับแหล่งข้อมูลที่อิงตาม [โฟลเดอร์ Common Data Model](connect-common-data-model.md)

2. เลือก **บันทึก**

การบันทึกการส่งออกไม่ได้เรียกใช้การส่งออกในทันที

การส่งออกทำงานกับทุก ๆ [การรีเฟรชตามกำหนดการ](system.md#schedule-tab) นอกจากนี้คุณยังสามารถ [ส่งออกข้อมูลตามความต้องการ](export-destinations.md#run-exports-on-demand)

ในการสอบถามข้อมูลที่ส่งออกไปยัง Synapse Analytics คุณต้องมีสิทธิ์ **ผู้อ่านข้อมูลของ Blob ในพื้นที่จัดเก็บ** เพื่อเข้าถึงที่เก็บข้อมูลปลายทางในพื้นที่ทำงานของการส่งออก 

### <a name="update-an-export"></a>อัปเดตการส่งออก

1. ไปที่ **ข้อมูล** > **การส่งออก**

1. เลือก **แก้ไข** ในการส่งออกที่คุณต้องการอัปเดต

   - **เพิ่ม** หรือ **ลบ** เอนทิตีจากการเลือก หากเอนทิตีถูกลบออกจากการเลือก เอนทิตีจะไม่ถูกลบออกจากฐานข้อมูล Synapse Analytics อย่างไรก็ตาม การรีเฟรชข้อมูลในอนาคตจะไม่อัปเดตเอนทิตีที่ถูกลบออกในฐานข้อมูลนั้น

   - **การเปลี่ยนชื่อฐานข้อมูล** สร้างฐานข้อมูล Synapse Analytics ใหม่ ฐานข้อมูลที่มีชื่อที่กำหนดค่าไว้ก่อน จะไม่ได้รับการอัปเดตใดๆ ในการรีเฟรชในอนาคต
