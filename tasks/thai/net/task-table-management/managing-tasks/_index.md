---
title: การจัดการงานใน Aspose.Tasks
linktitle: การจัดการงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจคำแนะนำที่ครอบคลุมเกี่ยวกับการจัดการงานด้วย Aspose.Tasks สำหรับ .NET เรียนรู้การเพิ่ม แสดงส่วนที่แยก ย้าย รับ/ตั้งค่าคุณสมบัติ และอื่นๆ
weight: 15
url: /th/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการงานใน Aspose.Tasks

## การแนะนำ
หากคุณเป็นนักพัฒนา .NET ที่ต้องการจัดการงานภายในโครงการของคุณอย่างมีประสิทธิภาพ Aspose.Tasks สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับแง่มุมต่างๆ ของการจัดการงานโดยใช้ Aspose.Tasks โดยเสนอคำแนะนำทีละขั้นตอนและตัวอย่างโค้ด ไม่ว่าคุณจะเพิ่มงาน แสดงส่วนที่แยก ย้ายงานภายใต้พาเรนต์เดียวกัน รับ/ตั้งค่าคุณสมบัติของงาน วนซ้ำการมอบหมายงาน การอ่านเส้นฐานของงาน หรือลบงาน คู่มือนี้ก็มีครอบคลุมทุกอย่างแล้ว
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Aspose.Tasks สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่จะจัดเก็บเอกสารโครงการของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. การเพิ่มงานในโครงการ
```csharp
// สร้างโครงการใหม่
var project = new Project();
// เพิ่มงาน
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// บันทึกโครงการ
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. การแสดงส่วนที่แยกของงาน
```csharp
// โหลดโปรเจ็กต์ที่มีงานแยก
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// เข้าถึงงาน
var task = project.RootTask.Children.GetById(4);
// แสดงการแบ่งส่วน
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. การย้ายงานภายใต้ผู้ปกครองคนเดียวกัน
```csharp
try
{
    // โหลดโปรเจ็กต์
    var project = new Project(DataDir + "MoveTask.mpp");
    // ย้ายงานด้วย id 5 ก่อนงานด้วย id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // บันทึกโปรเจ็กต์ที่แก้ไข
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. รับ/ตั้งค่าคุณสมบัติของงาน
```csharp
// สร้างโครงการใหม่
var project = new Project();
// เพิ่มงานและตั้งค่าคุณสมบัติ
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// รวบรวมและแสดงคุณสมบัติของงาน
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. ทำซ้ำการมอบหมายงาน
```csharp
// โหลดโปรเจ็กต์ที่มีการมอบหมาย
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// รวบรวมและแสดงการมอบหมายงาน
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. การอ่านบรรทัดฐานของงาน
```csharp
// สร้างโครงการใหม่
var project = new Project();
// เพิ่มงานและตั้งค่าพื้นฐาน
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// แสดงระยะเวลาพื้นฐานของงาน
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. การลบงาน
```csharp
// สร้างโครงการใหม่
var project = new Project();
// เพิ่มงาน
var task = project.RootTask.Children.Add("Task");
//แสดงจำนวนงานก่อนและหลังการลบ
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// ลบงาน
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## บทสรุป
การจัดการงานใน Aspose.Tasks สำหรับ .NET เป็นกระบวนการที่ราบรื่นพร้อมตัวอย่างที่ให้ไว้ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น การนำเทคนิคเหล่านี้ไปใช้จะช่วยเพิ่มความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET ทั้งหมดหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับเฟรมเวิร์ก .NET ที่หลากหลาย เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับสภาพแวดล้อมการพัฒนาของคุณ
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: คุณสามารถรับใบอนุญาตชั่วคราว 30 วันได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: มีข้อจำกัดใดๆ เมื่อทำงานกับการแบ่งงานใน Aspose.Tasks หรือไม่
 ตอบ: การแบ่งงานเป็นคุณสมบัติที่มีประสิทธิภาพ และสามารถดูเอกสารโดยละเอียดได้[ที่นี่](https://reference.aspose.com/tasks/net/).
### ถาม: ฉันสามารถปรับแต่งคุณสมบัติของงานนอกเหนือจากที่แสดงในตัวอย่างได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks มีตัวเลือกการปรับแต่งที่ครอบคลุมสำหรับคุณสมบัติของงาน ตรวจสอบเอกสารประกอบสำหรับรายละเอียดเพิ่มเติม
### ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
