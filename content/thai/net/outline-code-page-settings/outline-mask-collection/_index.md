---
title: Master MS Project Outline Masks พร้อม Aspose.Tasks
linktitle: คอลเลกชันของ Outline Masks ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการโครงร่างคอลเลกชัน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เพิ่มประสิทธิภาพการทำงานด้วยบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 15
url: /th/net/outline-code-page-settings/outline-mask-collection/
---
## การแนะนำ
คุณต้องการควบคุมพลังของโครงร่างมาสก์ของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET หรือไม่? คุณมาถูกที่แล้ว! ในบทช่วยสอนที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการจัดการเค้าร่างมาสก์ในโครงการของคุณอย่างมีประสิทธิภาพ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะช่วยให้คุณมีความรู้และทักษะที่จำเป็นในการเพิ่มประสิทธิภาพขั้นตอนการทำงานของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง Aspose.Tasks สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose[ที่นี่](https://releases.aspose.com/tasks/net/).
### 2. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET Framework
ทำความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และ .NET Framework เนื่องจากบทช่วยสอนนี้จะใช้ทั้งสองภาษา
### 3. ไฟล์โครงการไมโครซอฟต์
เตรียมไฟล์ Microsoft Project (MPP) ให้พร้อมสำหรับการทดสอบ คุณสามารถใช้ไฟล์ที่มีอยู่หรือสร้างไฟล์ใหม่เพื่อการทดลองได้
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและฟังก์ชันการทำงานที่จำเป็นที่ Aspose.Tasks สำหรับ .NET มอบให้

เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนและอธิบายแต่ละขั้นตอนโดยละเอียด:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุโครงการ
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 ที่นี่เราสร้างอินสแตนซ์ใหม่ของ`Project` class และโหลดไฟล์ Microsoft Project ที่มีอยู่ชื่อ "OutlineValues2010.mpp"
## ขั้นตอนที่ 2: เข้าถึงรหัสโครงร่าง
```csharp
var outline = project.OutlineCodes[0];
```
เราเข้าถึงโค้ดโครงร่างจากโครงการ รหัสเค้าร่างเป็นฟิลด์ที่กำหนดเองใน Microsoft Project ที่ช่วยให้คุณสามารถจัดหมวดหมู่และจัดระเบียบงานได้
## ขั้นตอนที่ 3: ล้างมาสก์โครงร่าง
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
ขั้นตอนนี้ช่วยให้แน่ใจว่าได้ล้างมาสก์เค้าร่างที่มีอยู่แล้วก่อนดำเนินการต่อ
## ขั้นตอนที่ 4: สร้างมาสก์โครงร่าง
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
เราสร้างมาสก์โครงร่างใหม่และระบุประเภทของมาสก์ ในตัวอย่างนี้ เราสร้างมาสก์โครงร่างที่ถูกต้องและมาสก์ที่ไม่ถูกต้อง
## ขั้นตอนที่ 5: แทรกและแก้ไขมาสก์
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
ที่นี่ เราแทรกมาสก์ที่ไม่ถูกต้องลงในคอลเลกชัน และแก้ไขความยาวของมาสก์โดยใช้ดัชนี
## ขั้นตอนที่ 6: ลบมาสก์
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
เราลบมาสก์ที่ไม่ถูกต้องออกจากคอลเลกชันตามดัชนี
## ขั้นตอนที่ 7: ทำซ้ำมาสก์
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
ลูปนี้จะวนซ้ำมาสก์โครงร่างแต่ละรายการในคอลเลกชัน และพิมพ์คุณสมบัติของมาสก์ เช่น ความยาว ระดับ ตัวคั่น และประเภท
## ขั้นตอนที่ 8: คัดลอกมาสก์ไปยังโปรเจ็กต์อื่น
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
สุดท้ายนี้ เราจะคัดลอกโครงร่างมาสก์จากโปรเจ็กต์หนึ่งไปยังอีกโปรเจ็กต์หนึ่ง เพื่อให้มั่นใจว่ามีความสอดคล้องกันในโปรเจ็กต์ต่างๆ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีจัดการโครงร่างคอลเลกชัน MS Project โดยใช้ Aspose.Tasks สำหรับ .NET เรียบร้อยแล้ว เมื่อทำตามบทช่วยสอนนี้ ตอนนี้คุณก็มีทักษะในการจัดการเค้าร่างมาสก์ในโครงการของคุณอย่างมีประสิทธิภาพ ซึ่งจะช่วยเพิ่มประสิทธิภาพการทำงานและขั้นตอนการทำงานของคุณได้ในที่สุด
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับไฟล์ Microsoft Project เวอร์ชันต่างๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### คำถามที่ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core ทำให้คุณสามารถใช้งานได้ในแอปพลิเคชันข้ามแพลตฟอร์ม
### คำถามที่ 3: ฉันสามารถปรับแต่งคุณสมบัติของเค้าร่างมาสก์ตามความต้องการของโปรเจ็กต์ของฉันได้หรือไม่
ตอบ: แน่นอน! คุณสามารถปรับแต่งโครงร่างมาสก์ได้โดยการปรับความยาว ระดับ ตัวคั่น และประเภทให้เหมาะกับความต้องการเฉพาะของโปรเจ็กต์ของคุณ
### คำถามที่ 4: Aspose.Tasks สำหรับ .NET มีเอกสารประกอบและการสนับสนุนหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET มีเอกสารที่ครอบคลุมและการสนับสนุนเฉพาะผ่านทางเว็บไซต์และ[ฟอรั่ม](https://forum.aspose.com/c/tasks/15).
### คำถามที่ 5: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks for .NET รุ่นทดลองใช้ฟรีได้จากพวกเขา[เว็บไซต์](https://releases.aspose.com/tasks/net/), เพื่อสำรวจคุณสมบัติและฟังก์ชันการทำงานก่อนตัดสินใจซื้อ