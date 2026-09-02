---
date: 2026-04-13
description: เรียนรู้วิธีลบข้อยกเว้นของปฏิทินใน Aspose.Tasks สำหรับ .NET และตรวจสอบวันที่ของข้อยกเว้นขณะจัดการการกำหนดเวลาปฏิทิน
  ASP.NET
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: ลบข้อยกเว้นปฏิทินด้วย Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ลบข้อยกเว้นปฏิทินด้วย Aspose.Tasks
url: /th/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ลบข้อยกเว้นปฏิทินด้วย Aspose.Tasks

## บทนำ

ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **ลบข้อยกเว้นปฏิทิน** และจัดการข้อยกเว้นปฏิทินอื่น ๆ ใน Aspose.Tasks ด้วยการใช้ .NET framework. ข้อยกเว้นปฏิทินช่วยให้คุณจำลองวันหยุด, การปิดชั่วคราว, หรือช่วงเวลาพิเศษใด ๆ ที่ตารางทำงานปกติเปลี่ยนแปลง การเข้าใจวิธีการเพิ่ม, ค้นหา, และลบข้อยกเว้นเหล่านี้เป็นสิ่งสำคัญสำหรับการกำหนดเวลาของโครงการอย่างแม่นยำ, โดยเฉพาะเมื่อทำงานกับสถานการณ์ **การกำหนดเวลาปฏิทิน ASP.NET**.

## คำตอบอย่างรวดเร็ว
- **วิธีหลักในการลบข้อยกเว้นคืออะไร?** ใช้เมธอด `Delete()` ของอ็อบเจกต์ `CalendarException`.  
- **คลาสใดที่ตรวจสอบวันที่กับข้อยกเว้น?** `CalendarException.CheckException()` — มีประโยชน์สำหรับ **ตรวจสอบวันที่ของข้อยกเว้น**.  
- **ต้องการไลเซนส์เพื่อรันโค้ดหรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **สามารถเพิ่มหลายข้อยกเว้นในปฏิทินเดียวได้หรือไม่?** ได้แน่นอน; คอลเลกชัน `Exceptions` รองรับหลายรายการ.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ข้อยกเว้นปฏิทินคืออะไร?

**ข้อยกเว้นปฏิทิน** แสดงถึงการเบี่ยงเบนจากปฏิทินทำงานปกติ — คิดว่าเป็นกฎที่บอกว่า “ในวันที่เหล่านี้ ชั่วโมงทำงานแตกต่างหรือไม่มีเลย”. ใน Aspose.Tasks, แต่ละข้อยกเว้นสามารถมีเวลาทำงานของตนเอง, รูปแบบการเกิดซ้ำ, และแฟล็กที่บ่งบอกว่าวันนั้นเป็นวันทำงานหรือไม่.

## ทำไมต้องจัดการข้อยกเว้นปฏิทินในการกำหนดเวลาปฏิทิน ASP.NET?

- **ไทม์ไลน์ที่แม่นยำ:** โครงการจะเคารพวันหยุดและการปิดพิเศษโดยอัตโนมัติ, ป้องกันกำหนดเวลาที่ไม่เป็นจริง.  
- **ความยืดหยุ่น:** คุณสามารถกำหนดรูปแบบรายวัน, รายสัปดาห์, รายเดือน, หรือรายปี, ตรงกับปฏิทินธุรกิจในโลกจริง.  
- **การอัตโนมัติ:** การตรวจสอบวันที่ของข้อยกเว้นแบบโปรแกรมช่วยให้คุณสร้างตรรกะการกำหนดเวลาที่เปลี่ยนแปลงได้ในแอปพลิเคชัน ASP.NET.

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของการเขียนโปรแกรม C#.  
- Visual Studio (เวอร์ชันล่าสุดใดก็ได้).  
- ไลบรารี Aspose.Tasks for .NET ที่เพิ่มเข้าไปในโปรเจคของคุณ (ผ่าน NuGet หรือการอ้างอิงแบบแมนนวล).

## นำเข้าชื่อเนมสเปซ

ก่อนอื่น, นำเข้าชื่อเนมสเปซที่คุณต้องการใช้:

```csharp
using Aspose.Tasks;
using System;
```

## ขั้นตอนที่ 1: ลบข้อยกเว้นปฏิทิน

การลบข้อยกเว้นที่ไม่ต้องการเป็นเรื่องง่าย. โค้ดต่อไปนี้จะโหลดโปรเจค, เลือกปฏิทินแรก, แสดงข้อมูลพื้นฐาน, ลบข้อยกเว้นแรก, และจากนั้นแสดงจำนวนที่อัปเดต.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **เคล็ดลับ:** ตรวจสอบให้แน่ใจว่าดัชนีของข้อยกเว้นมีอยู่ก่อนเรียก `Delete()` เพื่อหลีกเลี่ยง `IndexOutOfRangeException`.

