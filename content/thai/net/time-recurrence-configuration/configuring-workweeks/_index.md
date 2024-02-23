---
title: การเรียนรู้การกำหนดค่าสัปดาห์ทำงานอย่างเชี่ยวชาญใน Aspose.Tasks
linktitle: กำหนดค่าสัปดาห์การทำงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่าสัปดาห์ทำงานอย่างง่ายดายใน Aspose.Tasks for .NET ปรับปรุงการจัดกำหนดการโครงการและการจัดการทรัพยากรด้วยคำแนะนำทีละขั้นตอนของเรา
type: docs
weight: 16
url: /th/net/time-recurrence-configuration/configuring-workweeks/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการกำหนดค่าสัปดาห์ทำงานใน Aspose.Tasks สำหรับ .NET การจัดการสัปดาห์ทำงานอย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการวางแผนและกำหนดเวลาโครงการ Aspose.Tasks ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณปรับแต่งสัปดาห์การทำงานได้ตามความต้องการของโปรเจ็กต์ของคุณ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนต่างๆ เพื่อกำหนดค่าสัปดาห์ทำงานได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  ไลบรารี Aspose.Tasks: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ Aspose.Tasks](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อม .NET: ตรวจสอบให้แน่ใจว่าคุณกำลังทำงานในสภาพแวดล้อม .NET และคุณมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project();
```
## ขั้นตอนที่ 2: สร้างปฏิทินมาตรฐาน
```csharp
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## ขั้นตอนที่ 3: กำหนดสัปดาห์การทำงานที่กำหนดเอง
```csharp
var item = new WorkWeek();
item.Name = "My Work Week";
item.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
item.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## ขั้นตอนที่ 4: ระบุวันทำการ
```csharp
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
item.WeekDays.Add(new WeekDay(DayType.Saturday));
item.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(item);
```
## ขั้นตอนที่ 5: แสดงรายละเอียดสัปดาห์การทำงาน
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    // แสดงรายละเอียดสัปดาห์การทำงาน
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    Console.WriteLine();
    // แสดงเวลาทำงานพิเศษในแต่ละวัน
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        // แสดงเวลาการทำงาน
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถกำหนดค่าสัปดาห์ทำงานใน Aspose.Tasks ได้อย่างง่ายดาย ซึ่งช่วยเพิ่มความสามารถในการจัดการโครงการของคุณ
## บทสรุป
โดยสรุป การจัดการสัปดาห์ทำงานเป็นลักษณะพื้นฐานของการวางแผนโครงการ และ Aspose.Tasks ทำให้กระบวนการนี้ง่ายขึ้นด้วยฟีเจอร์อันทรงพลัง ด้วยการปรับแต่งสัปดาห์ทำงานตามความต้องการของโครงการ คุณสามารถรับประกันการใช้ทรัพยากรอย่างมีประสิทธิภาพและการจัดกำหนดการโครงการที่ดีขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถกำหนดค่าการทำงานหลายสัปดาห์ในโปรเจ็กต์เดียวได้หรือไม่
ใช่ คุณสามารถกำหนดค่าสัปดาห์ทำงานหลายสัปดาห์ภายในโปรเจ็กต์เดียวกันได้โดยใช้ Aspose.Tasks
### สามารถตั้งเวลาทำงานที่แตกต่างกันสำหรับวันใดวันหนึ่งได้หรือไม่?
อย่างแน่นอน. Aspose.Tasks ช่วยให้คุณสามารถกำหนดเวลาทำงานที่ไม่ซ้ำกันในแต่ละวันภายในสัปดาห์ทำงาน
### ฉันสามารถนำเข้า/ส่งออกสัปดาห์ทำงานระหว่างโครงการได้หรือไม่
แม้ว่า Aspose.Tasks จะมีความสามารถในการนำเข้า/ส่งออกที่มีประสิทธิภาพ แต่โดยปกติแล้วสัปดาห์ทำงานจะเป็นเฉพาะโครงการและอาจไม่สามารถถ่ายโอนได้โดยตรง
### มีการจำกัดจำนวนสัปดาห์ทำงานที่ฉันสามารถสร้างในโปรเจ็กต์ได้หรือไม่
ในเวอร์ชันปัจจุบัน ไม่มีการจำกัดจำนวนสัปดาห์ทำงานที่กำหนดไว้ล่วงหน้าที่คุณสามารถกำหนดค่าในโปรเจ็กต์ได้
### มีเทมเพลตในตัวสำหรับสัปดาห์ทำงานทั่วไปหรือไม่
ใช่ Aspose.Tasks มีเทมเพลตปฏิทินมาตรฐานที่คุณสามารถใช้เป็นจุดเริ่มต้นสำหรับโปรเจ็กต์ของคุณได้