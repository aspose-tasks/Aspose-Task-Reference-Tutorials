---
date: 2026-03-24
description: เรียนรู้วิธีตั้งค่าโหมดการคำนวณใน Aspose.Tasks สำหรับ .NET รวมถึงโหมดการคำนวณอัตโนมัติ,
  โหมดการคำนวณด้วยตนเอง, และโหมดไม่มี เพื่อจัดการการขึ้นต่อกันของงาน.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: วิธีตั้งค่าโหมดการคำนวณใน Aspose.Tasks สำหรับ .NET
url: /th/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าโหมดการคำนวณใน Aspose.Tasks สำหรับ .NET

## บทนำ

Aspose.Tasks for .NET เป็น API ที่ทรงพลังซึ่งช่วยให้คุณทำงานกับไฟล์ Microsoft Project อย่างโปรแกรมเมติก หนึ่งในการตั้งค่าที่สำคัญที่สุดที่คุณจะพบคือ **calculation mode** ซึ่งควบคุมวิธีที่วันที่ของงานและกำหนดการของโครงการถูกอัปเดต ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีตั้งค่า calculation** mode, สำรวจ **automatic calculation mode**, **manual calculation mode**, และ **none calculation mode**, และดูว่าตัวเลือกเหล่านี้ส่งผลต่อ **manage task dependencies**, **create project start date**, และ **link tasks finish‑start** อย่างไร

## คำตอบอย่างรวดเร็ว
- **What is calculation mode?** มันกำหนดว่าตารางวันที่ของงานจะถูกคำนวณใหม่โดยอัตโนมัติ, ด้วยตนเอง, หรือไม่คำนวณเลย  
- **Why use manual calculation mode?** เพื่อให้คุณควบคุมได้เต็มที่ว่าเมื่อใดกำหนดการจะถูกรีเฟรช, มีประโยชน์ในการอัปเดตเป็นกลุ่มใหญ่  
- **Which mode is default?** Automatic calculation mode, ซึ่งอัปเดตวันที่ทันทีหลังจากมีการเปลี่ยนแปลง  
- **Can I change the mode at runtime?** ใช่—เพียงตั้งค่า property `CalculationMode` บนวัตถุ `Project`  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต

