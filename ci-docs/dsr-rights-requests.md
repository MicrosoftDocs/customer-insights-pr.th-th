---
title: คำขอสิทธิ์เรื่องข้อมูล (DSR) ภายใต้ GDPR | Microsoft Docs
description: ตอบสนองต่อคำขอของเจ้าของข้อมูลสำหรับความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350292"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>คำขอสิทธิ์เรื่องข้อมูล (DSR) ภายใต้ GDPR

ข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR) ของสหภาพยุโรป มีผลบังคับใช้ตั้งแต่วันที่ 25 พฤษภาคม 2018 ซึ่งให้สิทธิ์ที่สำคัญแก่บุคคลเกี่ยวกับข้อมูลของพวกเขา GDPR เกี่ยวกับการปกป้องและการเปิดใช้งานสิทธิ์ความเป็นส่วนตัวของแต่ละบุคคล คุณสามารถอ่านเพิ่มเติมเกี่ยวกับการยืนยันของ Microsoft ในการรักษาความปลอดภัยและการปฏิบัติตามข้อกำหนดได้ที่ [Microsoft Trust Center](https://www.microsoft.com/trust-center)

เรามุ่งมั่นที่จะช่วยให้ลูกค้าของเราปฏิบัติตามข้อกำหนดของ GDPR ซึ่งรวมถึงสิทธิ์ในการลบและส่งออกข้อมูลที่มีข้อมูลส่วนบุคคล เช่น รหัสผู้ใช้ หมายเลขโทรศัพท์ และที่อยู่อีเมล ผู้ดูแลระบบสามารถดำเนินการตามคำขอของผู้ใช้เพื่อลบหรือส่งออกข้อมูลส่วนบุคคล

## <a name="audience-insights"></a>ข้อมูลเชิงลึกของผู้ชม

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>การตอบสนองต่อคำขอลบของเจ้าของข้อมูล GDPR สำหรับความสามารถของข้อมูลเชิงลึกกลุ่มเป้าหมาย Dynamics 365 Customer Insights

“สิทธิในการลบ” โดยการลบของข้อมูลส่วนบุคคลออกจากข้อมูลลูกค้าขององค์กร เป็นการป้องกันที่สำคัญในข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR) การลบข้อมูลส่วนบุคคลรวมถึงการลบข้อมูลส่วนบุคคลทั้งหมดและบันทึกที่ระบบที่สร้างขึ้น ยกเว้นข้อมูลบันทึกการตรวจสอบ

#### <a name="manage-data-subject-delete-requests"></a>จัดการคำขอลบสิทธิ์เรื่องข้อมูล

ข้อมูลเชิงลึกกลุ่มเป้าหมายนำเสนอประสบการณ์ในผลิตภัณฑ์ต่อไปนี้เพื่อลบข้อมูลส่วนบุคคลสำหรับลูกค้าหรือผู้ใช้เฉพาะ:

- **จัดการคำขอลบสำหรับข้อมูลลูกค้า**: ข้อมูลลูกค้าใน Customer Insights ถูกนำมาใช้จากแหล่งข้อมูลดั้งเดิมภายนอกไปยัง Customer Insights คำขอลบ GDPR ทั้งหมดจะต้องดำเนินการในแหล่งข้อมูลดั้งเดิม
- **จัดการคำขอลบข้อมูลผู้ใช้ Customer Insights**: ข้อมูลสำหรับผู้ใช้สร้างขึ้นโดย Customer Insights คำขอลบ GDPR ทั้งหมดจะต้องดำเนินการใน Customer Insights

##### <a name="manage-requests-to-delete-customer-data"></a>จัดการคำขอลบข้อมูลลูกค้า

ผู้ดูแลระบบ Customer Insights สามารถทำตามขั้นตอนเหล่านี้เพื่อลบข้อมูลลูกค้าที่ถูกลบในแหล่งข้อมูล:

1. เข้าสู่ระบบ Dynamics 365 Customer Insights
2. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ข้อมูล** > **แหล่งข้อมูล**
3. สำหรับแหล่งข้อมูลแต่ละรายการในรายการที่มีข้อมูลลูกค้าที่ถูกลบ:
   1. เลือก (...) และจากนั้นเลือก **รีเฟรช**
   2. ตรวจสอบสถานะของแหล่งข้อมูลภายใต้ **สถานะ** เครื่องหมายถูกหมายถึง การรีเฟรชสำเร็จ สามเหลี่ยมคำเตือนหมายถึง มีบางสิ่งผิดปกติ หากสามเหลี่ยมคำเตือนปรากฏขึ้น ให้ติดต่อ D365CI@microsoft.com

> [!div class="mx-imgBorder"]
> ![การจัดการคำขอลบ GDPR สำหรับข้อมูลลูกค้า](audience-insights/media/gdpr-data-sources.png "การจัดการคำขอลบ GDPR สำหรับข้อมูลลูกค้า")

##### <a name="manage-delete-requests-for-user-data"></a>จัดการคำขอลบสำหรับข้อมูลผู้ใช้

