---
title: การกำหนดค่ามุมมองการใช้ทรัพยากรโครงการ MS ใน Aspose.Tasks
linktitle: การกำหนดค่ามุมมองการใช้ทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่ามุมมองการใช้ทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดรวมอยู่ด้วย
type: docs
weight: 15
url: /th/net/resource-risk-analysis/resource-usage-views/
---
## การแนะนำ
Microsoft Project (MS Project) เป็นเครื่องมือที่มีประสิทธิภาพสำหรับการจัดการโครงการ ช่วยให้ผู้ใช้สามารถวางแผน ดำเนินการ และติดตามโครงการได้อย่างมีประสิทธิภาพ Aspose.Tasks for .NET มอบการผสานรวมกับไฟล์ MS Project ได้อย่างราบรื่น ช่วยให้นักพัฒนาสามารถจัดการข้อมูลโปรเจ็กต์โดยทางโปรแกรมได้ ในบทช่วยสอนนี้ เราจะสำรวจวิธีกำหนดค่ามุมมองการใช้ทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. ไฟล์โครงการ Microsoft: มีไฟล์โครงการ Microsoft (`.mpp`) ที่มีข้อมูลโครงการที่คุณต้องการทำงานด้วย

## นำเข้าเนมสเปซ
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก ให้โหลดไฟล์ MS Project โดยใช้ Aspose.Tasks:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึก
กำหนดตัวเลือกการบันทึกโดยระบุการตั้งค่ามาตราส่วนเวลาและรูปแบบการนำเสนอที่ต้องการ:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## ขั้นตอนที่ 3: บันทึกโปรเจ็กต์ด้วยมุมมองการใช้ทรัพยากร
บันทึกโปรเจ็กต์ด้วยมุมมองการใช้ทรัพยากรที่กำหนดค่าไว้เป็นไฟล์ PDF:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีกำหนดค่ามุมมองการใช้ทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ นักพัฒนาสามารถรวม Aspose.Tasks เข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น เพื่อจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึง .mpp, .mpt, .xml และ .mpx
### ถาม: ฉันสามารถปรับแต่งการตั้งค่ามาตราส่วนเวลาและรูปแบบการนำเสนอเพิ่มเติมได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks มอบความยืดหยุ่นในการปรับแต่งการตั้งค่ามาตราส่วนเวลาและรูปแบบการนำเสนอตามความต้องการของคุณ
### ถาม: Aspose.Tasks รองรับรูปแบบเอาต์พุตอื่นๆ นอกเหนือจาก PDF หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง XLSX, MPP, XML, HTML และอื่นๆ
### ถาม: มีชุมชนหรือฟอรัมสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถเยี่ยมชมได้[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับข้อสงสัย การสนทนา หรือความต้องการการสนับสนุน
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 ตอบ: แน่นอน คุณสามารถสำรวจ Aspose.Tasks พร้อมให้ทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).