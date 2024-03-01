---
title: โครงการ MS พร้อมตัวเลือก Spreadsheet 2003 สำหรับ Aspose.Tasks
linktitle: Spreadsheet 2003 บันทึกตัวเลือกสำหรับ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Spreadsheet 2003 บันทึกตัวเลือกโครงการ MS ด้วย Aspose.Tasks สำหรับ .NET ปรับแต่งและบันทึกไฟล์ MS Project ได้อย่างราบรื่นโดยทางโปรแกรม
type: docs
weight: 19
url: /th/net/saving-options/spreadsheet-2003-save-options/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการใช้ประโยชน์จาก Aspose.Tasks สำหรับ .NET เพื่อใช้ Spreadsheet 2003 Save MS Project Options เครื่องมืออันทรงพลังนี้ช่วยให้สามารถจัดการและปรับแต่งไฟล์ MS Project ในสภาพแวดล้อม .NET ได้อย่างราบรื่น มาแบ่งกระบวนการทีละขั้นตอนกัน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. ความคุ้นเคยกับการเขียนโปรแกรม C#: ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นในการเข้าใจแนวคิดที่กล่าวถึงในบทช่วยสอนนี้

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของคุณ:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
เนมสเปซเหล่านี้ให้การเข้าถึงฟังก์ชันที่จำเป็นสำหรับการบันทึกไฟล์ MS Project โดยใช้รูปแบบ Spreadsheet 2003 และปรับแต่งตัวเลือกมุมมอง
## ขั้นตอนที่ 1: โหลดโครงการ
ขั้นแรก ให้โหลดไฟล์ MS Project โดยใช้ Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 แทนที่`"Your Document Directory"`ด้วยเส้นทางไดเร็กทอรีจริงซึ่งมีไฟล์ MS Project ของคุณอยู่
## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึก
 กำหนดตัวเลือกบันทึก Spreadsheet 2003 โดยการสร้างอินสแตนซ์ของ`Spreadsheet2003SaveOptions`: :
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## ขั้นตอนที่ 3: ปรับแต่งคอลัมน์มุมมอง
ปรับแต่งคอลัมน์มุมมองสำหรับแผนภูมิแกนต์ มุมมองทรัพยากร และมุมมองการมอบหมาย:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
ขั้นตอนเหล่านี้จะเพิ่มคอลัมน์ที่กำหนดเองให้กับมุมมองที่เกี่ยวข้อง ช่วยเพิ่มความสามารถในการแสดงภาพและการวิเคราะห์ของไฟล์ MS Project
## ขั้นตอนที่ 4: บันทึกโครงการ
สุดท้าย ให้บันทึกโครงการด้วยตัวเลือกที่ระบุ:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
คำสั่งนี้จะบันทึกโครงการที่แก้ไขด้วยรูปแบบ Spreadsheet 2003 และคอลัมน์มุมมองที่กำหนดเอง

## บทสรุป
การใช้ Aspose.Tasks สำหรับ .NET โดยเฉพาะ Spreadsheet 2003 Save MS Project Options ช่วยให้นักพัฒนาสามารถจัดการและปรับแต่งไฟล์ MS Project ได้อย่างมีประสิทธิภาพโดยทางโปรแกรม ด้วยการทำตามคำแนะนำทีละขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถรวมความสามารถเหล่านี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพการทำงานและความยืดหยุ่น

## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ .NET สามารถใช้ทั้งในแอปพลิเคชันบนเว็บและเดสก์ท็อปได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET สามารถผสานรวมเข้ากับแอปพลิเคชันบนเว็บและเดสก์ท็อปได้อย่างราบรื่น โดยให้ฟังก์ชันการทำงานที่สอดคล้องกันในทุกแพลตฟอร์ม
### ถาม: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks for .NET รุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/)ให้คุณสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ
### ถาม: มีข้อจำกัดในการปรับแต่งคอลัมน์มุมมองโดยใช้ Aspose.Tasks สำหรับ .NET หรือไม่
ตอบ: Aspose.Tasks for .NET นำเสนอตัวเลือกการปรับแต่งที่ครอบคลุมสำหรับคอลัมน์มุมมอง โดยมีข้อจำกัดน้อยที่สุด อย่างไรก็ตาม การปรับแต่งที่ซับซ้อนอาจต้องใช้ความรู้ขั้นสูงเกี่ยวกับไลบรารี
### ถาม: ฉันสามารถขอความช่วยเหลือได้หรือไม่หากพบปัญหาขณะใช้งาน Aspose.Tasks for .NET
 ตอบ: แน่นอน! คุณสามารถค้นหาการสนับสนุนและทรัพยากรที่ครอบคลุมได้ในฟอรัม Aspose.Tasks ที่[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15)ซึ่งผู้เชี่ยวชาญและสมาชิกชุมชนพร้อมที่จะช่วยแก้ไขข้อสงสัยหรือความท้าทายที่คุณอาจเผชิญ
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/)ทำให้คุณสามารถประเมินความสามารถทั้งหมดของไลบรารีได้