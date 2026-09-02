---
date: 2026-04-03
description: เรียนรู้วิธีใช้ Aspose.Tasks เพื่อเพิ่มงานที่ทำซ้ำในโครงการและบันทึกโครงการเป็นไฟล์
  MPP คู่มือนี้แสดงคุณลักษณะการทำซ้ำตามปี สัปดาห์ วัน อย่างละเอียดขั้นตอนต่อขั้นตอน.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: การทำซ้ำตาม ปี สัปดาห์ วัน ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีใช้ Aspose.Tasks – การทำซ้ำตามปี สัปดาห์ วัน
url: /th/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การทำซ้ำตามปี สัปดาห์ วันใน Aspose.Tasks

## บทนำ

เมื่อคุณต้องการ **how to use Aspose.Tasks** เพื่อจัดการตารางงานที่ทำซ้ำซับซ้อน ไลบรารีจะให้การควบคุมระดับละเอียดต่อรูปแบบประจำปี ในบทแนะนำนี้เราจะสาธิตการสร้างงานที่ทำซ้ำในวันทำงานเฉพาะของเดือนที่กำหนด ครอบคลุมหลายปี เมื่อเสร็จคุณจะสามารถ **add recurring task project** และ **save project as MPP** ด้วยเพียงไม่กี่บรรทัดของ C#.

## คำตอบเร็ว
- **What does “Repetition by Year Week Day” mean?** มันทำซ้ำงานในวันทำงานที่เลือก (เช่น วันอาทิตย์แรก) ของเดือนที่กำหนดในแต่ละปี.  
- **Which .NET versions are supported?** ทั้งหมด .NET Framework และ .NET Core/5/6 เวอร์ชันล่าสุด.  
- **Do I need a license to run the code?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Can I change the recurrence range?** ได้ – คุณสามารถตั้งค่าวันเริ่มต้น, วันสิ้นสุด หรือจำนวนครั้งที่กำหนด.  
- **Is the output an MPP file?** แน่นอน – โครงการจะถูกบันทึกเป็นไฟล์ MPP พร้อมสำหรับ Microsoft Project.

## ฟีเจอร์ “Repetition by Year Week Day” คืออะไร?

ฟีเจอร์นี้ให้คุณกำหนดการทำซ้ำประจำปีที่มุ่งเป้าไปที่ **day of the week** เฉพาะ (เช่น Sunday) และ **position** ภายในเดือน (แรก, ที่สอง, สุดท้าย ฯลฯ) เหมาะสำหรับงานเช่น การตรวจสอบไตรมาส, การตรวจสอบประจำปี, หรือเหตุการณ์ใด ๆ ที่ตามจังหวะตามปฏิทิน

## ทำไมต้องใช้ Aspose.Tasks สำหรับงานที่ทำซ้ำ?

- **Precision** – การควบคุมเต็มรูปแบบต่อเดือน, วันทำงาน, และตำแหน่งลำดับ.  
- **Compatibility** – สร้างไฟล์ MPP แบบดั้งเดิมที่เปิดได้อย่างไม่มีข้อผิดพลาดใน Microsoft Project.  
- **No COM interop** – API .NET แท้ ๆ ไม่ต้องติดตั้ง Office.  
- **Scalability** – ทำงานได้ทั้งโครงการขนาดเล็กและตารางระดับองค์กร.

## ข้อกำหนดเบื้องต้น

ก่อนจะลงลึกในโค้ด, ตรวจสอบว่าคุณมี:

1. **Basic .NET knowledge** – ความคุ้นเคยกับ C# และแนวคิดเชิงวัตถุ  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดจาก [download link](https://releases.aspose.com/tasks/net/) แล้วเพิ่ม DLL ไปยังโปรเจคของคุณ.  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) มีรายละเอียดครบถ้วนของทุกคลาส.  
4. **A development IDE** – Visual Studio, Rider หรือเครื่องมือแก้ไข .NET ที่เข้ากันได้.

เมื่อคุณพร้อมแล้ว, มาดูการนำไปใช้กัน

## วิธีใช้ Aspose.Tasks สำหรับงานที่ทำซ้ำ

### การนำเข้า Namespaces ที่จำเป็น

แรก, นำ Namespaces ที่จำเป็นเข้าสู่ขอบเขตเพื่อให้คุณทำงานกับโครงการ, งาน, และตัวเลือกการบันทึกได้

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### ขั้นตอนที่ 1: เริ่มต้น Project และพารามิเตอร์ของงาน

