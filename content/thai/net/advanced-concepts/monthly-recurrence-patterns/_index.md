---
title: การจัดการรูปแบบการเกิดซ้ำรายเดือนใน Aspose.Tasks
linktitle: การจัดการรูปแบบการเกิดซ้ำรายเดือนใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการรูปแบบการเกิดซ้ำรายเดือนใน Aspose.Tasks for .NET ด้วยบทช่วยสอนทีละขั้นตอนนี้
type: docs
weight: 18
url: /th/net/advanced-concepts/monthly-recurrence-patterns/
---
## การแนะนำ

Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม หนึ่งในฟังก์ชันสำคัญที่มีให้คือความสามารถในการจัดการงานที่เกิดซ้ำได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีการทำงานกับรูปแบบการเกิดซ้ำรายเดือนโดยใช้ Aspose.Tasks ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งข้อกำหนดเบื้องต้นต่อไปนี้:

## นำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณแล้ว:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

ตอนนี้ เรามาแจกแจงกระบวนการจัดการรูปแบบการเกิดซ้ำรายเดือนออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: เริ่มต้นโครงการ

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ขั้นตอนที่ 2: ตั้งค่าพารามิเตอร์งานที่เกิดซ้ำ

กำหนดพารามิเตอร์สำหรับงานที่เกิดซ้ำ รวมถึงชื่องาน ระยะเวลา และรูปแบบการเกิดซ้ำ:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## ขั้นตอนที่ 3: เพิ่มพารามิเตอร์ให้กับโครงการ

```csharp
project.RootTask.Children.Add(parameters);
```

## ขั้นตอนที่ 4: บันทึกโครงการ

บันทึกโปรเจ็กต์ที่แก้ไขด้วยงานที่เกิดซ้ำ:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## บทสรุป

การจัดการรูปแบบการเกิดซ้ำรายเดือนใน Aspose.Tasks สำหรับ .NET นั้นตรงไปตรงมาและมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถสร้างงานที่เกิดซ้ำด้วยช่วงเวลารายเดือนและช่วงการเกิดซ้ำที่เฉพาะเจาะจงได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่

A1: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึง MPP, MPT, XML และ MPX

### คำถามที่ 2: ฉันสามารถปรับแต่งรูปแบบการเกิดซ้ำเพิ่มเติมได้หรือไม่

ตอบ 2: ใช่ Aspose.Tasks มีตัวเลือกมากมายสำหรับกำหนดรูปแบบการเกิดซ้ำ รวมถึงรายวัน รายสัปดาห์ รายเดือน และรายปี

### คำถามที่ 3: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่

 A3: ได้ คุณสามารถขอรับ Aspose.Tasks รุ่นทดลองใช้ฟรีได้จากเว็บไซต์[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร

 A4: คุณสามารถขอความช่วยเหลือและมีส่วนร่วมในการอภิปรายเกี่ยวกับ[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### คำถามที่ 5: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถซื้อใบอนุญาตสำหรับ Aspose.Tasks ได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy)