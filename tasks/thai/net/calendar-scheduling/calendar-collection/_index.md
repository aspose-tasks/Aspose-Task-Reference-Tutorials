---
title: การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks
linktitle: การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคอลเลกชันปฏิทินใน Aspose.Tasks สำหรับ .NET อย่างมีประสิทธิภาพ สร้าง แก้ไข และจัดการปฏิทินได้อย่างง่ายดาย
weight: 11
url: /th/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคอลเลกชันปฏิทินใน Aspose.Tasks สำหรับ .NET ปฏิทินมีบทบาทสำคัญในการจัดการโครงการ การกำหนดวันทำงาน วันหยุด และข้อยกเว้น Aspose.Tasks มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการจัดการปฏิทินภายในโปรเจ็กต์ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้สำหรับการพัฒนา .NET
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## การสร้างปฏิทินใหม่

###  ขั้นตอนที่ 1: เริ่มต้นใหม่`Project` object.
```csharp
var project = new Project();
```

### ขั้นตอนที่ 2: เพิ่มปฏิทินในคอลเลกชันปฏิทินของโครงการ
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### ขั้นตอนที่ 3: วนซ้ำปฏิทินและแสดงชื่อ
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## การแทนที่ปฏิทินด้วยปฏิทินใหม่

### ขั้นตอนที่ 1: โหลดโครงการที่มีอยู่
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ลบปฏิทินที่มีอยู่ (ถ้ามี)
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### ขั้นตอนที่ 3: เพิ่มปฏิทินใหม่
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## รับปฏิทินตามชื่อหรือ ID

### ขั้นตอนที่ 1: โหลดโครงการ
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ดึงข้อมูลปฏิทินตามชื่อหรือ UID
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### ขั้นตอนที่ 3: แสดงรายละเอียดปฏิทิน
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## วนซ้ำปฏิทิน

### ขั้นตอนที่ 1: โหลดโครงการ
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ดึงข้อมูลจำนวนปฏิทิน
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### ขั้นตอนที่ 3: วนซ้ำคอลเลกชันปฏิทินและชื่อที่แสดง
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## การทำปฏิทินมาตรฐาน

### ขั้นตอนที่ 1: เริ่มต้นโครงการใหม่
```csharp
var project = new Project();
```

### ขั้นตอนที่ 2: กำหนดปฏิทินใหม่และทำให้เป็นมาตรฐาน
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### ขั้นตอนที่ 3: บันทึกโครงการ
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## บทสรุป

การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks สำหรับ .NET ถือเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ ด้วยฟังก์ชันการทำงานที่มีให้ คุณสามารถสร้าง แก้ไข และจัดการปฏิทินตามความต้องการของโครงการได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถสร้างวันทำงานแบบกำหนดเองใน Aspose.Tasks ได้หรือไม่

A1: ได้ คุณสามารถสร้างวันทำงานแบบกำหนดเองได้โดยการเพิ่มข้อยกเว้นลงในปฏิทิน

### คำถามที่ 2: เป็นไปได้ไหมที่จะนำเข้าปฏิทินจากไฟล์ Microsoft Project

คำตอบ 2: แน่นอนว่า Aspose.Tasks รองรับการนำเข้าปฏิทินจากไฟล์ Microsoft Project

### คำถามที่ 3: ฉันจะลบปฏิทินเฉพาะออกจากโครงการได้อย่างไร

 A3: คุณสามารถเอาปฏิทินออกได้ โดยรับปฏิทินจากคอลเลกชันแล้วโทรไปที่`Remove` วิธี.

### คำถามที่ 4: Aspose.Tasks รองรับการส่งออกปฏิทินเป็นรูปแบบต่างๆ หรือไม่

A4: ใช่ Aspose.Tasks อนุญาตให้ส่งออกปฏิทินเป็นรูปแบบต่างๆ เช่น XML, MPP เป็นต้น

### คำถามที่ 5: ฉันสามารถปรับแต่งเวลาทำงานสำหรับวันที่ระบุในปฏิทินได้หรือไม่

A5: แน่นอน คุณสามารถกำหนดเวลาทำงานสำหรับแต่ละวันได้โดยใช้ข้อยกเว้นในปฏิทิน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
