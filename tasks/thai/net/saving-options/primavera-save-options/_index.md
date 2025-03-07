---
title: บันทึกตัวเลือกโครงการ MS Primavera ด้วย Aspose.Tasks
linktitle: Primavera บันทึกตัวเลือกสำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ค้นพบวิธีบันทึกตัวเลือก MS Project สำหรับ Primavera ได้อย่างราบรื่นโดยใช้ Aspose.Tasks สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเรา
weight: 14
url: /th/net/saving-options/primavera-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกตัวเลือกโครงการ MS Primavera ด้วย Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น หนึ่งในฟังก์ชันหลักที่มีให้คือความสามารถในการบันทึกตัวเลือก MS Project สำหรับ Primavera ซึ่งเป็นซอฟต์แวร์การจัดการโครงการยอดนิยม ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีการบรรลุเป้าหมายนี้โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
-  Aspose.Tasks สำหรับ .NET ที่ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- ไฟล์ MS Project ตัวอย่างสำหรับการทดลอง

## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นไปยังโค้ด C# ของเรา:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ MS
 เริ่มต้นด้วยการโหลดไฟล์ MS Project ที่คุณต้องการใช้งานลงในแอปพลิเคชัน C# ของคุณ คุณสามารถทำได้โดยใช้`Project` คลาสที่จัดทำโดย Aspose.Tasks
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึก Primavera
จากนั้น สร้างตัวเลือกการบันทึก Primavera และปรับแต่งตามความต้องการของคุณ ขั้นตอนนี้เกี่ยวข้องกับการระบุพารามิเตอร์ เช่น คำนำหน้า ID กิจกรรม ส่วนต่อท้าย การเพิ่มขึ้น และไม่ว่าจะกำหนดหมายเลขใหม่ให้กับ ID กิจกรรมหรือไม่
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## ขั้นตอนที่ 3: บันทึกตัวเลือกโครงการ MS สำหรับ Primavera
 เมื่อคุณได้โหลดไฟล์โปรเจ็กต์และกำหนดตัวเลือกการบันทึก Primavera แล้ว ก็ถึงเวลาบันทึกตัวเลือกสำหรับ Primavera ใช้`Save` วิธีการที่กำหนดโดย`Project` ผ่านเส้นทางไฟล์เอาต์พุตที่ต้องการและตัวเลือกการบันทึก Primavera
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## บทสรุป
โดยสรุป การใช้ประโยชน์จาก Aspose.Tasks สำหรับ .NET ช่วยให้นักพัฒนาสามารถจัดการไฟล์ MS Project ได้อย่างราบรื่น รวมถึงตัวเลือกการบันทึกสำหรับ Primavera ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งพารามิเตอร์อื่นๆ นอกเหนือจากรหัสกิจกรรมเมื่อบันทึกตัวเลือก MS Project สำหรับ Primavera ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks มีตัวเลือกมากมายสำหรับการปรับแต่ง รวมถึงการจัดสรรทรัพยากรและการจัดกำหนดการงาน
### ถาม: Aspose.Tasks รองรับซอฟต์แวร์การจัดการโครงการอื่นๆ นอกเหนือจาก Primavera หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบต่างๆ ที่เข้ากันได้กับเครื่องมือการจัดการโครงการยอดนิยม เช่น Oracle Primavera, Microsoft Project Server และอื่นๆ
### ถาม: Aspose.Tasks เหมาะสำหรับทั้งโครงการขนาดเล็กและระดับองค์กรหรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของนักพัฒนาที่ทำงานในโครงการทุกขนาด โดยให้ความสามารถในการปรับขนาดและประสิทธิภาพที่แข็งแกร่ง
### ถาม: ฉันสามารถทดลองใช้ Aspose.Tasks ฟรีก่อนตัดสินใจซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติและความสามารถของมัน
### ถาม: ฉันจะรับการสนับสนุนได้ที่ไหนหากฉันประสบปัญหาหรือมีคำถามขณะใช้งาน Aspose.Tasks
 ตอบ: คุณสามารถขอความช่วยเหลือจากชุมชน Aspose.Tasks และทีมสนับสนุนได้ที่[ฟอรั่ม](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
