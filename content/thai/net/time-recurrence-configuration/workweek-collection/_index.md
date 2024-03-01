---
title: ปรับแต่งสัปดาห์ทำงานใน Aspose.Tasks
linktitle: การรวบรวม Workweeks ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งสัปดาห์ทำงานใน Aspose.Tasks for .NET คำแนะนำทีละขั้นตอนสำหรับการสร้างปฏิทินโครงการส่วนบุคคล ดาวน์โหลดเดี๋ยวนี้!
type: docs
weight: 17
url: /th/net/time-recurrence-configuration/workweek-collection/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนของเราเกี่ยวกับการสร้างสัปดาห์การทำงานแบบกำหนดเองโดยใช้ Aspose.Tasks สำหรับ .NET! ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการกำหนดสัปดาห์การทำงานส่วนบุคคลสำหรับปฏิทินในโครงการของคุณ Aspose.Tasks เป็นไลบรารีที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร Microsoft Project ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: สร้างโครงการและปฏิทิน
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## ขั้นตอนที่ 2: กำหนดสัปดาห์การทำงานที่กำหนดเอง
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## ขั้นตอนที่ 3: กำหนดวันทำการ
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## ขั้นตอนที่ 4: แสดงข้อมูลสัปดาห์ทำงาน
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
คู่มือที่ครอบคลุมนี้ช่วยให้คุณสร้างและจัดการสัปดาห์การทำงานที่กำหนดเองได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET
## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการปฏิทินโครงการด้วยสัปดาห์การทำงานที่กำหนดเอง ด้วยการทำตามบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างและแสดงข้อมูลเกี่ยวกับสัปดาห์การทำงานที่กำหนดเองในโครงการของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถมีสัปดาห์ทำงานที่กำหนดเองหลายสัปดาห์ในโปรเจ็กต์เดียวได้หรือไม่
ได้ คุณสามารถเพิ่มสัปดาห์การทำงานที่กำหนดเองหลายสัปดาห์ลงในปฏิทินโครงการได้
### ฉันจะแก้ไขสัปดาห์การทำงานที่มีอยู่ได้อย่างไร
 ใช้ของที่ให้มา`WorkWeek`คุณสมบัติและวิธีการแก้ไขสัปดาห์การทำงานที่มีอยู่
### Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Tasks รองรับ .NET Core
### ฉันสามารถส่งออกโครงการที่มีสัปดาห์ทำงานที่กำหนดเองเป็นรูปแบบไฟล์ Microsoft Project ได้หรือไม่
แน่นอน Aspose.Tasks ช่วยให้คุณสามารถบันทึกโครงการของคุณในรูปแบบต่าง ๆ รวมถึง Microsoft Project
### ฉันจะขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวข้องกับ Aspose.Tasks ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนหรือความช่วยเหลือใด ๆ