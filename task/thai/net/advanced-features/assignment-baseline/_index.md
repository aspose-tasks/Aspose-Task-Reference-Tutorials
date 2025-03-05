---
title: การจัดการพื้นฐานการมอบหมายงานใน Aspose.Tasks
linktitle: การจัดการพื้นฐานการมอบหมายงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการพื้นฐานการมอบหมายอย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ .NET ช่วยให้มั่นใจในการติดตามความคืบหน้าและประสิทธิภาพของโครงการอย่างแม่นยำ
type: docs
weight: 14
url: /th/net/advanced-features/assignment-baseline/
---
## การแนะนำ

เมื่อทำงานด้านการจัดการโครงการ การจัดการพื้นฐานการมอบหมายเป็นสิ่งสำคัญสำหรับการติดตามความคืบหน้าอย่างถูกต้อง Aspose.Tasks สำหรับ .NET มีชุดเครื่องมือที่ครอบคลุมเพื่อจัดการพื้นฐานการมอบหมายงานอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการจัดการพื้นฐานการมอบหมายงานทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
- เพิ่มไลบรารี Aspose.Tasks สำหรับ .NET ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
- เข้าถึงไฟล์โครงการในรูปแบบ MPP

## นำเข้าเนมสเปซ

หากต้องการเริ่มทำงานกับ Aspose.Tasks คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์ C# ของคุณ:

```csharp
using Aspose.Tasks;
using System;


```

## ขั้นตอนที่ 1: โหลดโปรเจ็กต์และตั้งค่าพื้นฐาน

 ขั้นแรก ให้โหลดไฟล์โปรเจ็กต์โดยใช้นามสกุล`Project` คลาสจาก Aspose.Tasks จากนั้น ตั้งค่าประเภทพื้นฐานสำหรับโครงการโดยใช้`SetBaseline` วิธี.

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## ขั้นตอนที่ 2: อ่านข้อมูลพื้นฐานของการมอบหมาย

วนซ้ำการมอบหมายทรัพยากรแต่ละรายการในโครงการและดึงข้อมูลพื้นฐานสำหรับการมอบหมายแต่ละครั้ง

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## ขั้นตอนที่ 3: ตรวจสอบความเท่าเทียมกันพื้นฐาน

เปรียบเทียบข้อมูลพื้นฐานสำหรับงานที่ได้รับมอบหมายต่างๆ โดยใช้วิธีเปรียบเทียบต่างๆ ที่ Aspose.Tasks มอบให้

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// ตรวจสอบความเท่าเทียมกันพื้นฐาน
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// ตรวจสอบการเปรียบเทียบพื้นฐาน
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// แสดงรหัสแฮชพื้นฐาน
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## บทสรุป

การจัดการพื้นฐานการมอบหมายงานเป็นส่วนสำคัญในการจัดการโครงการ ช่วยให้สามารถติดตามความคืบหน้าและประสิทธิภาพได้อย่างแม่นยำ ด้วย Aspose.Tasks สำหรับ .NET การจัดการพื้นฐานการมอบหมายงานจะมีความคล่องตัวและมีประสิทธิภาพ ช่วยให้นักพัฒนามีเครื่องมืออันทรงพลังเพื่อปรับปรุงเวิร์กโฟลว์การจัดการโครงการ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สามารถจัดการหลายบรรทัดฐานสำหรับการมอบหมายงานเดียวได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks รองรับเส้นพื้นฐานหลายรายการสำหรับการมอบหมายงานแต่ละครั้ง ช่วยให้สามารถติดตามความคืบหน้าของโครงการในช่วงเวลาหนึ่งได้อย่างครอบคลุม

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับรูปแบบไฟล์โปรเจ็กต์ต่างๆ นอกเหนือจาก MPP หรือไม่

ตอบ 2: ใช่ Aspose.Tasks รองรับรูปแบบไฟล์โปรเจ็กต์ที่หลากหลาย รวมถึง XML, MPX และ MPP เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับเครื่องมือการจัดการโปรเจ็กต์ต่างๆ

### คำถามที่ 3: ฉันสามารถแก้ไขข้อมูลพื้นฐานโดยใช้โปรแกรม Aspose.Tasks ได้หรือไม่

ตอบ 3: แน่นอนว่า Aspose.Tasks มี API ที่ครอบคลุมเพื่อปรับเปลี่ยนข้อมูลพื้นฐานแบบไดนามิกตามความต้องการของโครงการ โดยให้ความยืดหยุ่นและการควบคุมกระบวนการจัดการโครงการ

### คำถามที่ 4: Aspose.Tasks มีเอกสารและทรัพยากรสนับสนุนสำหรับนักพัฒนาหรือไม่

ตอบ 4: ได้ นักพัฒนาสามารถเข้าถึงเอกสารประกอบ บทช่วยสอน และฟอรัมที่ครอบคลุมบนเว็บไซต์ Aspose.Tasks ซึ่งช่วยให้การบูรณาการและการแก้ไขปัญหาเป็นไปอย่างราบรื่น

### คำถามที่ 5: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 A5: ได้ นักพัฒนาสามารถรับ Aspose.Tasks สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/)ช่วยให้พวกเขาสามารถประเมินคุณสมบัติและความสามารถก่อนตัดสินใจซื้อ