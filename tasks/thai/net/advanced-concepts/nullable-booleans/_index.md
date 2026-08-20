---
date: 2026-03-14
description: เรียนรู้วิธีใช้บูลีนแบบ nullable ใน Aspose.Tasks สำหรับ .NET รวมถึงการแปลงค่าบูลีนแบบ
  nullable และการตั้งค่าคุณสมบัติบูลีนแบบ nullable
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีใช้บูลีนที่เป็นค่า null ได้ใน Aspose.Tasks
url: /th/net/advanced-concepts/nullable-booleans/
weight: 21
---

 for .NET (latest release)" translate "ทดสอบด้วย". Keep code.

"**Author:** Aspose" translate "ผู้เขียน". Keep Aspose.

Then closing shortcodes.

Also there is a backtop button shortcode at end, keep unchanged.

Now produce final content.

Let's craft translation.

Be careful with Thai punctuation.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการใช้ Nullable Booleans ใน Aspose.Tasks

ในบทแนะนำนี้เราจะอธิบาย **วิธีการใช้ nullable** booleans เมื่อทำงานกับ Aspose.Tasks .NET API. Nullable booleans ให้สถานะได้สามแบบ—`true`, `false`, หรือ *undefined*—ซึ่งเป็นประโยชน์อย่างยิ่งสำหรับการตั้งค่าระดับโครงการที่อาจไม่ได้ระบุอย่างชัดเจน คุณจะได้เห็นวิธีการสร้าง, แปลง, และ **ตั้งค่า nullable boolean** รวมถึงเหตุผลว่าการจัดการ nullable booleans อย่างถูกต้องสามารถป้องกันพฤติกรรมที่ไม่คาดคิดในแอปพลิเคชันการจัดตารางของคุณได้อย่างไร

## คำตอบสั้น ๆ
- **Nullable boolean คืออะไร?** ชนิดที่สามารถเก็บค่า `true`, `false`, หรือเป็น undefined.  
- **ทำไมต้องใช้ nullable booleans ใน Aspose.Tasks?** ช่วยให้คุณแสดงคุณสมบัติโครงการที่เป็นตัวเลือกได้โดยไม่ต้องเดาค่าตั้งต้น.  
- **จะแปลง nullable boolean เป็น bool ปกติอย่างไร?** ใช้การแปลงโดยอัตโนมัติหรือเช็ค `IsDefined` ก่อน.  
- **คลาสหลักคืออะไร?** `NullableBool` ในเนมสเปซ `Aspose.Tasks`.  
- **ต้องมีลิขสิทธิ์หรือไม่?** ต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในโปรดักชัน.

## Nullable Boolean คืออะไร?

Nullable boolean (`NullableBool`) ขยายชนิด `bool` ปกติโดยเพิ่มแฟล็ก *IsDefined*. เมื่อ `IsDefined` เป็น `false` ค่าจะถือว่า undefined, ทำให้คุณแยกความแตกต่างระหว่าง “false” กับ “ไม่ได้ตั้งค่า”.

## ทำไมต้องจัดการ Nullable Booleans ในการตั้งค่าโครงการ?

ตัวเลือกหลายอย่างในโครงการ—เช่น **ActualsInSync** หรือ **HonorConstraints**—เป็นตัวเลือกเสริม การใช้ `bool` ธรรมดาบังคับให้คุณเลือก `true` หรือ `false` ซึ่งอาจทำให้การตั้งค่าของผู้ใช้ถูกเขียนทับโดยไม่ได้ตั้งใจ ด้วยการ **จัดการ nullable booleans** คุณจะรักษาสถานะเดิมไว้และหลีกเลี่ยงการเปลี่ยนแปลงการกำหนดค่าที่ไม่ตั้งใจ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ให้แน่ใจว่าคุณมี:

1. **Visual Studio** (หรือ IDE ที่รองรับ .NET ใดก็ได้).  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/).

## นำเข้า Namespaces

ก่อนอื่น ให้นำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

ตอนนี้เราจะเดินผ่านแต่ละตัวอย่างแบบทีละขั้นตอน

## การทำงานกับ `NullableBool`

### ขั้นตอนที่ 1: สร้างอินสแตนซ์ `Project` ใหม่

```csharp
var project = new Project();
```

