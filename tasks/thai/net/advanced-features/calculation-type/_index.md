---
date: 2026-03-24
description: เรียนรู้วิธีตั้งค่าการคำนวณใน Aspose.Tasks สำหรับ .NET พร้อมตัวอย่างการคำนวณค่าสรุป,
  กำหนดสูตรการคำนวณ, และกำหนดค่าการสรุปแบบ rollup.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีตั้งค่าประเภทการคำนวณใน Aspose.Tasks
url: /th/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่า Calculation Type ใน Aspose.Tasks

## Introduction

หากคุณต้องการ **วิธีตั้งค่า calculation** สำหรับงานและแถวสรุปในไฟล์ Microsoft Project, บทเรียนนี้จะแสดงให้คุณทำเช่นนั้นโดยใช้ Aspose.Tasks สำหรับ .NET เราจะเดินผ่านตัวอย่าง **calculation type** อย่างครบถ้วน, สาธิตวิธี **calculate summary values**, และอธิบายวิธี **define calculation formula** และ **configure rollup summary** สำหรับคุณลักษณะขยาย (extended attributes) เมื่อจบคุณจะสามารถเพิ่มงานลงในโปรเจกต์, ตั้งค่าตรรกะการคำนวณแบบกำหนดเอง, และควบคุมพฤติกรรม roll‑up ได้อย่างมั่นใจ

## Quick Answers
- **What is the primary purpose?** เพื่อควบคุมวิธีการคำนวณค่าของงานและค่ารวมในไฟล์ Project  
- **Which API class is used?** `ExtendedAttributeDefinition` ร่วมกับ `CalculationType` และ `SummaryRowsCalculationType`  
- **Can I use a formula?** ใช่ – ตั้งค่า `CalculationType = CalculationType.Formula` แล้วใส่สตริงสูตร  
- **How do I roll‑up summary values?** ใช้ `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` และระบุ `RollupType` เช่น `Average`  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต

## What is Calculation Type and how to set calculation?

`CalculationType` บอก Aspose.Tasks ว่าจะคำนวณค่าของคุณลักษณะขยายอย่างไร คุณสามารถเลือกค่าคงที่, สูตร, หรือให้ไลบรารีทำการ roll‑up ค่าจากงานลูก การตั้งค่า calculation อย่างถูกต้องเป็นสิ่งสำคัญเมื่อคุณต้องการให้โปรเจกต์สะท้อนกฎธุรกิจที่กำหนดเองโดยไม่ต้องอัปเดตด้วยตนเอง

## Why use calculation type to calculate summary values?

เมื่อโปรเจกต์มีงานสรุป, คุณมักต้องการให้แถวสรุปแสดงข้อมูลที่รวมกัน (เช่น ค่าใช้จ่ายทั้งหมด, ระยะเวลาเฉลี่ย) โดยการกำหนด **calculate summary values** ผ่าน `SummaryRowsCalculationType` และ `RollupType`, Aspose.Tasks สามารถรักษาการรวมค่าเหล่านี้ให้สอดคล้องโดยอัตโนมัติขณะคุณแก้ไขงานแต่ละรายการ

## Prerequisites

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework  
2. Visual Studio (เวอร์ชันล่าสุดใดก็ได้) ติดตั้งบนเครื่องของคุณ  
3. ไลบรารี Aspose.Tasks สำหรับ .NET ติดตั้งแล้ว – คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/)  
4. การเข้าถึงเอกสารอย่างเป็นทางการของ Aspose.Tasks สำหรับ .NET เพื่ออ้างอิง, มีให้ที่ [here](https://reference.aspose.com/tasks/net/)

## Import Namespaces

ก่อนจะลงลึกในตัวอย่าง, อย่าลืมนำเข้า namespace ที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Create a new Project

ขั้นแรก, เราจะสร้างอ็อบเจ็กต์ `Project` ว่างที่ใช้เก็บงานและคุณลักษณะกำหนดเองของเรา

```csharp
var project = new Project();
```

## Step 2: Add a Task to the Project

ต่อไปเราจะ **add task project** โดยสร้างงานง่าย ๆ ตั้งค่าวันเริ่มต้นและกำหนดระยะเวลาเป็นหนึ่งวัน

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Step 3: Define Calculation Type for an Extended Attribute (Formula Example)

ที่นี่เราจะสร้างการกำหนดคุณลักษณะขยายที่ค่าถูกคำนวณจากสูตร ซึ่งเป็นการสาธิต **calculation type example** และแสดงวิธี **define calculation formula**

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Step 4: Define Calculation Type for Summary Rows (Configure Rollup Summary)

ต่อมาเราจะสร้างการกำหนดคุณลักษณะขยายอีกอันหนึ่งที่บอก Aspose.Tasks ให้ **configure rollup summary** โดยใช้ประเภท roll‑up *Average* วิธีนี้เป็นวิธีทั่วไปในการ **calculate summary values** สำหรับค่าใช้จ่าย, งาน, หรือฟิลด์กำหนดเอง

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Formula returns `null` | Incorrect field reference in the formula | Verify the field name inside brackets (e.g., `[Start]` not `[stARt]`). |
| Summary rows show 0 | `SummaryRowsCalculationType` not set or wrong `RollupType` | Ensure `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` and choose an appropriate `RollupType`. |
| Project fails to load after adding attributes | Mismatch between attribute definition and task usage | Add the attribute definition **before** you assign it to any task. |

## Conclusion

ในบทเรียนนี้ เราได้ครอบคลุม **วิธีตั้งค่า calculation** ใน Aspose.Tasks สำหรับ .NET ตั้งแต่การสร้างงานง่าย ๆ ไปจนถึงการกำหนดประเภทการคำนวณแบบสูตรและแบบ roll‑up ด้วยการควบคุมเหล่านี้ คุณจะได้การควบคุมระดับละเอียดในการ **calculate summary values**, ทำให้การวิเคราะห์โปรเจกต์มีความลึกซึ้งยิ่งขึ้นโดยไม่ต้องพึ่งสเปรดชีตแบบแมนนวล

## FAQ's

### Q1: What is Calculation Type in Aspose.Tasks?

A1: Calculation Type in Aspose.Tasks determines how values are calculated for tasks and summary tasks within a project, offering options such as Formula and Rollup.

### Q2: How do I set Calculation Type for an Extended Attribute?

A2: You can set Calculation Type for an Extended Attribute by defining its CalculationType property accordingly.

### Q3: Can I customize Calculation Type for summary rows in a project?

A3: Yes, Aspose.Tasks allows you to specify Calculation Type for summary rows, enabling you to tailor value calculations based on your requirements.

### Q4: Are there different Rollup Types available for summary task calculations?

A4: Yes, Aspose.Tasks provides various Rollup Types such as Average, Sum, and Count for calculating values of summary tasks.

### Q5: Where can I find more resources on Aspose.Tasks for .NET?

A5: You can explore the documentation and community support forums available on the [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) for comprehensive guidance and assistance.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}