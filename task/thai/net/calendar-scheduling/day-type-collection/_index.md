---
title: การจัดการคอลเลกชันประเภทวันใน Aspose.Tasks
linktitle: การจัดการคอลเลกชันประเภทวันใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคอลเลกชันประเภทวันอย่างมีประสิทธิภาพใน Aspose.Tasks for .NET สร้าง แก้ไข และจัดการข้อยกเว้นของปฏิทินได้อย่างง่ายดาย
type: docs
weight: 28
url: /th/net/calendar-scheduling/day-type-collection/
---
## การแนะนำ

 Aspose.Tasks for .NET มอบฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการจัดการคอลเลกชันประเภทวัน ซึ่งมีความสำคัญอย่างยิ่งต่อการกำหนดข้อยกเว้นปฏิทินรายสัปดาห์ในแอปพลิเคชันการจัดการโครงการ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้`DayTypeCollection` ชั้นเรียนอย่างมีประสิทธิภาพ 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำเนินการสอนต่อ โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และแนวคิดกรอบงาน .NET

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ:

```csharp
using Aspose.Tasks;
using System;


```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลดโครงการและเข้าถึงปฏิทิน

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

ขั้นตอนนี้จะเริ่มต้นอินสแตนซ์โครงการใหม่และดึงข้อมูลปฏิทินตาม UID

## ขั้นตอนที่ 2: ทำซ้ำผ่านข้อยกเว้นของปฏิทิน

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

ที่นี่ เราจะวนซ้ำข้อยกเว้นของปฏิทินแต่ละรายการ และพิมพ์ชื่อและประเภทวันที่เกี่ยวข้อง

## ขั้นตอนที่ 3: แก้ไขข้อยกเว้นของปฏิทิน

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

ขั้นตอนนี้สาธิตวิธีการแก้ไขข้อยกเว้นของปฏิทินโดยการเพิ่ม ลบ หรืออัปเดตประเภทวัน

## ขั้นตอนที่ 4: สร้างและจัดการข้อยกเว้นปฏิทินใหม่

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

ในขั้นตอนสุดท้ายนี้ เราสร้างข้อยกเว้นปฏิทินใหม่และจัดการโดยการเพิ่มและคัดลอกประเภทวัน

## บทสรุป

 โดยสรุป การจัดการคอลเลกชันประเภทวันใน Aspose.Tasks สำหรับ .NET เป็นสิ่งจำเป็นสำหรับการกำหนดและแก้ไขข้อยกเว้นปฏิทินรายสัปดาห์ในแอปพลิเคชันการจัดการโครงการ โดยการปฏิบัติตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถใช้ประโยชน์จาก`DayTypeCollection` คลาสสำหรับจัดการการดำเนินการปฏิทินต่างๆ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET สามารถใช้เพื่อสร้างแผนภูมิ Gantt โดยทางโปรแกรมได้หรือไม่

A1: ใช่ Aspose.Tasks สำหรับ .NET มี API เพื่อสร้างและจัดการแผนภูมิแกนต์ในแอปพลิเคชัน .NET

### คำถามที่ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับทั้ง .NET Core และ .NET Framework หรือไม่

A2: ใช่ Aspose.Tasks สำหรับ .NET รองรับทั้ง .NET Core และ .NET Framework

### คำถามที่ 3: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร

 A3: คุณสามารถรับการสนับสนุนได้โดยไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) ที่ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้รายอื่นได้

### คำถามที่ 4: Aspose.Tasks สำหรับ .NET ให้ทดลองใช้ฟรีหรือไม่

 A4: ได้ คุณสามารถทดลองใช้ Aspose.Tasks สำหรับ .NET ได้ฟรีจาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้หรือไม่

 A5: ใช่ ใบอนุญาตชั่วคราวสามารถซื้อได้จาก[เว็บไซต์กำหนด](https://purchase.aspose.com/temporary-license/).