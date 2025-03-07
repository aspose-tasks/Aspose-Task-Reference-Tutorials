---
title: การจัดการ MS Project Split Parts ใน Aspose.Tasks
linktitle: การจัดการชิ้นส่วนแยกใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการการแยกส่วน MS Project อย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ .NET ปรับปรุงขั้นตอนการจัดการโครงการของคุณ
weight: 18
url: /th/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการ MS Project Split Parts ใน Aspose.Tasks


## การแนะนำ
การจัดการส่วนแยกโครงการ MS อาจเป็นส่วนสำคัญของการจัดการโครงการเมื่อใช้ Aspose.Tasks สำหรับ .NET ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการส่วนที่แยกอย่างมีประสิทธิภาพโดยใช้คำแนะนำทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
   
2. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## ขั้นตอนที่ 1: การสร้างอินสแตนซ์โครงการ
```csharp
var project = new Project();
```
 สร้างอินสแตนซ์ใหม่ของ`Project` ระดับ.
## ขั้นตอนที่ 2: การตั้งค่าวันที่เริ่มต้นและสิ้นสุดโครงการ
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
กำหนดวันเริ่มต้นและสิ้นสุดของโครงการ
## ขั้นตอนที่ 3: การเพิ่มงาน
```csharp
var task = project.RootTask.Children.Add("Task1");
```
เพิ่มงานใหม่ให้กับโครงการ
## ขั้นตอนที่ 4: การตั้งค่าคุณสมบัติของงาน
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
ตั้งค่าคุณสมบัติ เช่น สถานะด้วยตนเอง วันที่เริ่มต้น และระยะเวลาสำหรับงาน
## ขั้นตอนที่ 5: การเพิ่มการมอบหมายทรัพยากร
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
เพิ่มการมอบหมายทรัพยากรให้กับงาน
## ขั้นตอนที่ 6: การตั้งค่าคุณสมบัติการมอบหมาย
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
ตั้งค่าคุณสมบัติ เช่น วันที่เริ่มต้น งาน และวันที่สิ้นสุดสำหรับงานที่ได้รับมอบหมาย
## ขั้นตอนที่ 7: การสร้างข้อมูลตามช่วงเวลา
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
สร้างข้อมูลตามช่วงเวลาสำหรับการมอบหมายงานตามปฏิทินโครงการ
## ขั้นตอนที่ 8: การแบ่งงาน
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
แบ่งงานออกเป็นหลายส่วนภายในกรอบเวลาที่กำหนด
## ขั้นตอนที่ 9: วนซ้ำส่วนแยก
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
ทำซ้ำส่วนที่แยกของงานและพิมพ์วันที่เริ่มต้นและสิ้นสุด

## บทสรุป
การจัดการส่วนแยก MS Project อย่างมีประสิทธิภาพใน Aspose.Tasks สำหรับ .NET เป็นสิ่งสำคัญสำหรับประสิทธิภาพการจัดการโครงการ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการงานแยกได้อย่างราบรื่นและปรับปรุงเวิร์กโฟลว์การจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ รวมถึง .NET Core และ .NET Standard
### ถาม: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถขอรับการทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: Aspose.Tasks for .NET รองรับการจัดการทรัพยากรหรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET ช่วยให้คุณจัดการทรัพยากรโปรเจ็กต์ได้อย่างมีประสิทธิภาพ
### ถาม: ฉันสามารถปรับแต่งปฏิทินโครงการโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: แน่นอน คุณสามารถปรับแต่งปฏิทินโครงการตามความต้องการของโครงการของคุณได้
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
