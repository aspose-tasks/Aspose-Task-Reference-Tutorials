---
title: การจัดการคอลเลกชันงานใน Aspose.Tasks
linktitle: การจัดการคอลเลกชันงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจการจัดการการรวบรวมงานที่มีประสิทธิภาพใน Aspose.Tasks สำหรับ .NET ตั้งแต่การสร้างไปจนถึงการแก้ไข การจัดการโครงการหลักได้อย่างง่ายดาย
type: docs
weight: 18
url: /th/net/task-table-management/task-collection/
---
## การแนะนำ
หากคุณกำลังเจาะลึกโลกแห่งการจัดการโครงการโดยใช้ .NET Aspose.Tasks คือโซลูชันที่เหมาะกับคุณสำหรับการจัดการคอลเลกชันงานอย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการจัดการคอลเลกชันงานอย่างมีประสิทธิภาพ เพื่อให้มั่นใจว่าคุณจะได้รับประโยชน์สูงสุดจากไลบรารีอันทรงพลังนี้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
- Aspose.Tasks สำหรับไลบรารี .NET ดาวน์โหลดและอ้างอิงในโครงการของคุณ
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณ:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
เนมสเปซเหล่านี้ให้การเข้าถึงคลาสที่จำเป็นและวิธีการที่จำเป็นสำหรับการจัดการงานที่มีประสิทธิภาพ
ตอนนี้ เราจะแบ่งบทช่วยสอนออกเป็นชุดขั้นตอน เพื่อให้มั่นใจถึงความชัดเจนและความเรียบง่าย
## ขั้นตอนที่ 1: การสร้างอินสแตนซ์โครงการ
```csharp
var project = new Project();
```
 สร้างอินสแตนซ์โครงการใหม่โดยใช้`Project` ระดับ.
## ขั้นตอนที่ 2: การตรวจสอบความพร้อมของการรวบรวมงาน
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
ตรวจสอบว่าการรวบรวมงานเป็นแบบอ่านอย่างเดียวหรือไม่
## ขั้นตอนที่ 3: การสร้างงาน
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// ตั้งค่าคุณสมบัติของงานเพิ่มเติม เช่น เริ่มต้น ระยะเวลา และสิ้นสุด
// ขั้นตอนที่คล้ายกันสำหรับภารกิจที่ 2 และภารกิจที่ 3
```
สร้างงานภายในโครงการและตั้งค่าคุณสมบัติ
## ขั้นตอนที่ 4: การพิมพ์งานโครงการ
```csharp
foreach (var child in project.RootTask.Children)
{
    // พิมพ์รายละเอียดงาน
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
พิมพ์รายละเอียดของแต่ละงานภายในโครงการ
## ขั้นตอนที่ 5: การแก้ไขงาน
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
แก้ไขงานโดยใช้ ID หรือ UID
## ขั้นตอนที่ 6: การเพิ่มงานที่เกิดซ้ำ
```csharp
var parameters = new RecurringTaskParameters
{
    // ตั้งค่าพารามิเตอร์งานที่เกิดซ้ำ
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
เพิ่มงานที่เกิดซ้ำในโครงการ
## ขั้นตอนที่ 7: การแปลงคอลเลกชันเป็นรายการ
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
แปลงคอลเลกชันงานให้เป็นรายการและดำเนินการกับแต่ละงาน
## บทสรุป
การจัดการคอลเลกชันงานใน Aspose.Tasks สำหรับ .NET เป็นเรื่องง่ายด้วยคำแนะนำทีละขั้นตอนนี้ ไม่ว่าคุณจะสร้าง แก้ไข หรือลบงาน Aspose.Tasks ช่วยให้คุณสามารถจัดการการจัดการโครงการได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Tasks รองรับ .NET Core ซึ่งทำให้คุณสามารถใช้ในแอปพลิเคชันข้ามแพลตฟอร์มได้
### ฉันสามารถส่งออกงานโครงการเป็นรูปแบบไฟล์อื่นได้หรือไม่
อย่างแน่นอน! Aspose.Tasks มีตัวเลือกการส่งออกที่หลากหลาย รวมถึง PDF, XLSX และ MPP
### ฉันจะจัดการกับการพึ่งพาระหว่างงานได้อย่างไร
 คุณสามารถตั้งค่าการพึ่งพางานได้โดยใช้`TaskLink` คลาสที่จัดทำโดย Aspose.Tasks
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ใช่ คุณสามารถหาการสนับสนุนและมีส่วนร่วมกับชุมชนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้หรือไม่
 ใช่ คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).