---
date: 2026-07-05
description: เรียนรู้วิธีการติดตามงบประมาณโครงการและจัดการค่าใช้จ่ายของโครงการโดยใช้
  Aspose.Tasks สำหรับ .NET. กำหนด Cost Accrual Types เพื่อการติดตามค่าใช้จ่ายที่แม่นยำ.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: ติดตามงบประมาณโครงการด้วย Cost Accrual Types ใน Aspose.Tasks
url: /th/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ติดตามงบประมาณโครงการด้วยประเภทการสะสมค่าใช้จ่ายใน Aspose.Tasks

## บทนำ

การ **ติดตามงบประมาณโครงการ** อย่างแม่นยำเป็นหัวใจของการส่งมอบโครงการที่ประสบความสำเร็จ เมื่อข้อมูลค่าใช้จ่ายถูกบันทึกในเวลาที่เหมาะสม คุณสามารถคาดการณ์การเกินงบประมาณ ปรับทรัพยากร และแจ้งให้ผู้มีส่วนได้ส่วนเสียรับทราบ Aspose.Tasks สำหรับ .NET ให้การควบคุมระดับละเอียดเกี่ยวกับการสะสมค่าใช้จ่ายแก่ผู้พัฒนา ทำให้คุณกำหนดว่า *เมื่อไหร่* ค่าจะถูกบันทึก—ไม่ว่าจะเป็นเมื่อเริ่มทำงาน อย่างต่อเนื่อง หรือเฉพาะเมื่อทำงานเสร็จสิ้น บทเรียนนี้จะพาคุณผ่านแนวคิดต่าง ๆ แสดงวิธีตั้งค่าประเภทการสะสมค่าใช้จ่าย และสาธิตแนวปฏิบัติที่ดีที่สุดสำหรับการติดตามงบประมาณอย่างเชื่อถือได้

## คำตอบสั้น

- **วัตถุประสงค์หลักของประเภทการสะสมค่าใช้จ่ายคืออะไร?** พวกมันกำหนดจุดในวงจรชีวิตของงานเมื่อค่าใช้จ่ายได้รับการรับรู้ ทำให้สามารถติดตามงบประมาณได้อย่างแม่นยำ  
- **ค่า enum ใดที่ทำให้ค่าใช้จ่ายล่าช้าจนกว่างานจะเสร็จ?** `CostAccrualType.End`.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** ใช่, จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถเปลี่ยนประเภทการสะสมค่าใช้จ่ายสำหรับหลายทรัพยากรพร้อมกันได้หรือไม่?** ได้—ทำการวนลูปผ่านคอลเลกชัน `Resources` และกำหนดประเภทที่ต้องการ  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ประเภทการสะสมค่าใช้จ่ายคืออะไร?

**ประเภทการสะสมค่าใช้จ่าย** บอกให้ Aspose.Tasks รู้ว่าเมื่อใดจะนำค่าใช้จ่ายของทรัพยากรไปใช้กับงบประมาณของโครงการ มันถูกแทนด้วย enumeration `CostAccrualType` และสามารถตั้งค่าได้ต่อทรัพยากรหรือแต่ละงาน การเลือกประเภทที่ถูกต้องทำให้ข้อมูลค่าใช้จ่ายสอดคล้องกับนโยบายการเรียกเก็บเงินขององค์กรของคุณ ไม่ว่าจะต้องการบันทึกค่าใช้จ่ายตั้งแต่เริ่มทำงาน การกระจายค่าใช้จ่ายตามระยะเวลา หรือเฉพาะหลังจากเสร็จสิ้น

## ทำไมต้องติดตามงบประมาณโครงการด้วยประเภทการสะสมค่าใช้จ่าย?

