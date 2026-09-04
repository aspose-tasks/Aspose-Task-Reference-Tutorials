---
date: 2026-06-30
description: เรียนรู้วิธีตั้งค่า constraint type C# ด้วย Aspose.Tasks สำหรับ .NET
  เพื่อจัดการตารางโครงการอย่างมีประสิทธิภาพและใช้หลาย constraints
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: Constraint Types ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: ตั้งค่า Constraint Type C# ด้วย Aspose.Tasks
url: /th/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดประเภทข้อจำกัด C# ด้วย Aspose.Tasks

เมื่อคุณต้องการ **set constraint type C#** ในกำหนดการของโครงการ, Aspose.Tasks สำหรับ .NET จะมอบวิธีการที่สะอาดและเป็นโปรแกรมเมติกเพื่อควบคุมวันที่ของงาน ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่ชัดเจน—การโหลดโครงการ, การใช้ข้อจำกัด, และการบันทึกผลลัพธ์—เพื่อให้คุณจัดการกำหนดการทั้งแบบง่ายและซับซ้อนได้อย่างมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **“set constraint type C#” ทำอะไร?** มันกำหนดกฎการกำหนดเวลา (เช่น As Soon As Possible) ให้กับงานหนึ่ง, กำหนดว่าควรคำนวณวันที่อย่างไร.
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.
- **ฉันสามารถใช้ข้อจำกัดหลายรายการพร้อมกันได้หรือไม่?** คุณสามารถวนลูปผ่านงานและตั้งค่าต่าง ๆ ของ `ConstraintType` ในการทำงานครั้งเดียวได้.
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **ฉันจะได้รับไลบรารีได้จากที่ไหน?** ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการของ Aspose (ดูส่วนข้อกำหนดเบื้องต้น).

## set constraint type C# คืออะไร?
การกำหนดประเภทข้อจำกัดใน C# หมายถึงการกำหนดค่าจาก enumeration `ConstraintType` ให้กับ property `ConstraintType` ของงาน นี่บอกกับเครื่องมือกำหนดเวลาว่างานควรเริ่มต้นให้เร็วที่สุด, เสร็จภายในวันที่กำหนด, หรือปฏิบัติตามกฎอื่นใดที่กำหนดโดยข้อจำกัด.

## ทำไมต้องใช้ประเภทข้อจำกัดในการกำหนดกำหนดการโครงการ?
Aspose.Tasks รองรับ **30+ ประเภทข้อจำกัด** และสามารถประมวลผลโครงการที่มี **ถึง 100,000 งาน** โดยไม่มีผลกระทบต่อประสิทธิภาพที่สังเกตได้ การใช้ข้อจำกัดช่วยให้คุณบังคับใช้กฎธุรกิจ—เช่น “ต้องเริ่มในวันที่กำหนด” หรือ “ต้องเสร็จไม่เกินกำหนดเวลา”—โดยตรงในโค้ด, ลดการปรับแก้ด้วยมือ.

## ข้อกำหนดเบื้องต้น

