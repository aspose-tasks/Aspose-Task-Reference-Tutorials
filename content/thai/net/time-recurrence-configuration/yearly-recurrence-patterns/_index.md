---
title: ต้นแบบรูปแบบการเกิดซ้ำรายปีใน Aspose.Tasks สำหรับ .NET
linktitle: การกำหนดค่ารูปแบบการเกิดซ้ำรายปีใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดค่ารูปแบบการเกิดซ้ำรายปีใน Aspose.Tasks สำหรับ .NET พัฒนาทักษะการจัดการโครงการของคุณด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 18
url: /th/net/time-recurrence-configuration/yearly-recurrence-patterns/
---
## การแนะนำ
ในโลกที่มีการเปลี่ยนแปลงตลอดเวลาของการจัดการโครงการ การจัดการงานที่เกิดซ้ำอย่างมีประสิทธิภาพถือเป็นส่วนสำคัญ Aspose.Tasks for .NET มอบโซลูชันอันทรงพลังในการกำหนดค่ารูปแบบการเกิดซ้ำรายปี ช่วยให้คุณสามารถปรับปรุงการจัดกำหนดการและการจัดการโครงการของคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีตั้งค่ารูปแบบการเกิดซ้ำรายปีโดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้เกี่ยวกับการทำงานของ C# และ .NET framework
-  ติดตั้งไลบรารี Aspose.Tasks แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการจัดการโครงการ
## นำเข้าเนมสเปซ
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ Aspose.Tasks ใหม่:
```csharp
var project = new Project("Your Document Directory" + "Project1.mpp");
```
## ขั้นตอนที่ 2: กำหนดพารามิเตอร์งานที่เกิดซ้ำ
สร้างชุดพารามิเตอร์สำหรับงานที่เกิดซ้ำ:
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
## ขั้นตอนที่ 3: เพิ่มพารามิเตอร์ในโครงการ
รวมพารามิเตอร์ในรายการงานของโครงการ:
```csharp
project.RootTask.Children.Add(parameters);
```
## ขั้นตอนที่ 4: บันทึกโครงการ
บันทึกโปรเจ็กต์ด้วยรูปแบบการเกิดซ้ำที่กำหนดค่าไว้:
```csharp
project.Save("Your Document Directory" + "WorkWithYearlyRecurrencePattern_out.mpp", SaveFileFormat.Mpp);
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการกำหนดค่ารูปแบบการเกิดซ้ำรายปีใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณจะสามารถเพิ่มความสามารถในการจัดการโครงการและจัดการงานที่เกิดซ้ำได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### จำเป็นต้องมี Aspose License ที่ถูกต้องเพื่อให้ตัวอย่างนี้ใช้งานได้หรือไม่
 ใช่ จำเป็นต้องมี Aspose License ที่ถูกต้อง คุณสามารถซื้อใบอนุญาตแบบเต็มหรือรับใบอนุญาตชั่วคราว 30 วัน[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันสามารถปรับแต่งรูปแบบการเกิดซ้ำเพิ่มเติมได้หรือไม่
 อย่างแน่นอน! ปรับพารามิเตอร์ใน`YearlyRecurrencePattern` และ`EndByRecurrenceRange` ชั้นเรียนเพื่อตอบสนองความต้องการเฉพาะของคุณ
### มีข้อกำหนดเบื้องต้นสำหรับการใช้ Aspose.Tasks สำหรับ .NET หรือไม่
 ตรวจสอบให้แน่ใจว่าคุณมีความรู้เกี่ยวกับ C# และ .NET รวมถึงติดตั้งไลบรารี Aspose.Tasks ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/net/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและช่วยเหลือชุมชน
### ฉันสามารถทดลองใช้ Aspose.Tasks ฟรีก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).