สร้างอินสแตนซ์ `Project` ใหม่, จากนั้นกำหนดอ็อบเจ็กต์ `RecurringTaskParameters` ที่อธิบายรูปแบบการทำซ้ำ

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** ปรับ `Month`, `WeekDay`, และ `Position` ให้ตรงกับตารางเวลาจริงของคุณ

### ขั้นตอนที่ 2: เพิ่มพารามิเตอร์ลงใน Project

แทรกการกำหนดงานที่ทำซ้ำลงในรากของโปรเจค

```csharp
project.RootTask.Children.Add(parameters);
```

### ขั้นตอนที่ 3: บันทึก Project เป็น MPP

สุดท้าย, บันทึกโปรเจคเป็นไฟล์ MPP เพื่อให้สามารถเปิดใน Microsoft Project หรือโปรแกรมดูที่เข้ากันได้

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> นี้แสดงการ **save project as mpp** ด้วยบรรทัดโค้ดเดียว

## ปัญหาทั่วไปและวิธีแก้

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| ไม่มีงานปรากฏหลังเปิดไฟล์ MPP | วันที่ช่วงการทำซ้ำอยู่นอกปฏิทินของโปรเจค | ตรวจสอบให้แน่ใจว่า `Start` และ `Finish` อยู่ในช่วงเวลาทำงานของโปรเจค |
| ข้อยกเว้น `ArgumentNullException` บน `Add` | `parameters` เป็น null หรือไม่ได้กำหนดค่าเต็มที่ | ตรวจสอบให้ทุกคุณสมบัติที่จำเป็น (TaskName, Duration, RecurrencePattern) ถูกตั้งค่า |
| เลือกวันทำงานผิด | `WeekDay` enum มีค่าไม่ตรงกัน | ใช้ `DayOfWeek.Monday` … `DayOfWeek.Sunday` ตามต้องการ |

## คำถามที่พบบ่อย

**Q: สามารถปรับแต่งรูปแบบการทำซ้ำนอกเหนือจากตัวอย่างที่ให้ไว้ได้หรือไม่?**  
**A:** ได้, Aspose.Tasks ให้คุณผสาน `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, หรือแม้แต่ `RecurrenceRange` ที่กำหนดเอง เพื่อให้ตรงกับตารางใด ๆ

**Q: Aspose.Tasks for .NET เข้ากันได้กับซอฟต์แวร์การจัดการโครงการอื่นหรือไม่?**  
**A:** แน่นอน – ไลบรารีสามารถอ่านและเขียนรูปแบบ MPP, XML, และ Primavera ทำให้การแลกเปลี่ยนข้อมูลเป็นไปอย่างราบรื่น

**Q: ฉันจะจัดการข้อยกเว้นหรือการแก้ไขงานที่ทำซ้ำอย่างไร?**  
**A:** ใช้คลาส `ExceptionTask` เพื่อสร้างการแทนที่สำหรับเหตุการณ์เฉพาะ, หรือแก้ไข `RecurringTaskParameters` แล้วบันทึกโปรเจคใหม่

**Q: Aspose.Tasks รองรับโซลูชันบนคลาวด์หรือไม่?**  
**A:** ใช่, คุณสามารถรัน API ใน Azure Functions, AWS Lambda, หรือบริการคลาวด์ที่เข้ากันได้กับ .NET ใด ๆ

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for .NET หรือไม่?**  
**A:** มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.Tasks for .NET จาก [website](https://releases.aspose.com/), เพื่อสำรวจคุณสมบัติก่อนตัดสินใจซื้อ

**Q: ฉันจะเพิ่มงานที่ทำซ้ำลงในโปรเจคที่มีอยู่โดยไม่เขียนทับข้อมูลอื่นได้อย่างไร?**  
**A:** โหลดโปรเจคที่มีอยู่ด้วย `new Project("Existing.mpp")`, เพิ่ม `RecurringTaskParameters` ไปที่ `RootTask.Children`, แล้ว `Save` ไฟล์

## สรุป

ด้วยการเชี่ยวชาญ **how to use Aspose.Tasks** สำหรับสถานการณ์ **Repetition by Year Week Day**, คุณจะได้ความสามารถในการ **add recurring task project** ที่สอดคล้องกับปฏิทินจริงและ **save project as MPP** เพื่อการทำงานร่วมกันอย่างราบรื่น นำโค้ดตัวอย่างเหล่านี้ไปใช้ในโซลูชันของคุณเพื่อเพิ่มความแม่นยำของการกำหนดเวลาและลดความพยายามด้วยมือ

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}