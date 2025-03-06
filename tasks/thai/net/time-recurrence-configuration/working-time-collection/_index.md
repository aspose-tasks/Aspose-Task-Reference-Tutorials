---
title: การควบคุมเวลาทำงานใน Aspose.Tasks
linktitle: การรวบรวมเวลาทำงานใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจพลังของ Aspose.Tasks สำหรับ .NET ในการจัดการไทม์ไลน์ของโครงการอย่างมีประสิทธิภาพ ปรับแต่งปฏิทิน ตั้งเวลาทำงาน และปรับปรุงโครงการของคุณได้อย่างง่ายดาย
weight: 14
url: /th/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การควบคุมเวลาทำงานใน Aspose.Tasks

## การแนะนำ
คุณกำลังมองหาการเรียนรู้ศิลปะในการจัดการเวลาทำงานใน Aspose.Tasks for .NET หรือไม่? ไม่ต้องมองอีกต่อไป! ในคำแนะนำทีละขั้นตอนนี้ เราจะเจาะลึกความซับซ้อนของการรวบรวมเวลาทำงานโดยใช้ Aspose.Tasks ซึ่งช่วยให้คุณจัดการปฏิทินแบบกำหนดเองได้อย่างมีประสิทธิภาพ และปรับปรุงไทม์ไลน์ของโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[หน้าเผยแพร่ Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- สภาพแวดล้อมการทำงาน: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม โดยควรใช้ IDE ที่เข้ากันได้กับ .NET
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
ตอนนี้ เราจะแบ่งบทแนะนำออกเป็นหลายขั้นตอนเพื่อให้มั่นใจว่าจะได้รับประสบการณ์การเรียนรู้ที่ราบรื่น
## ขั้นตอนที่ 1: สร้างปฏิทินแบบกำหนดเอง
เริ่มต้นด้วยการสร้างโปรเจ็กต์ใหม่และเพิ่มปฏิทินที่กำหนดเองลงไป:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## ขั้นตอนที่ 2: กำหนดวันทำงาน
ตั้งค่าวันทำการเริ่มต้นตั้งแต่วันจันทร์ถึงวันศุกร์:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## ขั้นตอนที่ 3: กำหนดเวลาทำงานวันเสาร์
ระบุเวลาทำงานวันเสาร์:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## ขั้นตอนที่ 4: พิมพ์ช่วงเวลาทำงานวันเสาร์
พิมพ์เวลาทำงานที่กำหนดไว้สำหรับวันเสาร์:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## ขั้นตอนที่ 5: กำหนดเวลาทำงานในวันอาทิตย์
กำหนดเวลาทำงานสำหรับวันอาทิตย์:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## ขั้นตอนที่ 6: พิมพ์ช่วงเวลาทำงานในวันอาทิตย์
พิมพ์เวลาทำงานที่กำหนดไว้สำหรับวันอาทิตย์:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## ขั้นตอนที่ 7: เพิ่มวันที่กำหนดเองลงในปฏิทิน
รวมวันเสาร์และวันอาทิตย์ที่กำหนดค่าไว้ในปฏิทิน:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## ขั้นตอนที่ 8: สำรวจตามเวลาทำงาน
ข้ามผ่านเวลาทำงานและแสดงในแต่ละวันในปฏิทิน:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
เมื่อคุณทำตามขั้นตอนต่างๆ ได้สำเร็จ คุณก็พร้อมที่จะควบคุมพลังของ Aspose.Tasks สำหรับ .NET ในการจัดการเวลาทำงานอย่างมีประสิทธิภาพ
## บทสรุป
การเรียนรู้การรวบรวมเวลาทำงานใน Aspose.Tasks ช่วยให้คุณสามารถปรับแต่งปฏิทินโครงการได้ ทำให้มั่นใจได้ถึงการกำหนดเวลาที่แม่นยำและการใช้ทรัพยากรอย่างมีประสิทธิภาพ เจาะลึกโครงการของคุณด้วยความมั่นใจ พร้อมด้วยความรู้ที่ได้รับจากคู่มือที่ครอบคลุมนี้
## คำถามที่พบบ่อย
### Aspose.Tasks เหมาะสำหรับการจัดการโครงการขนาดใหญ่หรือไม่
ใช่ Aspose.Tasks ได้รับการออกแบบมาเพื่อรองรับโปรเจ็กต์ที่มีขนาดแตกต่างกัน โดยให้คุณสมบัติที่แข็งแกร่งสำหรับการจัดการโปรเจ็กต์ที่มีประสิทธิภาพ
### ฉันสามารถรวม Aspose.Tasks เข้ากับไลบรารี .NET อื่นๆ ได้หรือไม่
แน่นอน! Aspose.Tasks ทำงานร่วมกับไลบรารี .NET อื่น ๆ ได้อย่างราบรื่น เพิ่มความคล่องตัวและความเข้ากันได้
### Aspose.Tasks อัปเดตบ่อยแค่ไหน?
 Aspose.Tasks ได้รับการอัปเดตเป็นประจำเพื่อรวมคุณสมบัติใหม่ การปรับปรุง และการปรับปรุงความเข้ากันได้ ตรวจสอบ[หน้าปล่อย](https://releases.aspose.com/tasks/net/) สำหรับการอัปเดตล่าสุด
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถสำรวจ Aspose.Tasks พร้อมรุ่นทดลองใช้ฟรีได้โดยไปที่[ลิงค์นี้](https://releases.aspose.com/).
### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ โปรดไปที่[ฟอรัมสนับสนุน Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
