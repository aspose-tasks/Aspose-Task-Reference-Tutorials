---
date: 2026-04-01
description: เรียนรู้วิธีตั้งการทำซ้ำใน Aspose.Tasks สำหรับ .NET, เพิ่มงานที่ทำซ้ำและอัตโนมัติงานที่ทำซ้ำตามเดือน,
  สัปดาห์, และวัน.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: การทำซ้ำตามเดือน สัปดาห์ และวันใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีตั้งการทำซ้ำใน Aspose.Tasks (เดือน, สัปดาห์, วัน)
url: /th/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งการทำซ้ำใน Aspose.Tasks (เดือน, สัปดาห์, วัน)

## บทนำ

หากคุณต้องการ **วิธีตั้งการทำซ้ำ** สำหรับงานในโครงการ Aspose.Tasks for .NET จะมอบวิธีการเชิงโปรแกรมที่สะอาดและง่ายต่อการเพิ่มคำนิยามงานที่ทำซ้ำที่ทำงานตามเดือน, สัปดาห์ หรือวัน ในบทเรียนนี้เราจะเดินผ่านตัวอย่างจากโลกจริงที่แสดงให้คุณเห็นวิธี **เพิ่มงานที่ทำซ้ำ**, **ทำงานที่ทำซ้ำโดยอัตโนมัติ**, และจัดการพวกมันโดยตรงจากโค้ด C# เมื่อเสร็จสิ้นคุณจะพร้อมผสานความสามารถนี้เข้าสู่โซลูชันการกำหนดเวลา หรือการจัดการโครงการใด ๆ

## คำตอบสั้น
- **'recurrence' หมายถึงอะไรใน Aspose.Tasks?** มันกำหนดรูปแบบ (รายวัน, รายสัปดาห์, รายเดือน) ที่สร้างอินสแตนซ์ของงานโดยอัตโนมัติในช่วงวันที่  
- **เมธอดหลักใดที่สร้างการทำซ้ำ?** `RecurringTaskParameters` combined with a specific `RecurrencePattern`.  
- **ฉันต้องใช้ไลเซนส์เพื่อรันโค้ดนี้หรือไม่?** รุ่นทดลองใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ฉันสามารถกำหนดงานรายสัปดาห์แทนรายเดือนได้หรือไม่?** ได้ – เปลี่ยน `MonthlyRecurrencePattern` เป็น `WeeklyRecurrencePattern`.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 and later.

## การทำซ้ำใน Aspose.Tasks คืออะไร?

การทำซ้ำคือชุดของกฎที่บอกให้ Aspose.Tasks สร้างอินสแตนซ์ของงานในช่วงเวลาที่กำหนด—รายวัน, รายสัปดาห์, หรือรายเดือน—โดยไม่ต้องทำซ้ำด้วยตนเอง ฟีเจอร์นี้สำคัญสำหรับโครงการที่มีกิจกรรมประจำเช่น การประชุมสถานะ, การตรวจสอบ, หรือการบำรุงรักษา

## ทำไมต้องใช้ฟีเจอร์การทำซ้ำ?

- **ประหยัดเวลา:** ไม่ต้องคัดลอก‑วางงานด้วยตนเอง  
- **ลดข้อผิดพลาด:** ไลบรารีรับประกันวันที่และระยะเวลาที่สอดคล้องกัน  
- **ความยืดหยุ่น:** รวมรูปแบบ (เช่น “วันอาทิตย์แรกของทุก 2 เดือน”)  
- **การอัตโนมัติ:** เหมาะสำหรับการสร้างตารางเวลาใน CI pipelines หรือเครื่องมือรายงาน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. **ความเข้าใจพื้นฐานของ C#** – you’ll be writing a few lines of C# code.  
2. **ติดตั้ง Aspose.Tasks for .NET** – grab it from the [download page](https://releases.aspose.com/tasks/net/).  
3. **ไฟล์โครงการ .mpp** – we’ll use `Project1.mpp` as the source file.

## นำเข้า Namespaces

เพื่อเริ่มต้น, นำเข้า namespaces ของ Aspose.Tasks ที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

เราสร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ Microsoft Project ที่มีอยู่

### ขั้นตอนที่ 2: กำหนดพารามิเตอร์ของงานที่ทำซ้ำ

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

ที่นี่เราจะ **สร้างพารามิเตอร์ของงานที่ทำซ้ำ**:

- **TaskName** – ชื่อของงานที่สร้างขึ้น.  
- **Duration** – ระยะเวลาที่แต่ละเหตุการณ์ดำเนินต่อเนื่อง.  
- **RecurrencePattern** – รูปแบบรายเดือนที่ทำซ้ำทุก 2 เดือนในวันอาทิตย์แรก.  
- **RecurrenceRange** – วันที่เริ่มต้นและสิ้นสุดที่กำหนดช่วงเวลาตาราง.

### ขั้นตอนที่ 3: เพิ่มงานที่ทำซ้ำลงในโครงการ

```csharp
project.RootTask.Children.Add(parameters);
```

บรรทัดนี้ **เพิ่มงานที่ทำซ้ำ** ไปยังรากของโครงสร้างโครงการ

### ขั้นตอนที่ 4: บันทึกโครงการที่อัปเดต

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

โครงการจะถูกบันทึกเป็นไฟล์ `.mpp` ใหม่ที่ตอนนี้มีตารางเวลาที่ทำอัตโนมัติ

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **งานไม่ปรากฏ** | ช่วงการทำซ้ำอยู่นอกวันที่ของโครงการ. | ตรวจสอบค่า `Start` และ `Finish` ว่าอยู่ในปฏิทินของโครงการ. |
| **วันสัปดาห์ไม่ถูกต้อง** | ค่า enum `WeekDay` ไม่ตรงกัน. | ใช้ `DayOfWeek.Monday` … `DayOfWeek.Sunday` ตามต้องการ. |
| **ข้อยกเว้นไลเซนส์** | รันโดยไม่มีไลเซนส์ที่ถูกต้องในสภาพการผลิต. | ใช้ไลเซนส์ชั่วคราวหรือเต็มก่อนบันทึก. |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถปรับแต่งรูปแบบการทำซ้ำได้เกินตัวอย่างที่ให้หรือไม่?

A1: ใช่, Aspose.Tasks for .NET มีตัวเลือกการปรับแต่งรูปแบบการทำซ้ำอย่างกว้างขวาง, ทำให้คุณสามารถปรับให้ตรงกับความต้องการเฉพาะของคุณ

### Q2: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for .NET หรือไม่?

A2: ใช่, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Tasks for .NET จาก [releases page](https://releases.aspose.com/)

### Q3: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks for .NET ได้อย่างไร?

A3: คุณสามารถขอความช่วยเหลือและเข้าร่วมกับชุมชนได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

### Q4: มีไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks for .NET หรือไม่?

A4: ใช่, คุณสามารถรับไลเซนส์ชั่วคราวจาก [purchase page](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล

### Q5: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Tasks for .NET ได้จากที่ไหน?

A5: คุณสามารถอ้างอิงเอกสารโดยละเอียดที่ [documentation](https://reference.aspose.com/tasks/net/) บนเว็บไซต์ของ Aspose เพื่อคำแนะนำเชิงลึกในการใช้ไลบรารี

---

**อัปเดตล่าสุด:** 2026-04-01  
**ทดสอบกับ:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}