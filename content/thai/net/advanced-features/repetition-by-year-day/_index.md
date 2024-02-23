---
title: การทำซ้ำตามวันปีใน Aspose.Tasks
linktitle: การทำซ้ำตามวันปีใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการกับการทำซ้ำวันปีใน Aspose.Tasks สำหรับ .NET เพื่อปรับปรุงการจัดการงานที่เกิดซ้ำอย่างมีประสิทธิภาพ
type: docs
weight: 27
url: /th/net/advanced-features/repetition-by-year-day/
---
## การแนะนำ

ในขอบเขตของการจัดการโครงการ การกำหนดเวลางานที่มีประสิทธิภาพและการเกิดซ้ำมีบทบาทสำคัญในการรับประกันการดำเนินการตามเวลาที่กำหนดและขั้นตอนการทำงานที่ราบรื่น Aspose.Tasks for .NET นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับนักพัฒนาเพื่อจัดการกับงานที่เกิดซ้ำภายในแอปพลิเคชันของตนได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกความซับซ้อนของการทำงานกับการทำซ้ำในแต่ละวันโดยใช้ Aspose.Tasks ซึ่งให้คำแนะนำที่ครอบคลุมสำหรับการสร้างงานที่เกิดซ้ำตามรูปแบบรายปี

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).
   
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสมด้วย Visual Studio หรือ IDE ที่ต้องการอื่นๆ สำหรับการพัฒนา .NET

3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C# เพื่อปฏิบัติตามพร้อมกับตัวอย่างโค้ด

4. แนวคิดการจัดการโครงการ: การทำความเข้าใจแนวคิดการจัดการโครงการและการกำหนดเวลางานจะช่วยในการเข้าใจแนวคิดการสอนได้อย่างมีประสิทธิภาพ

## นำเข้าเนมสเปซ

ก่อนที่เราจะเริ่มเขียนโค้ด เรามานำเข้าเนมสเปซที่จำเป็นเพื่ออำนวยความสะดวกในการจัดการงานของเราโดยใช้ Aspose.Tasks สำหรับ .NET ก่อน

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนและอธิบายแต่ละขั้นตอนโดยละเอียด

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 ที่นี่เราเริ่มต้นใหม่`Project` object และโหลดไฟล์โปรเจ็กต์ที่มีอยู่ชื่อ "Project1.mpp"

## ขั้นตอนที่ 2: กำหนดพารามิเตอร์งานที่เกิดซ้ำ

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

 ในขั้นตอนนี้ เรากำหนดพารามิเตอร์สำหรับงานที่เกิดซ้ำของเรา เราระบุชื่องาน ระยะเวลา และรูปแบบการเกิดซ้ำ สำหรับการเกิดซ้ำทุกปี เราใช้`YearlyRecurrencePattern` และกำหนดให้เกิดซ้ำในวันที่ 1 กรกฎาคม โดยใช้`ByYearDayRepetition`, นอกจากนี้ เรายังกำหนดช่วงการเกิดซ้ำตั้งแต่วันที่ 1 กรกฎาคม 2018 ถึงวันที่ 1 กรกฎาคม 2019

## ขั้นตอนที่ 3: เพิ่มงานในโครงการ

```csharp
project.RootTask.Children.Add(parameters);
```

ที่นี่ เราเพิ่มพารามิเตอร์งานที่เกิดซ้ำที่กำหนดไว้ให้กับงานรากของโครงการ

## ขั้นตอนที่ 4: บันทึกโครงการ

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

สุดท้าย เราจะบันทึกไฟล์โปรเจ็กต์ที่แก้ไขพร้อมกับงานที่เกิดซ้ำที่เพิ่มเข้ามา

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการทำงานกับการทำซ้ำวันปีใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ นักพัฒนาสามารถรวมฟังก์ชันงานที่เกิดซ้ำเข้ากับแอปพลิเคชันของตนได้อย่างราบรื่น ช่วยเพิ่มขีดความสามารถในการจัดการโครงการ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สามารถจัดการรูปแบบการเกิดซ้ำที่ซับซ้อนได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks ให้การสนับสนุนที่ครอบคลุมสำหรับรูปแบบการเกิดซ้ำต่างๆ รวมถึงรูปแบบที่ซับซ้อน เช่น การทำซ้ำรายปี รายเดือน รายสัปดาห์ และรายวัน

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่

คำตอบ 2: แน่นอน Aspose.Tasks รองรับรูปแบบไฟล์โปรเจ็กต์ยอดนิยม เช่น MPP, XML และ CSV ทำให้มั่นใจได้ถึงความเข้ากันได้กับเครื่องมือการจัดการโปรเจ็กต์ต่างๆ

### คำถามที่ 3: Aspose.Tasks มีเอกสารและการสนับสนุนสำหรับนักพัฒนาหรือไม่

ตอบ 3: ได้ นักพัฒนาสามารถเข้าถึงเอกสารประกอบที่ครอบคลุมและขอความช่วยเหลือจากฟอรัมชุมชน Aspose.Tasks สำหรับคำถามหรือปัญหาที่พวกเขาพบ

### คำถามที่ 4: ฉันสามารถปรับแต่งคุณสมบัติของงาน เช่น ระยะเวลาและวันที่เริ่มต้นโดยใช้ Aspose.Tasks ได้หรือไม่

ตอบ 4: แน่นอน Aspose.Tasks มี API ที่มีประสิทธิภาพเพื่อจัดการคุณสมบัติของงานแบบไดนามิก ช่วยให้นักพัฒนาสามารถปรับแต่งระยะเวลา วันที่เริ่มต้น การขึ้นต่อกัน และอื่นๆ อีกมากมาย

### คำถามที่ 5: Aspose.Tasks เหมาะสำหรับทั้งโครงการขนาดเล็กและระดับองค์กรหรือไม่

A5: แท้จริงแล้ว Aspose.Tasks ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของนักพัฒนาที่ทำงานในโครงการทุกขนาด ตั้งแต่งานเดี่ยวไปจนถึงโครงการระดับองค์กรขนาดใหญ่