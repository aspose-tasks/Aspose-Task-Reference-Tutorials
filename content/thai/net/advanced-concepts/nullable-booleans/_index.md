---
title: การจัดการ Booleans แบบ Nullable ใน Aspose.Tasks
linktitle: การจัดการ Booleans แบบ Nullable ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการบูลีนที่เป็นโมฆะอย่างมีประสิทธิภาพใน Aspose.Tasks สำหรับ .NET ด้วยบทช่วยสอนที่ครอบคลุมนี้ ฝึกฝนการใช้งานคลาส `NullableBool` และปรับปรุงการพัฒนา .NET ของคุณ
type: docs
weight: 21
url: /th/net/advanced-concepts/nullable-booleans/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกการทำงานกับบูลีนที่เป็นโมฆะใน Aspose.Tasks สำหรับ .NET บูลีนแบบ Nullable มีความยืดหยุ่นในการแสดงค่าบูลีน ซึ่งทำให้ไม่สามารถกำหนดความเป็นไปได้ได้ เราจะสำรวจวิธีการใช้`NullableBool` คลาส ตัวสร้าง คุณสมบัติ และวิธีการ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio หรือ IDE ที่ต้องการอื่นๆ สำหรับการพัฒนา .NET
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ

ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโค้ดของคุณ:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน

##  ทำงานกับ`NullableBool`

###  ขั้นตอนที่ 1: สร้างใหม่`Project` instance.

```csharp
var project = new Project();
```

###  ขั้นตอนที่ 2: สร้างอินสแตนซ์ a`NullableBool` object with specified values.

```csharp
var actualsInSync = new NullableBool(false, false);
```

###  ขั้นตอนที่ 3: ตรวจสอบค่าและสถานะที่กำหนดของ`NullableBool` object.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

###  ขั้นตอนที่ 4: ใช้`NullableBool` instance by setting it in the project.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

###  ขั้นตอนที่ 5: สร้างอินสแตนซ์อื่น`NullableBool` object with a single value.

```csharp
var honorConstraints = new NullableBool(true);
```

###  ขั้นตอนที่ 6: แสดงการแสดงสตริงของ`NullableBool` object.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

###  ขั้นตอนที่ 7: ใช้`NullableBool` instance by setting it in the project.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

##  การเปรียบเทียบ`NullableBool` Instances

###  ขั้นตอนที่ 1: สร้างอินสแตนซ์ที่สอง`NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

###  ขั้นตอนที่ 2: ตรวจสอบการแสดงสตริงของแต่ละรายการ`NullableBool` object.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

###  ขั้นตอนที่ 3: ตรวจสอบการแปลงโดยนัยเป็น`bool` and print the result.

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

###  ขั้นตอนที่ 4: เปรียบเทียบทั้งสอง`NullableBool` objects for equality.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

##  รับรหัสแฮชของ`NullableBool`

###  ขั้นตอนที่ 1: สร้างอินสแตนซ์ที่สอง`NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### ขั้นตอนที่ 2: พิมพ์รหัสแฮชสำหรับแต่ละรายการ`NullableBool` object.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## บทสรุป

 ในบทช่วยสอนนี้ เราได้สำรวจวิธีจัดการบูลีนที่เป็นโมฆะใน Aspose.Tasks สำหรับ .NET โดยการใช้`NullableBool` คลาสและวิธีการของมัน คุณสามารถจัดการค่าบูลีนได้อย่างมีประสิทธิภาพโดยมีความยืดหยุ่นเพิ่มเติมในการเป็นโมฆะ

## คำถามที่พบบ่อย

### คำถามที่ 1: บูลีนที่เป็นโมฆะคืออะไร

A1: บูลีนที่เป็นโมฆะคือชนิดที่สามารถแสดงถึงความจริง เท็จ หรือไม่ได้กำหนดไว้

### คำถามที่ 2: เหตุใดจึงใช้บูลีนที่เป็นโมฆะ

A2: บูลีนที่เป็น Nullable มีความยืดหยุ่นในสถานการณ์ที่อาจไม่ได้กำหนดค่าบูลีนเสมอไป

### คำถามที่ 3: บูลีนที่เป็นโมฆะเปรียบเทียบกับความเท่าเทียมกันได้อย่างไร

A3: บูลีนที่เป็น Nullable จะถูกเปรียบเทียบตามสถานะและค่าที่กำหนดไว้

### คำถามที่ 4: ฉันสามารถตั้งค่าบูลีนที่เป็นโมฆะให้เป็นไม่ได้กำหนดได้หรือไม่

A4: ได้ คุณสามารถตั้งค่าบูลีนที่เป็นโมฆะให้เป็นไม่ได้กำหนดได้ในระหว่างการก่อสร้าง

### คำถามที่ 5: ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Tasks for .NET ได้ที่ไหน

 A5: คุณสามารถค้นหาเอกสารโดยละเอียดได้[ที่นี่](https://reference.aspose.com/tasks/net/).