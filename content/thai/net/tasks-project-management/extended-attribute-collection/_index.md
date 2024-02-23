---
title: จัดการการรวบรวมแอตทริบิวต์ของโครงการ MS ใน Aspose.Tasks
linktitle: การจัดการคอลเลกชันแอตทริบิวต์เพิ่มเติมใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการแอตทริบิวต์เพิ่มเติมของ MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET จัดการคุณลักษณะของงานได้อย่างราบรื่นด้วยคำแนะนำทีละขั้นตอน
type: docs
weight: 12
url: /th/net/tasks-project-management/extended-attribute-collection/
---
## การแนะนำ
คุณกำลังมองหาวิธีจัดการแอตทริบิวต์เพิ่มเติมของ MS Project โดยใช้ Aspose.Tasks สำหรับ .NET อยู่ใช่ไหม? ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน มาดำน้ำกันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก ให้โหลดไฟล์ MS Project โดยใช้ข้อมูลโค้ดต่อไปนี้:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงงานและคุณสมบัติเพิ่มเติม
เข้าถึงงานเฉพาะและคุณลักษณะเพิ่มเติม:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## ขั้นตอนที่ 3: ล้างแอตทริบิวต์เพิ่มเติม
ล้างแอตทริบิวต์เพิ่มเติมที่มีอยู่หากจำเป็น:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## ขั้นตอนที่ 4: สร้างคำจำกัดความแอตทริบิวต์เพิ่มเติม
สร้างคำจำกัดความสำหรับแอตทริบิวต์เพิ่มเติมใหม่:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## ขั้นตอนที่ 5: ทำซ้ำแอตทริบิวต์ขยายงาน
วนซ้ำแอตทริบิวต์เพิ่มเติมของงาน:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## ขั้นตอนที่ 6: เพิ่มคุณสมบัติเพิ่มเติม
เพิ่มแอตทริบิวต์เพิ่มเติมใหม่ให้กับงาน:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## ขั้นตอนที่ 7: ทำงานกับคุณสมบัติเพิ่มเติม
ดำเนินการกับแอตทริบิวต์เพิ่มเติมตามความจำเป็น
## ขั้นตอนที่ 8: ลบคุณสมบัติเพิ่มเติม
ลบแอตทริบิวต์เพิ่มเติมตามดัชนีหรือตามเงื่อนไข:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## ขั้นตอนที่ 9: คัดลอกแอตทริบิวต์ไปยังงานอื่น
คัดลอกแอตทริบิวต์ไปยังงานอื่นภายในโปรเจ็กต์เดียวกันหรือต่างกัน:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## บทสรุป
การจัดการคอลเลกชันแอตทริบิวต์เพิ่มเติมของ MS Project จะราบรื่นด้วย Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการแอตทริบิวต์เพิ่มเติมได้อย่างมีประสิทธิภาพ และเพิ่มขีดความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถจัดการแอตทริบิวต์เพิ่มเติมในหลาย ๆ โปรเจ็กต์ได้หรือไม่
ตอบ: ได้ คุณสามารถคัดลอกแอตทริบิวต์เพิ่มเติมระหว่างงานในโครงการต่างๆ ได้โดยใช้ Aspose.Tasks สำหรับ .NET
### ถาม: มีการจำกัดจำนวนแอตทริบิวต์เพิ่มเติมต่องานหรือไม่
ตอบ: Aspose.Tasks สำหรับ .NET ไม่มีข้อจำกัดโดยธรรมชาติเกี่ยวกับจำนวนแอตทริบิวต์เพิ่มเติมต่องาน
### ถาม: ฉันสามารถสร้างช่องแอตทริบิวต์เพิ่มเติมที่กำหนดเองได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks สำหรับ .NET ช่วยให้คุณสามารถกำหนดฟิลด์แอตทริบิวต์เพิ่มเติมที่กำหนดเองซึ่งปรับให้เหมาะกับข้อกำหนดของโปรเจ็กต์ของคุณ
### ถาม: Aspose.Tasks สำหรับ .NET รองรับการอ่านและเขียนไฟล์ MS Project ในเวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับรูปแบบไฟล์ MS Project ในเวอร์ชันต่างๆ
### ถาม: Aspose.Tasks สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).