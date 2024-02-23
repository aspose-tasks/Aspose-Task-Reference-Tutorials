---
title: การเรียนรู้มุมมองการใช้งานใน Aspose.Tasks สำหรับ .NET
linktitle: กำหนดค่ามุมมองการใช้งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจ Aspose.Tasks สำหรับ .NET และเรียนรู้วิธีกำหนดค่ามุมมองการใช้งาน ปรับแต่งการตั้งค่ามาตราส่วนเวลาและปรับปรุงภาพการจัดการโครงการของคุณ
type: docs
weight: 24
url: /th/net/task-table-management/task-usage-views/
---
## การแนะนำ
ในขอบเขตของการจัดการโครงการ การแสดงภาพการใช้งานเป็นสิ่งสำคัญสำหรับการวางแผนและการดำเนินการที่มีประสิทธิภาพ Aspose.Tasks for .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการเรนเดอร์มุมมองการใช้งาน ซึ่งช่วยให้คุณปรับแต่งการตั้งค่ามาตราส่วนเวลาและรูปแบบการนำเสนอได้ ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนต่างๆ เพื่อกำหนดค่ามุมมองการใช้งานโดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Tasks ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อม .NET: ตั้งค่าสภาพแวดล้อม .NET ที่ใช้งานได้บนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks เพิ่มบรรทัดต่อไปนี้ลงในโค้ดของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
 ก่อนที่จะทำงานกับฟังก์ชัน Aspose.Tasks ให้กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"Your Document Directory"` กับเส้นทางที่แท้จริง
```csharp
String DataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดโครงการ
 เริ่มต้น Aspose.Tasks`Project` วัตถุโดยการโหลดไฟล์โครงการของคุณ (เช่น TaskUsageView.mpp)
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## ขั้นตอนที่ 3: กำหนด SaveOptions
 สร้างก`SaveOptions`วัตถุเพื่อระบุตัวเลือกการเรนเดอร์ ตั้งค่ามาตราส่วนเวลาเป็น 'วัน' และรูปแบบการนำเสนอเป็น 'TaskUsage'
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## ขั้นตอนที่ 4: บันทึกด้วย Days Timescale
บันทึกโครงการด้วยการตั้งค่ามาตราส่วนเวลาที่กำหนดไว้ล่วงหน้าเป็น 'วัน'
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## ขั้นตอนที่ 5: ประหยัดด้วยมาตราส่วนเวลา ThirdsOfMonths
เปลี่ยนการตั้งค่ามาตราส่วนเวลาเป็น 'ThirdsOfMonths' และบันทึกโครงการ
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## ขั้นตอนที่ 6: บันทึกด้วยมาตราเวลาเดือน
กำหนดมาตราส่วนเวลาเป็น 'เดือน' และบันทึกโปรเจ็กต์ด้วยการตั้งค่าที่อัปเดต
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## บทสรุป
การกำหนดค่ามุมมองการใช้งานด้วย Aspose.Tasks สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการปรับแต่งการตั้งค่ามาตราส่วนเวลา คุณสามารถปรับแต่งการแสดงภาพงานโครงการของคุณตามความต้องการเฉพาะของคุณได้
 รู้สึกอิสระที่จะสำรวจคุณสมบัติและฟังก์ชันการทำงานเพิ่มเติมใน[เอกสารประกอบ](https://reference.aspose.com/tasks/net/).
## คำถามที่พบบ่อย
### ฉันสามารถกำหนดมาตราส่วนเวลานอกเหนือจากการตั้งค่าที่กำหนดไว้ล่วงหน้าได้หรือไม่
ได้ คุณสามารถกำหนดมาตราส่วนเวลาที่กำหนดเองได้โดยการระบุช่วงเวลาและหน่วย
### มีรูปแบบการนำเสนออื่น ๆ หรือไม่?
Aspose.Tasks รองรับรูปแบบการนำเสนอที่หลากหลาย รวมถึง GanttChart, ResourceUsage และอื่นๆ อีกมากมาย
### Aspose.Tasks เข้ากันได้กับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks รองรับรูปแบบไฟล์โปรเจ็กต์ยอดนิยม เช่น MPP, XML และ CSV
### ฉันสามารถใช้การตั้งค่ามาตราส่วนเวลาที่แตกต่างกันกับงานเฉพาะเจาะจงได้หรือไม่
แน่นอน คุณสามารถปรับแต่งการตั้งค่ามาตราส่วนเวลาสำหรับงานแต่ละงานภายในโปรเจ็กต์ของคุณได้
### ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือสำหรับ Aspose.Tasks ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและคำแนะนำจากชุมชน