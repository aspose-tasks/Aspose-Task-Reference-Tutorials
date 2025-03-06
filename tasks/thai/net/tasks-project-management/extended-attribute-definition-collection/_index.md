---
title: โครงการ MS คำจำกัดความแอตทริบิวต์เพิ่มเติมหลักใน Aspose.Tasks
linktitle: การรวบรวมคำจำกัดความแอตทริบิวต์เพิ่มเติมใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคำจำกัดความแอตทริบิวต์เพิ่มเติมใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET ปรับแต่งและปรับปรุงข้อมูลโครงการของคุณได้อย่างง่ายดาย
type: docs
weight: 14
url: /th/net/tasks-project-management/extended-attribute-definition-collection/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับคำจำกัดความแอตทริบิวต์เพิ่มเติมใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET แอ็ตทริบิวต์เพิ่มเติมนำเสนอวิธีที่ยืดหยุ่นในการปรับแต่งและปรับปรุงข้อมูลโปรเจ็กต์ โดยช่วยให้ผู้ใช้สามารถเพิ่มฟิลด์เพิ่มเติมนอกเหนือจากฟิลด์มาตรฐานที่ให้ไว้ตามค่าเริ่มต้น ด้วย Aspose.Tasks คุณสามารถจัดการคุณลักษณะเพิ่มเติมเหล่านี้ได้อย่างง่ายดายเพื่อปรับแต่งความต้องการในการจัดการโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งข้อกำหนดเบื้องต้นต่อไปนี้:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการของ Aspose.Tasks ในโปรเจ็กต์ .NET ของคุณ ทำตามขั้นตอนเหล่านี้:
## ขั้นตอนที่ 1: เปิดโครงการ .NET ของคุณ
เปิดโปรเจ็กต์ .NET ของคุณใน IDE ที่คุณต้องการ เช่น Visual Studio
## ขั้นตอนที่ 2: เพิ่มเนมสเปซ Aspose.Tasks
เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณเพื่อนำเข้าเนมสเปซ Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

ตอนนี้ เรามาแบ่งตัวอย่างโค้ดที่ให้มาออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ครอบคลุม:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## ขั้นตอนที่ 2: ล้างข้อกำหนดแอตทริบิวต์เพิ่มเติมที่มีอยู่ (ไม่บังคับ)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## ขั้นตอนที่ 3: สร้างและเพิ่มข้อกำหนดแอตทริบิวต์เพิ่มเติมสำหรับงาน
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## ขั้นตอนที่ 4: ทำซ้ำคุณลักษณะเพิ่มเติมของงาน
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## ขั้นตอนที่ 5: สร้างและเพิ่มข้อกำหนดแอตทริบิวต์เพิ่มเติมสำหรับทรัพยากร
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## ขั้นตอนที่ 6: แทรกข้อกำหนดแอตทริบิวต์เพิ่มเติมของทรัพยากร
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## ขั้นตอนที่ 7: ลบแอตทริบิวต์เพิ่มเติมตามดัชนี
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการทำงานกับข้อกำหนดแอตทริบิวต์เพิ่มเติมใน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการและปรับแต่งแอตทริบิวต์เพิ่มเติมให้เหมาะกับความต้องการการจัดการโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถแก้ไขคำจำกัดความแอตทริบิวต์เพิ่มเติมที่มีอยู่ได้หรือไม่
ตอบ: ได้ คุณสามารถแก้ไขคำจำกัดความแอตทริบิวต์เพิ่มเติมที่มีอยู่หรือสร้างขึ้นใหม่ได้ตามความต้องการของคุณ
### ถาม: Microsoft Project ทุกเวอร์ชันรองรับแอตทริบิวต์เพิ่มเติมหรือไม่
ตอบ: ใช่ Microsoft Project เวอร์ชันส่วนใหญ่รองรับแอตทริบิวต์เพิ่มเติม รวมถึงเวอร์ชันล่าสุดด้วย
### ถาม: ฉันสามารถใช้แอตทริบิวต์เพิ่มเติมเพื่อคำนวณฟิลด์ที่กำหนดเองได้หรือไม่
ตอบ: แน่นอน คุณสามารถใช้แอตทริบิวต์เพิ่มเติมเพื่อคำนวณฟิลด์ที่กำหนดเองตามเกณฑ์เฉพาะที่คุณกำหนดได้
### ถาม: Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET อื่นๆ หรือไม่
ตอบ: Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นและความสะดวกในการบูรณาการ
### ถาม: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อการสนับสนุนและสำรวจเอกสาร[ที่นี่](https://reference.aspose.com/tasks/net/).