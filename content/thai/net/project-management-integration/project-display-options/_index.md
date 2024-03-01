---
title: การกำหนดค่าตัวเลือกการแสดงโครงการ MS ใน Aspose.Tasks
linktitle: การกำหนดค่าตัวเลือกการแสดงโครงการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่าตัวเลือกการแสดงผล MS Project โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET ปรับแต่งรูปลักษณ์ของโครงการของคุณได้อย่างง่ายดาย
type: docs
weight: 17
url: /th/net/project-management-integration/project-display-options/
---
## การแนะนำ
Microsoft Project มีตัวเลือกการแสดงผลมากมายเพื่อปรับแต่งรูปลักษณ์ของโครงการของคุณ Aspose.Tasks สำหรับ .NET มีเฟรมเวิร์กที่แข็งแกร่งเพื่อจัดการตัวเลือกเหล่านี้โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะสำรวจวิธีกำหนดค่าตัวเลือกการแสดงผล MS Project โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไฟล์ Microsoft Project: มีไฟล์ MS Project ที่ถูกต้อง (.mpp) พร้อมที่จะใช้ตัวเลือกการแสดงผล
3. ความรู้พื้นฐานเกี่ยวกับ C#: จำเป็นต้องมีความคุ้นเคยกับภาษาการเขียนโปรแกรม C#

## การนำเข้าเนมสเปซ
ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
 โหลดไฟล์ MS Project โดยใช้นามสกุล`Project` คลาสที่จัดทำโดย Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการแสดงผล
ตอนนี้เรามากำหนดค่าตัวเลือกการแสดงผลต่าง ๆ ที่มีอยู่ใน MS Project:
### ปิดใช้งานคำเตือนกำหนดการงาน
หากต้องการปิดใช้งานคำเตือนสำหรับความขัดแย้งในการกำหนดเวลากับงานที่กำหนดเวลาไว้ด้วยตนเอง (สำหรับ Project 2010 และใหม่กว่า):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### เพิ่มช่องว่างก่อนป้ายกำกับ
ตั้งค่าให้เพิ่มช่องว่างก่อนค่าตัวเลขและตัวย่อเวลา:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### กำหนดค่าการแสดงฉลากสำหรับหน่วยเวลา
ปรับแต่งวิธีการแสดงหน่วยเวลาที่แตกต่างกัน:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### แสดงงานสรุปโครงการ
แสดงข้อมูลสรุปเกี่ยวกับโครงการทั้งหมดบนแถวเดียว:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### เปิดใช้งานคำแนะนำกำหนดการงาน
อนุญาตให้แสดงคำแนะนำสำหรับข้อขัดแย้งในการกำหนดเวลากับงานที่กำหนดเวลาไว้ด้วยตนเอง:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### ขีดเส้นใต้ไฮเปอร์ลิงก์
ตั้งค่าให้ขีดเส้นใต้ไฮเปอร์ลิงก์ภายในโครงการ:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## ขั้นตอนที่ 3: บันทึกโครงการ
สุดท้าย ให้บันทึกโปรเจ็กต์ด้วยตัวเลือกการแสดงผลที่ใช้:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีกำหนดค่าตัวเลือกการแสดงผล MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยความสามารถเหล่านี้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของไฟล์โปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพโดยทางโปรแกรม
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ตัวเลือกการแสดงผลเหล่านี้กับงานเฉพาะเท่านั้นได้หรือไม่
ตอบ: ได้ คุณสามารถเลือกใช้ตัวเลือกการแสดงผลกับงานแต่ละงานได้โดยใช้ Aspose.Tasks API
### ถาม: ตัวเลือกการแสดงผลเหล่านี้ส่งผลต่อข้อมูลโครงการพื้นฐานหรือไม่
ตอบ: ไม่ ตัวเลือกเหล่านี้แก้ไขการแสดงภาพของโครงการเท่านั้น และไม่ได้เปลี่ยนแปลงข้อมูลพื้นฐาน
### ถาม: ตัวเลือกการแสดงผลเหล่านี้เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: ไม่ ตัวเลือกบางอย่างอาจมีเฉพาะกับ MS Project บางเวอร์ชันเท่านั้น โปรดดูเอกสารประกอบสำหรับรายละเอียดความเข้ากันได้
### ถาม: ฉันสามารถเปลี่ยนตัวเลือกการแสดงผลกลับเป็นการตั้งค่าเริ่มต้นได้หรือไม่
ตอบ: ได้ คุณสามารถรีเซ็ตตัวเลือกการแสดงผลเป็นค่าเริ่มต้นได้โดยใช้ Aspose.Tasks API
### ถาม: มีข้อจำกัดในการปรับแต่งตัวเลือกการแสดงผลโดยทางโปรแกรมหรือไม่
ตอบ: แม้ว่า Aspose.Tasks จะมีความสามารถในการปรับแต่งที่กว้างขวาง แต่ตัวเลือกการแสดงผลบางอย่างอาจไม่สามารถเข้าถึงได้โดยทางโปรแกรมเนื่องจากข้อจำกัดในรูปแบบไฟล์ MS Project