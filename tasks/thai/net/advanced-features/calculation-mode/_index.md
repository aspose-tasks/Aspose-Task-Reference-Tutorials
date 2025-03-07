---
title: โหมดการคำนวณใน Aspose.Tasks
linktitle: โหมดการคำนวณใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการโหมดการคำนวณอย่างมีประสิทธิภาพใน Aspose.Tasks สำหรับ .NET เพื่อปรับปรุงการจัดกำหนดการโครงการและการพึ่งพางาน
weight: 29
url: /th/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# โหมดการคำนวณใน Aspose.Tasks

## การแนะนำ

Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรมในแอปพลิเคชัน .NET ของตน สิ่งสำคัญอย่างหนึ่งในการทำงานกับไฟล์โครงการคือการจัดการโหมดการคำนวณ ซึ่งกำหนดวิธีการคำนวณและอัปเดตงานและกำหนดการของโครงการ ในบทช่วยสอนนี้ เราจะเจาะลึกโหมดการคำนวณต่างๆ ที่ Aspose.Tasks สำหรับ .NET รองรับ และสาธิตวิธีการใช้งานอย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#: ทำความคุ้นเคยกับแนวคิดการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ก่อนที่เราจะเริ่มทำงานกับ Aspose.Tasks สำหรับ .NET เรามานำเข้าเนมสเปซที่จำเป็นก่อน:

```csharp
using Aspose.Tasks;
using System;


```

## การใช้โหมดการคำนวณอัตโนมัติ

### ขั้นตอนที่ 1: สร้างอินสแตนซ์โครงการใหม่

 เริ่มต้นใหม่`Project` วัตถุและตั้งค่า`CalculationMode` ทรัพย์สินเพื่อ`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### ขั้นตอนที่ 2: กำหนดวันที่เริ่มต้นโครงการและเพิ่มงาน

กำหนดวันที่เริ่มต้นของโครงการและเพิ่มงานลงไป

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### ขั้นตอนที่ 3: เชื่อมโยงงาน

สร้างการพึ่งพาระหว่างงาน

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### ขั้นตอนที่ 4: ตรวจสอบวันที่ที่คำนวณใหม่

ตรวจสอบว่าวันที่ได้รับการคำนวณใหม่โดยอัตโนมัติหรือไม่

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// เพิ่มการยืนยันเพิ่มเติมตามความจำเป็น
```

## การใช้โหมดการคำนวณด้วยตนเอง

### ขั้นตอนที่ 1: สร้างอินสแตนซ์โครงการใหม่

 เริ่มต้นใหม่`Project` วัตถุและตั้งค่า`CalculationMode` ทรัพย์สินเพื่อ`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### ขั้นตอนที่ 2: กำหนดวันที่เริ่มต้นโครงการและเพิ่มงาน

กำหนดวันที่เริ่มต้นของโครงการและเพิ่มงานลงไป

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### ขั้นตอนที่ 3: ตรวจสอบคุณสมบัติของงาน

ตรวจสอบว่าคุณสมบัติงานได้รับการตั้งค่าอย่างถูกต้องในโหมดแมนนวลหรือไม่

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// เพิ่มการยืนยันเพิ่มเติมตามความจำเป็น
```

### ขั้นตอนที่ 4: เชื่อมโยงงานและตรวจสอบวันที่

เชื่อมโยงงานเข้าด้วยกันและตรวจสอบว่าไม่มีการคำนวณวันที่ใหม่หรือไม่

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## การใช้โหมดการคำนวณไม่มี

### ขั้นตอนที่ 1: สร้างอินสแตนซ์โครงการใหม่

 เริ่มต้นใหม่`Project` วัตถุและตั้งค่า`CalculationMode` ทรัพย์สินเพื่อ`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### ขั้นตอนที่ 2: เพิ่มงานใหม่

เพิ่มงานใหม่ให้กับโครงการ

```csharp
var task = project.RootTask.Children.Add("Task");
```

### ขั้นตอนที่ 3: ตรวจสอบคุณสมบัติของงาน

ตรวจสอบว่าคุณสมบัติของงานไม่ได้ถูกคำนวณโดยอัตโนมัติหรือไม่

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// เพิ่มการยืนยันเพิ่มเติมตามความจำเป็น
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจโหมดการคำนวณที่มีอยู่ใน Aspose.Tasks สำหรับ .NET และเรียนรู้วิธีนำไปใช้ในสถานการณ์จริง ไม่ว่าคุณจะต้องการโหมดการคำนวณแบบอัตโนมัติ แบบแมนนวล หรือแบบไม่ใช้เลย Aspose.Tasks มอบความยืดหยุ่นให้เหมาะกับความต้องการของโปรเจ็กต์ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเปลี่ยนโหมดการคำนวณแบบไดนามิกระหว่างรันไทม์ได้หรือไม่

A1: ได้ คุณสามารถเปลี่ยนโหมดการคำนวณของโครงการได้ตลอดเวลาระหว่างรันไทม์โดยการแก้ไข`CalculationMode` คุณสมบัติ.

### คำถามที่ 2: Aspose.Tasks รองรับรูปแบบไฟล์การจัดการโครงการอื่นๆ นอกเหนือจาก Microsoft Project หรือไม่

คำตอบ 2: Aspose.Tasks มุ่งเน้นไปที่รูปแบบไฟล์ Microsoft Project เป็นหลัก แต่ยังรองรับรูปแบบอื่นๆ เช่น Primavera P6 XML, Primavera DB และ Asta Powerproject XML อีกด้วย

### คำถามที่ 3: Aspose.Tasks เหมาะสำหรับทั้งโครงการขนาดเล็กและระดับองค์กรหรือไม่

A3: แน่นอน! Aspose.Tasks ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของทั้งโปรเจ็กต์ขนาดเล็กและระดับองค์กรด้วยฟีเจอร์ที่ครอบคลุมและ API ที่แข็งแกร่ง

### คำถามที่ 4: ฉันสามารถรวม Aspose.Tasks เข้ากับไลบรารีและเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่

ตอบ 4: ได้ คุณสามารถผสานรวม Aspose.Tasks เข้ากับไลบรารีและเฟรมเวิร์ก .NET อื่นๆ ได้อย่างราบรื่น เพื่อปรับปรุงฟังก์ชันการทำงานของแอปพลิเคชันของคุณ

### คำถามที่ 5: มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับผู้ใช้ Aspose.Tasks หรือไม่

 A5: ใช่ คุณสามารถเยี่ยมชมได้[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
