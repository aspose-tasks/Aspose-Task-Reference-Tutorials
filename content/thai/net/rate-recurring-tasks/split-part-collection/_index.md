---
title: รวบรวม MS Project ของ Split Parts ใน Aspose.Tasks
linktitle: การรวบรวมชิ้นส่วนแยกใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีรวบรวมส่วนที่แยกใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
type: docs
weight: 19
url: /th/net/rate-recurring-tasks/split-part-collection/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีการรวบรวมส่วนที่แยกใน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET การแบ่งงานออกเป็นส่วนๆ อาจเป็นส่วนสำคัญของการจัดการโครงการ และ Aspose.Tasks ก็มอบวิธีการที่สะดวกในการจัดการสิ่งนี้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. การติดตั้ง Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ เนื่องจากเราจะเขียนโค้ดขนาดสั้นใน C#

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้รวมเนมสเปซที่จำเป็น:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ใหม่ใน IDE ที่คุณต้องการ และตรวจสอบให้แน่ใจว่ามีการอ้างอิง Aspose.Tasks สำหรับ .NET อย่างถูกต้อง
## ขั้นตอนที่ 2: เริ่มต้นวัตถุโครงการ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
เริ่มต้นวัตถุ Project ใหม่ด้วยเส้นทางไปยังไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 3: ดึงข้อมูลงานและวนซ้ำส่วนที่แยก
```csharp
var task = project.RootTask.Children.GetById(1);
// ทำซ้ำส่วนที่แยก
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
รับงานจากโครงการและทำซ้ำส่วนที่แยกออก พิมพ์วันที่เริ่มต้นและสิ้นสุด
## ขั้นตอนที่ 4: รับการแบ่งส่วนตามดัชนี
```csharp
// รับชิ้นส่วนตามดัชนี
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
ดึงส่วนที่แยกเฉพาะตามดัชนีและพิมพ์วันที่เริ่มต้น

## บทสรุป
การจัดการส่วนที่แยกในไฟล์ MS Project สามารถเพิ่มประสิทธิภาพการจัดการโครงการได้อย่างมาก Aspose.Tasks สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยการจัดหา API ที่ใช้งานง่ายเพื่อจัดการงานที่แยกกันได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถแบ่งงานแบบไดนามิกระหว่างรันไทม์ได้หรือไม่
ตอบ: ได้ คุณสามารถแบ่งงานโดยทางโปรแกรมได้โดยใช้ Aspose.Tasks for .NET
### ถาม: Aspose.Tasks รองรับไฟล์ MS Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้บนแพลตฟอร์มต่างๆ
### ถาม: มีเวอร์ชันทดลองใช้งานสำหรับการทดสอบหรือไม่
 ตอบ: ได้ คุณสามารถขอรับเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) สำหรับการประเมินผล
### ถาม: ฉันจะรับใบอนุญาตชั่วคราวสำหรับโครงการของฉันได้อย่างไร
 ตอบ: สามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับการใช้งานระยะสั้น
### ถาม: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเกี่ยวกับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมฟอรัม Aspose.Tasks ได้[ที่นี่](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือจากชุมชนหรือทีมสนับสนุน Aspose