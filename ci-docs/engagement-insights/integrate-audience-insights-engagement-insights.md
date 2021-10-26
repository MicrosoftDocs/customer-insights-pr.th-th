---
title: สร้างลิงก์ระหว่างข้อมูลเชิงลึกของผู้ชมและข้อมูลเชิงลึกของการมีส่วนร่วม
description: สร้างลิงก์ที่ใช้งานอยู่ระหว่างข้อมูลเชิงลึกของผู้ชมและข้อมูลเชิงลึกของการมีส่วนร่วม เพื่อเปิดใช้การแชร์ข้อมูลแบบสองทิศทาง
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: db38778c0da862e119f9b374e07c82ead0d3a4f2
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645605"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>สร้างลิงก์ระหว่างข้อมูลเชิงลึกของผู้ชมและข้อมูลเชิงลึกของการมีส่วนร่วม

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

การรวมระหว่างข้อมูลเชิงลึกของการมีส่วนร่วมและข้อมูลเชิงลึกของผู้ชม จะเชื่อมโยงสภาพแวดล้อมจากความสามารถทั้งสองรายการ และทำให้ข้อมูลสามารถแบ่งปันแบบสองทิศทางระหว่างกันได้

ใช้โปรไฟล์และเซ็กเมนต์แบบรวมจากข้อมูลเชิงลึกของผู้ชมสำหรับตัวเลือกการวิเคราะห์เพิ่มเติมในข้อมูลเชิงลึกของการมีส่วนร่วม ส่งออกเหตุการณ์ที่มีมูลค่าทางธุรกิจสูงจากข้อมูลเชิงลึกของการมีส่วนร่วม ใช้เหตุการณ์เหล่านี้เพื่อเพิ่มข้อมูลไปยังโปรไฟล์แบบรวมในข้อมูลเชิงลึกของผู้ชม

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- โปรไฟล์ข้อมูลเชิงลึกของผู้ชมต้องถูกเก็บไว้ในบัญชี Azure Data Lake Storage ที่คุณเป็นเจ้าของ หรือในที่จัดเก็บข้อมูลดิบที่มีการจัดการของ [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash; 
- สภาพแวดล้อมข้อมูลเชิงลึกของผู้ชมของคุณควรมีสภาพแวดล้อม Dataverse ที่สัมพันธ์กัน และถ้าสภาพแวดล้อมนั้นยังใช้ Dataverse สำหรับการจัดเก็บข้อมูล ตรวจสอบให้แน่ใจว่าคุณได้เลือกตัวเลือก **เปิดใช้งานการแชร์ข้อมูล** ในข้อมูลเชิงลึกของผู้ชม สำหรับข้อมูลเพิ่มเติม โปรดดู [สร้างและกำหนดค่าสภาพแวดล้อมในข้อมูลเชิงลึกของผู้ชม](../audience-insights/create-environment.md)
- คุณต้องมีสิทธิ์ของผู้ดูแลระบบสำหรับทั้งข้อมูลเชิงลึกของการมีส่วนร่วมและสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชม
- สภาพแวดล้อมที่เชื่อมโยงต้องอยู่ในภูมิภาคทางภูมิศาสตร์เดียวกัน

> [!NOTE]
> - หากการสมัครใช้งานข้อมูลข้อมูลเชิงลึกของผู้ชมของคุณเป็นแบบทดลองใช้ ซึ่งใช้ที่จัดเก็บข้อมูลดิบที่มีการจัดการภายในของข้อมูลเชิงลึกของผู้ชม โปรดติดต่อ [pirequest@microsoft.com](mailto:pirequest@microsoft.com) สำหรับความช่วยเหลือ 
> - หากสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชมของคุณใช้ Azure Data Lake Storage ของคุณเองในการจัดเก็บข้อมูล คุณต้องเพิ่มหลักบริการ Azure ของข้อมูลเชิงลึกของการมีส่วนร่วมไปยังบัญชีที่เก็บข้อมูลของคุณ สำหรับรายละเอียด ไปที่ [เชื่อมต่อกับบัญชี Azure Data Lake Storage ที่มีบริการหลัก Azure สำหรับข้อมูลเชิงลึกของผู้ชม](../audience-insights/connect-service-principal.md) 


## <a name="create-an-environment-link"></a>สร้างลิงก์สภาพแวดล้อม

คุณสามารถสร้างลิงก์สภาพแวดล้อมได้โดยการอัพเดตการตั้งค่า **ผู้ดูแลระบบ** > **สภาพแวดล้อม** ในข้อมูลเชิงลึกของการมีส่วนร่วม

**เพื่อสร้างลิงก์ที่ใช้งานอยู่ระหว่างข้อมูลเชิงลึกของผู้ชมและข้อมูลเชิงลึกของการมีส่วนร่วม**

1. บนหน้า **ผู้ดูแลระบบสิ่งแวดล้อม** เลือกแท็บ **ลิงก์สภาพแวดล้อม**

    :::image type="content" source="media/integrate1.png" alt-text="ตั้งค่าสภาพแวดล้อม":::

1. เลือก **ตั้งค่าสภาพแวดล้อม** ที่มุมซ้ายบน หรือที่ด้านล่างของหน้าจอ

     :::image type="content" source="media/integrate2.png" alt-text="เลือกสภาพแวดล้อมข้อมูลเชิงลึกของผู้ชม":::

1. เลือกสภาพแวดล้อมข้อมูลเชิงลึกฃองผู้ชม แล้วจากนั้น เลือก ***ถัดไป** เพื่อให้เสร็จสิ้น ขณะนี้ คุณสามารถเลือกคุณลักษณะที่เป็นตัวเลือกสำหรับสภาพแวดล้อมที่เชื่อมโยงได้
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>เปิดใช้งานแอตทริบิวต์และเซ็กเมนต์โปรไฟล์แบบรวมของข้อมูลเชิงลึกของผู้ชม

หลังจากการเชื่อมโยงสภาพแวดล้อม คุณสามารถเลือกคุณลักษณะที่เป็นตัวเลือกสำหรับสภาพแวดล้อมที่เชื่อมโยงได้ คุณลักษณะเหล่านี้เปิดใช้งานแอตทริบิวต์และเซ็กเมนต์โปรไฟล์แบบรวมจากข้อมูลเชิงลึกของผู้ชม สำหรับการวิเคราะห์เชิงโต้ตอบเกี่ยวกับข้อมูลลูกค้า

> [!IMPORTANT]
> สำหรับเซ็กเมนต์ข้อมูลเชิงลึกของผู้ชมที่จะแสดงในข้อมูลเชิงลึกของการมีส่วนร่วม ก่อนอื่นคุณต้อง [เรียกใช้กระบวนการรวมเข้าด้วยกันและดาวน์สตรีม](../audience-insights/merge-entities.md) กระบวนการดาวน์สตรีมมีความสำคัญ เนื่องจากจะสร้างตารางเฉพาะที่จัดเตรียมเซ็กเมนต์ข้อมูลเชิงลึกของผู้ชมที่จะมีการแชร์กับข้อมูลเชิงลึกของการมีส่วนร่วม (หากมีการจัดกำหนดการรีเฟรชระบบ ระบบจะรวมกระบวนการดาวน์สตรีมโดยอัตโนมัติ)

**เพื่อวิเคราะห์ข้อมูลเว็บในข้อมูลเชิงลึกของการมีส่วนร่วม**

1. บนหน้า **ผู้ดูแลระบบสิ่งแวดล้อม** ให้เปิดตัวสลับ **แชร์ข้อมูลจากข้อมูลเชิงลึกของผู้ชมกับข้อมูลเชิงลึกของการมีส่วนร่วม** แล้วจากนั้น เลือก **ถัดไป**

    :::image type="content" source="media/integrate4.png" alt-text="เลือกคุณลักษณะ":::

1. เลือกแอตทริบิวต์ของโปรไฟล์แบบรวมซึ่งจะกลายเป็นมิติในข้อมูลเชิงลึกของการมีส่วนร่วม (แอตทริบิวต์บางรายการไม่ใช่มิติข้อมูลที่เป็นประโยชน์ ตัวอย่างเช่น ไม่จำเป็นว่าคุณจะต้องการ **ชื่อ** หรือ **นามสกุล** เป็นแอตทริบิวต์สำหรับการวิเคราะห์ของเหตุการณ์ในเว็บไซต์ของคุณ)

    :::image type="content" source="media/integrate5.png" alt-text="เรียบเรียงมิติ":::

   >[!NOTE]
   > แอตทริบิวต์โปรไฟล์ข้อมูลเชิงลึกของผู้ชมทั้งหมดที่แสดงถึงตัวระบุ (เช่น **รหัส** และ **รหัสสำรอง**) ถูกกรองออกจากแอตทริบิวต์ที่มีอยู่และกลายเป็นมิติในข้อมูลเชิงลึกของการมีส่วนร่วม

1. เมื่อคุณเลือกแอตทริบิวต์เสร็จแล้ว ให้เลือก **ถัดไป**
1. เพิ่มผู้ใช้ที่สามารถดูมิติและเซ็กเมนต์ของโปรไฟล์ข้อมูลเชิงลึกของผู้ชมในข้อมูลเชิงลึกของการมีส่วนร่วมได้

    :::image type="content" source="media/integrate6.png" alt-text="จัดการการเข้าถึงข้อมูลลูกค้า":::

   > [!IMPORTANT]
   > หากคุณไม่ได้เพิ่มผู้ใช้อย่างชัดแจ้งในขั้นตอนนี้ ข้อมูลจะถูกซ่อนจากผู้ใช้ในข้อมูลเชิงลึกของการมีส่วนร่วม
   > สำหรับเซ็กเมนต์ข้อมูลเชิงลึกของผู้ชมที่จะแสดงในข้อมูลเชิงลึกของการมีส่วนร่วม ก่อนอื่นคุณต้อง [เรียกใช้กระบวนการรวมเข้าด้วยกันและดาวน์สตรีม](../audience-insights/merge-entities.md) กระบวนการดาวน์สตรีมมีความสำคัญ เนื่องจากจะสร้างตารางเฉพาะที่จัดเตรียมเซ็กเมนต์ข้อมูลเชิงลึกของผู้ชมที่จะมีการแชร์กับข้อมูลเชิงลึกของการมีส่วนร่วม (หากมีการจัดกำหนดการรีเฟรชระบบ ระบบจะรวมกระบวนการดาวน์สตรีมโดยอัตโนมัติ)

1. รีวิวการเลือกของคุณ แล้วจากนั้น เลือก **เสร็จสิ้น**

    :::image type="content" source="media/integrate7.png" alt-text="รีวิวการตั้งค่าข้อมูลลูกค้า":::

## <a name="export-refined-events-to-audience-insights"></a>ส่งออกเหตุการณ์ที่ปรับปรุงไปยังข้อมูลเชิงลึกของผู้ชม

หลังจากที่คุณสร้างลิงก์ระหว่างสภาพแวดล้อม คุณสามารถส่งออกเหตุการณ์ที่ปรับปรุงแล้วจากข้อมูลเชิงลึกของการมีส่วนร่วมไปยังข้อมูลเชิงลึกของผู้ชม และนำเข้าเป็นแหล่งข้อมูลใหม่ 

สำหรับข้อมูลเพิ่มเติม ไปที่ [รวมข้อมูลเว็บจากข้อมูลเชิงลึกของการมีส่วนร่วมกับข้อมูลเชิงลึกของผู้ชม](../audience-insights/integrate-engagement-insights.md)

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
