---
title: เชื่อมต่อกับแหล่งข้อมูล Azure Synapse (พรีวิว)
description: ใช้ฐานข้อมูลใน Azure Synapse เป็นแหล่งข้อมูลใน Dynamics 365 Customer Insights
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259821"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>เชื่อมต่อกับแหล่งข้อมูล Azure Synapse Analytics (พรีวิว)

Azure Synapse Analytics เป็นบริการวิเคราะห์ระดับองค์กรที่เร่งเวลาในการเข้าถึงข้อมูลเชิงลึกภายในคลังข้อมูลและระบบข้อมูลขนาดใหญ่ Azure Synapse Analytics นำเทคโนโลยี SQL ที่ดีที่สุดมาใช้ในการคลังข้อมูลองค์กร เทคโนโลยี Spark ที่ใช้สำหรับข้อมูลขนาดใหญ่ Data Explorer สำหรับการวิเคราะห์บันทึกและอนุกรมเวลา ไปป์ไลน์สำหรับการรวมข้อมูลและ ETL/ELT และการผสานรวมเชิงลึกกับบริการอื่นๆ ของ Azure เช่น Power BI, Cosmos DB และ AzureML

สำหรับข้อมูลเพิ่มเติม ให้ดูที่ [ภาพรวมของ Azure Synapse](/azure/synapse-analytics/overview-what-is)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

> [!NOTE]
> Synapse Workspace ที่มี [การเปิดใช้งานไฟร์วอลล์](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) ยังไม่รองรับในขณะนี้
> [!IMPORTANT]
> อย่าลืมตั้งค่า **การกำหนดบทบาท** ทั้งหมดตามที่อธิบายไว้  

**ใน Customer Insights**:

* คุณมีบทบาท **ผู้ดูแลระบบ** ใน Customer Insights เรียนรู้เพิ่มเติมเกี่ยวกับ [สิทธิ์ของผู้ใช้ใน Customer Insights](permissions.md#add-users)

**ใน Azure**:

- การสมัครใช้งาน Azure ที่ใช้งานอยู่

- หากใช้บัญชี Azure Data Lake Storage รุ่น2 ใหม่ *บริการหลักสำหรับ Customer Insights* ซึ่งเป็น "Dynamics 365 AI for Customer Insights" ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลในที่เก็บข้อมูล Blob** เรียนรู้เพิ่มเติมเกี่ยวกับ [การเชื่อมต่อกับ Azure Data Lake Storage ด้วยบริการหลักสำหรับ Customer Insights](connect-service-principal.md) Data Lake Storage Gen2 **จำเป็นต้อง** เปิดใช้งาน [เนมสเปซตามลำดับชั้น](/azure/storage/blobs/data-lake-storage-namespace)

- ในกลุ่มทรัพยากรที่มี Azure Synapse workspace อยู่ *บริการหลัก* ที่เป็น "Dynamics 365 AI for Customer Insights" และ *ผู้ใช้ Customer Insights* ต้องได้รับการกำหนดสิทธิ์ของ **ผู้อ่าน** เป็นอย่างน้อย สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)

- *ผู้ใช้* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- *[ข้อมูลประจำตัวที่มีการจัดการของพื้นที่ทำงาน Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ต้องการสิทธิ์ **ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ** ในบัญชี Azure Data Lake Storage Gen2 ที่ซึ่งมีข้อมูลอยู่และเชื่อมโยงกับพื้นที่ทำงาน Azure Synapse เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้พอร์ทัล Azure เพื่อมอบหมายบทบาท Azure สำหรับการเข้าถึงข้อมูล blob และคิว](/azure/storage/common/storage-auth-aad-rbac-portal) และ [สิทธิ์ผู้สนับสนุนข้อมูลของ Blob ในพื้นที่จัดเก็บ](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)

- บน Azure Synapse workspace *บริการหลักสำหรับ Customer Insights* ซึ่งเป็น "Dynamics 365 AI for Customer Insights" ต้องได้รับการกำหนดบทบาท **ผู้ดูแลระบบ Synapse** สำหรับข้อมูลเพิ่มเติม โปรดดู [วิธีตั้งค่าการควบคุมการเข้าถึงสำหรับพื้นที่ทำงาน Synapse ของคุณ](/azure/synapse-analytics/security/how-to-set-up-access-control)

- หากสภาพแวดล้อม Customer Insights ของคุณเก็บข้อมูลใน [Azure Data Lake Storage ของตนเอง](own-data-lake-storage.md) ผู้ใช้ที่ตั้งค่าการเชื่อมต่อกับ Azure Synapse Analytics ต้องมีบทบาท **ผู้อ่าน** ในตัวเป็นอย่างน้อยในบัญชี Data Lake Storage สำหรับข้อมูลเพิ่มเติม โปรดดู [มอบหมายบทบาท Azure โดยใช้พอร์ทัล Azure](/azure/role-based-access-control/role-assignments-portal)

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>เชื่อมต่อกับฐานข้อมูลที่จัดเก็บข้อมูลดิบใน Azure Synapse Analytics

1. ไปที่ **ข้อมูล** > **แหล่งข้อมูล**

1. เลือก **เพิ่มแหล่งข้อมูล**

1. เลือกวิธีการ **Azure Synapse Analytics (พรีวิว)**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="กล่องโต้ตอบเพื่อเชื่อมต่อกับข้อมูล Synapse Analytics":::
  
1. ป้อน **ชื่อ** สำหรับแหล่งข้อมูลและ **คำอธิบาย** ที่ระบุหรือไม่ก็ได้

1. เลือก [การเชื่อมต่อที่มีอยู่](connections.md) กับ Azure Synapse Analytics หรือ [สร้างการเชื่อมต่อใหม่](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse)

1. เลือก **ฐานข้อมูล** จากพื้นที่ทำงานที่เชื่อมต่อในการเชื่อมต่อ Azure Synapse Analytics ที่เลือก แล้วเลือก **ถัดไป** ขณะนี้เรารองรับเฉพาะชนิดฐานข้อมูล *ฐานข้อมูลที่จัดเก็บข้อมูลดิบ*

1. เลือกเอนทิตีที่จะนำเข้าจากฐานข้อมูลที่เชื่อมต่อ และเลือก **ถัดไป**

1. หรือเลือกเอนทิตีข้อมูลเพื่ออนุญาตการทำโปรไฟล์ข้อมูลก็ได้

1. เลือก **บันทึก** เพื่อใช้การเลือกของคุณและเริ่มต้นการนำเข้าข้อมูลจากแหล่งข้อมูลที่สร้างขึ้นใหม่ซึ่งเชื่อมโยงกับตารางฐานข้อมูล Lake ใน Azure Synapse Analytics หน้า **แหล่งข้อมูล** จะเปิดขึ้นเพื่อแสดงแหล่งข้อมูลใหม่ในสถานะ **กำลังรีเฟรช**

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

การโหลดข้อมูลอาจต้องใช้เวลา หลังจากการรีเฟรชที่สำเร็จ จะสามารถตรวจสอบข้อมูลที่ถูกนำไปใช้ได้จากหน้า [**เอนทิตี**](entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
