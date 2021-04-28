---
title: การเพิ่มความสมบูรณ์ด้วยการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896074"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>การเพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)

HERE Technologies เป็นบริษัทแพลตฟอร์มด้านสถานที่ตั้งที่ให้บริการข้อมูลและสถานที่ตั้งเป็นหลัก ด้วยบริการเพิ่มข้อมูลจาก HERE Technologies คุณสามารถสร้างความเข้าใจตำแหน่งที่ตั้งที่แม่นยำยิ่งขึ้นสำหรับลูกค้าของคุณด้วยการทำให้ที่อยู่เป็นมาตรฐาน การแยกละติจูดและลองจิจูด และอื่นๆ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

การกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies จะต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณต้องมีการสมัครใช้งาน HERE Technologies ที่ใช้งานอยู่ หากต้องการสมัครใช้งาน คุณสามารถ [ลงทะเบียนที่นี่](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) หรือ [ติดต่อ HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) โดยตรง [เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูลตำแหน่งที่ตั้งของ HERE Technologies](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- มี [การเชื่อมต่อ](connections.md) HERE ใช้ได้ *หรือ* คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator) และคีย์ API ของ HERE Technologies

## <a name="configure-the-enrichment"></a>กำหนดค่าการเพิ่มข้อมูล

1. ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล** 

1. เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ HERE Technologies แล้วเลือก **เริ่มต้นใช้งาน**

   > [!div class="mx-imgBorder"]
   > ![ไทล์ HERE Technologies](media/HERE-tile.png "ไทล์ HERE Technologies")

1. เลือก [การเชื่อมต่อ](connections.md) จากรายการแบบหล่นลง ติดต่อผู้ดูแลระบบหากไม่มีการเชื่อมต่อ หากคุณเป็นผู้ดูแลระบบ คุณสามารถสร้างการเชื่อมต่อโดยเลือก **เพิ่มการเชื่อมต่อ** เลือก **HERE Technologies** จากเมนูแบบหล่นลง 

1. เลือก **เชื่อมต่อกับ HERE Technologies** เพื่อยืนยันการเลือก

1.  เลือก **ต่อไป** และเลือก **ชุดข้อมูลลูกค้า** ที่คุณต้องการเพิ่มข้อมูลด้วยข้อมูลตำแหน่งที่ตั้งจาก HERE Technologies คุณสามารถเลือกเอนทิตี **ลูกค้า** เพื่อเพิ่มโปรไฟล์ลูกค้าของคุณทั้งหมด หรือเลือกเอนทิตีเซ็กเมนต์เพื่อเพิ่มเฉพาะโปรไฟล์ลูกค้าที่มีอยู่ในเซ็กเมนต์นั้น

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ภาพหน้าจอเมื่อเลือกชุดข้อมูลของลูกค้า":::

1. เลือกว่าคุณต้องการแม็ปฟิลด์กับที่อยู่หลักและ/หรือที่อยู่รอง คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งสองและเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งสองแยกกัน ตัวอย่างเช่น หากมีที่อยู่บ้านและที่อยู่ของธุรกิจ เลือก **ถัดไป**

1. กำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลตำแหน่งที่ตั้งที่ตรงกันจาก HERE Technologies ต้องระบุฟิลด์ **ถนน 1** และ **รหัสไปรษณีย์** สำหรับที่อยู่หลักและ/หรือรองที่เลือก เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถเพิ่มฟิลด์มากขึ้นได้

   > [!div class="mx-imgBorder"]
   > ![เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies](media/enrichment-HERE-configuration.png "เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies")

1. ให้เลือก **ถัดไป** เพื่อทำการแม็ปฟิลด์ให้เสร็จ

1. ระบุชื่อสำหรับการเพิ่มข้อมูล 

1. เลือก **บันทึกการเพิ่มข้อมูล** หลังจากตรวจสอบตัวเลือกของคุณแล้ว

## <a name="configure-the-connection-for-here-technologies"></a>กำหนดค่าการเชื่อมต่อสำหรับ HERE technologies 

คุณต้องเป็นผู้ดูแลระบบเพื่อกำหนดค่าการเชื่อมต่อ เลือก **เพิ่มการเชื่อมต่อ** เมื่อกำหนดค่าการเพิ่มข้อมูล *หรือ* ไปที่ **การจัดการ** > **การเชื่อมต่อ** และเลือก **ตั้งค่า** บนไทล์ HERE Technologies

1. ป้อนชื่อสำหรับการเชื่อมต่อในกล่อง **ชื่อที่แสดง**

1. ระบุคีย์ API ของ HERE Technologies ที่ถูกต้อง

1. รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย**

1. เลือก **ยืนยัน** เพื่อตรวจสอบการกำหนดค่า

1. หลังจากเสร็จสิ้นการตรวจสอบแล้ว ให้เลือก **บันทึก**

> [!div class="mx-imgBorder"]
   > ![หน้าการกำหนดค่าการเชื่อมต่อสำหรับ HERE technologies](media/enrichment-HERE-connection.png "หน้าการกำหนดค่าการเชื่อมต่อสำหรับ HERE technologies")

## <a name="enrichment-results"></a>ผลการเพิ่มข้อมูล

ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab) เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและเวลาตอบสนองของ API จาก HERE Technologies

หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน** นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม

คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**

## <a name="next-steps"></a>ขั้นตอนถัดไป

สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง HERE Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า HERE Technologies ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ


[!INCLUDE[footer-include](../includes/footer-banner.md)]
