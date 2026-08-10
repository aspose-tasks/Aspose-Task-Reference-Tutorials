---
date: 2026-04-09
description: เรียนรู้วิธีตั้งปฏิทินมาตรฐานและจัดการวันหยุดโครงการในโปรเจกต์ .NET ของคุณด้วย
  Aspose.Tasks เพื่อการกำหนดเวลาอย่างแม่นยำ.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: ตั้งปฏิทินมาตรฐานและจัดการข้อยกเว้นใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ตั้งปฏิทินมาตรฐานและจัดการข้อยกเว้นใน Aspose.Tasks
url: /th/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าปฏิทินมาตรฐานและจัดการข้อยกเว้นใน Aspose.Tasks

## บทนำ

การกำหนดตารางเวลาอย่างแม่นยำเป็นหัวใจของโครงการที่ประสบความสำเร็จ และแผนในโลกจริงมักต้องเบี่ยงเบนจากปฏิทินทำงานเริ่มต้นเนื่องจากวันหยุด, งานพิเศษ, หรือการหยุดทำงานโดยไม่คาดคิด Aspose.Tasks for .NET ทำให้คุณสามารถ **ตั้งค่าปฏิทินมาตรฐาน** ได้อย่างง่ายดายและเพิ่มข้อยกเว้นแบบกำหนดเองต่อไป ในบทเรียนนี้คุณจะได้เรียนรู้วิธีโหลดปฏิทินของโครงการ, ตั้งค่าปฏิทินมาตรฐาน, และจัดการวันหยุดของโครงการผ่านฟีเจอร์ Calendar Exception Collection

## คำตอบอย่างรวดเร็ว
- **What does “set standard calendar” do?** มันรีเซ็ตปฏิทินให้เป็นเวลาทำงานเริ่มต้น (9 น.-17 น., จันทร์‑ศุกร์) ก่อนที่คุณจะเพิ่มข้อยกเว้นแบบกำหนดเอง.  
- **Which method clears existing exceptions?** เมธอด `Calendar.Exceptions.Clear()` จะลบข้อยกเว้นทั้งหมดที่กำหนดไว้ก่อนหน้า.  
- **How can I add a holiday?** สร้าง `CalendarException` โดยตั้งค่า `DayWorking = false` แล้วเพิ่มลงในคอลเลกชัน.  
- **Do I need to reload the project after changes?** ไม่จำเป็น, การเปลี่ยนแปลงจะถูกนำไปใช้โดยตรงกับอ็อบเจ็กต์ `Project` ในหน่วยความจำ.  
- **What libraries are required?** Aspose.Tasks for .NET (เวอร์ชัน .NET ที่รองรับ) และเนมสเปซ `System`.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มเขียนโค้ด, โปรดตรวจสอบว่าคุณมี:

1. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/net/).  
2. ความรู้พื้นฐานของ **C#** – คุณจะเขียนโค้ดสั้น ๆ ไม่กี่ส่วน.  
3. สภาพแวดล้อมการพัฒนา เช่น **Visual Studio** หรือ **JetBrains Rider**.

## นำเข้า Namespaces

คำสั่ง `using` เหล่านี้ทำให้คุณเข้าถึงคลาสที่จำเป็นสำหรับการจัดการปฏิทินได้.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## ข้อยกเว้นของปฏิทินคืออะไร?

*ข้อยกเว้นของปฏิทิน* แสดงช่วงเวลาที่ตารางทำงานปกติถูกเปลี่ยนแปลง – เช่น วันหยุดทั่วบริษัทหรือกำหนดการทำงานล่วงเวลาแบบชั่วคราว การเพิ่มข้อยกเว้นลงในปฏิทินช่วยให้คุณจำลองข้อจำกัดในโลกจริงได้โดยไม่ต้องเปลี่ยนแปลงปฏิทินฐาน.

## วิธีตั้งค่าปฏิทินมาตรฐานใน Aspose.Tasks

ขั้นตอนแรกคือโหลดไฟล์โครงการของคุณและดึงปฏิทินที่ต้องการทำงานด้วย.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### ขั้นตอนที่ 1: ลบข้อยกเว้นที่มีอยู่และรีเซ็ตเป็นปฏิทินมาตรฐาน

ก่อนเพิ่มกฎใหม่ ควรลบข้อยกเว้นเก่าและ **ตั้งค่าปฏิทินมาตรฐาน** เพื่อให้ได้ฐานที่สะอาด.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### ขั้นตอนที่ 2: กำหนดข้อยกเว้นเวลาทำงาน

บางครั้งคุณอาจต้องสร้างตารางชั่วคราว (เช่น ชั่วโมงทำงานเพิ่มสำหรับการเปิดตัวผลิตภัณฑ์) โค้ดต่อไปนี้กำหนดข้อยกเว้นเวลาทำงานที่ครอบคลุมหลายวันและมีสองช่วงเวลาทำงานต่อวัน.

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

