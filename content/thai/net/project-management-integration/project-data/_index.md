---
title: การเรียนรู้ข้อมูลโปรเจ็กต์ด้วย Aspose.Tasks
linktitle: การทำงานกับข้อมูลโครงการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการข้อมูล Microsoft Project โดยใช้ Aspose.Tasks ใน .NET สร้างงาน เพิ่มทรัพยากร และบันทึกโครงการได้อย่างง่ายดาย
type: docs
weight: 16
url: /th/net/project-management-integration/project-data/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับข้อมูล Microsoft Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ .NET Aspose.Tasks มอบฟีเจอร์อันทรงพลังในการจัดการไฟล์โปรเจ็กต์ รวมถึงการสร้างงาน การเพิ่มทรัพยากร การตั้งค่าคุณสมบัติ และการบันทึกโปรเจ็กต์ในรูปแบบต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  การติดตั้งไลบรารี Aspose.Tasks: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET แล้ว
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ก่อนที่จะทำงานกับ Aspose.Tasks ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: เริ่มต้นวัตถุโครงการ
```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project();
```
 บรรทัดนี้เริ่มต้นอินสแตนซ์ใหม่ของ`Project` คลาสซึ่งแสดงถึงไฟล์ Microsoft Project
## ขั้นตอนที่ 2: ตั้งค่าคุณสมบัติของโครงการ
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
บรรทัดเหล่านี้สาธิตวิธีการตั้งค่าคุณสมบัติของโครงการ เช่น รูปแบบงานและโหมดการสร้างงาน
## ขั้นตอนที่ 3: การเพิ่มงาน
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
ที่นี่ งานใหม่ชื่อ "งาน 1" จะถูกเพิ่มไปยังงานรากของโครงการ
## ขั้นตอนที่ 4: การตั้งค่าคุณสมบัติของงาน
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
บรรทัดเหล่านี้จะกำหนดวันที่เริ่มต้น ระยะเวลา และวันที่สิ้นสุดสำหรับ "งาน 1"
## ขั้นตอนที่ 5: การเพิ่มทรัพยากร
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
ส่วนนี้สาธิตวิธีการเพิ่มทรัพยากรงานให้กับโครงการ
## ขั้นตอนที่ 6: การกำหนดทรัพยากรให้กับงาน
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
บรรทัดเหล่านี้แสดงวิธีการกำหนดทรัพยากรงานที่เพิ่มไว้ก่อนหน้านี้ให้กับ "งาน 1" ด้วยวันที่เริ่มต้น งาน และสิ้นสุดที่เฉพาะเจาะจง
## ขั้นตอนที่ 7: บันทึกโครงการ
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
สุดท้าย โครงการจะถูกบันทึกในรูปแบบไฟล์ Microsoft Project XML

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับข้อมูล Microsoft Project โดยใช้ไลบรารี Aspose.Tasks ใน .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการไฟล์โครงการ เพิ่มงาน ทรัพยากร มอบหมายทรัพยากรให้กับงาน และบันทึกโครงการในรูปแบบต่างๆ ได้
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: ได้ Aspose.Tasks ให้การสนับสนุนที่ครอบคลุมสำหรับโครงสร้างโปรเจ็กต์ที่ซับซ้อน ช่วยให้คุณจัดการงาน ทรัพยากร และการมอบหมายได้อย่างมีประสิทธิภาพ
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ มากมาย จึงรับประกันความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ถาม: ฉันสามารถผสานรวม Aspose.Tasks เข้ากับไลบรารี .NET อื่นๆ ได้หรือไม่
ตอบ: แน่นอน Aspose.Tasks ทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น มอบความยืดหยุ่นในโครงการพัฒนาของคุณ
### ถาม: Aspose.Tasks รองรับอัลกอริธึมการจัดกำหนดการโปรเจ็กต์หรือไม่
ตอบ: ใช่ Aspose.Tasks มีอัลกอริธึมการจัดกำหนดการขั้นสูงเพื่อช่วยคุณปรับไทม์ไลน์ของโครงการและการใช้ทรัพยากรให้เหมาะสม
### ถาม: มีฟอรัมชุมชนสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถค้นหาแหล่งข้อมูลที่เป็นประโยชน์และมีส่วนร่วมกับผู้ใช้ Aspose.Tasks คนอื่นๆ ได้บน[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).