---
title: การตั้งค่าพารามิเตอร์งานที่เกิดซ้ำใน Aspose.Tasks
linktitle: การตั้งค่าพารามิเตอร์งานที่เกิดซ้ำใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีตั้งค่าพารามิเตอร์งานที่เกิดซ้ำใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนที่ครอบคลุมพร้อมคำแนะนำทีละขั้นตอน
weight: 14
url: /th/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าพารามิเตอร์งานที่เกิดซ้ำใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าพารามิเตอร์งานที่เกิดซ้ำของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
2. ติดตั้ง Visual Studio หรือ C # IDE อื่น ๆ
3. ติดตั้งและอ้างอิงไลบรารี Aspose.Tasks สำหรับ .NET ในโครงการของคุณ

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
using Aspose.Tasks;
using System;

```
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
```csharp
String DataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 บรรทัดโค้ดนี้จะโหลดไฟล์ Microsoft Project ลงในไฟล์`project` ตัวแปร.
## ขั้นตอนที่ 3: กำหนดพารามิเตอร์งานที่เกิดซ้ำ
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
ที่นี่ คุณกำหนดพารามิเตอร์สำหรับงานที่เกิดซ้ำ เช่น ชื่องาน ระยะเวลา รูปแบบการเกิดซ้ำ ช่วงที่เกิดซ้ำ และจะละเว้นปฏิทินทรัพยากรหรือไม่
## ขั้นตอนที่ 4: ตั้งค่าปฏิทินสำหรับงานที่เกิดซ้ำ
```csharp
parameters.SetCalendar(project, "Standard");
```
ขั้นตอนนี้จะตั้งค่าปฏิทินสำหรับงานที่เกิดซ้ำ ในตัวอย่างนี้ จะตั้งค่าปฏิทินเป็น "มาตรฐาน"
## ขั้นตอนที่ 5: เพิ่มพารามิเตอร์ในโครงการ
```csharp
project.RootTask.Children.Add(parameters);
```
สุดท้าย เพิ่มพารามิเตอร์ให้กับงานรูทของโปรเจ็กต์

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการตั้งค่าพารามิเตอร์งานที่เกิดซ้ำของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการงานที่เกิดซ้ำในโครงการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งรูปแบบการเกิดซ้ำเพิ่มเติมได้หรือไม่
ใช่ Aspose.Tasks มีรูปแบบการเกิดซ้ำและตัวเลือกต่างๆ เพื่อปรับแต่งตามความต้องการของโปรเจ็กต์ของคุณ
### มีรุ่นทดลองใช้ก่อนซื้อหรือไม่?
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก Aspose.Tasks[เว็บไซต์](https://purchase.aspose.com/buy) เพื่อประเมินคุณสมบัติของห้องสมุด
### Aspose.Tasks รองรับไฟล์โปรเจ็กต์รูปแบบอื่นหรือไม่
ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML, XLSX และอื่นๆ
### ฉันจะได้รับการสนับสนุนหากฉันพบปัญหาใดๆ ระหว่างการใช้งานหรือไม่
ได้ คุณสามารถไปที่ฟอรัม Aspose.Tasks เพื่อขอความช่วยเหลือจากชุมชน หรือติดต่อฝ่ายสนับสนุนเพื่อขอความช่วยเหลือโดยตรง
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[เว็บไซต์](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