### ขั้นตอนที่ 2: สร้างอ็อบเจกต์ `NullableBool` พร้อมค่าที่ระบุ

```csharp
var actualsInSync = new NullableBool(false, false);
```

### ขั้นตอนที่ 3: ตรวจสอบค่าและสถานะการกำหนดของอ็อบเจกต์ `NullableBool`

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### ขั้นตอนที่ 4: **ตั้งค่า nullable boolean** บนโครงการ

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### ขั้นตอนที่ 5: สร้างอ็อบเจกต์ `NullableBool` อีกอันหนึ่งด้วยค่าเดียว

```csharp
var honorConstraints = new NullableBool(true);
```

### ขั้นตอนที่ 6: แสดงการแสดงผลเป็นสตริงของอ็อบเจกต์ `NullableBool`

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### ขั้นตอนที่ 7: ใช้อ็อบเจกต์ `NullableBool` โดยตั้งค่าในโครงการ

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## การเปรียบเทียบอินสแตนซ์ `NullableBool`

### ขั้นตอนที่ 1: สร้างอ็อบเจกต์ `NullableBool` สองตัว

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### ขั้นตอนที่ 2: ตรวจสอบการแสดงผลเป็นสตริงของแต่ละอ็อบเจกต์ `NullableBool`

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### ขั้นตอนที่ 3: แปลงโดยอัตโนมัติเป็น `bool` และพิมพ์ผลลัพธ์

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### ขั้นตอนที่ 4: เปรียบเทียบอ็อบเจกต์ `NullableBool` สองตัวเพื่อความเท่าเทียม

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## การรับค่า Hash Code ของ `NullableBool`

### ขั้นตอนที่ 1: สร้างอ็อบเจกต์ `NullableBool` สองตัว

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### ขั้นตอนที่ 2: พิมพ์ค่า hash code ของแต่ละอ็อบเจกต์ `NullableBool`

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## ข้อผิดพลาดทั่วไป & เคล็ดลับ

- **อย่าถือว่า nullable boolean ถูกกำหนดค่าไว้เสมอ** ตรวจสอบ `IsDefined` ก่อนใช้ `Value` ทุกครั้ง.  
- **การแปลงเป็น bool ปกติ** โดยไม่ตรวจสอบอาจทำให้เกิดข้อยกเว้นหากค่าเป็น undefined. ใช้การแปลงโดยอัตโนมัติเฉพาะเมื่อคุณมั่นใจว่ามันถูกกำหนดค่า.  
- **เมื่อกำหนดค่าคุณสมบัติโครงการ** ให้ใช้เมธอด `Set` พร้อม `NullableBool` เพื่อรักษาสถานะ undefined หากต้องการ.

## คำถามที่พบบ่อย

**ถาม: Nullable boolean คืออะไร?**  
ตอบ: Nullable boolean สามารถแสดงค่า `true`, `false`, หรือสถานะ undefined ทำให้มีผลลัพธ์สามแบบที่แตกต่างกัน

**ถาม: จะทำอย่างไรให้แปลง nullable boolean เป็น bool ปกติได้อย่างปลอดภัย?**  
ตอบ: ตรวจสอบ `IsDefined` ก่อน, จากนั้นใช้คุณสมบัติ `Value` หรือพึ่งพาการแปลงโดยอัตโนมัติเมื่อคุณมั่นใจว่ามันถูกกำหนดค่า

**ถาม: ทำไมต้องใช้ nullable booleans แทน bool ธรรมดาใน Aspose.Tasks?**  
ตอบ: เพราะช่วยให้คุณรักษาการตั้งค่าโครงการที่เป็นตัวเลือกไว้โดยไม่ทำให้ค่าเหล่านั้นถูกเขียนทับโดยบังเอิญ

**ถาม: สามารถตั้งค่า nullable boolean ให้เป็น undefined ได้หรือไม่?**  
ตอบ: ได้ — ใช้คอนสตรัคเตอร์ที่รับเพียงแฟล็กการกำหนดค่า เช่น `new NullableBool(false, false)`

**ถาม: จะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Tasks for .NET ได้จากที่ไหน?**  
ตอบ: คุณสามารถดูเอกสารโดยละเอียดได้ [here](https://reference.aspose.com/tasks/net/).

---

**อัปเดตล่าสุด:** 2026-03-14  
**ทดสอบด้วย:** Aspose.Tasks for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}