---
date: 2026-04-03
description: เรียนรู้การจัดตารางงานในโครงการและวิธีการเพิ่มงานที่ทำซ้ำโดยใช้ Aspose.Tasks
  สำหรับ .NET รวมถึงการบันทึกโครงการเป็นไฟล์ MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: การทำซ้ำตามวันของปีใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: การจัดตารางงานโครงการโดยทำซ้ำตามวันของปีใน Aspose.Tasks
url: /th/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดตารางงานการจัดการโครงการด้วยการทำซ้ำตามวันของปีใน Aspose.Tasks

## บทนำ

การ **project management task scheduling** ที่มีประสิทธิภาพเป็นหัวใจหลักของโครงการที่ประสบความสำเร็จทุกโครงการ เมื่อภารกิจทำซ้ำเป็นประจำปี—เช่น การตรวจสอบประจำปี, ช่วงเวลาบำรุงรักษา, หรือการตรวจทานตามฤดูกาล—การจัดการการทำซ้ำเหล่านี้ด้วยตนเองอาจทำให้เกิดข้อผิดพลาดและเสียเวลา Aspose.Tasks สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยให้คุณกำหนดรูปแบบปี‑วันแบบโปรแกรมได้ ดังนั้นคุณจึงสามารถมุ่งเน้นที่สิ่งสำคัญที่สุดคือการส่งมอบคุณค่า ในบทเรียนนี้คุณจะได้เรียนรู้ **how to add recurring task** ตามวันเฉพาะของปีและดู **how to save project as MPP** อย่างชัดเจนเพื่อการผสานรวมกับ Microsoft Project อย่างราบรื่น.

