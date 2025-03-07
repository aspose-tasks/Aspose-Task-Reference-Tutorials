---
title: การกำหนดค่าเวลาทำงานใน Aspose.Tasks
linktitle: การกำหนดค่าเวลาทำงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ปรับปรุงการกำหนดเวลาโครงการใน .NET ด้วย Aspose.Tasks กำหนดเวลาทำงานได้อย่างง่ายดายเพื่อการจัดการทรัพยากรที่แม่นยำ ดาวน์โหลดห้องสมุดทันที!
weight: 13
url: /th/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่าเวลาทำงานใน Aspose.Tasks

## การแนะนำ
ในการจัดการโครงการ การควบคุมเวลาทำงานที่แม่นยำเป็นสิ่งสำคัญอย่างยิ่งต่อการจัดกำหนดการและการจัดสรรทรัพยากรที่แม่นยำ Aspose.Tasks for .NET มอบโซลูชันอันทรงพลังสำหรับการจัดการข้อมูลเวลาทำงานภายในโครงการของคุณ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการกำหนดเวลาการทำงานโดยใช้ Aspose.Tasks ในสภาพแวดล้อม .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ที่ต้องการ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## ขั้นตอนที่ 1: สร้างปฏิทิน
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
ที่นี่ เราเริ่มต้นโครงการใหม่และสร้างปฏิทินชื่อ "MyCalendar" ตามปฏิทินมาตรฐาน ปฏิทินนี้จะใช้เพื่อกำหนดเวลาการทำงานเฉพาะ

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## ขั้นตอนที่ 2: แสดงข้อมูลสัปดาห์การทำงาน
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
ขั้นตอนนี้จะพิมพ์จำนวนวันทำการทั้งหมดในปฏิทินที่ระบุ
## ขั้นตอนที่ 3: รายละเอียดเวลาทำงาน
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
ในส่วนนี้ เราจะวนซ้ำในแต่ละวันของสัปดาห์ พิมพ์ประเภทวันและเวลาทำงานที่เกี่ยวข้อง คุณสามารถปรับแต่งเวลาทำงานในแต่ละวันได้ตามความต้องการของโครงการ
## บทสรุป
การกำหนดค่าเวลาทำงานอย่างมีประสิทธิภาพใน Aspose.Tasks สำหรับ .NET ช่วยให้มั่นใจในการวางแผนโครงการและการจัดการทรัพยากรที่แม่นยำ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถรวมการปรับเปลี่ยนเวลาทำงานเข้ากับเวิร์กโฟลว์โครงการของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.Tasks เหมาะสำหรับการจัดการโครงการขนาดใหญ่หรือไม่
ใช่ Aspose.Tasks ได้รับการออกแบบมาเพื่อจัดการกับโปรเจ็กต์ขนาดต่างๆ โดยนำเสนอฟีเจอร์ที่แข็งแกร่งสำหรับการจัดการโปรเจ็กต์ที่มีประสิทธิภาพ
### ฉันสามารถตั้งเวลาทำงานที่แตกต่างกันสำหรับสมาชิกในทีมแต่ละคนได้หรือไม่
อย่างแน่นอน. คุณสามารถปรับแต่งเวลาทำงานตามทรัพยากรได้ เพื่อให้สามารถจัดกำหนดการเป็นรายบุคคลได้
### Aspose.Tasks รองรับการทำงานร่วมกับเครื่องมือการจัดการโครงการอื่นๆ หรือไม่
ใช่ Aspose.Tasks อำนวยความสะดวกในการบูรณาการกับเครื่องมือการจัดการโครงการต่างๆ ช่วยเพิ่มความสามารถในการทำงานร่วมกัน
### เป็นไปได้หรือไม่ที่จะนำเข้า/ส่งออกข้อมูลโครงการในรูปแบบที่แตกต่างกัน?
Aspose.Tasks รองรับไฟล์ได้หลายรูปแบบ ช่วยให้ดำเนินการนำเข้า/ส่งออกข้อมูลโครงการได้อย่างราบรื่น
### มีการเผยแพร่การอัปเดต Aspose.Tasks บ่อยเพียงใด
มีการเผยแพร่การอัปเดตเป็นประจำเพื่อให้มั่นใจว่าสามารถใช้งานร่วมกับเทคโนโลยีล่าสุดและตอบสนองต่อความคิดเห็นของผู้ใช้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
