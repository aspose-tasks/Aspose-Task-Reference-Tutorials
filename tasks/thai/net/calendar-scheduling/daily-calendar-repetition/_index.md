---
title: การทำซ้ำปฏิทินรายวันใน Aspose.Tasks
linktitle: การทำซ้ำปฏิทินรายวันใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีสร้างงานที่เกิดซ้ำด้วยการทำซ้ำปฏิทินรายวันใน Aspose.Tasks สำหรับ .NET เพิ่มประสิทธิภาพการจัดการโครงการได้อย่างง่ายดาย
weight: 25
url: /th/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การทำซ้ำปฏิทินรายวันใน Aspose.Tasks

## การแนะนำ

 Aspose.Tasks สำหรับ .NET มอบชุดเครื่องมืออันทรงพลังสำหรับการจัดการงานและโครงการโดยทางโปรแกรม คุณสมบัติที่โดดเด่นประการหนึ่งคือความสามารถในการจัดการการทำซ้ำปฏิทินรายวันได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้`DailyCalendarRepetition` คลาสพร้อมกับคลาสอื่น ๆ ที่เกี่ยวข้องเพื่อสร้างงานที่เกิดซ้ำโดยมีการทำซ้ำรายวันตามปฏิทินที่ระบุ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าต่อไปนี้:

1.  การติดตั้ง: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

2. การนำเข้าเนมสเปซ: นำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## ขั้นตอนที่ 1: เริ่มต้นโครงการ

ขั้นแรก เราต้องโหลดโปรเจ็กต์ที่มีอยู่หรือสร้างโปรเจ็กต์ใหม่เพื่อใช้งาน:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ขั้นตอนที่ 2: กำหนดปฏิทิน

ต่อไป เราจะสร้างปฏิทินที่มีระยะเวลา 24 ชั่วโมงและเชื่อมโยงกับโครงการ:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์งานที่เกิดซ้ำ

ตอนนี้ เรามาตั้งค่าพารามิเตอร์สำหรับงานที่เกิดซ้ำของเรากันดีกว่า เรากำหนดชื่อ ระยะเวลา รูปแบบการเกิดซ้ำ และช่วง:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## ขั้นตอนที่ 4: ตั้งค่าปฏิทินสำหรับงาน

เชื่อมโยงปฏิทินที่กำหนดกับงาน:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## ขั้นตอนที่ 5: เพิ่มงานในโครงการ

เพิ่มงานด้วยพารามิเตอร์ที่กำหนดให้กับโครงการ:

```csharp
project.RootTask.Children.Add(parameters);
```

## ขั้นตอนที่ 6: บันทึกโครงการ

สุดท้าย ให้บันทึกโปรเจ็กต์ด้วยงานที่เกิดซ้ำที่เพิ่มเข้ามา:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

ตอนนี้คุณได้สร้างโครงการที่มีงานที่เกิดซ้ำซึ่งกำหนดให้ทำซ้ำทุกวันตามปฏิทินแบบ 24 ชั่วโมงโดยใช้ Aspose.Tasks สำหรับ .NET สำเร็จแล้ว!

## บทสรุป

ในบทช่วยสอนนี้ เราได้สาธิตวิธีใช้ Aspose.Tasks สำหรับ .NET เพื่อจัดการการทำซ้ำปฏิทินรายวันอย่างมีประสิทธิภาพ เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถรวมงานที่เกิดซ้ำเข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพการทำงานและองค์กร

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งระยะเวลาของการทำซ้ำแต่ละครั้งได้หรือไม่

A1: ได้ คุณสามารถปรับระยะเวลาของการทำซ้ำแต่ละครั้งได้ตามความต้องการของคุณโดยการแก้ไขพารามิเตอร์ในโค้ด

### คำถามที่ 2: เป็นไปได้ไหมที่จะตั้งค่าปฏิทินที่แตกต่างกันสำหรับงานที่แตกต่างกันภายในโปรเจ็กต์เดียวกัน

ตอบ 2: แน่นอน Aspose.Tasks ช่วยให้คุณสามารถกำหนดปฏิทินเฉพาะให้กับงานแต่ละงานได้ โดยให้ความยืดหยุ่นในการจัดกำหนดการ

### คำถามที่ 3: Aspose.Tasks รองรับรูปแบบการเกิดซ้ำอื่นๆ นอกเหนือจากรายวันหรือไม่

A3: ใช่ Aspose.Tasks มีรูปแบบการเกิดซ้ำที่หลากหลาย เช่น รายสัปดาห์ รายเดือน รายปี ฯลฯ เพื่อรองรับความต้องการของโครงการที่หลากหลาย

### คำถามที่ 4: ฉันสามารถเห็นภาพงานที่เกิดซ้ำซึ่งสร้างโดยใช้ Aspose.Tasks ได้หรือไม่

ตอบ 4: แน่นอนว่า Aspose.Tasks มีตัวเลือกการแสดงภาพเพื่อช่วยให้คุณวิเคราะห์และติดตามงานที่เกิดซ้ำได้อย่างมีประสิทธิภาพ

### คำถามที่ 5: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่

 A5: ได้ คุณสามารถทดลองใช้ Aspose.Tasks ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