## คำตอบสั้น
- **What does “year day repetition” mean?** มันกำหนดการทำงานในวันเฉพาะของเดือนเฉพาะแต่ละปี.  
- **Which API class creates the recurrence?** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **Can I set a start and end date?** ใช่, โดยใช้ `EndByRecurrenceRange`.  
- **What file format is produced?** โครงการจะถูกบันทึกเป็นไฟล์ MPP (`SaveFileFormat.Mpp`).  
- **Do I need a license for production?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่การประเมินผล.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มบทเรียน, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. Aspose.Tasks for .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก [website](https://releases.aspose.com/tasks/net/).  
2. Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสมด้วย Visual Studio หรือ IDE ที่คุณชื่นชอบสำหรับการพัฒนา .NET.  
3. Basic Knowledge of C#: ทำความคุ้นเคยกับพื้นฐานของภาษาโปรแกรม C# เพื่อให้สามารถทำตามตัวอย่างโค้ดได้.  
4. Project Management Concepts: ความเข้าใจในแนวคิดการจัดการโครงการและการจัดตารางงานจะช่วยให้คุณเข้าใจเนื้อหาบทเรียนได้อย่างมีประสิทธิภาพ.

## นำเข้า Namespaces

ก่อนที่เราจะเริ่มเขียนโค้ด, ให้เรานำเข้า namespaces ที่จำเป็นเพื่ออำนวยความสะดวกในการจัดการภารกิจด้วย Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

ต่อไปนี้เราจะแบ่งตัวอย่างที่ให้มาออกเป็นหลายขั้นตอนและอธิบายแต่ละขั้นตอนอย่างละเอียด.

## วิธีเพิ่มงานที่ทำซ้ำด้วยรูปแบบปี‑วัน

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

ที่นี่เราจะสร้างอ็อบเจกต์ `Project` ใหม่และโหลดไฟล์โครงการที่มีอยู่ชื่อ **Project1.mpp**.

### ขั้นตอนที่ 2: กำหนดพารามิเตอร์ของงานที่ทำซ้ำ

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

ในขั้นตอนนี้เรากำหนดพารามิเตอร์สำหรับงานที่ทำซ้ำของเรา เราระบุชื่องาน, ระยะเวลา, และรูปแบบการทำซ้ำ สำหรับการทำซ้ำประจำปี เราใช้ `YearlyRecurrencePattern` และตั้งค่าการทำซ้ำให้เกิดขึ้นใน **วันแรกของเดือนกรกฎาคม** ด้วย `ByYearDayRepetition` นอกจากนี้เรายังกำหนดช่วงการทำซ้ำตั้งแต่ 1 กรกฎาคม 2018 ถึง 1 กรกฎาคม 2019.

### ขั้นตอนที่ 3: เพิ่มงานลงในโครงการ

```csharp
project.RootTask.Children.Add(parameters);
```

ที่นี่เราจะเพิ่มพารามิเตอร์ของงานที่ทำซ้ำที่กำหนดไว้ลงในงานรากของโครงการ.

### ขั้นตอนที่ 4: บันทึกโครงการเป็นไฟล์ MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

สุดท้ายเราจะ **บันทึกโครงการเป็นไฟล์ MPP** เพื่อให้พร้อมเปิดใน Microsoft Project หรือโปรแกรมดูไฟล์ที่รองรับ.

## ทำไมเรื่องนี้ถึงสำคัญ

- **Automation** – ลดการป้อนข้อมูลงานประจำปีด้วยมือ ลดข้อผิดพลาดของมนุษย์.  
- **Consistency** – รับประกันว่ารูปแบบวัน‑เดือนเดียวกันจะถูกนำไปใช้ในหลายปี.  
- **Integration** – ไฟล์ MPP ที่ได้สามารถแชร์กับผู้มีส่วนได้ส่วนเสียที่ใช้ Microsoft Project.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **DateTime precision** – ตรวจสอบให้แน่ใจว่าเวลาเริ่มต้นสอดคล้องกับปฏิทินโครงการของคุณ; หากไม่เช่นนั้น งานอาจแสดงผลล่าช้า.  
- **Time zones** – API ทำงานกับอ็อบเจกต์ `DateTime`; พิจารณาการแปลงเป็น UTC หากแอปพลิเคชันของคุณครอบคลุมหลายภูมิภาค.  
- **License enforcement** – ในโหมดประเมินผล ไฟล์ MPP ที่บันทึกอาจมีลายน้ำ; ใช้ใบอนุญาตที่ถูกต้องสำหรับการใช้งานจริง.

## คำถามที่พบบ่อย

**Q: Can Aspose.Tasks handle complex recurrence patterns?**  
A: ใช่, Aspose.Tasks มีการสนับสนุนอย่างครบถ้วนสำหรับรูปแบบการทำซ้ำต่าง ๆ รวมถึงการทำซ้ำประจำปี, รายเดือน, รายสัปดาห์, และรายวัน.

**Q: Is Aspose.Tasks compatible with different project file formats?**  
A: แน่นอน, Aspose.Tasks รองรับรูปแบบไฟล์โครงการที่เป็นที่นิยมเช่น MPP, XML, และ CSV, ทำให้เข้ากันได้กับเครื่องมือการจัดการโครงการต่าง ๆ.

**Q: Does Aspose.Tasks offer documentation and support for developers?**  
A: ใช่, นักพัฒนาสามารถเข้าถึงเอกสารที่ครอบคลุมและขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks สำหรับคำถามหรือปัญหาต่าง ๆ ที่พบ.

**Q: Can I customize task properties like duration and start date using Aspose.Tasks?**  
A: แน่นอน, Aspose.Tasks มี API ที่แข็งแกร่งสำหรับการจัดการคุณสมบัติของงานแบบไดนามิก, ให้ผู้พัฒนาสามารถปรับระยะเวลา, วันที่เริ่มต้น, ความขึ้นต่อกัน, และอื่น ๆ ได้.

**Q: Is Aspose.Tasks suitable for both small‑scale and enterprise‑level projects?**  
A: จริง ๆ แล้ว, Aspose.Tasks ถูกออกแบบมาเพื่อรองรับความต้องการของนักพัฒนาที่ทำงานกับโครงการทุกขนาด, ตั้งแต่งานเดี่ยวจนถึงโครงการระดับองค์กรขนาดใหญ่.

---

**อัปเดตล่าสุด:** 2026-04-03  
**ทดสอบด้วย:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}