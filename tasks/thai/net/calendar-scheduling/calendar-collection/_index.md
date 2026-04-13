---
date: 2026-04-13
description: เรียนรู้วิธีตั้งชั่วโมงทำงานและจัดการคอลเลกชันปฏิทินใน Aspose.Tasks สำหรับ
  .NET นำเข้าปฏิทินจาก Microsoft Project ลบปฏิทินโครงการ และดึงปฏิทินตามชื่อได้อย่างง่ายดาย.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: กำหนดชั่วโมงทำงานในคอลเลกชันปฏิทินของ Aspose.Tasks
url: /th/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าชั่วโมงทำงานในคอลเลกชันปฏิทินของ Aspose.Tasks

ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **ตั้งค่าชั่วโมงทำงาน** และจัดการคอลเลกชันปฏิทินโดยใช้ Aspose.Tasks สำหรับ .NET ปฏิทินกำหนดวันทำงาน, วันหยุด, และข้อยกเว้น ดังนั้นการเชี่ยวชาญจึงทำให้คุณควบคุมกำหนดการของโครงการได้อย่างแม่นยำ เราจะยังแสดงวิธีนำเข้าปฏิทินจาก Microsoft Project, ลบปฏิทินจากโครงการ, และดึงปฏิทินตามชื่อ

