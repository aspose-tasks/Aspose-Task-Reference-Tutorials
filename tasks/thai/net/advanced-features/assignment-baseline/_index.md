---
date: 2026-03-19
description: เรียนรู้วิธีตั้งค่า baseline ของโครงการและจัดการ baseline ของการมอบหมายอย่างมีประสิทธิภาพด้วย
  Aspose.Tasks for .NET เพื่อให้การติดตามความก้าวหน้าของโครงการเป็นไปอย่างแม่นยำ
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ตั้งค่า Baseline ของโครงการ – การจัดการ Baseline ของการมอบหมายใน Aspose.Tasks
url: /th/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่า Baseline ของโครงการ – การจัดการ Baseline ของการมอบหมายใน Aspose.Tasks

## Introduction

เมื่อทำงานกับงานการจัดการโครงการ, **การตั้งค่า baseline ของโครงการ** เป็นสิ่งสำคัญสำหรับการวัดความก้าวหน้าจริงเทียบกับแผนเดิม. Aspose.Tasks for .NET ไม่เพียงแต่ให้คุณ **ตั้งค่า baseline ของโครงการ** แต่ยังให้คุณควบคุม baseline ของการมอบหมายได้อย่างเต็มที่, ทำให้การติดตามประสิทธิภาพเป็นไปอย่างแม่นยำ. ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมด—การโหลดโครงการ, การตั้งค่า baseline, การอ่านข้อมูล baseline ของการมอบหมาย, และการเปรียบเทียบ baseline—เพื่อให้คุณสามารถตรวจสอบโครงการของคุณได้อย่างมั่นใจ.

## Quick Answers
- **การตั้งค่า “set project baseline” หมายถึงอะไร?** มันบันทึกตารางเวลาและข้อมูลต้นทุนต้นฉบับเพื่อใช้เปรียบเทียบกับประสิทธิภาพจริงในภายหลัง.  
- **เมธอด API ใดที่ตั้งค่า baseline?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Baseline ของการมอบหมายต้องการการเรียกแยกหรือไม่?** ไม่, พวกมันจะถูกจัดเก็บโดยอัตโนมัติเมื่อคุณตั้งค่า baseline ของโครงการ.  
- **รูปแบบใดบ้างที่รองรับ?** MPP, XML, MPX และอื่น ๆ ผ่าน Aspose.Tasks.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้ที่ไม่ใช่รุ่นทดลอง.

## Prerequisites

- ความรู้พื้นฐานของการเขียนโปรแกรม C#.  
- Visual Studio (เวอร์ชันล่าสุดใดก็ได้).  
- ไลบรารี Aspose.Tasks for .NET เพิ่มเข้าในโครงการของคุณ. คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/net/).  
- เข้าถึงไฟล์โครงการในรูปแบบ MPP (เช่น `AssignmentBaseline2007.mpp`).

## Import Namespaces

เพิ่ม namespace ที่จำเป็นที่ส่วนบนของไฟล์ C# ของคุณเพื่อให้คอมไพเลอร์รู้ว่าจะหา class ของ Aspose.Tasks ได้จากที่ไหน.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

ขั้นตอนที่ 1: โหลดโครงการและตั้งค่า Baseline ของโครงการ

แรก, โหลดไฟล์ MPP ที่มีอยู่แล้วจากนั้นเรียก `SetBaseline` เพื่อ **ตั้งค่า baseline ของโครงการ** สำหรับโครงการทั้งหมด.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

ขั้นตอนที่ 2: อ่านข้อมูล Baseline ของการมอบหมาย

หลังจากตั้งค่า baseline แล้ว, การมอบหมายทรัพยากรแต่ละรายการจะมีบันทึก baseline ของตนเอง. ลูปด้านล่างจะดึงและพิมพ์รายละเอียดเหล่านั้น, รวมถึงวันที่เริ่ม/สิ้นสุด, ค่าใช้จ่าย, งาน, และข้อมูลแบบ time‑phased ใด ๆ.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Step 3: Compare Assignment Baselines

ขั้นตอนที่ 3: เปรียบเทียบ Baseline ของการมอบหมาย

คุณสามารถเปรียบเทียบ baseline ของการมอบหมายที่แตกต่างกันโดยใช้ตัวดำเนินการเทียบเท่าและเปรียบเทียบที่มีในตัว. สิ่งนี้เป็นประโยชน์เมื่อคุณต้องการตรวจจับการเปลี่ยนแปลงตารางเวลา หรือค่าใช้จ่ายเกินงบประมาณระหว่างงาน.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Common Issues and Solutions

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ข้อมูล Baseline ปรากฏว่างเปล่า** | ไฟล์โครงการถูกเปิดในโหมดอ่านอย่างเดียวหรือ baseline ไม่เคยตั้งค่า. | เรียก `project.SetBaseline(BaselineType.Baseline)` ก่อนอ่าน baseline ของการมอบหมาย. |
| **`NullReferenceException` บน `TimephasedData`** | Baseline ทั้งหมดไม่ได้มีรายการ time‑phased. | ตรวจสอบเสมอว่า `baseline.TimephasedData != null` (ตามที่แสดงในโค้ด). |
| **การดึง UID ไม่ถูกต้อง** | ค่า UID แตกต่างกันระหว่างเวอร์ชันของไฟล์. | ใช้ `ResourceAssignments.GetByUid` พร้อม UID ที่ถูกต้องหรือวนลูปเพื่อค้นหาการมอบหมายที่ต้องการ. |

## Frequently Asked Questions

**ถาม: Aspose.Tasks สามารถจัดการหลาย baseline สำหรับการมอบหมายเดียวได้หรือไม่?**  
ตอบ: ใช่, Aspose.Tasks รองรับหลาย baseline สำหรับแต่ละการมอบหมาย, ทำให้สามารถติดตามความคืบหน้าของโครงการได้อย่างครอบคลุมตลอดเวลา.

**ถาม: Aspose.Tasks เข้ากันได้กับรูปแบบไฟล์โครงการหลายรูปแบบนอกจาก MPP หรือไม่?**  
ตอบ: ใช่, Aspose.Tasks รองรับรูปแบบไฟล์โครงการหลากหลาย รวมถึง XML, MPX, และ MPP, ทำให้เข้ากันได้กับเครื่องมือการจัดการโครงการต่าง ๆ.

**ถาม: ฉันสามารถแก้ไขข้อมูล baseline ผ่านโปรแกรมโดยใช้ Aspose.Tasks ได้หรือไม่?**  
ตอบ: แน่นอน, Aspose.Tasks มี API ที่ครอบคลุมเพื่อแก้ไขข้อมูล baseline อย่างไดนามิกตามความต้องการของโครงการ, ให้ความยืดหยุ่นและการควบคุมกระบวนการจัดการโครงการ.

**ถาม: Aspose.Tasks มีเอกสารและแหล่งสนับสนุนสำหรับนักพัฒนาหรือไม่?**  
ตอบ: มี, นักพัฒนาสามารถเข้าถึงเอกสารที่ครบถ้วน, บทเรียน, และฟอรั่มบนเว็บไซต์ Aspose.Tasks, ช่วยให้การรวมระบบและการแก้ไขปัญหาเป็นไปอย่างราบรื่น.

**ถาม: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for .NET หรือไม่?**  
ตอบ: มี, นักพัฒนาสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Tasks for .NET จาก [ที่นี่](https://releases.aspose.com/), เพื่อประเมินคุณลักษณะและความสามารถก่อนตัดสินใจซื้อ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-19  
**ทดสอบด้วย:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose