---
date: 2026-03-19
description: เรียนรู้วิธีอ่าน baseline และจัดการ baseline ของการจัดการโครงการอย่างมีประสิทธิภาพด้วย
  Aspose.Tasks สำหรับ .NET.
linktitle: Project Management Baselines using Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ฐานข้อมูลการจัดการโครงการโดยใช้ Aspose.Tasks
url: /th/net/advanced-features/assignment-baseline-collection/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การกำหนดค่าเบสไลน์การจัดการโครงการด้วย Aspose.Tasks

## บทนำ

ในการจัดการโครงการ, เบสไลน์เป็นจุดอ้างอิงที่ช่วยให้คุณเปรียบเทียบระหว่างแผนกับผลการดำเนินงานจริง การจัดการ **project management baselines**—โดยเฉพาะ assignment baselines—ช่วยให้กำหนดเวลาเป็นไปตามแผนและรับประกันความรับผิดชอบ Aspose.Tasks สำหรับ .NET มี API ที่ทรงพลังสำหรับสร้าง, อ่าน, ปรับปรุงและลบเบสไลน์เหล่านี้โดยโปรแกรม ในบทแนะนำนี้ เราจะอธิบายวิธีทำงานกับ Assignment Baseline Collections ด้วย Aspose.Tasks สำหรับ .NET.

## คำตอบสั้น
- **What is the primary purpose of assignment baselines?** เพื่อบันทึกวันที่เริ่มต้น/สิ้นสุดที่วางแผนไว้สำหรับการมอบหมายทรัพยากรแต่ละรายการ.  
- **Which API method reads baselines?** คอลเลกชัน `Assignment.Baselines`.  
- **Can baselines be deleted programmatically?** ใช่, โดยการลบรายการจากคอลเลกชัน `Assignment.Baselines`.  
- **Do I need a license to use these features?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## เบสไลน์การจัดการโครงการคืออะไร?
เบสไลน์การจัดการโครงการเป็นภาพถ่ายของข้อมูลตารางเวลา, ค่าใช้จ่ายและขอบเขตที่บันทึกในช่วงเวลาหนึ่ง พวกมันทำหน้าที่เป็นมาตรฐานสำหรับวัดประสิทธิภาพของโครงการและระบุความแตกต่างตลอดวงจรชีวิตของโครงการ.

## ทำไมต้องใช้ Aspose.Tasks สำหรับเบสไลน์การจัดการโครงการ?
- **Full control:** เข้าถึงและจัดการข้อมูลเบสไลน์โดยไม่ต้องเปิดโครงการใน Microsoft Project.  
- **Automation‑ready:** ผสานการจัดการเบสไลน์เข้าสู่ pipeline CI/CD หรือเครื่องมือรายงาน.  
- **Cross‑format support:** ทำงานกับไฟล์ MPP, XML, และ MPX, ทำให้มีความยืดหยุ่นกับรูปแบบไฟล์โครงการต่าง ๆ.

## ข้อกำหนดเบื้องต้น

ก่อนดำเนินการตามบทแนะนำนี้, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. ความรู้พื้นฐานของภาษาโปรแกรม C#.  
2. ติดตั้ง Visual Studio บนระบบของคุณ.  
3. ไลบรารี Aspose.Tasks สำหรับ .NET ถูกติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/).

