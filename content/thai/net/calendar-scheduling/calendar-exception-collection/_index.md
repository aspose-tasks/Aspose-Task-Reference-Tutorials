---
title: การรวบรวมข้อยกเว้นของปฏิทินใน Aspose.Tasks
linktitle: การรวบรวมข้อยกเว้นของปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการข้อยกเว้นปฏิทินในโปรเจ็กต์ .NET ของคุณอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks ช่วยให้มั่นใจได้ถึงการจัดกำหนดการและการจัดการทรัพยากรที่แม่นยำ
type: docs
weight: 13
url: /th/net/calendar-scheduling/calendar-exception-collection/
---
## การแนะนำ

ในการจัดการโครงการ การจัดกำหนดการที่แม่นยำเป็นสิ่งสำคัญต่อความสำเร็จ อย่างไรก็ตาม สถานการณ์ในโลกแห่งความเป็นจริงมักกำหนดให้มีการเบี่ยงเบนไปจากกำหนดการมาตรฐานเนื่องจากวันหยุด กิจกรรมพิเศษ หรือปัจจัยอื่นๆ Aspose.Tasks for .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการข้อยกเว้นดังกล่าวผ่านฟีเจอร์ Calendar Exception Collection บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟังก์ชันนี้ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ในการทำความเข้าใจตัวอย่าง
3. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการ เช่น Visual Studio หรือ JetBrains Rider

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มทำงานกับ Aspose.Tasks สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ขั้นตอนนี้ช่วยให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการจัดการข้อยกเว้นของปฏิทิน

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

ตอนนี้ เรามาแยกย่อยตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลดโปรเจ็กต์และดึงข้อมูลปฏิทิน

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

ในขั้นตอนนี้ เราจะโหลดไฟล์โครงการและดึงข้อมูลปฏิทินที่ต้องการด้วย UID

## ขั้นตอนที่ 2: ล้างข้อยกเว้นที่มีอยู่และตั้งค่าปฏิทินมาตรฐาน

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

ขั้นตอนนี้จะล้างข้อยกเว้นที่มีอยู่จากปฏิทินและตั้งค่าเป็นการกำหนดค่ามาตรฐาน

## ขั้นตอนที่ 3: กำหนดและเพิ่มข้อยกเว้นเวลาทำงาน

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

ขั้นตอนนี้กำหนดข้อยกเว้นเวลาทำงานพร้อมวันที่เริ่มต้นและสิ้นสุดที่ระบุ พร้อมด้วยเวลาทำงานภายในวันที่เหล่านั้น และเพิ่มลงในปฏิทิน

## ขั้นตอนที่ 4: กำหนดและเพิ่มข้อยกเว้นเวลาที่ไม่ทำงาน

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// เพิ่มข้อยกเว้นเพิ่มเติมหากจำเป็น

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

ขั้นตอนนี้กำหนดข้อยกเว้นเวลาที่ไม่ทำงาน เช่น วันหยุด และเพิ่มลงในปฏิทิน

## ขั้นตอนที่ 5: แสดงข้อยกเว้นของปฏิทิน

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

ขั้นตอนนี้จะแสดงข้อยกเว้นของปฏิทินที่เพิ่มเข้ามาพร้อมกับรายละเอียด

## ขั้นตอนที่ 6: ลบข้อยกเว้นทั้งหมด

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

สุดท้าย ขั้นตอนนี้จะลบข้อยกเว้นทั้งหมดออกจากปฏิทิน

## บทสรุป

การจัดการข้อยกเว้นของปฏิทินถือเป็นสิ่งสำคัญสำหรับการจัดกำหนดการโครงการที่แม่นยำ Aspose.Tasks สำหรับ .NET ช่วยให้งานนี้ง่ายขึ้นโดยจัดเตรียมชุดคุณลักษณะที่ครอบคลุม รวมถึง Calendar Exception Collection ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการสถานการณ์การจัดกำหนดการต่างๆ ภายในโครงการของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเพิ่มข้อยกเว้นหลายรายการลงในปฏิทินเดียวได้หรือไม่

 A1: ได้ คุณสามารถเพิ่มข้อยกเว้นหลายรายการลงในปฏิทินได้โดยใช้`AddRange` วิธี.

### คำถามที่ 2: ฉันจะจัดการกับข้อยกเว้นที่เกิดซ้ำ เช่น วันหยุดประจำสัปดาห์ได้อย่างไร

A2: คุณสามารถคำนวณข้อยกเว้นที่เกิดซ้ำโดยทางโปรแกรมและเพิ่มลงในปฏิทินโดยใช้ตรรกะที่กำหนดเองได้

### คำถามที่ 3: สามารถนำเข้าข้อยกเว้นปฏิทินจากแหล่งภายนอกได้หรือไม่

A3: ได้ คุณสามารถอ่านข้อยกเว้นของปฏิทินจากแหล่งภายนอก เช่น ฐานข้อมูลหรือไฟล์ CSV และรวมเข้ากับโครงการของคุณได้

### Q4: จะเกิดอะไรขึ้นถ้ามีข้อยกเว้นที่ทับซ้อนกันในปฏิทิน

A4: Aspose.Tasks สำหรับ .NET ช่วยให้คุณสามารถจัดการกับข้อยกเว้นที่ทับซ้อนกันโดยการกำหนดลำดับความสำคัญหรือแก้ไขข้อขัดแย้งตามความต้องการของโครงการของคุณ

### คำถามที่ 5: ฉันสามารถกำหนดเวลาทำงานในแต่ละวันภายในข้อยกเว้นได้หรือไม่

A5: ได้ คุณสามารถระบุเวลาทำงานที่กำหนดเองสำหรับแต่ละวันได้ โดยมีข้อยกเว้นเพื่อรองรับความต้องการในการจัดกำหนดการที่เฉพาะเจาะจง