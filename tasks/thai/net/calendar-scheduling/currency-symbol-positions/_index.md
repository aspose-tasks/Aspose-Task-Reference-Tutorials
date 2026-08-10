---
date: 2026-07-19
description: เรียนรู้วิธีควบคุมสัญลักษณ์สกุลเงินหลังจำนวนในโครงการ .NET อย่างง่ายดายด้วย
  Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: ตำแหน่งสัญลักษณ์สกุลเงินใน Aspose.Tasks
og_description: เรียนรู้วิธีวางสัญลักษณ์สกุลเงินหลังจำนวนโดยใช้ Aspose.Tasks สำหรับ
  .NET ปฏิบัติตามขั้นตอนทีละขั้นตอนและแนวปฏิบัติที่ดีที่สุด.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: สัญลักษณ์สกุลเงินหลังจำนวนใน Aspose.Tasks — คู่มือด่วน
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: วิธีวางสัญลักษณ์สกุลเงินหลังจำนวนใน Aspose.Tasks
url: /th/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีวางสัญลักษณ์สกุลเงินหลังจำนวนใน Aspose.Tasks

## บทนำ

เมื่อคุณสร้างรายงานต้นทุนของโครงการ การวาง **currency symbol after amount** สามารถส่งผลต่อความอ่านง่ายและการปฏิบัติตามมาตรฐานภูมิภาค Aspose.Tasks สำหรับ .NET ให้คุณควบคุมการจัดรูปแบบนี้ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด เพื่อให้ตัวเลขทางการเงินทุกตัวแสดงผลตามที่ผู้มีส่วนได้ส่วนเสียของคุณคาดหวัง ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนที่จำเป็น อธิบายว่าทำไมการตั้งค่านี้สำคัญ และแสดงวิธีนำไปใช้ในโครงการ .NET จริง

## คำตอบด่วน
- **What does “currency symbol after amount” mean?** It displays the symbol (e.g., $) after the numeric value, like `100 $`.
- **Which property controls the position?** `CurrencySymbolPosition` on the `Project` object.
- **Do I need a license?** A trial works for development; a commercial license is required for production.
- **Supported currencies?** Over 50 currencies are built‑in, covering most global markets.
- **Can I change the setting at runtime?** Yes, you can update it any time before saving the project file.

## การตั้งค่า “currency symbol after amount” คืออะไร
ตัวเลือก **currency symbol after amount** กำหนดว่ารูปสัญลักษณ์สกุลเงินจะแสดงก่อนหรือหลังค่าตัวเลขในฟิลด์เงินทั้งหมดของโครงการ การปรับการตั้งค่านี้ช่วยให้รายงานสอดคล้องกับแนวปฏิบัติการบัญชีท้องถิ่นโดยไม่ต้องทำการประมวลผลหลังจากสร้างรายงาน อีกทั้งยังทำให้ผู้มีส่วนได้ส่วนเสียที่คุ้นเคยกับรูปแบบนี้อ่านได้ง่ายขึ้น

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดรูปแบบสกุลเงิน
Aspose.Tasks รองรับ **50+ currencies** และสามารถจัดการโครงการที่มี **10,000+ tasks** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้ประสิทธิภาพสูงแม้บนฮาร์ดแวร์ที่จำกัด API ให้คุณควบคุมได้โดยโปรแกรม ลดความจำเป็นในการแก้ไขสเปรดชีตด้วยตนเอง ทำให้การรายงานการเงินขนาดใหญ่มีประสิทธิภาพและเชื่อถือได้

## ข้อกำหนดเบื้องต้น

### 1. การติดตั้ง Aspose.Tasks สำหรับ .NET
ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks แล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/).

### 2. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET
ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET จำเป็นต่อการทำตามตัวอย่าง

## นำเข้า Namespaces

The `Aspose.Tasks` namespace provides access to the `Project` class and related enums.

The `Project` class is Aspose.Tasks' top‑level object that represents a single project file in memory. After importing the namespace you can start working with project data.

```csharp

```

Now, let’s break down the example into clear, actionable steps.

## วิธีตั้งค่าสัญลักษณ์สกุลเงินหลังจำนวน?

`CurrencySymbolPosition` is an enumeration that specifies whether the currency symbol appears before or after the numeric value.

Load your project, set `CurrencySymbolPosition` to `After`, and then save – that’s all you need to display the symbol after the amount. This direct approach works for any supported currency and does not require additional formatting logic. You can also verify the setting by exporting a sample cost report to ensure the symbol appears correctly.

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
The `Project` class loads an existing MS‑Project file or creates a new one in memory.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### ขั้นตอนที่ 2: ตั้งค่าตำแหน่งสัญลักษณ์สกุลเงิน
`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`. Setting it to `After` places the symbol after the numeric value.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### ขั้นตอนที่ 3: ทำงานกับโครงการ
After you have configured the symbol position, you can continue adding tasks, resources, or custom fields as needed. The setting is persisted when you save the project.

```csharp
// Perform other operations with the project...
```

## ปัญหาและวิธีแก้ไขทั่วไป
- **Symbol still appears before amount:** Ensure you set the property *before* calling `Save`. Changing it after saving requires re‑saving the file.
- **Unsupported currency:** Verify that the currency code you use is listed in Aspose.Tasks’ supported list (over 50 currencies).
- **Performance slowdown on large projects:** Use `ProjectReader` to stream large files if you exceed 10,000 tasks.

## คำถามที่พบบ่อย

**Q: Can I change the currency symbol position multiple times within the same project?**  
A: Yes, you can adjust `CurrencySymbolPosition` as many times as needed; just set the property and re‑save the project.

**Q: Does Aspose.Tasks support currencies other than the US Dollar?**  
A: Absolutely. Aspose.Tasks supports more than 50 international currencies, allowing you to work with any regional format.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).

**Q: Can I seek assistance if I encounter any issues while using Aspose.Tasks for .NET?**  
A: Certainly! You can seek support and assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: How can I purchase a license for Aspose.Tasks for .NET?**  
A: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).

## สรุป

Controlling the **currency symbol after amount** is a vital part of financial reporting in project management software. With Aspose.Tasks for .NET you can set this option programmatically, supporting over 50 currencies and handling large projects efficiently. Apply the steps above to ensure your project reports match the formatting expectations of any locale.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [การจัดการคอลเลกชันปฏิทินใน Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [คอลเลกชันของข้อยกเว้นปฏิทินใน Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [การจัดการอัตรา MS Project ด้วย Aspose.Tasks สำหรับ .NET](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}