Aspose.Tasks รองรับ **สี่** ตัวเลือกการสะสม—`Start`, `Prorated`, `Duration`, และ `End`—ครอบคลุมช่วงทั้งหมดของสถานการณ์การบัญชีโครงการทั่วไป การเลือกตัวเลือกที่เหมาะสมช่วยให้คุณสอดคล้องการรับรู้ค่าใช้จ่ายกับรอบการเรียกเก็บเงินตามสัญญา ลดความแปรปรวนในรายงานการเงิน และสร้างใบแสดงค่าใช้จ่ายที่ผสานรวมกับระบบ ERP อย่างราบรื่น ทั้งนี้ยังช่วยให้การใช้หน่วยความจำต่ำสำหรับโครงการขนาดใหญ่

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET

เพื่อเริ่มต้น คุณต้องมี Aspose.Tasks สำหรับ .NET ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จาก [download page](https://releases.aspose.com/tasks/net/) และทำตามคำแนะนำการติดตั้งที่ให้มา

### 2. ความคุ้นเคยกับ .NET Framework

ต้องมีความรู้พื้นฐานเกี่ยวกับ .NET Framework และภาษาโปรแกรม C# เพื่อให้สามารถทำตามตัวอย่างในบทเรียนนี้ได้

## วิธีตั้งค่าประเภทการสะสมค่าใช้จ่ายสำหรับทรัพยากร?

โหลดโครงการ, ค้นหาทรัพยากรเป้าหมาย, และกำหนด `CostAccrualType` ที่ต้องการ รูปแบบสองบรรทัดด้านล่างเป็นวิธีมาตรฐาน: สร้างอินสแตนซ์ `Project`, ดึงทรัพยากรตาม ID, จากนั้นตั้งค่า `CostAccrualType` ลำดับที่กระชับนี้ทำให้คุณ **ติดตามงบประมาณโครงการ** อย่างแม่นยำตั้งแต่ทรัพยากรถูกเพิ่มเข้ามา

### ขั้นตอนที่ 1: นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า Namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.Tasks ในโครงการ .NET ของเรา:

```csharp

```

เมื่อเรามี Namespaces พร้อมแล้ว เราสามารถดำเนินการต่อไปเพื่อโหลดไฟล์โครงการได้

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ

คลาส `Project` แทนไฟล์ Microsoft Project และให้การเข้าถึงงาน, ทรัพยากร, และข้อมูลอื่น ๆ ของมัน

```csharp
var project = new Project("Project2.mpp");
```

แรกสุด เราต้องโหลดไฟล์โครงการเข้าสู่แอปพลิเคชันของเรา เราสร้างอ็อบเจกต์ `Project` ใหม่และกำหนดค่าเริ่มต้นด้วยเส้นทางไปยังไฟล์โครงการของเรา

### ขั้นตอนที่ 3: เข้าถึงทรัพยากร

คอลเลกชัน `Resources` เก็บทรัพยากรทั้งหมดที่กำหนดในโครงการ เมธอด `GetById` ดึงทรัพยากรตามตัวระบุที่ไม่ซ้ำกันของมัน

```csharp
var resource = project.Resources.GetById(1);
```

ต่อไป เราเข้าถึงทรัพยากรที่ต้องการนำประเภทการสะสมค่าใช้จ่ายไปใช้ เราใช้เมธอด `GetById` ของคอลเลกชัน `Resources` และส่งค่า ID ของทรัพยากรเป็นอาร์กิวเมนต์ สิ่งนี้แสดงให้เห็น **access resource by id** ซึ่งเป็นความต้องการทั่วไปเมื่อทำการอัปเดตค่าใช้จ่ายโดยอัตโนมัติ

### ขั้นตอนที่ 4: ตั้งค่าประเภทการสะสมค่าใช้จ่าย

เมธอด `Set` กำหนดค่าลงในฟิลด์ของทรัพยากร

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

ที่นี่ เราตั้งค่าประเภทการสะสมค่าใช้จ่ายสำหรับทรัพยากร ในตัวอย่างนี้ เราตั้งค่าเป็น `CostAccrualType.End` ซึ่งหมายความว่าค่าใช้จ่ายจะไม่ถูกสะสมจนกว่างานที่เหลือจะเป็นศูนย์ การเลือก `End` เหมาะเมื่อคุณต้องการ **ติดตามงบประมาณโครงการ** เฉพาะหลังจากงานเสร็จสมบูรณ์เต็มที่

### ขั้นตอนที่ 5: ทำงานต่อกับโครงการ

หลังจากตั้งค่าประเภทการสะสมค่าใช้จ่ายแล้ว คุณสามารถทำงานต่อกับโครงการตามต้องการ เช่น ทำการดำเนินการหรือคำนวณเพิ่มเติม เช่น การสร้างรายงานค่าใช้จ่าย, การอัปเดตการมอบหมาย, หรือการส่งออกไฟล์

## ข้อผิดพลาดทั่วไปและเคล็ดลับมืออาชีพ

- **เคล็ดลับ:** ควรเรียก `project.Save` เสมอหลังจากแก้ไขประเภทการสะสมค่าใช้จ่ายเพื่อบันทึกการเปลี่ยนแปลง  
- **ข้อผิดพลาด:** การตั้งค่า `CostAccrualType.Start` ให้กับทรัพยากรที่ไม่เคยเริ่มทำงานจะทำให้รายงานงบประมาณบวมขึ้น—ควรตรวจสอบกำหนดการของงานก่อน  
- **เคล็ดลับ:** ใช้ `project.Resources.ToList()` เมื่อคุณต้องการอัปเดตหลายทรัพยากรเป็นชุด; วิธีนี้ช่วยหลีกเลี่ยงการค้นหาคอลเลกชันซ้ำและเพิ่มประสิทธิภาพในโครงการขนาดใหญ่

## คำถามที่พบบ่อย

**Q: ฉันสามารถเปลี่ยนประเภทการสะสมค่าใช้จ่ายสำหรับหลายทรัพยากรพร้อมกันได้หรือไม่?**  
A: ได้, ทำการวนลูปผ่าน `project.Resources` และกำหนด `CostAccrualType` ที่ต้องการให้กับแต่ละทรัพยากรภายในลูป `foreach`

**Q: มีประเภทการสะสมค่าใช้จ่ายอื่น ๆ ที่มีอยู่นอกจาก `End` หรือไม่?**  
A: Aspose.Tasks มี `Start`, `Prorated`, และ `Duration`—แต่ละประเภทสอดคล้องกับกลยุทธ์การเรียกเก็บเงินที่แตกต่างกัน

**Q: ฉันจะตรวจสอบประเภทการสะสมค่าใช้จ่ายปัจจุบันของทรัพยากรเฉพาะได้อย่างไร?**  
A: ดึงค่าด้วย `resource.Get(TskResource.CostAccrualType)`; มันจะคืนค่า enum ที่แสดงการตั้งค่าปัจจุบัน

**Q: สามารถกำหนดประเภทการสะสมค่าใช้จ่ายที่แตกต่างกันให้กับงานต่าง ๆ ในโครงการเดียวกันได้หรือไม่?**  
A: แน่นอน ทั้งงานและทรัพยากรมีคุณสมบัติ `CostAccrualType` ทำให้สามารถกำหนดค่าแยกกันตามเอนทิตี้ได้

**Q: Aspose.Tasks รองรับประเภทการสะสมค่าใช้จ่ายแบบกำหนดเองหรือไม่?**  
A: ไม่, ไลบรารีในขณะนี้รองรับเพียงสี่ประเภทที่สร้างมาแล้วเท่านั้น; หากต้องการตรรกะแบบกำหนดเองต้องทำการ implement ภายนอก

---

**อัปเดตล่าสุด:** 2026-07-05  
**ทดสอบด้วย:** Aspose.Tasks 24.8 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [ปฏิทินและการกำหนดเวลา Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [จัดการอัตรา MS Project ด้วย Aspose.Tasks สำหรับ .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [จัดการทรัพยากร MS Project อย่างง่ายดายด้วย Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}