## คำตอบอย่างรวดเร็ว
- **คลาสหลักสำหรับปฏิทินคืออะไร?** `Project.Calendars` collection.
- **ฉันจะตั้งค่าชั่วโมงทำงานอย่างไร?** สร้างหรือแก้ไขอ็อบเจ็กต์ `Calendar` และกำหนด `WorkingTime` ของมัน.
- **ฉันสามารถนำเข้าปฏิทินจาก Microsoft Project ได้หรือไม่?** ได้ – โหลดไฟล์ MPP และเข้าถึงปฏิทินของมัน.
- **จะลบปฏิทินจากโครงการอย่างไร?** ใช้ `Project.Calendars.Remove(calendar)`.
- **จะดึงปฏิทินตามชื่ออย่างไร?** เรียก `Project.Calendars.GetByName("YourCalendar")`.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio หรือ IDE ที่เข้ากันได้อื่นสำหรับการพัฒนา .NET.  
2. Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks for .NET จาก [here](https://releases.aspose.com/tasks/net/).  
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาโปรแกรม C# จะเป็นประโยชน์.

## นำเข้า Namespaces

ก่อนอื่น, เรามานำเข้า namespaces ที่จำเป็นสำหรับทำงานกับ Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## การสร้างปฏิทินใหม่

### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจ็กต์ `Project` ใหม่.
```csharp
var project = new Project();
```

### ขั้นตอนที่ 2: เพิ่มปฏิทินลงในคอลเลกชันปฏิทินของโครงการ.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### ขั้นตอนที่ 3: วนลูปผ่านปฏิทินและแสดงชื่อของพวกมัน.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## วิธีตั้งค่าชั่วโมงทำงานสำหรับปฏิทิน?

เพื่อ **ตั้งค่าชั่วโมงทำงาน**, คุณต้องแก้ไขคอลเลกชัน `WorkingTime` ของ `Calendar`.  
เช่น คุณสามารถกำหนดวันทำงานมาตรฐาน 9 am‑5 pm หรือเพิ่มข้อยกเว้นแบบกำหนดเอง.  
โค้ดสำหรับนี้เหมือนกับตัวอย่างที่แสดงต่อไปเมื่อเราสร้างปฏิทินมาตรฐาน.

## การแทนที่ปฏิทินด้วยปฏิทินใหม่

### ขั้นตอนที่ 1: โหลดโครงการที่มีอยู่.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ลบปฏิทินที่มีอยู่ (หากมี).  
นี่เป็นการสาธิตสถานการณ์ **remove calendar project**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### ขั้นตอนที่ 3: เพิ่มปฏิทินใหม่.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## การดึงปฏิทินตามชื่อหรือ ID

### ขั้นตอนที่ 1: โหลดโครงการ.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ดึงปฏิทินตามชื่อหรือ UID.  
นี่เป็นการแสดงการทำงานของ **get calendar by name**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### ขั้นตอนที่ 3: แสดงรายละเอียดของปฏิทิน.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## การวนลูปผ่านปฏิทิน

### ขั้นตอนที่ 1: โหลดโครงการ.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### ขั้นตอนที่ 2: ดึงจำนวนของปฏิทิน.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### ขั้นตอนที่ 3: วนลูปผ่านคอลเลกชันปฏิทินและแสดงชื่อ.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## การสร้างปฏิทินมาตรฐาน

### ขั้นตอนที่ 1: เริ่มต้นโครงการใหม่.
```csharp
var project = new Project();
```

### ขั้นตอนที่ 2: กำหนดปฏิทินใหม่และทำให้เป็นมาตรฐาน.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### ขั้นตอนที่ 3: บันทึกโครงการ.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## ปัญหาทั่วไปและวิธีแก้

- **ไม่พบปฏิทินเมื่อใช้ `GetByName`** – ตรวจสอบให้แน่ใจว่าชื่อที่ใช้ตรงกับตัวพิมพ์ที่ใช้เมื่อตอนเพิ่มปฏิทิน.  
- **ชั่วโมงทำงานไม่ถูกนำไปใช้** – หลังจากตั้งค่า `WorkingTime` จำไว้ว่าให้บันทึกโครงการ; มิฉะนั้นการเปลี่ยนแปลงจะอยู่ในหน่วยความจำเท่านั้น.  
- **การนำเข้าปฏิทินจากไฟล์ MPP ล้มเหลว** – ตรวจสอบว่าไฟล์ต้นทางเป็นไฟล์ Microsoft Project ที่ถูกต้องและคุณมีสิทธิ์อ่าน.

## คำถามที่พบบ่อย

### Q1: ฉันสามารถสร้างวันทำงานแบบกำหนดเองใน Aspose.Tasks ได้หรือไม่?
A1: ได้, คุณสามารถสร้างวันทำงานแบบกำหนดเองโดยการเพิ่มข้อยกเว้นในปฏิทิน.

### Q2: สามารถนำเข้าปฏิทินจากไฟล์ Microsoft Project ได้หรือไม่?
A2: แน่นอน, Aspose.Tasks รองรับการนำเข้าปฏิทินจากไฟล์ Microsoft Project.

### Q3: ฉันจะลบปฏิทินเฉพาะจากโครงการได้อย่างไร?
A3: คุณสามารถลบปฏิทินโดยดึงมันจากคอลเลกชันแล้วเรียกเมธอด `Remove`.

### Q4: Aspose.Tasks รองรับการส่งออกปฏิทินเป็นรูปแบบต่าง ๆ หรือไม่?
A4: ใช่, Aspose.Tasks อนุญาตให้ส่งออกปฏิทินเป็นรูปแบบต่าง ๆ เช่น XML, MPP, เป็นต้น.

### Q5: ฉันสามารถปรับแต่งชั่วโมงทำงานสำหรับวันเฉพาะในปฏิทินได้หรือไม่?
A5: แน่นอน, คุณสามารถกำหนดชั่วโมงทำงานสำหรับแต่ละวันโดยใช้ข้อยกเว้นในปฏิทิน.

## คำถามที่พบบ่อย

**Q: วิธีที่ดีที่สุดในการตั้งค่าปฏิทินกะ 24 ชั่วโมงคืออะไร?**  
A: สร้างปฏิทินใหม่, ลบรายการ `WorkingTime` ที่มีอยู่, และเพิ่มช่วง `WorkingTime` เดียวจาก 00:00 ถึง 24:00 สำหรับแต่ละวันทำงาน.

**Q: ฉันสามารถคัดลอกปฏิทินจากโครงการหนึ่งไปยังอีกโครงการได้หรือไม่?**  
A: ได้—ส่งออกปฏิทินเป็น XML ด้วย `project.Save` แล้วนำเข้ามาในโครงการอื่นด้วย `new Project(xmlPath)`.

**Q: ฉันจะนำเข้าปฏิทินจาก Microsoft Project อย่างโปรแกรมได้อย่างไร?**  
A: โหลดไฟล์ MPP ด้วย `new Project("source.mpp")`; ปฏิทินจะพร้อมใช้งานผ่าน `project.Calendars`.

**Q: มีขีดจำกัดจำนวนปฏิทินในโครงการหรือไม่?**  
A: โดยปฏิบัติไม่มี; คอลเลกชันสามารถเก็บปฏิทินได้ตามที่หน่วยความจำอนุญาต, แต่ควรจัดการรายการให้เหมาะสมเพื่อประสิทธิภาพ.

**Q: การเปลี่ยนแปลงปฏิทินจะอัปเดตงานที่ใช้มันโดยอัตโนมัติหรือไม่?**  
A: ใช่—งานที่เชื่อมโยงกับปฏิทินจะแสดงเวลาทำงานที่อัปเดตหลังจากคุณบันทึกโครงการ.

---

**อัปเดตล่าสุด:** 2026-04-13  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}