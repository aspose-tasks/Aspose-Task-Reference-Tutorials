---
title: การรวบรวมคำจำกัดความของโค้ดโครงร่างใน Aspose.Tasks .NET
linktitle: การรวบรวมคำจำกัดความของโค้ดโครงร่างใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคำจำกัดความของโค้ดเค้าร่างในเอกสาร Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET การจัดหมวดหมู่ข้อมูลโครงการของคุณได้อย่างง่ายดาย
weight: 13
url: /th/net/outline-code-page-settings/outline-code-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การรวบรวมคำจำกัดความของโค้ดโครงร่างใน Aspose.Tasks .NET

## การแนะนำ
Aspose.Tasks เป็นไลบรารี .NET ที่ทรงพลังซึ่งออกแบบมาเพื่อจัดการเอกสาร Microsoft Project ได้อย่างง่ายดายและมีประสิทธิภาพ หนึ่งในคุณสมบัติที่สำคัญคือความสามารถในการทำงานกับคำจำกัดความของโค้ดเค้าร่าง ทำให้ผู้ใช้สามารถจัดระเบียบและจัดหมวดหมู่ข้อมูลโครงการได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับคำจำกัดความของโค้ดเค้าร่างโดยใช้ Aspose.Tasks สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์
2. Visual Studio: ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ ที่ต้องการ
3.  Aspose.Tasks for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

## นำเข้าเนมสเปซ
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## ขั้นตอนที่ 1: โหลดเอกสารโครงการ Microsoft
ขั้นแรก โหลดเอกสาร Microsoft Project เพื่อเริ่มทำงานกับคำจำกัดความโค้ดเค้าร่าง:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## ขั้นตอนที่ 2: เข้าถึงคำจำกัดความของรหัสเค้าร่าง
ตอนนี้ เรามาเข้าถึงคำจำกัดความของโค้ดเค้าร่างภายในโปรเจ็กต์กันดีกว่า:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## ขั้นตอนที่ 3: เพิ่มคำจำกัดความโค้ดโครงร่างที่กำหนดเอง
คุณสามารถเพิ่มคำจำกัดความของโค้ดเค้าร่างแบบกำหนดเองได้ดังต่อไปนี้:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## ขั้นตอนที่ 4: แก้ไขคำจำกัดความของโค้ดโครงร่าง
แก้ไขคำจำกัดความโค้ดโครงร่างที่มีอยู่ได้อย่างง่ายดาย:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## ขั้นตอนที่ 5: ลบคำจำกัดความของโค้ดโครงร่าง
ลบคำจำกัดความของโค้ดโครงร่างเมื่อไม่ต้องการอีกต่อไป:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## ขั้นตอนที่ 6: บันทึกการเปลี่ยนแปลง
สุดท้าย บันทึกการเปลี่ยนแปลงของคุณลงในเอกสารโครงการ:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ .NET มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการจัดการคำจำกัดความของโค้ดเค้าร่างในเอกสาร Microsoft Project ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการคำจำกัดความของโค้ดโครงร่างเพื่อจัดระเบียบและจัดหมวดหมู่ข้อมูลโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถเพิ่มคำจำกัดความโค้ดโครงร่างหลายรายการให้กับโปรเจ็กต์เดียวได้หรือไม่
 ตอบ: ได้ คุณสามารถเพิ่มคำจำกัดความโค้ดโครงร่างหลายรายการให้กับโปรเจ็กต์ได้ตามความต้องการของคุณ เพียงใช้`Add` วิธีการสำหรับแต่ละคำจำกัดความที่คุณต้องการรวมไว้
### ถาม: เป็นไปได้ไหมที่จะลบคำจำกัดความของโค้ดโครงร่างทั้งหมดออกจากโปรเจ็กต์ในคราวเดียว
 ตอบ: ได้ คุณสามารถล้างคำจำกัดความของโครงร่างโค้ดทั้งหมดจากโปรเจ็กต์ได้โดยใช้`Clear` วิธี.
### ถาม: จะเกิดอะไรขึ้นหากฉันพยายามแก้ไขคำจำกัดความของโค้ดเค้าร่างแบบอ่านอย่างเดียว
ตอบ: หากคำจำกัดความของโค้ดเค้าร่างเป็นแบบอ่านอย่างเดียว คุณจะไม่สามารถแก้ไขได้โดยตรง คุณจะต้องตรวจสอบสถานะอ่านอย่างเดียวก่อนที่จะพยายามแก้ไขใดๆ
### ถาม: มีข้อจำกัดเกี่ยวกับจำนวนคำจำกัดความโค้ดโครงร่างที่ฉันสามารถเพิ่มลงในโปรเจ็กต์ได้หรือไม่
ตอบ: Aspose.Tasks for .NET ไม่ได้กำหนดข้อจำกัดเฉพาะใดๆ เกี่ยวกับจำนวนคำจำกัดความของโค้ดเค้าร่างที่คุณสามารถเพิ่มลงในโปรเจ็กต์ได้ อย่างไรก็ตาม ให้พิจารณาผลกระทบของประสิทธิภาพการทำงานเมื่อทำงานกับคำจำกัดความจำนวนมาก
### ถาม: ฉันสามารถใช้คำจำกัดความโค้ดเค้าร่างเพื่อจัดกลุ่มงานตามเกณฑ์ที่กำหนดเองได้หรือไม่
ตอบ: ได้ คำจำกัดความของโค้ดโครงร่างช่วยให้คุณสามารถจัดหมวดหมู่งานตามเกณฑ์ที่กำหนดเองได้ ซึ่งให้ความยืดหยุ่นในการจัดระเบียบข้อมูลโครงการ ## ซอร์สโค้ดที่สมบูรณ์
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
