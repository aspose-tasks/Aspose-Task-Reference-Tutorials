---
title: จัดการค่าโครงร่างโครงการ MS ด้วย Aspose.Tasks
linktitle: การรวบรวมค่าเค้าร่างใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการค่าเค้าร่างในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET บทช่วยสอนทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 17
url: /th/net/outline-code-page-settings/outline-value-collection/
---
## การแนะนำ
Aspose.Tasks สำหรับ .NET มีชุดคุณลักษณะที่ครอบคลุมเพื่อโต้ตอบกับไฟล์ Microsoft Project คุณสมบัติอย่างหนึ่งคือความสามารถในการจัดการค่าเค้าร่างภายในโครงการ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการรวบรวมและจัดการค่าเค้าร่างโดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Tasks สำหรับ .NET: คุณสามารถดาวน์โหลดไลบรารี่ได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง IDE ที่เหมาะสม เช่น Visual Studio
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์
## นำเข้าเนมสเปซ
ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการของ Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
มาแบ่งตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
 ขั้นแรก ให้เริ่มต้น a`Project` วัตถุโดยการโหลดไฟล์ Microsoft Project ที่มีอยู่:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## ขั้นตอนที่ 2: ล้างค่าเค้าร่างที่มีอยู่
ถัดไป ล้างค่าโครงร่างที่มีอยู่ออกจากโครงการ:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## ขั้นตอนที่ 3: กำหนดโค้ดโครงร่างใหม่
ตอนนี้ ให้กำหนดโค้ดโครงร่างใหม่พร้อมคำอธิบายและค่า:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## ขั้นตอนที่ 4: อัปเดตค่าเค้าร่าง
อัปเดตค่าของโค้ดโครงร่าง:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## ขั้นตอนที่ 5: วนซ้ำค่าเค้าร่าง
วนซ้ำค่าโครงร่างและพิมพ์รายละเอียด:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## ขั้นตอนที่ 6: จัดการค่าเค้าร่าง
ดำเนินการต่างๆ เช่น การลบ การแทรก และการคัดลอกค่าโครงร่างตามความจำเป็น:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับค่าเค้าร่างในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถจัดการค่าโครงร่างภายในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพ ทำให้สามารถควบคุมและยืดหยุ่นได้มากขึ้น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถจัดการโค้ดโครงร่างหลายโค้ดพร้อมกันได้หรือไม่
ตอบ: ได้ คุณสามารถกำหนดและจัดการโค้ดโครงร่างหลายรายการภายในโปรเจ็กต์ได้โดยใช้ Aspose.Tasks
### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP และ XML
### ถาม: ฉันจะจัดการกับข้อผิดพลาดขณะทำงานกับค่าเค้าร่างได้อย่างไร
ตอบ: คุณสามารถใช้กลไกการจัดการข้อผิดพลาด เช่น บล็อก try-catch เพื่อจัดการข้อยกเว้นได้อย่างสง่างาม
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของค่าโครงร่างในโครงการของฉันได้หรือไม่
ตอบ: ได้ Aspose.Tasks มี API มากมายเพื่อปรับแต่งรูปลักษณ์และลักษณะการทำงานของค่าเค้าร่างตามความต้องการของคุณ
### ถาม: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนชุมชนและการสำรวจ[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับ API และคุณสมบัติต่างๆ