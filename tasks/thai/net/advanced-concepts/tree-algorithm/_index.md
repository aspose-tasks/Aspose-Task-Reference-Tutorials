---
date: 2026-03-19
description: เรียนรู้วิธีเพิ่มทรัพยากรลงในโครงการและคำนวณระยะเวลาของงานโดยใช้ Tree
  Algorithm ของ Aspose.Tasks และกำหนดทรัพยากรให้กับงานใน .NET
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: เพิ่มทรัพยากรให้กับโครงการด้วยอัลกอริทึมต้นไม้ใน Aspose.Tasks
url: /th/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากรลงในโครงการด้วยอัลกอริทึมต้นไม้ใน Aspose.Tasks

## Introduction

ในบทแนะนำนี้คุณจะค้นพบ **วิธีเพิ่มทรัพยากรลงในโครงการ** โดยใช้ประโยชน์จากอัลกอริทึมต้นไม้ที่ทรงพลังที่จัดหาโดย Aspose.Tasks สำหรับ .NET เราจะเดินผ่านการสร้างโครงสร้างงาน, การคำนวณระยะเวลางาน, และการกำหนดทรัพยากรให้กับงาน—ทั้งหมดในรูปแบบขั้นตอนที่ชัดเจนซึ่งคุณสามารถคัดลอกไปใช้ในโซลูชันของคุณเองได้

## Quick Answers
- **อัลกอริทึมต้นไม้ทำอะไร?** มันจะเดินผ่านโครงสร้างงานเพื่อรวมค่าปริมาณงานอย่างมีประสิทธิภาพ.  
- **การดำเนินการหลักที่คู่มือนี้ครอบคลุมคืออะไร?** การเพิ่มทรัพยากรลงในโครงการและการอัปเดตผลรวมงาน.  
- **ฉันต้องการใบอนุญาตหรือไม่?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถใช้กับ .NET Core ได้หรือไม่?** ใช่, Aspose.Tasks รองรับ .NET Framework และ .NET Core.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับไฟล์โครงการพื้นฐาน.

## What is “add resource to project” in Aspose.Tasks?

การเพิ่มทรัพยากรลงในโครงการหมายถึงการสร้างอ็อบเจ็กต์ `Resource` กำหนดประเภทของมัน (เช่น work) และเชื่อมโยงกับหนึ่งหรือหลายงานผ่าน `ResourceAssignments` สิ่งนี้ทำให้ตัวกำหนดเวลาสามารถคำนวณความพยายาม, ค่าใช้จ่าย, และระยะเวลารวมของโครงการได้

## Why use the Tree Algorithm for resource work calculations?

อัลกอริทึมต้นไม้เดินผ่านต้นไม้ของงานเพียงครั้งเดียว, สะสมปริมาณงานจากงานใบไปยังงานสรุป วิธีนี้มีประสิทธิภาพมากกว่าการวนลูปผ่านแต่ละงานโดยเฉพาะในโครงการขนาดใหญ่ที่มีโครงสร้างลึก นอกจากนี้ยังรับประกันว่าค่าปริมาณงานสรุปจะสอดคล้องกับงานลูก

## Prerequisites

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Visual Studio** – รุ่นใดก็ได้ที่ทันสมัย (2019, 2022, หรือใหม่กว่า).  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – คุณควรคุ้นเคยกับคลาส, อ็อบเจ็กต์, และ LINQ เบื้องต้น.

## Import Namespaces

ในโปรเจกต์ C# ของคุณ, นำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับฟังก์ชันของ Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

ตอนนี้, เราจะแบ่งตัวอย่างแต่ละส่วนออกเป็นหลายขั้นตอน:

## Step 1: Load Project File

ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

โหลดไฟล์โครงการเข้าสู่หน่วยความจำโดยใช้คลาส `Project`.

## Step 2: Define Task Hierarchy

ขั้นตอนที่ 2: กำหนดโครงสร้างงาน

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

กำหนดโครงสร้างงานโดยการเพิ่มงานพาเรนท์และงานชิลด์.

