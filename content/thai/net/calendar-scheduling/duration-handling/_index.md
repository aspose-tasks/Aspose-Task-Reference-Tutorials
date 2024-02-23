---
title: การจัดการระยะเวลาใน Aspose.Tasks
linktitle: การจัดการระยะเวลาใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการระยะเวลาอย่างมีประสิทธิภาพใน Aspose.Tasks for .NET พร้อมบทช่วยสอนทีละขั้นตอน
type: docs
weight: 30
url: /th/net/calendar-scheduling/duration-handling/
---
## การแนะนำ

การจัดการระยะเวลาอย่างมีประสิทธิภาพเป็นสิ่งสำคัญในแอปพลิเคชันการจัดการโครงการ Aspose.Tasks สำหรับ .NET มอบฟังก์ชันการทำงานที่แข็งแกร่งสำหรับการจัดการระยะเวลาอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจแง่มุมต่างๆ ของการจัดการระยะเวลาโดยใช้ Aspose.Tasks สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งสำคัญในการทำความเข้าใจและนำตัวอย่างไปใช้
2. Visual Studio: ติดตั้ง Visual Studio IDE เพื่อสร้างและเรียกใช้แอปพลิเคชัน .NET
3.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน:

## การอัปเดตระยะเวลาของงาน

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ขั้นตอนที่ 2: รับงานและระยะเวลา

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### ขั้นตอนที่ 3: อัปเดตระยะเวลา

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### ขั้นตอนที่ 4: แสดงระยะเวลาที่อัปเดต

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## การลบระยะเวลาของงาน

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ขั้นตอนที่ 2: รับงานและระยะเวลา

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### ขั้นตอนที่ 3: ลบระยะเวลา

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### ขั้นตอนที่ 4: แสดงระยะเวลาที่อัปเดต

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## การแปลงระยะเวลาเป็น TimeSpan

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ขั้นตอนที่ 2: รับงานและระยะเวลา

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### ขั้นตอนที่ 3: แปลงระยะเวลาเป็น TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## การแปลงระยะเวลาเป็นสตริง

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### ขั้นตอนที่ 2: รับงานและระยะเวลา

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### ขั้นตอนที่ 3: แปลงระยะเวลาเป็นสตริง

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงแง่มุมต่างๆ ของการจัดการระยะเวลาใน Aspose.Tasks สำหรับ .NET การทำความเข้าใจและการจัดการระยะเวลาอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่ประสบความสำเร็จ Aspose.Tasks มีฟังก์ชันการทำงานที่ครอบคลุมเพื่อลดความซับซ้อนของงานการจัดการระยะเวลาในแอปพลิเคชัน .NET ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET คืออะไร

คำตอบ 1: Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน .NET

### คำถามที่ 2: Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่

ตอบ 2: ได้ Aspose.Tasks สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้อย่างง่ายดาย โดยมี API มากมายสำหรับการจัดการ

### คำถามที่ 3: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่

ตอบ 3: ใช่ Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core ซึ่งทำให้คุณสามารถใช้ในแอปพลิเคชันข้ามแพลตฟอร์มได้

### คำถามที่ 4: Aspose.Tasks รองรับการอ่านและเขียนไฟล์ Microsoft Project หรือไม่

A4: ใช่ Aspose.Tasks รองรับการอ่านและเขียนไฟล์ Microsoft Project ในรูปแบบต่าง ๆ รวมถึง MPP, XML และ MPX

### คำถามที่ 5: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 A5: ได้ คุณสามารถทดลองใช้ Aspose.Tasks สำหรับ .NET ได้ฟรีจาก[ที่นี่](https://releases.aspose.com/).