## “วิธีตั้งค่า calculation” ใน Aspose.Tasks คืออะไร?
การตั้งค่าโหมดการคำนวณง่ายเพียงการกำหนดค่า enum ให้กับ property `Project.CalculationMode` enum มีสามตัวเลือก: `Automatic`, `Manual`, และ `None` การเลือกโหมดที่เหมาะสมขึ้นอยู่กับกระบวนการทำงานของคุณ—ไม่ว่าจะต้องการอัปเดตทันที, ประมวลผลเป็นชุด, หรือควบคุมทั้งหมด

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงานให้ตรวจสอบว่าคุณมี:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (2019, 2022 หรือใหม่กว่า)  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดและติดตั้งไลบรารีจาก [here](https://releases.aspose.com/tasks/net/)  
3. **Basic C# knowledge** – คุณควรคุ้นเคยกับการสร้างแอปพลิเคชันคอนโซลและการใช้แพ็กเกจ NuGet

## นำเข้า Namespaces

ก่อนที่เราจะเริ่มทำงานกับ Aspose.Tasks for .NET, ให้เรานำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;
```

## วิธีตั้งค่าโหมดการคำนวณ

ด้านล่างนี้คุณจะพบตัวอย่างขั้นตอน‑ต่อ‑ขั้นตอนสำหรับแต่ละโหมดการคำนวณ โค้ดบล็อกจะไม่เปลี่ยนแปลงจากบทแนะนำต้นฉบับ; คำอธิบายโดยรอบได้ถูกขยายเพื่อความชัดเจน

### การใช้ Automatic Calculation Mode

Automatic mode คำนวณวันที่ใหม่ทันทีทุกครั้งที่คุณแก้ไขงานหรือการเชื่อมโยง

#### ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project ใหม่

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### ขั้นตอนที่ 2: ตั้งค่าวันเริ่มต้นของโครงการและเพิ่มงาน

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### ขั้นตอนที่ 3: เชื่อมโยงงาน (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### ขั้นตอนที่ 4: ตรวจสอบวันที่ที่คำนวณใหม่

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### การใช้ Manual Calculation Mode

Manual mode ปิดการอัปเดตอัตโนมัติ, ให้คุณสามารถประมวลผลการเปลี่ยนแปลงเป็นชุดก่อนบังคับให้คำนวณใหม่

#### ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project ใหม่

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### ขั้นตอนที่ 2: ตั้งค่าวันเริ่มต้นของโครงการและเพิ่มงาน

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### ขั้นตอนที่ 3: ตรวจสอบคุณสมบัติงาน

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### ขั้นตอนที่ 4: เชื่อมโยงงานและตรวจสอบวันที่ (ไม่มีการคำนวณอัตโนมัติ)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### การใช้ None Calculation Mode

None mode ปิดการคำนวณภายในทั้งหมด ใช้เมื่อคุณต้องการอ่านหรือส่งออกข้อมูลโดยไม่ต้องเปลี่ยนแปลงกำหนดการ

#### ขั้นตอนที่ 1: สร้างอินสแตนซ์ Project ใหม่

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### ขั้นตอนที่ 2: เพิ่มงานใหม่

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### ขั้นตอนที่ 3: ตรวจสอบคุณสมบัติงาน (ไม่มีการสร้าง ID อัตโนมัติ)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| วันที่ไม่อัปเดตหลังจากเชื่อมโยงงาน | โครงการอยู่ในโหมด **Manual** หรือ **None** | ตั้งค่า `project.CalculationMode = CalculationMode.Automatic` หรือเรียก `project.Calculate()` ด้วยตนเอง |
| Task IDs ค้างที่ 0 | การใช้โหมด **None** ป้องกันการสร้าง ID | เปลี่ยนเป็นโหมด **Automatic** หรือ **Manual** แล้วทำการคำนวณใหม่ |
| การเชื่อมโยงล้มเหลวด้วย `ArgumentException` | วันที่เริ่มของงานก่อนหน้ามากกว่างานต่อเมื่อใช้โหมด **Manual** โดยไม่มีการคำนวณใหม่ | ตรวจสอบให้แน่ใจว่ามีวันที่เริ่มที่ถูกต้องหรือคำนวณใหม่หลังจากเพิ่มลิงก์ |

## คำถามที่พบบ่อย

**Q1: ฉันสามารถเปลี่ยนโหมดการคำนวณแบบไดนามิกระหว่างการทำงานได้หรือไม่?**  
A1: ใช่, คุณสามารถแก้ไข property `CalculationMode` ได้ทุกจุดในโค้ดของคุณและจากนั้นเรียก `project.Calculate()` หากต้องการอัปเดตทันที

**Q2: Aspose.Tasks รองรับรูปแบบไฟล์การจัดการโครงการอื่น ๆ นอกจาก Microsoft Project หรือไม่?**  
A2: Aspose.Tasks มุ่งเน้นที่รูปแบบไฟล์ Microsoft Project เป็นหลัก, แต่ยังรองรับ Primavera P6 XML, Primavera DB, และ Asta Powerproject XML ด้วย

**Q3: Aspose.Tasks เหมาะกับโครงการขนาดเล็กและระดับองค์กรหรือไม่?**  
A3: แน่นอน. API สามารถขยายจากรายการงานง่าย ๆ ไปจนถึงกำหนดการระดับองค์กรที่ซับซ้อนหลายเฟส

**Q4: ฉันสามารถผสานรวม Aspose.Tasks กับไลบรารีและเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?**  
A4: ได้, คุณสามารถใช้ Aspose.Tasks ร่วมกับ ASP.NET, WPF, Xamarin หรือเทคโนโลยี .NET ใด ๆ เพื่อสร้างโซลูชันการจัดการโครงการที่ครบวงจร

**Q5: มีฟอรั่มชุมชนหรือช่องทางสนับสนุนสำหรับผู้ใช้ Aspose.Tasks หรือไม่?**  
A5: มี, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

---

**อัปเดตล่าสุด:** 2026-03-24  
**ทดสอบกับ:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}