ผู้ดูแลระบบ Customer Insights สามารถทำตามขั้นตอนเหล่านี้เพื่อลบข้อมูลผู้ใช้ Customer Insights:

1. เข้าสู่ระบบ Dynamics 365 Customer Insights
2. ในข้อมูลเชิงลึกกลุ่มเป้าหมาย ให้ไปที่ **ผู้ดูแลระบบ** > **สิทธิ์**
3. เลือกกล่องกาเครื่องหมายสำหรับผู้ใช้ที่คุณต้องการลบ
4. เลือก **เอาออก**

### <a name="responding-to-gdpr-data-subject-export-requests"></a>การตอบสนองต่อคำขอส่งออกของเจ้าของข้อมูล GDPR

ในฐานะที่เป็นส่วนหนึ่งของข้อผูกพันของเราที่จะร่วมมือกับคุณในการเดินทางไปยังข้อบังคับทั่วไปเกี่ยวกับการคุ้มครองข้อมูล (GDPR) เราได้พัฒนาเอกสารเพื่อช่วยคุณเตรียมความพร้อม เอกสารนี้อธิบายขั้นตอนที่คุณสามารถทำได้ในปัจจุบันเพื่อสนับสนุนการปฏิบัติตาม GDPR เมื่อใช้ข้อมูลเชิงลึกกลุ่มเป้าหมาย

#### <a name="manage-export-and-view-requests"></a>จัดการการส่งออกและดูคำขอ

สิทธิ์ของความสามารถในการเคลื่อนย้ายข้อมูลอนุญาตให้หัวข้อของข้อมูลร้องขอสำเนาข้อมูลส่วนบุคคลของพวกเขาในรูปแบบอิเล็กทรอนิกส์ ("รูปแบบที่มีโครงสร้าง มีการใช้โดยทั่วไป สามารถอ่านได้ด้วยเครื่อง และสามารถทำงานร่วมกันได้") ซึ่งอาจถูกส่งไปยังตัวควบคุมข้อมูลอื่น

##### <a name="export-customer-data-tenant-admin"></a>ส่งออกข้อมูลลูกค้า (ผู้ดูแลระบบผู้เช่า)

ผู้ดูแลระบบผู้เช่าสามารถทำตามขั้นตอนเหล่านี้เพื่อส่งออกข้อมูล:

1. ส่งอีเมลไปที่ D365CI@microsoft.com ซึ่งระบุที่อยู่อีเมลของลูกค้าในคำขอ ทีม Customer Insights จะส่งอีเมลไปยังที่อยู่อีเมลผู้ดูแลระบบของผู้เช่าที่ลงทะเบียน โดยขอให้ยืนยันการส่งออกข้อมูล
2. รับทราบการยืนยันในการส่งออกข้อมูลสำหรับลูกค้าที่ร้องขอ
3. รับข้อมูลที่ส่งออกผ่านที่อยู่อีเมลผู้ดูแลระบบของผู้เช่า

##### <a name="export-user-data-tenant-admin"></a>ส่งออกข้อมูลผู้ใช้ (ผู้ดูแลระบบผู้เช่า)

1. ส่งอีเมลไปที่ D365CI@microsoft.com ซึ่งระบุที่อยู่อีเมลของผู้ใช้ในคำขอ ทีม Customer Insights จะส่งอีเมลไปยังที่อยู่อีเมลผู้ดูแลระบบของผู้เช่าที่ลงทะเบียน โดยขอให้ยืนยันการส่งออกข้อมูล
2. รับทราบการยืนยันในการส่งออกข้อมูลสำหรับผู้ใช้ที่ร้องขอ
3. รับข้อมูลที่ส่งออกผ่านที่อยู่อีเมลผู้ดูแลระบบของผู้เช่า

## <a name="consent-management-preview"></a>การจัดการความยินยอม (พรีวิว)

ความสามารถในการจัดการความยินยอมไม่ได้รวบรวมข้อมูลผู้ใช้โดยตรง แต่เป็นเพียงการนำเข้าและประมวลผลข้อมูลความยินยอมที่ผู้ใช้ให้ไว้ในแอปพลิเคชันอื่นเท่านั้น

หากต้องการเอาข้อมูลความยินยอมเกี่ยวกับผู้ใช้บางรายออก ให้เอาข้อมูลดังกล่าวในแหล่งข้อมูลที่นำเข้าไปยังความสามารถในการจัดการคำยินยอมออก หลังจากรีเฟรชแหล่งข้อมูล แล้ว ข้อมูลที่เอาออกจะถูกลบออกจากศูนย์ความยินยอมด้วย แอปพลิเคชันที่ใช้เอนทิตีความยินยอมจะลบข้อมูลที่ถูกลบออกจากแหล่งที่มาหลังจาก [รีเฟรช](audience-insights/system.md#refresh-processes) เราแนะนำให้รีเฟรชแหล่งข้อมูลทันทีหลังจากตอบสนองต่อคำขอของเจ้าของข้อมูลเพื่อลบข้อมูลของผู้ใช้ออกจากกระบวนการและแอปพลิเคชันอื่นๆ ทั้งหมด


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]