## นำเข้า Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;
```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

ก่อนอื่น, เราต้องโหลดไฟล์โครงการที่มี assignment baselines.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## วิธีอ่านเบสไลน์?

ต่อไป, เราจะวนลูปผ่านการมอบหมายทรัพยากรแต่ละรายการในโครงการเพื่อเข้าถึงเบสไลน์ที่เกี่ยวข้องของแต่ละรายการ.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## ขั้นตอนที่ 3: ลบ Assignment Baselines

ในขั้นตอนนี้, เราจะแสดงวิธีลบ assignment baselines ทั้งหมดออกจากโครงการ.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **Baselines appear empty** | ตรวจสอบว่าไฟล์โครงการมีการบันทึกเบสไลน์จริง ๆ; เบสไลน์จะไม่ถูกสร้างโดยอัตโนมัติ. |
| **`NullReferenceException` when accessing `baselines.ParentAssignment`** | ตรวจสอบว่าอ็อบเจกต์ assignment ไม่เป็น null และเบสไลน์ได้ถูกกำหนดค่าแล้ว. |
| **Performance slowdown on large projects** | ประมวลผล assignment เป็นชุดหรือกรองด้วย `Assignment.Id` เพื่อจำกัดขอบเขต. |

## สรุป

การจัดการ assignment baselines อย่างมีประสิทธิภาพเป็นสิ่งสำคัญในการจัดการโครงการ, ช่วยให้เป็นไปตามกำหนดเวลาและติดตามความคืบหน้าโครงการอย่างแม่นยำ ด้วย Aspose.Tasks สำหรับ .NET การจัดการ assignment baselines จะเป็นเรื่องง่าย, มอบเครื่องมือที่จำเป็นให้กับนักพัฒนาเพื่อปรับกระบวนการจัดการโครงการให้ราบรื่น.

## คำถามที่พบบ่อย

### Q1: Aspose.Tasks สามารถจัดการ assignment baselines สำหรับรูปแบบไฟล์โครงการที่ต่างกันได้หรือไม่?
A1: ใช่, Aspose.Tasks รองรับรูปแบบไฟล์โครงการหลายประเภท, รวมถึง MPP, XML, และ MPX, ทำให้คุณสามารถจัดการ assignment baselines ข้ามประเภทไฟล์ต่าง ๆ ได้อย่างง่ายดาย.

### Q2: Aspose.Tasks เข้ากันได้กับทุกเวอร์ชันของ .NET Framework หรือไม่?
A2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับหลายเวอร์ชันของ .NET Framework, ทำให้มั่นใจในความเข้ากันได้และความยืดหยุ่นสำหรับนักพัฒนาในสภาพแวดล้อมต่าง ๆ.

### Q3: ฉันสามารถจัดการ assignment baselines ด้วยโปรแกรมโดยใช้ Aspose.Tasks ได้หรือไม่?
A3: แน่นอน, Aspose.Tasks มี API ที่ครอบคลุมซึ่งทำให้นักพัฒนาสามารถสร้าง, อ่าน, ปรับปรุงและลบ assignment baselines ได้ตามความต้องการของโครงการโดยโปรแกรม.

### Q4: Aspose.Tasks มีการสนับสนุนทางเทคนิคสำหรับนักพัฒนาหรือไม่?
A4: ใช่, Aspose.Tasks มีการสนับสนุนทางเทคนิคที่แข็งแกร่งผ่านฟอรั่มชุมชน, ที่นักพัฒนาสามารถขอความช่วยเหลือ, แบ่งปันความรู้และทำงานร่วมกับเพื่อนร่วมงาน.

### Q5: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนตัดสินใจซื้อได้หรือไม่?
A5: ใช่, Aspose.Tasks มีเวอร์ชันทดลองฟรี, ให้ผู้พัฒนาสามารถสำรวจคุณลักษณะและฟังก์ชันการทำงานก่อนตัดสินใจซื้อ.

## คำถามที่พบบ่อย

**Q: ฉันจะอ่านเบสไลน์สำหรับการมอบหมายเฉพาะอย่างไร?**  
A: เข้าถึงคอลเลกชัน `Assignment.Baselines` ของการมอบหมายนั้นและวนลูปผ่านมันตามที่แสดงในส่วน “How to read baselines?”.

**Q: สามารถเพิ่มเบสไลน์ใหม่ให้กับการมอบหมายที่มีอยู่ได้หรือไม่?**  
A: ใช่, คุณสามารถสร้างอ็อบเจกต์ `AssignmentBaseline`, ตั้งค่า `Start` และ `Finish` แล้วเพิ่มลงในคอลเลกชัน `Assignment.Baselines`.

**Q: การลบเบสไลน์จะส่งผลต่อกำหนดการต้นฉบับหรือไม่?**  
A: การลบเบสไลน์จะเพียงลบภาพถ่ายที่บันทึกไว้; ตารางเวลาปัจจุบัน (วันที่จริง) จะไม่เปลี่ยนแปลง.

**Q: ฉันสามารถส่งออกข้อมูลเบสไลน์เป็น CSV ได้หรือไม่?**  
A: แม้ว่า Aspose.Tasks จะไม่มีฟังก์ชันส่งออก CSV โดยตรงสำหรับเบสไลน์, คุณสามารถวนลูปคอลเลกชันและเขียนค่าลงไฟล์ CSV ด้วยคลาส I/O ของ .NET มาตรฐาน.

**Q: Aspose.Tasks รองรับรายงานการเปรียบเทียบเบสไลน์หรือไม่?**  
A: ใช่, คุณสามารถเปรียบเทียบวันที่เบสไลน์กับวันที่จริงโดยโปรแกรมและสร้างรายงานแบบกำหนดเองโดยใช้ไลบรารีการรายงานใดก็ได้ที่คุณต้องการ.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}