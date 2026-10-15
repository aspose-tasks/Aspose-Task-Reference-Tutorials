---
date: 2026-10-15
description: เรียนรู้วิธีเพิ่มคุณสมบัติกำหนดเองและจัดการคุณสมบัติโครงการแบบกำหนดเองใน
  Aspose.Tasks สำหรับ .NET เพื่อเพิ่มประสิทธิภาพการควบคุมเมตาดาต้าโครงการของคุณ
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: การจัดการคอลเลกชันคุณสมบัติโครงการแบบกำหนดเองใน Aspose.Tasks
og_description: เพิ่มคุณสมบัติกำหนดเองในไฟล์โครงการของคุณด้วย Aspose.Tasks สำหรับ
  .NET คู่มือนี้จะแสดงวิธีจัดการคุณสมบัติกำหนดเอง อ่านค่า และเพิ่มค่าบูลีนหรือสตริงอย่างมีประสิทธิภาพ
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: เพิ่มคุณสมบัติกำหนดเองโดยใช้ Aspose.Tasks .NET API สำหรับโครงการ
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: วิธีเพิ่มคุณสมบัติกำหนดเองใน Aspose.Tasks สำหรับ .NET
url: /th/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มคุณสมบัติกำหนดเองใน Aspose.Tasks สำหรับ .NET

## บทนำ

การสนับสนุนการเพิ่มคุณสมบัติกำหนดเองช่วยให้คุณเก็บข้อมูลเมตาดาต้าระดับโครงการที่ฟิลด์ที่มีอยู่ไม่ครอบคลุม ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **เพิ่มคุณสมบัติกำหนดเอง**, อ่านค่ากลับ, และจัดการคอลเลกชันของคุณสมบัติกำหนดเองทั้งหมดโดยใช้ Aspose.Tasks สำหรับ .NET. เมื่อเสร็จคุณจะสามารถปรับแต่งไฟล์โครงการด้วยค่า Boolean, DateTime, Double, และ String ที่สอดคล้องกับกฎธุรกิจของคุณ.

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถเพิ่มคุณสมบัติกำหนดเองแบบ Boolean ได้หรือไม่?** ใช่ – ใช้ `CustomPropertyType.Boolean`.
- **มีประเภทของคุณสมบัติกำหนดเองกี่ประเภทที่รองรับ?** สี่ประเภท: Boolean, DateTime, Double, String.
- **คอลเลกชันของคุณสมบัติกำหนดเองเป็นแบบอ่านอย่างเดียวหรือไม่?** สามารถเป็นแบบอ่านอย่างเดียวได้หากโครงการถูกโหลดจากแหล่งที่เป็นแบบอ่านอย่างเดียว.
- **ฉันต้องมีลิขสิทธิ์เพื่อใช้ฟีเจอร์นี้หรือไม่?** ลิขสิทธิ์ชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.
- **เวอร์ชัน .NET ใดที่เข้ากันได้?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## คุณสมบัติกำหนดเองคืออะไร?

คุณสมบัติกำหนดเองคือฟิลด์เมตาดาต้าที่ผู้ใช้กำหนดซึ่งคุณแนบกับอ็อบเจ็กต์ Project. มันช่วยให้คุณเก็บข้อมูลเพิ่มเติมเช่น “ระดับความเสี่ยง”, “รหัสลูกค้า”, หรือแฟล็ก Boolean ใด ๆ ที่ไม่ได้ครอบคลุมโดยฟิลด์มาตรฐานของ MS‑Project.

## ทำไมต้องเพิ่มคุณสมบัติกำหนดเองใน Aspose.Tasks?

Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ** และสามารถจัดการโครงการที่มี **งานสูงสุด 10,000 งาน** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ การเพิ่มคุณสมบัติกำหนดเองช่วยให้คุณฝังข้อมูลสำคัญทางธุรกิจโดยตรงในไฟล์โครงการ, ลดความจำเป็นในการใช้ฐานข้อมูลภายนอกและทำให้ข้อมูลเดินทางพร้อมกับโครงการ.

## ข้อกำหนดเบื้องต้น
- Visual Studio (any recent edition) ที่ติดตั้งบนเวิร์กสเตชันของคุณ.  
- Aspose.Tasks for .NET – ดาวน์โหลดจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/tasks/net/).  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ C# และโครงสร้างโครงการ .NET.

## นำเข้า namespace

Namespace ต่อไปนี้ให้คุณเข้าถึงโมเดลโครงการหลักและ API ของคุณสมบัติกำหนดเอง.

```csharp
using Aspose.Tasks;
using System;


```

## วิธีเพิ่มคุณสมบัติกำหนดเองใน Aspose.Tasks?