## ขั้นตอนที่ 2: รับเวลาทำงานของข้อยกเว้นปฏิทิน

หากคุณต้องการตรวจสอบชั่วโมงทำงานที่กำหนดไว้สำหรับข้อยกเว้น, ใช้ `GetWorkingTime()`. ตัวอย่างนี้ยังแสดงวิธี **ตรวจสอบวันที่ของข้อยกเว้น** ด้วย `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## ขั้นตอนที่ 3: กำหนดข้อยกเว้นปฏิทิน

ด้านล่างเป็นขั้นตอนเต็มที่แสดงวิธี **เพิ่ม**, **ตรวจสอบ**, และ **ลบ** ข้อยกเว้นปฏิทิน. สังเกตการใช้ `CheckException` เพื่อ **ตรวจสอบวันที่ของข้อยกเว้น** สำหรับช่วงเวลาที่กำหนด.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## ปัญหาและเคล็ดลับทั่วไป

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **`IndexOutOfRangeException` เมื่อทำการลบ** | พยายามลบข้อยกเว้นที่ไม่มีอยู่. | ตรวจสอบว่า `calendar.Exceptions.Count` > ดัชนีก่อนเรียก `Delete()`. |
| **เวลาทำงานไม่ถูกต้อง** | ไม่ได้ตั้งค่า `DayWorking` หรือ `WorkingTimes` อย่างถูกต้อง. | ใช้ `exception.WorkingTimes.Add(new WorkingTime(...))` เพื่อกำหนดช่วงเวลาที่ชัดเจน. |
| **ข้อยกเว้นไม่ถูกตรวจจับ** | `CheckException` คืนค่า `false` เนื่องจากวันที่อยู่นอกช่วงที่กำหนด. | ตรวจสอบ `FromDate`/`ToDate` และ `Type` (Daily, Weekly, ฯลฯ) อีกครั้ง. |

## คำถามที่พบบ่อย

**Q:** ฉันสามารถเพิ่มหลายข้อยกเว้นในปฏิทินเดียวได้หรือไม่?  
**A:** ได้, คุณสามารถเพิ่มข้อยกเว้นได้ตามต้องการเพื่อแสดงวันหยุด, หน้าต่างการบำรุงรักษา, หรือกฎการกำหนดเวลาพิเศษใด ๆ  

**Q:** ฉันจะ **ตรวจสอบวันที่ของข้อยกเว้น** สำหรับวันเฉพาะได้อย่างไร?  
**A:** ใช้เมธอด `CheckException(DateTime date)` บนอินสแตนซ์ `CalendarException`. มันจะคืนค่า `true` หากวันที่ที่ระบุอยู่ในช่วงของข้อยกเว้น.  

**Q:** สามารถลบข้อยกเว้นที่มีอยู่จากปฏิทินได้หรือไม่?  
**A:** แน่นอน. เข้าถึงคอลเลกชัน `Exceptions` แล้วเรียก `Remove()` หรือใช้ `Delete()` บนอ็อบเจกต์ `CalendarException` เฉพาะ.  

**Q:** ประเภทของข้อยกเว้นปฏิทินที่รองรับมีอะไรบ้าง?  
**A:** Aspose.Tasks รองรับประเภทข้อยกเว้น Daily, Weekly, Monthly, และ Yearly, ทำให้คุณมีความยืดหยุ่นในการจำลองรูปแบบการเกิดซ้ำเกือบทั้งหมด.  

**Q:** ฉันสามารถปรับแต่งชั่วโมงทำงานสำหรับวันที่มีข้อยกเว้นเฉพาะได้หรือไม่?  
**A:** ได้. หลังจากสร้างข้อยกเว้น, เติมคอลเลกชัน `WorkingTimes` ของมันด้วยอ็อบเจกต์ `WorkingTime` ที่กำหนดเวลาเริ่มและสิ้นสุดสำหรับวันนั้น.  

## สรุป

เราได้เดินผ่านวงจรชีวิตเต็มของการดำเนินการ **ลบข้อยกเว้นปฏิทิน** ตั้งแต่การตรวจสอบข้อยกเว้นที่มีอยู่จนถึงการเพิ่มใหม่และการตรวจสอบวันที่. การเชี่ยวชาญเทคนิคเหล่านี้ทำให้ตารางโครงการของคุณเคารพปฏิทินจริง, ทำให้การนำการกำหนดเวลาปฏิทิน ASP.NET ของคุณมีความทนทานและเชื่อถือได้.

---

**อัปเดตล่าสุด:** 2026-04-13  
**ทดสอบด้วย:** Aspose.Tasks for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}