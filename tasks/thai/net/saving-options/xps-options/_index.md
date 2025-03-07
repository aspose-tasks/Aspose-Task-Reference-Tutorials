---
title: แปลง MSP เป็นตัวเลือก XPS ด้วย Aspose.Tasks
linktitle: ตัวเลือก XPS สำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีแปลงไฟล์ Microsoft Project เป็นรูปแบบ XPS โดยใช้ Aspose.Tasks สำหรับ .NET บูรณาการได้ง่าย มีฟังก์ชันการทำงานที่แข็งแกร่ง
weight: 21
url: /th/net/saving-options/xps-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง MSP เป็นตัวเลือก XPS ด้วย Aspose.Tasks

## การแนะนำ
Microsoft Project (MSP) เป็นเครื่องมือที่ใช้กันอย่างแพร่หลายสำหรับการจัดการโครงการ อำนวยความสะดวกในการวางแผน การติดตาม และการรายงานกิจกรรมของโครงการ Aspose.Tasks สำหรับ .NET นำเสนอฟังก์ชันการทำงานที่มีประสิทธิภาพในการจัดการไฟล์ MSP โดยทางโปรแกรม ช่วยให้นักพัฒนาสามารถทำงานต่างๆ ที่เกี่ยวข้องกับการจัดการโครงการได้โดยอัตโนมัติ ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการใช้ประโยชน์จาก Aspose.Tasks สำหรับ .NET เพื่อสร้างไฟล์ XPS จากเอกสาร MSP โดยสำรวจขั้นตอนและข้อควรพิจารณาที่จำเป็น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
2. เอกสารโครงการ Microsoft: เตรียมเอกสาร Microsoft Project (.mpp) ที่คุณต้องการแปลงเป็นรูปแบบ XPS

## นำเข้าเนมสเปซ
หากต้องการเริ่มต้นกระบวนการ ให้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณ:
```csharp

using Aspose.Tasks.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางที่เอกสาร MSP ของคุณตั้งอยู่
## ขั้นตอนที่ 2: โหลดเอกสาร MSP
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 ที่นี่เราเริ่มต้นใหม่`Project` วัตถุโดยผ่านเส้นทางของเอกสาร MSP
## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก XPS
```csharp
// สร้างตัวเลือกการบันทึก XPS และปรับแต่งพารามิเตอร์
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 ในขั้นตอนนี้ เราจะสร้างอินสแตนซ์`XpsOptions`และกำหนดค่าพารามิเตอร์ การตั้งค่า`RenderMetafileAsBitmap` ถึง`true` ช่วยให้มั่นใจได้ถึงการเรนเดอร์ metafiles ที่เหมาะสม
## ขั้นตอนที่ 4: บันทึกเอกสารเป็น XPS
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 ในที่สุดเราก็เรียกว่า`Save` วิธีการบน`Project` วัตถุระบุเส้นทางของไฟล์เอาต์พุตและกำหนดค่าไว้ก่อนหน้านี้`XpsOptions`.

## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ .NET ช่วยลดความยุ่งยากในการแปลงเอกสาร Microsoft Project เป็นรูปแบบ XPS โดยทางโปรแกรม ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ นักพัฒนาสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น เพิ่มประสิทธิภาพเวิร์กโฟลว์การจัดการโครงการได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ .NET สามารถจัดการไฟล์ MSP ที่ซับซ้อนได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET สามารถจัดการไฟล์ Microsoft Project ที่ซับซ้อนได้อย่างมีประสิทธิภาพ รับประกันการแปลงเป็นรูปแบบต่างๆ ได้อย่างแม่นยำ
### ถาม: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถขอรับเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: Aspose.Tasks สำหรับ .NET รองรับรูปแบบเอาต์พุตอื่นๆ นอกเหนือจาก XPS หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับรูปแบบเอาต์พุตที่หลากหลาย เช่น PDF, HTML, PNG และ JPEG และอื่นๆ อีกมากมาย
### ถาม: ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับไฟล์เอาท์พุตได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งพารามิเตอร์การเรนเดอร์ตามความต้องการของคุณ
### ถาม: ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมสำหรับ Aspose.Tasks for .NET ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) หากมีข้อสงสัยหรือความช่วยเหลือเกี่ยวกับ Aspose.Tasks สำหรับ .NET
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
