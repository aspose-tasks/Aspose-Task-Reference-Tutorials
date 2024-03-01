---
title: การรวบรวมพื้นฐานการมอบหมายงานใน Aspose.Tasks
linktitle: การรวบรวมพื้นฐานการมอบหมายงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการพื้นฐานการมอบหมายในการจัดการโครงการอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET เพิ่มผลผลิตและความแม่นยำ
type: docs
weight: 15
url: /th/net/advanced-features/assignment-baseline-collection/
---
## การแนะนำ

ในขอบเขตของการจัดการโครงการ การติดตามและการจัดการพื้นฐานการมอบหมายเป็นสิ่งสำคัญเพื่อให้มั่นใจว่าโครงการจะประสบความสำเร็จและเป็นไปตามกำหนดเวลา Aspose.Tasks สำหรับ .NET นำเสนอชุดคุณสมบัติที่แข็งแกร่งเพื่ออำนวยความสะดวกในการจัดการพื้นฐานการมอบหมายงานภายในโครงการอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกความซับซ้อนของการทำงานกับ Assignment Baseline Collections โดยใช้ Aspose.Tasks สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนดำเนินการบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
2. ติดตั้ง Visual Studio บนระบบของคุณแล้ว
3.  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

อันดับแรก เราต้องโหลดไฟล์โปรเจ็กต์ที่มีพื้นฐานการมอบหมายงาน

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## ขั้นตอนที่ 2: อ่านพื้นฐานการมอบหมายงาน

ต่อไป เราจะวนซ้ำการมอบหมายทรัพยากรแต่ละรายการในโปรเจ็กต์เพื่อเข้าถึงข้อมูลพื้นฐานตามลำดับ

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## ขั้นตอนที่ 3: ลบเส้นฐานการมอบหมายงาน

ในขั้นตอนนี้ เราจะสาธิตวิธีการลบเส้นฐานการมอบหมายทั้งหมดออกจากโครงการ

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## บทสรุป

การจัดการพื้นฐานการมอบหมายงานอย่างมีประสิทธิภาพเป็นสิ่งสำคัญยิ่งในการจัดการโครงการ ทำให้มั่นใจได้ว่าจะปฏิบัติตามกำหนดการและติดตามความคืบหน้าของโครงการได้อย่างแม่นยำ ด้วย Aspose.Tasks สำหรับ .NET การจัดการพื้นฐานการมอบหมายงานจะราบรื่น ช่วยให้นักพัฒนามีเครื่องมือที่จำเป็นในการปรับปรุงกระบวนการจัดการโครงการ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สามารถจัดการพื้นฐานการมอบหมายสำหรับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks รองรับรูปแบบไฟล์โปรเจ็กต์ที่หลากหลาย รวมถึง MPP, XML และ MPX ทำให้คุณจัดการพื้นฐานการมอบหมายงานในไฟล์ประเภทต่างๆ ได้อย่างง่ายดาย

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

คำตอบ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Framework หลายเวอร์ชัน เพื่อให้มั่นใจถึงความเข้ากันได้และความยืดหยุ่นสำหรับนักพัฒนาในสภาพแวดล้อมที่แตกต่างกัน

### คำถามที่ 3: ฉันสามารถจัดการเส้นฐานการมอบหมายโดยทางโปรแกรมโดยใช้ Aspose.Tasks ได้หรือไม่

ตอบ 3: แน่นอนว่า Aspose.Tasks มี API ที่ครอบคลุมซึ่งช่วยให้นักพัฒนาสามารถสร้าง อ่าน อัปเดต และลบเส้นฐานการมอบหมายงานตามข้อกำหนดของโปรเจ็กต์โดยทางโปรแกรม

### คำถามที่ 4: Aspose.Tasks ให้การสนับสนุนด้านเทคนิคสำหรับนักพัฒนาหรือไม่

ตอบ 4: ได้ Aspose.Tasks ให้การสนับสนุนทางเทคนิคที่มีประสิทธิภาพผ่านฟอรัมชุมชน ซึ่งนักพัฒนาสามารถขอความช่วยเหลือ แบ่งปันความรู้ และทำงานร่วมกับเพื่อนร่วมงานได้

### คำถามที่ 5: ฉันสามารถลองใช้ Aspose.Tasks ก่อนตัดสินใจซื้อได้หรือไม่

ตอบ 5: ใช่ Aspose.Tasks มีเวอร์ชันทดลองใช้ฟรี ช่วยให้นักพัฒนาสามารถสำรวจฟีเจอร์และฟังก์ชันต่างๆ ก่อนตัดสินใจซื้อ