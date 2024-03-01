---
title: แยกข้อมูลงานที่เกิดซ้ำใน Aspose.Tasks
linktitle: แยกข้อมูลงานที่เกิดซ้ำใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีแยกข้อมูลงานที่เกิดซ้ำจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET บูรณาการอย่างง่ายดายสำหรับนักพัฒนา .NET
type: docs
weight: 13
url: /th/net/rate-recurring-tasks/recurring-task-information/
---
## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน .NET ของตนได้ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการดึงข้อมูลงานที่เกิดซ้ำจากไฟล์ MS Project โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
2. ติดตั้ง Visual Studio บนระบบของคุณแล้ว
3.  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไฟล์โครงการ
```csharp
String DataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 บรรทัดนี้เริ่มต้นใหม่`Project` วัตถุโดยการโหลดไฟล์ MS Project ที่ระบุโดยเส้นทาง
## ขั้นตอนที่ 3: อ่านข้อมูลงานที่เกิดซ้ำ
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // เข้าถึงและแสดงข้อมูลงานที่เกิดซ้ำ
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // แสดงข้อมูลงานที่เกิดซ้ำอื่นๆ ต่อไปตามความจำเป็น
}
```
ลูปนี้จะวนซ้ำงานทั้งหมดในโปรเจ็กต์และตรวจสอบว่าแต่ละงานมีข้อมูลที่เกี่ยวข้องกันเป็นประจำหรือไม่ หากเป็นเช่นนั้น ระบบจะดึงข้อมูลและแสดงคุณสมบัติต่างๆ ของงานที่เกิดซ้ำ เช่น วันที่เริ่มต้น ระยะเวลา วันที่สิ้นสุด เป็นต้น
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแยกข้อมูลงานที่เกิดซ้ำจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยความรู้นี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณเพื่อทำงานกับงานที่เกิดซ้ำได้อย่างมีประสิทธิภาพมากขึ้น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถแก้ไขข้อมูลงานที่เกิดซ้ำโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: ได้ คุณสามารถแก้ไขข้อมูลงานที่เกิดซ้ำได้โดยทางโปรแกรมโดยใช้ API ที่ให้มา
### ถาม: Aspose.Tasks รองรับไฟล์โปรเจ็กต์รูปแบบอื่นนอกเหนือจาก MS Project หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ เช่น MPP, XML และ CSV
### ถาม: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/net/).
### ถาม: ฉันจะได้รับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถรับการสนับสนุนทางเทคนิคได้จากฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).