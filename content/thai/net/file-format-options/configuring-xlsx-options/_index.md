---
title: กำหนดค่าตัวเลือก MS Project XLSX ใน Aspose.Tasks สำหรับ .NET
linktitle: กำหนดค่าตัวเลือก XLSX ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่าตัวเลือก MS Project XLSX ใน Aspose.Tasks สำหรับ .NET ปรับแต่งคอลัมน์ การเข้ารหัส และอื่นๆ ได้อย่างง่ายดาย
type: docs
weight: 11
url: /th/net/file-format-options/configuring-xlsx-options/
---
## การแนะนำ
Microsoft Project (MS Project) เป็นเครื่องมืออันทรงพลังสำหรับการจัดการโครงการ และ Aspose.Tasks สำหรับ .NET มอบการบูรณาการที่ราบรื่นสำหรับการทำงานกับไฟล์ MS Project โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการกำหนดค่าตัวเลือก MS Project XLSX โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[Aspose.Tasks สำหรับหน้าดาวน์โหลด .NET](https://releases.aspose.com/tasks/net/).
### 2. ความเข้าใจพื้นฐานเกี่ยวกับ C# และ .NET Framework
จำเป็นต้องมีความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และเฟรมเวิร์ก .NET ควบคู่ไปกับบทช่วยสอนนี้
### 3. ไฟล์โครงการไมโครซอฟต์
เตรียมไฟล์ Microsoft Project (MPP) ที่คุณต้องการกำหนดค่าและบันทึกเป็นไฟล์ XLSX

## การนำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: โหลดโครงการ
```csharp
var project = new Project("YourProjectFile.mpp");
```
โหลดไฟล์ Microsoft Project ที่คุณต้องการกำหนดค่า
## ขั้นตอนที่ 2: กำหนด XlsxOptions
```csharp
var options = new XlsxOptions();
```
 สร้างอินสแตนซ์ของ`XlsxOptions` เพื่อกำหนดการตั้งค่าสำหรับการบันทึกเป็น XLSX
## ขั้นตอนที่ 3: เพิ่มคอลัมน์แผนภูมิแกนต์
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
เพิ่มคอลัมน์แผนภูมิแกนต์ที่ต้องการลงในตัวเลือก
## ขั้นตอนที่ 4: เพิ่มคอลัมน์มุมมองทรัพยากร
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
รวมคอลัมน์ที่ต้องการสำหรับมุมมองทรัพยากรในตัวเลือก
## ขั้นตอนที่ 5: เพิ่มคอลัมน์มุมมองการมอบหมาย
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
เพิ่มคอลัมน์ที่ต้องการสำหรับมุมมองการมอบหมายในตัวเลือก
## ขั้นตอนที่ 6: ตั้งค่าการเข้ารหัส
```csharp
options.Encoding = Encoding.Unicode;
```
ตั้งค่าการเข้ารหัสสำหรับไฟล์เอาต์พุต
## ขั้นตอนที่ 7: บันทึกโครงการเป็น XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
บันทึกโปรเจ็กต์ด้วยตัวเลือกที่กำหนดค่าไว้เป็นไฟล์ XLSX

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีกำหนดค่าตัวเลือก MS Project XLSX โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งรูปแบบเอาต์พุตได้ตามความต้องการของคุณ ซึ่งช่วยเพิ่มความยืดหยุ่นและความสามารถในการใช้งานเวิร์กโฟลว์การจัดการโครงการของคุณ
## คำถามที่พบบ่อย

### ถาม: ฉันสามารถกำหนดค่าคอลัมน์ต่างๆ สำหรับแผนภูมิแกนต์ มุมมองทรัพยากร และมุมมองการมอบหมายแยกกันได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งคอลัมน์แยกกันสำหรับแต่ละมุมมองได้โดยใช้ Aspose.Tasks for .NET

### ถาม: มีเวอร์ชันทดลองใช้ก่อนที่จะซื้อ Aspose.Tasks สำหรับ .NET หรือไม่

 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[Aspose.Tasks สำหรับหน้าเผยแพร่ .NET](https://releases.aspose.com/).

### ถาม: ฉันจะได้รับการสนับสนุนได้อย่างไร หากฉันพบปัญหาหรือมีคำถามระหว่างการใช้งาน

 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือจากชุมชนและทีมสนับสนุน Aspose

### ถาม: ฉันสามารถสร้างไฟล์ XLSX ด้วย Aspose.Tasks สำหรับ .NET บนแพลตฟอร์มที่ไม่ใช่ Windows ได้หรือไม่

ตอบ: Aspose.Tasks for .NET ได้รับการออกแบบมาเพื่อแพลตฟอร์ม Windows เป็นหลัก แต่คุณอาจสำรวจตัวเลือกความเข้ากันได้สำหรับแพลตฟอร์มอื่นๆ ได้

### ถาม: มีตัวเลือกใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่

 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราวของ Aspose.Tasks](https://purchase.aspose.com/temporary-license/).