เพื่อเพิ่มคุณสมบัติกำหนดเอง, ก่อนอื่นให้โหลดโครงการ, จากนั้นสร้างอ็อบเจ็กต์ `CustomProperty`, ตั้งชื่อ, ประเภท, และค่า, และสุดท้ายเพิ่มลงในคอลเลกชัน `CustomProperties` ของโครงการ การดำเนินการนี้ฝังเมตาดาต้าโดยตรงในไฟล์โครงการ, และการเปลี่ยนแปลงจะถูกบันทึกเมื่อคุณเรียก `project.Save(...)`.  
`CustomProperty` แสดงถึงฟิลด์ที่ผู้ใช้กำหนดหนึ่งฟิลด์ที่แนบกับโครงการ.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### ขั้นตอนที่ 1: เริ่มต้นโครงการ

`Project` คือคลาสหลักที่แทนไฟล์โครงการใน Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### ขั้นตอนที่ 2: ตรวจสอบความพร้อมของคอลเลกชันคุณสมบัติกำหนดเอง

`CustomProperties` คือคอลเลกชันที่เก็บอ็อบเจ็กต์คุณสมบัติกำหนดเองทั้งหมดสำหรับโครงการ.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### ขั้นตอนที่ 3: เพิ่มคุณสมบัติกำหนดเอง

เมธอด `Add` แทรกคุณสมบัติกำหนดเองใหม่เข้าสู่คอลเลกชันของโครงการ.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### ขั้นตอนที่ 4: เข้าถึงคุณสมบัติกำหนดเอง

คอลเลกชัน `CustomProperties` implements IEnumerable, ทำให้สามารถวนซ้ำแต่ละ `CustomProperty` ได้.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### ขั้นตอนที่ 5: ดึงค่าของคุณสมบัติกำหนดเอง

เมธอด `Get` คืนค่าของคุณสมบัติกำหนดเองตามชื่อของมัน.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### ขั้นตอนที่ 6: วนซ้ำชื่อคุณสมบัติกำหนดเอง

พร็อพเพอร์ตี้ `Names` ให้รายการของชื่อคุณสมบัติกำหนดเองทั้งหมดในคอลเลกชัน.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### ขั้นตอนที่ 7: ลบหรือเคลียร์คุณสมบัติกำหนดเอง

เมธอด `Remove` ลบคุณสมบัติเฉพาะ, ในขณะที่ `Clear` ทำให้คอลเลกชันทั้งหมดว่างเปล่า.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **คอลเลกชันแบบอ่าน‑อย่างเดียว** – หาก `project.CustomProperties.IsReadOnly` คืนค่า `true`, ตรวจสอบให้แน่ใจว่าไฟล์ต้นทางไม่ได้เปิดด้วยการเข้าถึงแบบอ่าน‑อย่างเดียวหรือคัดลอกไปยังตำแหน่งที่เขียนได้ก่อนทำการแก้ไข.  
- **ประเภทไม่ตรงกัน** – การกำหนดค่าที่ไม่ตรงกับ `CustomPropertyType` ที่ประกาศจะทำให้เกิด `ArgumentException`. ควรตั้งค่า `Value` หลังจากกำหนด `Type` ที่ถูกต้องเสมอ.  
- **การบันทึกการเปลี่ยนแปลง** – หลังจากเพิ่มหรือเอาคุณสมบัติออก, เรียก `project.Save("output.mpp")` เพื่อบันทึกการแก้ไข; มิฉะนั้นการเปลี่ยนแปลงจะอยู่ในหน่วยความจำเท่านั้น.

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มคุณสมบัติกำหนดเองของประเภทข้อมูลใดก็ได้ในโครงการของฉันโดยใช้ Aspose.Tasks สำหรับ .NET หรือไม่?**  
A: ใช่, คุณสามารถเพิ่มคุณสมบัติกำหนดเองที่รองรับประเภท Boolean, DateTime, Double, และ String.

**Q: สามารถวนซ้ำชื่อคุณสมบัติกำหนดเองใน Aspose.Tasks สำหรับ .NET ได้หรือไม่?**  
A: ได้แน่นอน, คุณสามารถวนซ้ำชื่อคุณสมบัติกำหนดเองโดยใช้พร็อพเพอร์ตี้ `Names`.

**Q: ฉันจะลบคุณสมบัติกำหนดเองเฉพาะจากโครงการของฉันได้อย่างไร?**  
A: คุณสามารถลบคุณสมบัติกำหนดเองโดยใช้ชื่อของมันผ่านเมธอด `Remove`.

**Q: Aspose.Tasks สำหรับ .NET มีการสนับสนุนลิขสิทธิ์ชั่วคราวหรือไม่?**  
A: ใช่, คุณสามารถรับลิขสิทธิ์ชั่วคราวจากเว็บไซต์ Aspose เพื่อการประเมิน.

**Q: ฉันสามารถหาแหล่งสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Tasks สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถเยี่ยมชมฟอรั่ม Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) สำหรับคำถามหรือความช่วยเหลือใด ๆ.

---

**อัปเดตล่าสุด:** 2026-10-15  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีอ่านคุณสมบัติโครงการที่มีอยู่ใน Aspose.Tasks สำหรับ .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [จัดการคอลเลกชันแอตทริบิวต์ของ MS Project ใน Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [ประเภทฟิลด์กำหนดเองของ Aspose.Tasks – ปฏิทินและการกำหนดเวลา](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}