---
title: การทำซ้ำการทำงานรายวันใน Aspose.Tasks
linktitle: การทำซ้ำการทำงานรายวันใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีสร้างงานที่เกิดซ้ำรายวันในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เพิ่มผลผลิตและองค์กรได้อย่างง่ายดาย
weight: 26
url: /th/net/calendar-scheduling/daily-work-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การทำซ้ำการทำงานรายวันใน Aspose.Tasks

## การแนะนำ

Aspose.Tasks สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย ในบรรดาคุณสมบัติมากมายคือความสามารถในการจัดการงานที่เกิดซ้ำได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกฟังก์ชันการทำงานซ้ำในแต่ละวัน ซึ่งช่วยให้สามารถสร้างงานที่ทำซ้ำทุกวันภายในโปรเจ็กต์ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
-  Aspose.Tasks สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- ความคุ้นเคยกับไฟล์ Microsoft Project (.mpp)

## นำเข้าเนมสเปซ

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

มาแบ่งตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

ขั้นแรก ให้โหลดไฟล์โครงการโดยใช้นามสกุล`Project` ระดับ:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ขั้นตอนที่ 2: กำหนดพารามิเตอร์งานที่เกิดซ้ำ

กำหนดพารามิเตอร์สำหรับงานที่เกิดซ้ำ:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## ขั้นตอนที่ 3: ตั้งค่าปฏิทินและวันที่เริ่มต้นงาน

กำหนดปฏิทินและวันที่เริ่มต้นสำหรับงาน:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ Aspose.Tasks สำหรับ .NET เพื่อสร้างงานที่เกิดซ้ำโดยมีงานซ้ำในแต่ละวัน ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการงานภายในโครงการของคุณได้อย่างมีประสิทธิภาพ ทำให้มั่นใจได้ถึงขั้นตอนการทำงานและองค์กรที่ราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งรูปแบบการเกิดซ้ำเพิ่มเติมได้หรือไม่

A1: ได้ คุณสามารถปรับพารามิเตอร์ เช่น วันที่เริ่มต้น หมายเลขที่เกิดขึ้น และช่วงเวลาการเกิดซ้ำ เพื่อปรับแต่งรูปแบบการเกิดซ้ำตามความต้องการของคุณ

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่

ตอบ 2: ใช่ Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และการผสานรวมที่ราบรื่น

### คำถามที่ 3: ฉันจะจัดการกับข้อยกเว้นหรือการปรับเปลี่ยนงานที่เกิดซ้ำได้อย่างไร

A3: Aspose.Tasks มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการจัดการข้อยกเว้นและการแก้ไขภายในงานที่เกิดซ้ำ ช่วยให้มีความยืดหยุ่นและปรับแต่งได้

### คำถามที่ 4: ฉันสามารถส่งออกโปรเจ็กต์เป็นรูปแบบอื่นได้หรือไม่

ตอบ 4: แน่นอนว่า Aspose.Tasks ให้การสนับสนุนการส่งออกโปรเจ็กต์เป็นรูปแบบต่างๆ รวมถึง PDF, HTML, XML และอื่นๆ อีกมากมาย ช่วยให้การแบ่งปันและการทำงานร่วมกันทำได้ง่าย

### คำถามที่ 5: Aspose.Tasks ให้การสนับสนุนทางเทคนิคหรือไม่

A5: ใช่ Aspose.Tasks ให้การสนับสนุนด้านเทคนิคอย่างครอบคลุมผ่านฟอรัม ซึ่งคุณสามารถขอความช่วยเหลือ แบ่งปันประสบการณ์ และมีส่วนร่วมกับผู้ใช้รายอื่นได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
