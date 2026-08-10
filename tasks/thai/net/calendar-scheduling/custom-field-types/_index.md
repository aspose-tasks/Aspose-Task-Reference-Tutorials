---
date: 2026-07-19
description: เรียนรู้วิธีเพิ่มประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks สำหรับ .NET พร้อมขั้นตอน‑โดย‑ขั้นตอนโค้ด,
  ข้อกำหนดเบื้องต้น, และคำถามที่พบบ่อย.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: ประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks
og_description: เรียนรู้วิธีเพิ่มประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks สำหรับ .NET.
  ปฏิบัติตามคู่มือขั้นตอน‑โดย‑ขั้นตอนนี้เพื่อสร้าง, กำหนด, และใช้ extended attributes
  อย่างมีประสิทธิภาพ.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: วิธีเพิ่มประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: วิธีเพิ่มประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks สำหรับ .NET
url: /th/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มประเภทฟิลด์แบบกำหนดเองใน Aspose.Tasks

## บทนำ

ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีเพิ่มฟิลด์แบบกำหนดเอง** ประเภทต่าง ๆ ไปยังไฟล์ Microsoft Project ด้วย Aspose.Tasks สำหรับ .NET ฟิลด์แบบกำหนดเองช่วยให้คุณเก็บข้อมูลเพิ่มเติม—เช่นคะแนนความเสี่ยง, รหัสแผนก, หรือบันทึกเฉพาะ—โดยตรงบนงาน, ทรัพยากร, หรือโครงการเอง เราจะเดินผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการกำหนด, การเพิ่ม, และการตรวจสอบฟิลด์ข้อความแบบกำหนดเอง

## คำตอบอย่างรวดเร็ว
- **What is a custom field?** คอลัมน์ที่ผู้ใช้กำหนดซึ่งสามารถเก็บข้อความ, ตัวเลข, วันที่ หรือแฟล็กบนงาน/ทรัพยากร.  
- **Which class defines a custom field?** `ExtendedAttributeDefinition`.  
- **Can I add a custom field to an existing project?** ใช่ — โหลดโปรเจกต์, สร้างการกำหนด, แล้วเพิ่มลงในคอลเลกชัน.  
- **Do I need a license for Aspose.Tasks?** จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “วิธีเพิ่มฟิลด์แบบกำหนดเอง” คืออะไรใน Aspose.Tasks?
**วิธีเพิ่มฟิลด์แบบกำหนดเอง** หมายถึงกระบวนการสร้าง `ExtendedAttributeDefinition` และผูกมันเข้ากับคอลเลกชัน `ExtendedAttributes` ของโครงการ ซึ่งทำให้คุณสามารถเก็บเมตาดาต้าเพิ่มเติมที่ไม่ได้อยู่ในสคีมามาตรฐานของ Project ได้ สามารถใช้กับงาน, ทรัพยากร, หรือโครงการเอง เพื่อบันทึกข้อมูลเช่นระดับความเสี่ยง, รหัสแผนก, หรือบันทึกเฉพาะที่ไม่มีในฟิลด์เริ่มต้น

## ทำไมต้องใช้ฟิลด์แบบกำหนดเองในการจัดการโครงการ?
Aspose.Tasks รองรับ **50+ ประเภทแอตทริบิวต์ขยายที่มีมาในตัว** และให้คุณกำหนด **ฟิลด์แบบกำหนดเองได้ไม่จำกัดจำนวน** โดยไม่ทำให้ขนาดไฟล์เพิ่มมากนัก การใช้ฟิลด์แบบกำหนดเองคุณสามารถ:
- ฟิลด์เหล่านี้ปรากฏเป็นคอลัมน์เพิ่มเติมใน Microsoft Project และสามารถอ้างอิงในสูตร, รายงาน, และฟิลเตอร์
- ฟิลด์ถูกเก็บไว้ในไฟล์โครงการและเดินทางพร้อมไฟล์ ทำให้เครื่องมือ downstream ใด ๆ ก็ยังคงข้อมูลแบบกำหนดเองได้

## ข้อกำหนดเบื้องต้น

### 1. ติดตั้ง Visual Studio
ตรวจสอบให้แน่ใจว่า Visual Studio (2019 หรือใหม่กว่า) ติดตั้งอยู่บนเครื่องของคุณ คุณสามารถดาวน์โหลดได้จากเว็บไซต์ของ Microsoft