### ขั้นตอนที่ 3: เพิ่มข้อยกเว้นเวลาที่ไม่ทำงาน (วันหยุด)

เพื่อ **จัดการวันหยุดของโครงการ** ให้สร้างข้อยกเว้นที่ `DayWorking` เป็น `false` ตัวอย่างด้านล่างเพิ่มบล็อกวันหยุดสองวัน.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### ขั้นตอนที่ 4: แสดงข้อยกเว้นของปฏิทิน (การตรวจสอบ)

หลังจากเพิ่มข้อยกเว้น คุณมักต้องการตรวจสอบว่ามันถูกบันทึกอย่างถูกต้องหรือไม่ โค้ดลูปต่อไปนี้จะแสดงรายละเอียดของแต่ละข้อยกเว้นบนคอนโซล.

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

### ขั้นตอนที่ 5: ลบข้อยกเว้นทั้งหมด (ทำความสะอาด)

หากต้องการคืนปฏิทินสู่สถานะเดิม คุณสามารถลบข้อยกเว้นทั้งหมดโดยโปรแกรม.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| ข้อยกเว้นไม่แสดงหลังจากบันทึก | โครงการไม่ได้บันทึกหลังจากแก้ไข | เรียก `project.Save("output.mpp")` หลังจากทำการเปลี่ยนแปลง. |
| ข้อยกเว้นที่ทับกันทำให้ชั่วโมงทำงานไม่คาดคิด | Aspose.Tasks ใช้ข้อยกเว้นที่เพิ่มล่าสุดสำหรับช่วงที่ทับกัน | จัดลำดับการเรียก `Add` อย่างระมัดระวังหรือปรับลำดับความสำคัญด้วยตนเอง. |
| `MakeStandardCalendar` รีเซ็ตเวลาทำงานที่กำหนดเอง | มันตั้งใจลบเวลาที่กำหนดเอง; หากต้องการให้เพิ่มกลับหลังจากเรียก | เพิ่มอ็อบเจ็กต์ `WorkingTime` ที่กำหนดเองของคุณหลังจากเรียก `MakeStandardCalendar`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มหลายข้อยกเว้นในปฏิทินเดียวได้หรือไม่?**  
A: ได้, คุณสามารถเพิ่มหลายข้อยกเว้นในปฏิทินโดยใช้เมธอด `AddRange`.

**Q: ฉันจะจัดการข้อยกเว้นที่เกิดซ้ำ เช่น วันหยุดประจำสัปดาห์อย่างไร?**  
A: คุณสามารถคำนวณข้อยกเว้นที่เกิดซ้ำโดยโปรแกรมและเพิ่มลงในปฏิทินด้วยตรรกะที่กำหนดเอง.

**Q: สามารถนำเข้าข้อยกเว้นของปฏิทินจากแหล่งภายนอกได้หรือไม่?**  
A: ได้, คุณสามารถอ่านข้อยกเว้นจากแหล่งภายนอกเช่นฐานข้อมูลหรือไฟล์ CSV แล้วรวมเข้ากับโครงการของคุณ.

**Q: จะเกิดอะไรขึ้นหากมีข้อยกเว้นที่ทับกันในปฏิทิน?**  
A: Aspose.Tasks for .NET อนุญาตให้คุณจัดการข้อยกเว้นที่ทับกันโดยกำหนดลำดับความสำคัญหรือแก้ไขความขัดแย้งตามความต้องการของโครงการ.

**Q: ฉันสามารถกำหนดเวลาทำงานสำหรับแต่ละวันภายในข้อยกเว้นได้หรือไม่?**  
A: ได้, คุณสามารถระบุเวลาทำงานที่กำหนดเองสำหรับแต่ละวันภายในข้อยกเว้นเพื่อรองรับความต้องการกำหนดเวลาเฉพาะ.

## สรุป

โดย **ตั้งค่าปฏิทินมาตรฐาน** ก่อนแล้วจึงเพิ่มข้อยกเว้นแบบกำหนดเอง คุณจะได้การควบคุมการกำหนดเวลาของโครงการอย่างเต็มที่ ทำให้ **จัดการวันหยุดของโครงการ** และไทม์ไลน์พิเศษอื่น ๆ ง่ายขึ้น คอลเลกชันข้อยกเว้นของปฏิทินใน Aspose.Tasks ให้วิธีที่สะอาดและเป็นโปรแกรมในการจำลองปฏิทินจริง ๆ ภายในแอปพลิเคชัน .NET ของคุณ.

---

**อัปเดตล่าสุด:** 2026-04-09  
**ทดสอบกับ:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}