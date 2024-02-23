---
title: การทำงานกับ Assignment ใน Aspose.Tasks
linktitle: การทำงานกับ Assignment ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการการมอบหมายโครงการใน .NET โดยใช้ Aspose.Tasks สำรวจรูปทรงต่างๆ สำหรับการจัดกำหนดการทรัพยากร
type: docs
weight: 13
url: /th/net/advanced-features/working-with-assignment/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับการมอบหมายงานใน Aspose.Tasks for .NET การมอบหมายงานมีความสำคัญอย่างยิ่งในการจัดการโครงการ เนื่องจากเป็นการจัดสรรทรัพยากรให้กับงาน ช่วยในการจัดกำหนดการและติดตามความคืบหน้า เราจะมุ่งเน้นไปที่การสร้างข้อมูลตามระยะเวลาที่กำหนดทรัพยากรด้วยรูปทรงต่างๆ โดยใช้ Aspose.Tasks

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1.  การติดตั้ง Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).
2. ความเข้าใจพื้นฐานเกี่ยวกับ C# และ .NET Framework: จำเป็นต้องปฏิบัติตามความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และแนวคิดกรอบงาน .NET

## นำเข้าเนมสเปซ

ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของคุณ:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## ขั้นตอนที่ 1: สร้างโครงการและงาน

เริ่มต้นด้วยการสร้างโปรเจ็กต์ใหม่และเพิ่มงานลงไป กำหนดวันที่เริ่มต้น ระยะเวลา และวันที่สิ้นสุดสำหรับงาน:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## ขั้นตอนที่ 2: เพิ่มทรัพยากรและมอบหมายให้กับงาน

ถัดไป เพิ่มทรัพยากรให้กับโปรเจ็กต์และมอบหมายให้กับงานที่สร้างไว้ก่อนหน้านี้:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## ขั้นตอนที่ 3: สร้างข้อมูลตามช่วงเวลาด้วยรูปทรงที่แตกต่างกัน

ตอนนี้ เรามาสร้างข้อมูลตามช่วงเวลาที่มีรูปทรงที่แตกต่างกันสำหรับการกำหนดทรัพยากรกัน:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## ขั้นตอนที่ 4: เปลี่ยนรูปทรงและสร้างข้อมูล

เราสามารถเปลี่ยนประเภทรูปร่างและสร้างข้อมูลตามช่วงเวลาได้ นี่คือตัวอย่างบางส่วน:

```csharp
// เปลี่ยนรูปร่าง
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// สร้างข้อมูลตามช่วงเวลาและพิมพ์
// ทำซ้ำขั้นตอนนี้กับคอนทัวร์ประเภทอื่น
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับการมอบหมายงานใน Aspose.Tasks สำหรับ .NET เราสำรวจการสร้างข้อมูลตามระยะเวลาของการมอบหมายทรัพยากรด้วยรูปทรงต่างๆ ความรู้นี้สามารถมีประโยชน์อย่างมากในสถานการณ์การจัดการโครงการ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks เพื่อกำหนดเวลางานในแอปพลิเคชัน .NET ของฉันได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks มี API ที่ครอบคลุมสำหรับการกำหนดเวลางานและการจัดการในแอปพลิเคชัน .NET

### คำถามที่ 2: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่

 A2: ได้ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: มีข้อจำกัดเกี่ยวกับจำนวนงานหรือทรัพยากรใน Aspose.Tasks หรือไม่

A3: Aspose.Tasks ไม่มีการจำกัดจำนวนงานหรือทรัพยากรที่คุณสามารถจัดการในโครงการของคุณได้

### คำถามที่ 4: ฉันสามารถปรับแต่งรูปทรงสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks ได้หรือไม่

A4: ได้ ดังที่แสดงในบทช่วยสอนนี้ คุณสามารถตั้งค่ารูปทรงต่างๆ เช่น เต่า กระดิ่ง จุดสูงสุด ฯลฯ ตามความต้องการของโปรเจ็กต์ของคุณ

### คำถามที่ 5: ฉันจะรับการสนับสนุนสำหรับแบบสอบถามที่เกี่ยวข้องกับ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถค้นหาการสนับสนุนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) ที่ซึ่งผู้เชี่ยวชาญและสมาชิกในชุมชนมีส่วนร่วมอย่างแข็งขันในการอภิปราย