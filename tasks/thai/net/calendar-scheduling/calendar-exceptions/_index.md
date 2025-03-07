---
title: การจัดการข้อยกเว้นปฏิทินใน Aspose.Tasks
linktitle: การจัดการข้อยกเว้นปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการข้อยกเว้นปฏิทินใน Aspose.Tasks สำหรับ .NET พร้อมบทช่วยสอนและตัวอย่างทีละขั้นตอน
weight: 12
url: /th/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการข้อยกเว้นปฏิทินใน Aspose.Tasks

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการข้อยกเว้นปฏิทินใน Aspose.Tasks โดยใช้เฟรมเวิร์ก .NET ข้อยกเว้นของปฏิทินช่วยให้เราสามารถกำหนดวันที่หรือช่วงเวลาพิเศษในปฏิทินโครงการที่ตารางการทำงานปกติมีการเปลี่ยนแปลง เช่น วันหยุดหรือการปิดทำการชั่วคราว เราจะกล่าวถึงวิธีการต่างๆ ในการจัดการข้อยกเว้นของปฏิทินทีละขั้นตอน โดยใช้ Aspose.Tasks สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
- เพิ่มไลบรารี Aspose.Tasks สำหรับ .NET ในโครงการของคุณ

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นสำหรับโครงการของเรา:

```csharp
using Aspose.Tasks;
using System;


```

## ขั้นตอนที่ 1: การลบข้อยกเว้นปฏิทิน

เมื่อต้องการลบข้อยกเว้นปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // แสดงข้อมูลปฏิทิน
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // ลบข้อยกเว้นแรกออก
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## ขั้นตอนที่ 2: รับเวลาทำงานของข้อยกเว้นปฏิทิน

เมื่อต้องการดึงข้อมูลเวลาทำงานของข้อยกเว้นปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // แสดงปฏิทินและข้อมูลข้อยกเว้น
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // รับเวลาทำงานและแสดงรายละเอียด
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## ขั้นตอนที่ 3: การกำหนดข้อยกเว้นของปฏิทิน

เมื่อต้องการเพิ่มหรือลบข้อยกเว้นปฏิทิน ให้ทำตามขั้นตอนเหล่านี้:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // สร้างข้อยกเว้นปฏิทินใหม่
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // กำหนดรายละเอียดข้อยกเว้น
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // ตรวจสอบว่าวันที่เป็นข้อยกเว้นหรือไม่
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // เพิ่มข้อยกเว้นลงในปฏิทิน
    calendar.Exceptions.Add(exception);

    // ลบข้อยกเว้นหากมีอยู่
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // เพิ่มข้อยกเว้นใหม่
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // พิมพ์ข้อยกเว้น
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## บทสรุป

ในบทความนี้ เราได้กล่าวถึงแง่มุมต่างๆ ของการจัดการข้อยกเว้นของปฏิทินใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถจัดการข้อยกเว้นในกำหนดการโครงการของคุณได้อย่างมีประสิทธิภาพ รับรองว่าจะแสดงชั่วโมงทำงานและกิจกรรมพิเศษได้อย่างแม่นยำ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเพิ่มข้อยกเว้นหลายรายการลงในปฏิทินเดียวได้หรือไม่

A1: ได้ คุณสามารถเพิ่มข้อยกเว้นได้หลายรายการในปฏิทินเพื่อรองรับวันหรือช่วงเวลาพิเศษต่างๆ

### คำถามที่ 2: ฉันจะตรวจสอบได้อย่างไรว่าวันที่ที่ระบุเป็นข้อยกเว้นหรือไม่

 A2: คุณสามารถใช้`CheckException()` วิธีการตรวจสอบว่าวันที่ใดตกอยู่ภายใต้ข้อยกเว้น

### คำถามที่ 3: เป็นไปได้ไหมที่จะลบข้อยกเว้นที่มีอยู่ออกจากปฏิทิน

 A3: ได้ คุณสามารถลบข้อยกเว้นได้โดยเข้าไปที่`Exceptions` การรวบรวมปฏิทินและการใช้`Remove()` วิธี.

### คำถามที่ 4: รองรับข้อยกเว้นปฏิทินประเภทใดบ้าง

A4: Aspose.Tasks รองรับข้อยกเว้นหลายประเภท รวมถึงข้อยกเว้นรายวัน รายสัปดาห์ รายเดือน และรายปี ซึ่งให้ความยืดหยุ่นในการกำหนดกฎข้อยกเว้น

### คำถามที่ 5: ฉันสามารถปรับแต่งเวลาทำงานสำหรับวันยกเว้นที่เฉพาะเจาะจงได้หรือไม่

A5: ได้ คุณสามารถกำหนดเวลาทำงานที่กำหนดเองสำหรับวันที่ยกเว้นแต่ละรายการได้โดยใช้วิธีการที่เหมาะสมที่ Aspose.Tasks มอบให้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