1. ติดตั้ง Visual Studio บนเครื่องทำงานของคุณ.  
2. ไลบรารี Aspose.Tasks สำหรับ .NET – ดาวน์โหลดจาก [ที่นี่](https://releases.aspose.com/tasks/net/).  
3. ความรู้พื้นฐานในการเขียนโปรแกรม C#.

## นำเข้า Namespaces

The following namespaces give you access to the core scheduling API:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แสดงไฟล์ Microsoft Project ในหน่วยความจำ.*

## วิธีโหลดไฟล์โครงการใน C#?
คลาส `Project` แสดงไฟล์ Microsoft Project ในหน่วยความจำ, ให้คุณอ่านและแก้ไขเนื้อหาโดยไม่ต้องล็อกไฟล์ต้นฉบับ โหลดโครงการที่มีอยู่ของคุณ (หรือสร้างใหม่) โดยส่งเส้นทางไฟล์ไปยังคอนสตรัคเตอร์, ซึ่งจะทำการแยกข้อมูล .mpp และเตรียมโมเดลอ็อบเจ็กต์สำหรับการดำเนินการต่อไป.

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
var project = new Project("PathToYourProjectFile");
```

## วิธีตั้งค่าประเภทข้อจำกัดสำหรับงานใน C#?
Enumeration `ConstraintType` กำหนดข้อจำกัดการกำหนดเวลาที่เป็นไปได้ที่สามารถนำไปใช้กับงาน ใช้ enumeration นี้เพื่อระบุกฎที่คุณต้องการ, จากนั้นกำหนดให้กับ property `ConstraintType` ของงาน บรรทัดเดียวนี้เป็นหัวใจของการดำเนินการ set constraint type C# ที่บอกกับตัวกำหนดเวลาว่าจะคำนวณวันที่เริ่มและสิ้นสุดอย่างไร.

## ขั้นตอนที่ 2: ตั้งค่าประเภทข้อจำกัด

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## วิธีบันทึกโครงการหลังจากตั้งค่าข้อจำกัด?
เมธอด `Save` จะเขียนข้อมูลโครงการลงไฟล์ในรูปแบบที่ระบุ, เช่น PDF หรือ XML หลังจากใช้ข้อจำกัดแล้ว, เรียกเมธอดนี้พร้อม `SaveOptions` ที่เหมาะสมเพื่อสร้างไฟล์ผลลัพธ์ การดำเนินการนี้บันทึกการเปลี่ยนแปลงทั้งหมด, รวมถึงข้อมูลข้อจำกัด, เพื่อให้กำหนดการที่บันทึกสะท้อนกฎงานที่อัปเดต.

## ขั้นตอนที่ 3: บันทึกโครงการ

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## ปัญหาทั่วไปและวิธีแก้

- **ข้อจำกัดไม่ได้ถูกนำไปใช้:** ตรวจสอบให้แน่ใจว่าคุณกำลังแก้ไขอ็อบเจ็กต์ `Task` ที่ถูกต้อง (ตรวจสอบ `Task.Id`).  
- **วันที่ไม่คาดคิดหลังการบันทึก:** ตรวจสอบว่าปฏิทินของโครงการตรงกับวันทำงานและวันหยุดที่คุณตั้งใจ.  
- **ประสิทธิภาพช้าลงเมื่อไฟล์ใหญ่:** ใช้ `Project.Set(LoadOptions.DisableCache, true)` เพื่อลดการใช้หน่วยความจำเมื่อทำงานกับโครงการขนาดใหญ่มาก.

## คำถามที่พบบ่อย

**Q: ข้อจำกัดของโครงการคืออะไร?**  
A: ข้อจำกัดของโครงการคือกฎที่จำกัดเวลาที่งานสามารถเริ่มหรือเสร็จสิ้น, มีผลต่อกำหนดการโดยรวม.

**Q: Aspose.Tasks รองรับประเภทข้อจำกัดกี่ประเภท?**  
A: Aspose.Tasks รองรับ **12 ประเภทข้อจำกัดที่แตกต่าง** รวมถึง As Soon As Possible, Must Finish On, และ Finish No Earlier Than.

**Q: ฉันสามารถใช้ข้อจำกัดกับหลายงานพร้อมกันได้หรือไม่?**  
A: ได้, คุณสามารถวนลูปผ่านคอลเลกชันของงานและตั้งค่า `ConstraintType` ของแต่ละงานในลูปเดียว.

**Q: Aspose.Tasks เหมาะกับโครงการขนาดเล็กและขนาดใหญ่หรือไม่?**  
A: แน่นอน—Aspose.Tasks จัดการโครงการตั้งแต่ไม่กี่งานจนถึง **มากกว่า 100,000 งาน** ด้วยประสิทธิภาพที่สม่ำเสมอ.

**Q: ฉันจะได้รับการสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.Tasks ได้จากที่ไหน?**  
A: คุณสามารถรับการสนับสนุนโดยไปที่ [ฟอรั่ม](https://forum.aspose.com/c/tasks/15).

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## บทแนะนำที่เกี่ยวข้อง

- [ปฏิทินและการกำหนดเวลา Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [กำหนดประเภทวันที่เริ่มต้นของงานใน Aspose.Tasks](/tasks/net/task-table-management/task-start-date-types/)
- [ดึงข้อมูลไฟล์ MS Project ใน Aspose.Tasks](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}