### 2. Aspose.Tasks สำหรับ .NET
เพิ่มแพ็กเกจ NuGet ของ Aspose.Tasks ไปยังโปรเจกต์ของคุณ ดาวน์โหลดเวอร์ชันล่าสุดจาก [here](https://releases.aspose.com/tasks/net/)

### 3. ความรู้พื้นฐาน C#
คุณควรคุ้นเคยกับไวยากรณ์ C#, คลาส, และโครงสร้างโปรเจกต์ .NET

## นำเข้า Namespaces

`Project`, `ExtendedAttributeDefinition`, และ enum ที่เกี่ยวข้องอยู่ใน namespace `Aspose.Tasks` ให้นำเข้า namespace นี้ที่ส่วนหัวของไฟล์ของคุณ

Namespace `Aspose.Tasks` มีประเภทหลักทั้งหมดสำหรับการจัดการไฟล์ Microsoft Project

```csharp

```

## วิธีเพิ่มฟิลด์แบบกำหนดเองไปยังโปรเจกต์?

โหลดโปรเจกต์ที่มีอยู่, สร้างการกำหนดฟิลด์แบบกำหนดเอง, แล้วเพิ่มลงในคอลเลกชันแอตทริบิวต์ขยายของโปรเจกต์ — ทั้งหมดในสามขั้นตอนสั้น ๆ รูปแบบนี้ทำงานได้กับงาน, ทรัพยากร, และโครงการเอง และรับประกันว่าฟิลด์แบบกำหนดเองจะถูกบันทึกเมื่อคุณบันทึกไฟล์

### ขั้นตอนที่ 1: สร้างอ็อบเจกต์ Project
`Project` เป็นอ็อบเจกต์ระดับบนของ Aspose.Tasks ที่แสดงไฟล์ Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอ็อบเจกต์นี้จะโหลดไฟล์และให้คุณเข้าถึงงาน, ทรัพยากร, และแอตทริบิวต์ขยาย

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### ขั้นตอนที่ 2: กำหนดฟิลด์แบบกำหนดเอง
`ExtendedAttributeDefinition` อธิบายคอลัมน์ใหม่ ในตัวอย่างนี้เราจะสร้างฟิลด์แบบกำหนดเองประเภท **Text** สำหรับงานและตั้งชื่อแทน “MyText” ค่า enum `ExtendedAttributeTask.Text1` บอก Aspose.Tasks ว่าจะเก็บค่าที่ไหน

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### ขั้นตอนที่ 3: เพิ่มการกำหนดฟิลด์แบบกำหนดเองไปยังโปรเจกต์
คอลเลกชัน `ExtendedAttributes` ของโปรเจกต์เก็บการกำหนดฟิลด์แบบกำหนดเองทั้งหมด การเพิ่มการกำหนดนี้ทำให้ฟิลด์พร้อมใช้งานสำหรับทุกงานในโปรเจกต์

```csharp
project.ExtendedAttributes.Add(definition);
```

## ปัญหาทั่วไปและวิธีแก้ไข
- **Field not appearing in MS Project UI** – ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่า property `Alias`; MS Project จะแสดง alias เป็นหัวคอลัมน์  
- **Saving throws an exception** – ตรวจสอบว่าไฟล์โปรเจกต์ไม่ได้ตั้งเป็นอ่าน‑อย่างเดียวและคุณมีไลเซนส์ที่ถูกต้อง  
- **Custom field values are lost after reload** – อย่าลืมเรียก `project.Save("output.mpp")` หลังจากกำหนดค่าให้กับงาน

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Tasks with other .NET frameworks?**  
A: ใช่, Aspose.Tasks ทำงานกับ .NET Framework, .NET Core, และ .NET 5/6/7

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: แน่นอน. รองรับการประมวลผลโครงการที่มี **สูงสุด 10,000 งาน** และสามารถทำงานในสภาพแวดล้อมเซิร์ฟเวอร์แบบหลายเธรดได้

**Q: Does Aspose.Tasks support multiple project file formats?**  
A: ใช่ — Aspose.Tasks อ่านและเขียนไฟล์ MPP, XML, HTML, และ CSV ครอบคลุม **ทุกเวอร์ชันหลักของ Microsoft Project**

**Q: Can I manipulate resource data using Aspose.Tasks?**  
A: ใช่, คุณสามารถเพิ่ม, ปรับปรุง, และลบทรัพยากร รวมถึงกำหนดฟิลด์แบบกำหนดเองให้กับทรัพยากรได้

**Q: Is there a community forum for Aspose.Tasks users?**  
A: ใช่, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อโต้ตอบกับผู้ใช้คนอื่นและรับการสนับสนุนจากทีม Aspose

---

**อัปเดตล่าสุด:** 2026-07-19  
**ทดสอบกับ:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [ทำความเข้าใจการกำหนด Extended Attribute ใน MS Project ด้วย Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [จัดการ Extended Attributes ของ MS Project ด้วย Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper การบูรณาการ MS Project ใน Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}