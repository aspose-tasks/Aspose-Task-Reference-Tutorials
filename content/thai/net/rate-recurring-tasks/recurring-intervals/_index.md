---
title: ช่วงเวลาที่เกิดซ้ำของโครงการ MS ได้อย่างง่ายดายใน Aspose.Tasks
linktitle: การจัดการช่วงเวลาที่เกิดซ้ำใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: ค้นพบวิธีจัดการช่วงเวลาที่เกิดซ้ำใน MS Project ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ .NET
type: docs
weight: 12
url: /th/net/rate-recurring-tasks/recurring-intervals/
---
## การแนะนำ
คุณต้องการจัดการช่วงเวลาที่เกิดซ้ำอย่างมีประสิทธิภาพในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET หรือไม่? บทช่วยสอนที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถจัดการกับช่วงเวลาที่เกิดซ้ำในโครงการของคุณได้อย่างง่ายดาย ก่อนที่จะเข้าสู่บทแนะนำสอนการใช้งาน เรามาดูข้อกำหนดเบื้องต้นบางประการเพื่อให้แน่ใจว่าคุณพร้อมที่จะเริ่มต้นแล้ว
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการบทช่วยสอนนี้ โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ความรู้เกี่ยวกับการเขียนโปรแกรม C#: จำเป็นต้องมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และไวยากรณ์ของมัน
2. ติดตั้ง Visual Studio แล้ว: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณสำหรับการเข้ารหัสและรวบรวมแอปพลิเคชัน .NET
3. Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET Library คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานที่จัดเตรียมโดยไลบรารี Aspose.Tasks สำหรับ .NET
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
ตอนนี้ เรามาแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนและอธิบายโดยละเอียด
## ขั้นตอนที่ 1: เริ่มต้นวัตถุโครงการ:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
ที่นี่เราเริ่มต้นอินสแตนซ์ใหม่ของ`Project` คลาสโดยระบุเส้นทางไปยังไฟล์ Microsoft Project
## ขั้นตอนที่ 2: กำหนดวันที่สถานะ:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
ขั้นตอนนี้กำหนดวันที่สถานะของโครงการเป็นวันที่เริ่มต้น
## ขั้นตอนที่ 3: เข้าถึงมุมมองแผนภูมิแกนต์:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
เราเข้าถึงมุมมองแผนภูมิแกนต์ของโครงการ
## ขั้นตอนที่ 4: อ่านบรรทัดความคืบหน้า:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
ขั้นตอนนี้ดึงข้อมูลช่วงเวลาที่เกิดซ้ำสำหรับบรรทัดความคืบหน้าจากมุมมองแผนภูมิแกนต์
## ขั้นตอนที่ 5: แสดงข้อมูลช่วงเวลา:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
ที่นี่ เราแสดงข้อมูลเกี่ยวกับช่วงเวลา หมายเลขสัปดาห์รายสัปดาห์ และวันรายสัปดาห์
## ขั้นตอนที่ 6: กำหนดช่วงเวลาที่เกิดซ้ำใหม่:
```csharp
var newInterval = new RecurringInterval();
```
 เราสร้างอินสแตนซ์ใหม่ของ`RecurringInterval` เพื่อกำหนดช่วงเวลาที่เกิดซ้ำอีกครั้ง
## ขั้นตอนที่ 7: กำหนดเส้นความคืบหน้ารายเดือน:
```csharp
// กำหนดเส้นความคืบหน้ารายเดือนตามวัน
interval.MonthlyDay = true;
// กำหนดจำนวนวันของเส้นความคืบหน้ารายเดือน
interval.MonthlyDayDayNumber = 1;
// กำหนดจำนวนเดือนของเส้นความคืบหน้ารายเดือน
interval.MonthlyDayMonthNumber = 1;
// กำหนดเส้นความคืบหน้าตามวันแรกหรือวันสุดท้ายที่กำหนดไว้ล่วงหน้า
interval.MonthlyFirstLast = true;
// ตั้งค่าประเภทวันแรกหรือวันสุดท้ายของเส้นความคืบหน้ารายเดือน
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// กำหนดจำนวนเดือนของเส้นความคืบหน้า
interval.MonthlyFirstLastMonthNumber = 1;
```
ขั้นตอนเหล่านี้กำหนดค่าบรรทัดความคืบหน้ารายเดือนตามพารามิเตอร์ที่ระบุ
## ขั้นตอนที่ 8: อัปเดตเส้นความคืบหน้า:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
เราอัปเดตเส้นความคืบหน้าในมุมมองแผนภูมิแกนต์ด้วยช่วงเวลาที่เกิดซ้ำซึ่งกำหนดใหม่
## ขั้นตอนที่ 9: บันทึกโครงการเป็น PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
สุดท้าย เราจะบันทึกโปรเจ็กต์ด้วยช่วงเวลาที่เกิดซ้ำที่อัปเดตเป็นไฟล์ PDF

## บทสรุป
โดยสรุป การจัดการช่วงเวลาที่เกิดซ้ำในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET นั้นทำได้ง่ายด้วยฟังก์ชันที่ครอบคลุมจากไลบรารี ด้วยการทำตามคำแนะนำทีละขั้นตอนที่สรุปไว้ในบทช่วยสอนนี้ คุณสามารถจัดการกับช่วงเวลาที่เกิดซ้ำในโปรเจ็กต์ของคุณ เพิ่มประสิทธิภาพการทำงานและองค์กรได้อย่างมีประสิทธิภาพ
### คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ได้ Aspose.Tasks สำหรับ .NET สามารถใช้ได้กับภาษาใดก็ได้ที่รองรับ .NET เช่น C# และ VB.NET
### มีรุ่นทดลองใช้สำหรับ Aspose.Tasks สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ .NET ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารฉบับสมบูรณ์สำหรับ Aspose.Tasks for .NET ได้ที่ไหน
 สามารถดูเอกสารฉบับสมบูรณ์ได้[ที่นี่](https://reference.aspose.com/tasks/net/).