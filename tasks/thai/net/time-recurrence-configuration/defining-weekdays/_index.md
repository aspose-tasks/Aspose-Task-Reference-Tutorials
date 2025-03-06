---
title: การเรียนรู้วันธรรมดาใน Aspose.Tasks สำหรับ .NET
linktitle: การกำหนดวันธรรมดาใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: สำรวจพลังของการกำหนดวันธรรมดาใน Aspose.Tasks .NET ปฏิบัติตามบทช่วยสอนโดยละเอียดของเราเพื่อจัดการปฏิทินโครงการอย่างมีประสิทธิภาพ กำหนดเวลาการทำงาน และอื่นๆ อีกมากมาย
weight: 10
url: /th/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้วันธรรมดาใน Aspose.Tasks สำหรับ .NET

## การแนะนำ
หากคุณกำลังดำดิ่งสู่โลกแห่งการจัดการโครงการโดยใช้ Aspose.Tasks สำหรับ .NET การทำความเข้าใจและการจัดการวันธรรมดาถือเป็นสิ่งสำคัญ การจัดการและปรับแต่งวันทำงานอย่างมีประสิทธิภาพภายในปฏิทินโครงการของคุณอาจส่งผลกระทบอย่างมากต่อไทม์ไลน์ของโครงการ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการกำหนดวันธรรมดาโดยใช้ Aspose.Tasks โดยให้คำแนะนำและตัวอย่างทีละขั้นตอนเพื่อความชัดเจนยิ่งขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/tasks/net/).
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. ตรวจสอบความเท่าเทียมกันในวันทำงาน
```csharp
// ไดเรกทอรีเอกสารของคุณ
String DataDir = "Your Document Directory";
// โหลดไฟล์โครงการ
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// เข้าถึงวันธรรมดา
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// ตรวจสอบความเท่าเทียมกันตามคุณสมบัติต่างๆ
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. โคลนวันธรรมดา
```csharp
// โหลดไฟล์โครงการ
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// สร้างสำเนาเชิงลึกของวันทำงาน
var weekDay2 = weekDay1.Clone();
// คุณสมบัติเอาต์พุตของทั้งสองวันธรรมดา
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. รับรหัสแฮชของวันธรรมดา
```csharp
// โหลดไฟล์โครงการ
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// คุณสมบัติเอาต์พุตของทั้งสองวันธรรมดา
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. สร้างปฏิทินใหม่โดยกำหนดวันธรรมดา
```csharp
// สร้างโครงการใหม่
var project = new Project();
// กำหนดปฏิทิน
var calendar = project.Calendars.Add("Calendar1");
// เพิ่มวันทำการและวันยกเว้น
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ FromDate และ ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// กำหนดเวลาทำงานวันศุกร์
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. ตั้งเวลาทำงานเริ่มต้นสำหรับหนึ่งวัน
```csharp
// สร้างโครงการใหม่
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// เพิ่มเวลาทำงานเริ่มต้นสำหรับวันจันทร์ถึงวันศุกร์
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// ทำซ้ำในวันอังคาร วันพุธ วันพฤหัสบดี และวันศุกร์
// กำหนดวันที่ไม่ทำงานสำหรับวันเสาร์และวันอาทิตย์
// เพิ่มคำสั่งเอาต์พุตที่คล้ายกันสำหรับ DayWorking, FromDate, ToDate และ WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้ครอบคลุมประเด็นสำคัญในการกำหนดวันธรรมดาใน Aspose.Tasks สำหรับ .NET การจัดการวันธรรมดาเป็นทักษะสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ ทดลองใช้ตัวอย่างที่ให้มา ปรับแต่งตามความต้องการของโปรเจ็กต์ของคุณ และปลดล็อกศักยภาพทั้งหมดของ Aspose.Tasks
## คำถามที่พบบ่อย
### ฉันสามารถกำหนดเวลาทำงานที่กำหนดเองในแต่ละวันได้หรือไม่?
ใช่ คุณสามารถตั้งเวลาทำงานแบบกำหนดเองสำหรับวันธรรมดาที่ต้องการได้โดยใช้ตัวอย่างที่ให้ไว้
### เป็นไปได้ไหมที่จะเพิ่มวันยกเว้นหลายวันลงในปฏิทิน?
อย่างแน่นอน. แก้ไขโค้ดในตัวอย่างที่สี่เพื่อรวมวันยกเว้นเพิ่มเติม
### ฉันจะลบวันทำงานที่ต้องการออกจากปฏิทินได้อย่างไร
ใช้วิธีการที่เหมาะสมที่ได้รับจากไลบรารี Aspose.Tasks เพื่อลบวันธรรมดาตามความจำเป็น
### การเปลี่ยนแปลงที่เกิดขึ้นกับวันธรรมดายังคงมีอยู่ในไฟล์โครงการหรือไม่
ใช่ การแก้ไขใดๆ ในวันธรรมดาจะแสดงในไฟล์โครงการเมื่อบันทึก
### ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Tasks รองรับภาษาการเขียนโปรแกรมที่หลากหลาย แต่ตัวอย่างที่นี่มีไว้สำหรับ .NET โดยเฉพาะ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
