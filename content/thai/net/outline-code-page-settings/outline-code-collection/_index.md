---
title: การรวบรวมโครงการ MS ของรหัสเค้าร่างใน Aspose.Tasks
linktitle: การรวบรวมรหัสโครงร่างใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีรวบรวมโค้ดโครงร่างของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนที่ครอบคลุมนี้ให้คำแนะนำทีละขั้นตอน
type: docs
weight: 11
url: /th/net/outline-code-page-settings/outline-code-collection/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการรวบรวมโค้ดโครงร่างของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เราจะแบ่งกระบวนการออกเป็นคำแนะนำทีละขั้นตอนเพื่อให้มั่นใจถึงความชัดเจนและความเข้าใจ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของการเขียนโปรแกรม C#: ความคุ้นเคยกับ C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ขั้นแรก นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Tasks ในโปรเจ็กต์ C# ของคุณ
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
 เริ่มต้นด้วยการโหลดไฟล์ Microsoft Project โดยใช้นามสกุล`Project` ระดับ.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## ขั้นตอนที่ 2: รวบรวมรหัสโครงร่าง
สร้างตัวรวบรวมเพื่อรวบรวมโค้ดโครงร่างจากงานโปรเจ็กต์
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## ขั้นตอนที่ 3: วนซ้ำงานและโค้ดโครงร่าง
ทำซ้ำงานที่รวบรวมและโค้ดเค้าร่าง จากนั้นพิมพ์รายละเอียด
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## ขั้นตอนที่ 4: เพิ่มคำจำกัดความโค้ดโครงร่างที่กำหนดเอง
เพิ่มคำจำกัดความโค้ดโครงร่างแบบกำหนดเองให้กับโปรเจ็กต์
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## ขั้นตอนที่ 5: สร้างและแทรกโค้ดโครงร่าง
สร้างโค้ดโครงร่างและแทรกลงในงาน
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## ขั้นตอนที่ 6: จัดการรหัสโครงร่าง
จัดการโค้ดโครงร่างตามความจำเป็น เช่น การแทรก การถอด หรือการล้าง
```csharp
// ตัวอย่างของการยักย้าย
// ...
// ใส่โค้ดที่มี 2 ในตำแหน่งที่ถูกต้อง
task.OutlineCodes.Insert(2, code2);
// ตรวจสอบว่ามีการใส่รหัสหรือไม่
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรวบรวมโค้ดโครงร่างของ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการโค้ดเค้าร่างภายในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพ เพิ่มประสิทธิภาพการจัดระเบียบและความชัดเจน
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET มีเป้าหมายหลักคือแพลตฟอร์ม .NET แต่ยังให้การสนับสนุนภาษาการเขียนโปรแกรมอื่นๆ ผ่าน Aspose.Tasks for Cloud อีกด้วย
### ถาม: มีข้อจำกัดเกี่ยวกับขนาดของไฟล์โปรเจ็กต์ที่ Aspose.Tasks สำหรับ .NET สามารถรองรับได้หรือไม่
ตอบ: Aspose.Tasks สำหรับ .NET สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ แต่ประสิทธิภาพอาจแตกต่างกันไปขึ้นอยู่กับความซับซ้อนและขนาดของไฟล์
### ถาม: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ Microsoft Project เวอร์ชันล่าสุดหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับ Microsoft Project เวอร์ชันต่างๆ รวมถึงเวอร์ชันล่าสุดด้วย
### ถาม: ฉันสามารถปรับแต่งรูปแบบเอาต์พุตเมื่อทำงานกับ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งรูปแบบเอาต์พุตตามความต้องการของคุณ
### ถาม: ฉันจะค้นหาการสนับสนุนหรือแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยเกี่ยวกับ Aspose.Tasks สำหรับ .NET