---
title: การเรียนรู้วันธรรมดาใน Aspose.Tasks
linktitle: การรวบรวมวันธรรมดาใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ค้นพบพลังของ Aspose.Tasks สำหรับ .NET ในการจัดการวันธรรมดาได้อย่างง่ายดาย ปรับแต่งวันทำงาน ลบวันหยุดสุดสัปดาห์ และสร้างปฏิทินพิเศษได้อย่างง่ายดาย
weight: 11
url: /th/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้วันธรรมดาใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งอำนวยความสะดวกในการจัดการข้อมูลการจัดการโครงการอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจคอลเลกชั่นวันธรรมดาใน Aspose.Tasks ซึ่งช่วยให้คุณปรับแต่งวันทำงาน ลบวันหยุดสุดสัปดาห์ และสร้างปฏิทินพิเศษเพื่อให้ตรงตามข้อกำหนดของโปรเจ็กต์ของคุณ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการทำงานกับวันธรรมดาใน Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  ติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[Aspose.Tasks สำหรับหน้าดาวน์โหลด .NET](https://releases.aspose.com/tasks/net/).
- ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์
เริ่มต้นโครงการ Aspose.Tasks ใหม่:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## ขั้นตอนที่ 2: เข้าถึงปฏิทิน
ดึงข้อมูลปฏิทินโครงการ:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## ขั้นตอนที่ 3: ปรับแต่งวันธรรมดา
ล้างวันธรรมดาที่มีอยู่และตั้งค่าวันทำงานเริ่มต้น:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// เพิ่มวันธรรมดาอื่นๆ ในทำนองเดียวกัน...
```
## ขั้นตอนที่ 4: เพิ่มเวลาทำงาน
เพิ่มเวลาทำงานสำหรับวันธรรมดาที่ระบุ:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## ขั้นตอนที่ 5: แสดงข้อมูลปฏิทิน
รายละเอียดปฏิทินส่งออกไปยังคอนโซล:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// แสดงวันธรรมดาและเวลาทำงาน...
```
## ขั้นตอนที่ 6: ลบวันหยุดสุดสัปดาห์
ลบวันเสาร์และวันอาทิตย์ออกจากวันธรรมดา:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## ขั้นตอนที่ 7: แสดงเวลาทำงานที่อัปเดต
เอาต์พุตอัปเดตเวลาทำงานหลังจากลบวันหยุดสุดสัปดาห์:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// แสดงวันทำงานและเวลาทำงานที่อัปเดตแต่ละครั้ง...
```
## ขั้นตอนที่ 8: สร้างปฏิทินแบบ 24 ชั่วโมง
สร้างปฏิทินแบบ 24 ชั่วโมงและคัดลอกวันธรรมดา:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจความสามารถอันทรงพลังของ Aspose.Tasks สำหรับ .NET ในการจัดการวันธรรมดาภายในปฏิทินโครงการ ตั้งแต่การกำหนดวันทำงานไปจนถึงการสร้างปฏิทินพิเศษตลอด 24 ชั่วโมง Aspose.Tasks ช่วยลดความซับซ้อนของกระบวนการ โดยให้ความยืดหยุ่นและการควบคุมในการจัดการโครงการ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
ตอบ: Aspose.Tasks รองรับภาษา .NET เป็นหลัก แต่ก็มีเวอร์ชันสำหรับ Java ด้วย
### ถาม: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[หน้าเผยแพร่ Aspose.Tasks](https://releases.aspose.com/).
### ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนจากชุมชนหรือพิจารณาซื้อแผนการสนับสนุน
### ถาม: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Tasks for .NET ได้ที่ไหน
 ตอบ: โปรดดูที่[Aspose.Tasks สำหรับเอกสาร .NET](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลโดยละเอียด
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
