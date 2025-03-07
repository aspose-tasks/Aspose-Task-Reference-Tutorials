---
title: การจัดการลิงค์งานใน Aspose.Tasks
linktitle: การจัดการลิงค์งานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจพลังของ Aspose.Tasks สำหรับ .NET ในการจัดการลิงก์งานโครงการอย่างมีประสิทธิภาพ ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อปรับปรุงประสบการณ์การจัดการโครงการของคุณ
weight: 19
url: /th/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการลิงค์งานใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการจัดการลิงก์งานใน Aspose.Tasks for .NET! ลิงก์งานมีบทบาทสำคัญในการจัดการโครงการ ทำให้คุณสามารถสร้างความสัมพันธ์ระหว่างงานและสร้างการขึ้นต่อกันได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทำงานกับคอลเลกชันลิงก์งานโดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไฟล์โครงการตัวอย่าง: เตรียมไฟล์โครงการตัวอย่าง (เช่น "SampleProject.mpp") เพื่อติดตามพร้อมกับตัวอย่าง
เอาล่ะ มาเริ่มกันเลย!
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: โหลดโครงการและงานการเข้าถึง
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
// โหลดโปรเจ็กต์
var project = new Project(DataDir + "SampleProject.mpp");
// เข้าถึงงานด้วย ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## ขั้นตอนที่ 2: สร้างลิงค์งาน
เชื่อมโยงงานเข้าด้วยกันเพื่อสร้างการพึ่งพา:
```csharp
// เชื่อมโยงงานโดยใช้การพึ่งพา FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## ขั้นตอนที่ 3: พิมพ์ลิงค์งาน
พิมพ์ลิงค์งานสำหรับโครงการ:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//ทำซ้ำผ่านลิงก์งาน
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## ขั้นตอนที่ 4: แก้ไขลิงก์งาน
แก้ไขลิงค์งานโดยการเข้าถึงดัชนี:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## ขั้นตอนที่ 5: ลบลิงค์งาน
ลบลิงก์งานทั้งหมดออกจากโครงการ:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีจัดการลิงก์งานใน Aspose.Tasks for .NET เรียบร้อยแล้ว คู่มือที่ครอบคลุมนี้ครอบคลุมถึงการโหลดโปรเจ็กต์ การสร้างลิงก์งาน การพิมพ์ลิงก์ การแก้ไขลิงก์ และการลบลิงก์งาน
รู้สึกอิสระที่จะสำรวจคุณสมบัติและฟังก์ชันเพิ่มเติมที่นำเสนอโดย Aspose.Tasks เพื่อปรับปรุงประสบการณ์การจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
ใช่ Aspose.Tasks ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับ .NET ทุกเวอร์ชัน
### ฉันสามารถสร้างประเภทลิงก์งานแบบกำหนดเองโดยใช้ Aspose.Tasks ได้หรือไม่
ปัจจุบัน Aspose.Tasks รองรับประเภทลิงก์งานมาตรฐาน และไม่มีประเภทลิงก์แบบกำหนดเองให้เลือก
### ฉันจะใช้ข้อจำกัดกับงานใน Aspose.Tasks ได้อย่างไร
 คุณสามารถใช้ข้อจำกัดได้โดยใช้`ConstraintType` ทรัพย์สินของ`Task` คลาสใน Aspose.Tasks
### มีข้อจำกัดเกี่ยวกับขนาดของไฟล์โปรเจ็กต์ที่ Aspose.Tasks สามารถรองรับได้หรือไม่
Aspose.Tasks สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้อย่างมีประสิทธิภาพโดยมีผลกระทบต่อประสิทธิภาพน้อยที่สุด
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ใช่ คุณสามารถหาการสนับสนุนและมีส่วนร่วมกับชุมชนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
