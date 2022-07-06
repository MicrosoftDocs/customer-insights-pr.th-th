---
title: เชื่อมต่อกับแหล่งข้อมูล Azure Synapse (พรีวิว)
description: ใช้ฐานข้อมูลใน Azure Synapse เป็นแหล่งข้อมูลใน Dynamics 365 Customer Insights
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052722"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>เชื่อมต่อกับแหล่งข้อมูล Azure Synapse Analytics (พรีวิว)

Azure Synapse Analytics เป็นบริการวิเคราะห์ระดับองค์กรที่เร่งเวลาในการเข้าถึงข้อมูลเชิงลึกภายในคลังข้อมูลและระบบข้อมูลขนาดใหญ่ Azure Synapse Analytics นำเทคโนโลยี SQL ที่ดีที่สุดมาใช้ในการคลังข้อมูลองค์กร เทคโนโลยี Spark ที่ใช้สำหรับข้อมูลขนาดใหญ่ Data Explorer สำหรับการวิเคราะห์บันทึกและอนุกรมเวลา ไปป์ไลน์สำหรับการรวมข้อมูลและ ETL/ELT และการผสานรวมเชิงลึกกับบริการอื่นๆ ของ Azure เช่น Power BI, Cosmos DB และ AzureML

สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [ภาพรวมของ Azure Synapse](/azure/synapse-analytics/overview-what-is)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

> [!IMPORTANT]
> อย่าลืมตั้งค่า **การกำหนดบทบาท** ทั้งหมดตามที่อธิบายไว้  

**ใน Customer Insights**:

* คุณมีบทบาท **ผู้ดูแลระบบ** ใน Customer Insights เรียนรู้เพิ่มเติมเกี่ยวกับ [สิทธิ์ของผู้ใช้ใน Customer Insights](permissions.md#assign-roles-and-permissions)

**ใน Azure**:

- การสมัครใช้งาน Azure ที่ใช้งานอยู่

- หากใช้บัญชี Azure Data Lake Storage รุ่น2 ใหม่ *บริการหลักสำหรับ Customer Insights* จะต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลในที่เก็บข้อมูล Blob** เรียนรู้เพิ่มเติมเกี่ยวกับ [การเชื่อมต่อกับ Azure Data Lake Storage ด้วยบริการหลักสำหรับ Customer Insights](connect-service-principal.md) Data Lake Storage Gen2 **จำเป็นต้อง** เปิดใช้งาน [เนมสเปซตามลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)

- ในกลุ่มทรัพยากรที่มี Azure Synapse workspace อยู่ *บริการหลัก* และ *ผู้ใช้สำหรับ Customer Insights* ต้องได้รับการกำหนดสิทธิ์ **ผู้อ่าน** เป็นอย่างน้อย สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)

- *ผู้ใช้* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- *[ข้อมูลประจำตัวที่มีการจัดการของพื้นที่ทำงาน Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- บน Azure Synapse workspace *บริการหลักสำหรับ Customer Insights* จะต้องได้รับการกำหนดบทบาท **ผู้ดูแลระบบ Synapse** สำหรับข้อมูลเพิ่มเติม โปรดดู [วิธีตั้งค่าการควบคุมการเข้าถึงสำหรับพื้นที่ทำงาน Synapse ของคุณ](/azure/synapse-analytics/security/how-to-set-up-access-control)

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>เชื่อมต่อกับฐานข้อมูลที่จัดเก็บข้อมูลดิบใน Azure Synapse Analytics

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. เลือก **เพิ่มแหล่งข้อมูล**

1. เลือกวิธีการ **Azure Synapse Analytics (พรีวิว)**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="กล่องโต้ตอบเพื่อเชื่อมต่อกับข้อมูล Synapse Analytics":::
  
1. ป้อน **ชื่อ** สำหรับแหล่งข้อมูลและ **คำอธิบาย** ที่ระบุหรือไม่ก็ได้

1. เลือก [การเชื่อมต่อที่มีอยู่](connections.md) กับ Azure Synapse Analytics หรือสร้างการเชื่อมต่อใหม่

1. เลือก **ฐานข้อมูล** จากพื้นที่ทำงานที่เชื่อมต่อในการเชื่อมต่อ Azure Synapse Analytics ที่เลือก แล้วเลือก **ถัดไป** ขณะนี้เรารองรับเฉพาะชนิดฐานข้อมูล *ฐานข้อมูลที่จัดเก็บข้อมูลดิบ*

1. เลือกเอนทิตีที่จะนำเข้าจากฐานข้อมูลที่เชื่อมต่อ และเลือก **ถัดไป**

1. หรือเลือกเอนทิตีข้อมูลเพื่ออนุญาตการทำโปรไฟล์ข้อมูลก็ได้

1. เลือก **บันทึก** เพื่อใช้การเลือกของคุณและเริ่มต้นการนำเข้าข้อมูลจากแหล่งข้อมูลที่สร้างขึ้นใหม่ซึ่งเชื่อมโยงกับตารางฐานข้อมูล Lake ใน Azure Synapse Analytics หน้า **แหล่งข้อมูล** จะเปิดขึ้นเพื่อแสดงแหล่งข้อมูลใหม่ในสถานะ **กำลังรีเฟรช**
