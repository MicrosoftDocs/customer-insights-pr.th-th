---
title: การเพิ่มความสมบูรณ์ด้วยการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
description: ข้อมูลทั่วไปเกี่ยวกับการเพิ่มข้อมูลจากบุคคลที่สาม HERE Technologies
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668701"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>การเพิ่มข้อมูลโปรไฟล์ลูกค้าด้วย HERE Technologies (พรีวิว)

HERE Technologies เป็นบริษัทแพลตฟอร์มด้านสถานที่ตั้งที่ให้บริการข้อมูลและสถานที่ตั้งเป็นหลัก ด้วยบริการเพิ่มข้อมูลจาก HERE Technologies คุณสามารถสร้างความเข้าใจตำแหน่งที่ตั้งที่แม่นยำยิ่งขึ้นสำหรับลูกค้าของคุณด้วยการทำให้ที่อยู่เป็นมาตรฐาน การแยกละติจูดและลองจิจูด และอื่นๆ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

การกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies จะต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

- คุณต้องมีการสมัครใช้งาน HERE Technologies ที่ใช้งานอยู่ หากต้องการสมัครใช้งาน คุณสามารถ [ลงทะเบียนที่นี่](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) หรือ [ติดต่อ HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) โดยตรง [เรียนรู้เพิ่มเติมเกี่ยวกับการเพิ่มข้อมูลตำแหน่งที่ตั้งของ HERE Technologies](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- คุณมีคีย์ API ของ HERE Technologies

- คุณมีสิทธิ์ [ผู้ดูแลระบบ](permissions.md#administrator)

## <a name="configuration"></a>การกำหนดค่า

1. ไปที่ **ข้อมูล** > **การเพิ่มข้อมูล**

1. เลือก **เพิ่มข้อมูลของฉัน** บนไทล์ HERE Technologies

   > [!div class="mx-imgBorder"]
   > ![ไทล์ HERE Technologies](media/HERE-tile.png "ไทล์ HERE Technologies")

1. ป้อน **คีย์ API ของ HERE Technologies** รีวิวและให้ความยินยอมของคุณสำหรับ **ความเป็นส่วนตัวและความสอดคล้องของข้อมูล** โดยการเลือกกล่องกาเครื่องหมาย **ฉันเห็นด้วย** 

1. ยืนยันการป้อนข้อมูลทั้งคู่โดยการเลือก **เชื่อมต่อกับ HERE**

1. เลือก **เพิ่มข้อมูล** และเลือกว่าคุณต้องการแมปฟิลด์กับที่อยู่หลักและ/หรือรอง คุณสามารถระบุการแมปฟิลด์สำหรับที่อยู่ทั้งคู่ (เช่น ที่อยู่ที่บ้านและที่อยู่ของธุรกิจ) และเพิ่มข้อมูลโปรไฟล์สำหรับที่อยู่ทั้งคู่แยกกัน เลือก **ถัดไป**

1. กำหนดว่าฟิลด์ใดจากโปรไฟล์แบบรวมของคุณที่ควรใช้เพื่อค้นหาข้อมูลตำแหน่งที่ตั้งที่ตรงกันจาก HERE Technologies ต้องระบุฟิลด์ **ถนน 1** และ **รหัสไปรษณีย์** สำหรับที่อยู่หลักและ/หรือรองที่เลือก เพื่อความแม่นยำในการจับคู่ที่สูงขึ้น คุณสามารถเพิ่มฟิลด์มากขึ้นได้

   > [!div class="mx-imgBorder"]
   > ![เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies](media/enrichment-HERE-configuration.png "เพจการกำหนดค่าการเพิ่มข้อมูลจาก HERE Technologies")

1. เลือก **นำไปใช้** เพื่อทำการแมปฟิลด์ให้เสร็จสมบูรณ์

## <a name="enrichment-results"></a>ผลการเพิ่มข้อมูล

ในการเริ่มการเพิ่มข้อมูล ให้เลือก **ทำงาน** จากแถบคำสั่ง คุณยังสามารถปล่อยให้ระบบรันการเพิ่มข้อมูลโดยอัตโนมัติโดยเป็นส่วนหนึ่งของ [การรีเฟรชตามกำหนด](system.md#schedule-tab) เวลาในการประมวลผลจะขึ้นอยู่กับขนาดของข้อมูลลูกค้าของคุณและเวลาตอบสนองของ API จาก HERE Technologies

หลังจากขั้นตอนการเพิ่มข้อมูลเสร็จสมบูรณ์ คุณสามารถตรวจสอบข้อมูลโปรไฟล์ลูกค้าเพิ่มข้อมูลใหม่ได้ภายใต้ **การเพิ่มข้อมูลของฉัน** นอกจากนี้ คุณจะพบเวลาของการอัปเดตครั้งล่าสุด และจำนวนโปรไฟล์ที่มีการเพิ่ม

คุณสามารถเข้าถึงมุมมองแบบละเอียดของแต่ละโปรไฟล์ที่มีการเพิ่มข้อมูล โดยเลือก **ดูข้อมูลที่มีการเพิ่ม**

## <a name="next-steps"></a>ขั้นตอนถัดไป

สร้างบนข้อมูลลูกค้าที่เพิ่มด้านบนของคุณ สร้าง [เซ็กเมนต์](segments.md) [การวัด](measures.md) และแม้กระทั่ง [ส่งออกข้อมูล](export-destinations.md) เพื่อมอบประสบการณ์ที่เป็นส่วนตัวให้กับลูกค้าของคุณ

## <a name="data-privacy-and-compliance"></a>ความเป็นส่วนตัวของข้อมูลและการปฏิบัติตามกฎระเบียบ

เมื่อคุณเปิดใช้งาน Dynamics 365 Customer Insights ในการส่งข้อมูลไปยัง HERE Technologies คุณอนุญาตให้ถ่ายโอนข้อมูลนอกขอบเขตการปฏิบัติตามข้อกำหนดสำหรับ Dynamics 365 Customer Insights รวมถึงข้อมูลที่อาจมีความละเอียดอ่อน เช่น ข้อมูลส่วนบุคคล Microsoft จะถ่ายโอนข้อมูลดังกล่าวตามคำสั่งของคุณ แต่คุณมีหน้าที่รับผิดชอบในการตรวจสอบว่า HERE Technologies ปฏิบัติตามข้อผูกพันด้านความเป็นส่วนตัวหรือความปลอดภัยที่คุณอาจมี สำหรับข้อมูลเพิ่มเติม ดู [คำชี้แจงสิทธิส่วนบุคคลของ Microsoft](https://go.microsoft.com/fwlink/?linkid=396732)
ผู้ดูแลระบบ Dynamics 365 Customer Insights ของคุณสามารถเอาการเพิ่มข้อมูลนี้ออกได้ตลอดเวลาเพื่อยกเลิกการใช้ฟังก์ชันนี้ต่อ