## Step 3: Set Task Properties (including **calculate task duration**)

ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติงาน (รวมถึง **คำนวณระยะเวลางาน**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

ที่นี่เราจะ **คำนวณระยะเวลางาน** โดยแปลงชั่วโมงทำงานเป็นอ็อบเจ็กต์ `Duration` แล้วคำนวณวันที่สิ้นสุด.

## Step 4: Add Resource (**assign resources to tasks**)

ขั้นตอนที่ 4: เพิ่มทรัพยากร (**กำหนดทรัพยากรให้กับงาน**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

โค้ดส่วนนี้ **เพิ่มทรัพยากรลงในโครงการ** และ **กำหนดทรัพยากรให้กับงาน** เพื่อให้ตัวกำหนดเวลารู้ว่าใครรับผิดชอบงานนั้น.

## Step 5: Apply Tree Algorithm

ขั้นตอนที่ 5: ใช้อัลกอริทึมต้นไม้

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

เริ่มต้นคลาส `WorkAccumulator` และใช้อัลกอริทึมต้นไม้เพื่อรวบรวมปริมาณงานรวมทั่วโครงสร้าง.

## Step 6: Update Task Work

ขั้นตอนที่ 6: อัปเดตปริมาณงานของงาน

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

อัปเดตค่าปริมาณงานของงานตามข้อมูลที่รวบรวมได้.

## Common Issues & Tips

ปัญหาทั่วไปและเคล็ดลับ

- **การตั้งค่าปฏิทินหายไป:** หากวันที่สิ้นสุดดูผิดพลาด, ตรวจสอบให้แน่ใจว่าปฏิทินของโครงการถูกกำหนดอย่างถูกต้องก่อนเรียก `GetFinishDateByStartAndWork`.  
- **ประเภททรัพยากรไม่ตรงกัน:** ควรตั้งค่า `Rsc.Type` เป็น `ResourceType.Work` สำหรับทรัพยากรที่อิงความพยายาม; มิฉะนั้นการสะสมงานอาจได้ค่าเป็นศูนย์.  
- **เคล็ดลับระดับมืออาชีพ:** หลังจากอัปเดตงาน, เรียก `project.Save("UpdatedProject.mpp")` เพื่อบันทึกการเปลี่ยนแปลง.

## Conclusion

โดยทำตามขั้นตอนเหล่านี้คุณจะรู้วิธี **เพิ่มทรัพยากรลงในโครงการ**, **คำนวณระยะเวลางาน**, และ **กำหนดทรัพยากรให้กับงาน** ด้วยอัลกอริทึมต้นไม้ของ Aspose.Tasks วิธีนี้ช่วยจัดการโครงสร้างลำดับชั้นได้อย่างมีประสิทธิภาพและทำให้ค่าปริมาณงานสรุปแม่นยำด้วยโค้ดที่สั้น.

## FAQ's

### Q1: Aspose.Tasks for .NET คืออะไร?

A1: Aspose.Tasks for .NET เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project อย่างโปรแกรมมิ่งโดยใช้ C#.

### Q2: ฉันสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks for .NET ได้หรือไม่?

A2: ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks for .NET ได้จาก [here](https://releases.aspose.com/).

### Q3: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้จากที่ไหน?

A3: คุณสามารถค้นหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ [here](https://reference.aspose.com/tasks/net/).

### Q4: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks for .NET อย่างไร?

A4: สำหรับการสนับสนุนที่เกี่ยวกับ Aspose.Tasks for .NET, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?

A5: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้จาก [here](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: ฉันสามารถใช้วิธีนี้กับไฟล์โครงการขนาดใหญ่ที่มีอยู่แล้วได้หรือไม่?**  
A: แน่นอน. อัลกอริทึมต้นไม้ทำงานกับอินสแตนซ์ `Project` ใดก็ได้, ไม่ว่าจะขนาดใด.

**Q: อัลกอริทึมนี้อัปเดตค่าต้นทุนด้วยหรือไม่?**  
A: ตัวอย่างนี้เน้นที่งาน, แต่คุณสามารถขยายให้รวมค่าต้นทุนได้โดยการสะสม `Tsk.Cost` ในลักษณะเดียวกัน.

**Q: เวอร์ชัน .NET ใดที่รองรับ?**  
A: Aspose.Tasks รองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, และ .NET 6+.

**Q: ฉันจะจัดการกับหลายทรัพยากรต่อหนึ่งงานอย่างไร?**  
A: เพิ่มแต่ละทรัพยากรด้วย `project.ResourceAssignments.Add(task, resource)`; ตัวสะสมจะรวมปริมาณงานของพวกมันโดยอัตโนมัติ.

---

**อัปเดตล่าสุด:** 2026-03-19  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}