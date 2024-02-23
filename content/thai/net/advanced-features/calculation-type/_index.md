---
title: ประเภทการคำนวณใน Aspose.Tasks
linktitle: ประเภทการคำนวณใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีปรับแต่งการคำนวณมูลค่าในโครงการ .NET ด้วยประเภทการคำนวณในไลบรารี Aspose.Tasks
type: docs
weight: 30
url: /th/net/advanced-features/calculation-type/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจฟีเจอร์ประเภทการคำนวณใน Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา .NET สามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project บนระบบของพวกเขา ประเภทการคำนวณช่วยให้เรากำหนดวิธีการคำนวณค่าสำหรับงานและสรุปงานภายในโครงการได้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ความรู้พื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
2. ติดตั้ง Visual Studio บนระบบของคุณแล้ว
3.  ติดตั้ง Aspose.Tasks สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
4.  เข้าถึงเอกสาร Aspose.Tasks สำหรับ .NET เพื่อใช้อ้างอิงได้[ที่นี่](https://reference.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกตัวอย่าง ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;


```

## ขั้นตอนที่ 1: สร้างโครงการใหม่

ขั้นแรก เรามาสร้างวัตถุโครงการใหม่:

```csharp
var project = new Project();
```

## ขั้นตอนที่ 2: เพิ่มงาน

ตอนนี้ เรามาเพิ่มงานให้กับโครงการของเรา:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## ขั้นตอนที่ 3: กำหนดประเภทการคำนวณสำหรับแอตทริบิวต์เพิ่มเติม

เราจะสร้างคำจำกัดความแอตทริบิวต์เพิ่มเติมโดยตั้งค่าประเภทการคำนวณเป็นสูตร:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## ขั้นตอนที่ 4: กำหนดประเภทการคำนวณสำหรับแถวสรุป

ต่อไป เราจะสร้างข้อกำหนดแอตทริบิวต์เพิ่มเติมอื่นโดยที่ค่าสำหรับงานสรุปจะถูกคำนวณโดยใช้ประเภทค่าสะสมเฉลี่ย:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานกับประเภทการคำนวณใน Aspose.Tasks สำหรับ .NET ด้วยการกำหนดประเภทการคำนวณสำหรับแอตทริบิวต์เพิ่มเติม เราสามารถปรับแต่งวิธีคำนวณค่าสำหรับงานและงานสรุปภายในโครงการได้ ซึ่งให้ความยืดหยุ่นและการควบคุมที่มากขึ้น

## คำถามที่พบบ่อย

### คำถามที่ 1: ประเภทการคำนวณใน Aspose.Tasks คืออะไร

A1: ประเภทการคำนวณใน Aspose.Tasks จะกำหนดวิธีคำนวณค่าสำหรับงานและงานสรุปภายในโปรเจ็กต์ โดยเสนอตัวเลือกต่างๆ เช่น สูตรและค่าสะสม

### คำถามที่ 2: ฉันจะตั้งค่าประเภทการคำนวณสำหรับแอตทริบิวต์เพิ่มเติมได้อย่างไร

A2: คุณสามารถตั้งค่าประเภทการคำนวณสำหรับแอตทริบิวต์แบบขยายได้โดยการกำหนดคุณสมบัติ CalculationType ให้สอดคล้องกัน

### คำถามที่ 3: ฉันสามารถปรับแต่งประเภทการคำนวณสำหรับแถวสรุปในโครงการได้หรือไม่

A3: ใช่ Aspose.Tasks อนุญาตให้คุณระบุประเภทการคำนวณสำหรับแถวสรุป ช่วยให้คุณสามารถปรับแต่งการคำนวณมูลค่าตามความต้องการของคุณ

### คำถามที่ 4: มีประเภทชุดรวมที่แตกต่างกันสำหรับการคำนวณงานสรุปหรือไม่

A4: ใช่ Aspose.Tasks มีประเภท Rollup หลากหลาย เช่น ค่าเฉลี่ย ผลรวม และจำนวน สำหรับการคำนวณค่าของงานสรุป

### คำถามที่ 5: ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน

 A5: คุณสามารถสำรวจเอกสารและฟอรัมสนับสนุนชุมชนที่มีอยู่ใน[Aspose.Tasks สำหรับ .NET](https://reference.aspose.com/tasks/net/) เพื่อขอคำแนะนำและความช่วยเหลืออย่างครอบคลุม