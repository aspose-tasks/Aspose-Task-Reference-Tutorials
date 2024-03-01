---
title: การลบงานโครงการ MS ด้วย Aspose.Tasks
linktitle: การลบงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีลบงาน MS Project โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดรวมอยู่ด้วย
type: docs
weight: 15
url: /th/net/rate-recurring-tasks/removing-tasks/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีลบงานออกจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม การลบงานออกจากไฟล์โครงการอาจเป็นข้อกำหนดทั่วไปในสถานการณ์การจัดการโครงการ และ Aspose.Tasks มอบวิธีที่ตรงไปตรงมาในการบรรลุเป้าหมายนี้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: คุณต้องมี Aspose.Tasks สำหรับ .NET ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ไฟล์โครงการ Microsoft: เตรียมไฟล์โครงการ Microsoft (`Project1.mpp` ในตัวอย่างนี้) ที่คุณต้องการลบงานออก

## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
    using Aspose.Tasks.Util;
Console.WriteLine("Number of tasks before using the algorithm: " + tasks.Count);
Console.WriteLine("Number of tasks after using the algorithm: " + tasks.Count);
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 ในขั้นตอนนี้ เราจะโหลดไฟล์ Microsoft Project ลงในอินสแตนซ์ของ`Project` คลาสที่จัดทำโดย Aspose.Tasks
## ขั้นตอนที่ 2: ระบุงานที่จะลบ
```csharp
var task1 = project.RootTask.Children.Add("1");
var task2 = project.RootTask.Children.Add("2");
var task3 = project.RootTask.Children.Add("3");
var task4 = project.RootTask.Children.Add("4");
```
ที่นี่ เรากำลังเพิ่มงานให้กับงานรากของโครงการ คุณจะแทนที่สิ่งนี้ด้วยตรรกะของคุณเองเพื่อระบุงานที่คุณต้องการลบ
## ขั้นตอนที่ 3: ลบงาน
```csharp
// ใช้อัลกอริธึมแบบทรีเพื่อลบภารกิจ 1 ออกจากทรี
var algorithm = new RemoveTask(task1);
// ใช้อัลกอริทึมกับแผนผังงาน
TaskUtils.Apply(project.RootTask, algorithm, 0);
```
ขั้นตอนนี้เกี่ยวข้องกับการใช้อัลกอริทึมแบบต้นไม้เพื่อลบงานที่ระบุ (`task1` ในตัวอย่างนี้) จากไฟล์โครงการ
## ขั้นตอนที่ 4: ตรวจสอบผลลัพธ์
```csharp
// ตรวจสอบผลลัพธ์
List<Task> tasks = new List<Task>(project.RootTask.SelectAllChildTasks());
Console.WriteLine("Number of tasks after using the algorithm: " + tasks.Count);
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    Console.WriteLine("Task Name: " + task.Get(Tsk.Name));
}
```
สุดท้าย เราจะตรวจสอบผลลัพธ์เพื่อให้แน่ใจว่างานที่ระบุได้ถูกลบออกจากไฟล์โครงการเรียบร้อยแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีลบงานออกจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยเพิ่มขีดความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถลบงานหลายงานพร้อมกันโดยใช้ Aspose.Tasks ได้หรือไม่
ตอบ: ได้ คุณสามารถลบงานหลายงานออกได้โดยการวนซ้ำงานที่คุณต้องการลบ และใช้อัลกอริธึมการลบกับแต่ละงาน
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### ถาม: ฉันสามารถยกเลิกการดำเนินการลบงานได้หรือไม่ หากจำเป็น
ตอบ: Aspose.Tasks มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการยกเลิกการดำเนินการ คุณสามารถใช้ตรรกะแบบกำหนดเองเพื่อจัดการกับสถานการณ์การเลิกทำหากจำเป็น
### ถาม: Aspose.Tasks รองรับโครงสร้างโปรเจ็กต์ที่ซับซ้อนหรือไม่
ตอบ: แน่นอน Aspose.Tasks ให้การสนับสนุนที่ครอบคลุมสำหรับโครงสร้างโปรเจ็กต์ที่ซับซ้อน ช่วยให้คุณสามารถจัดการงาน ทรัพยากร และองค์ประกอบโปรเจ็กต์อื่น ๆ ได้อย่างง่ายดาย
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/) เพื่อสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