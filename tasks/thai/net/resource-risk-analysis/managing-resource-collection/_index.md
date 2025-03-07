---
title: การจัดการการรวบรวมทรัพยากรโครงการใน Aspose.Tasks
linktitle: การจัดการการรวบรวมทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคอลเลกชันทรัพยากร Microsoft Project ใน .NET อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks API เพิ่มผลผลิตและความยืดหยุ่น
weight: 13
url: /th/net/resource-risk-analysis/managing-resource-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการการรวบรวมทรัพยากรโครงการใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคอลเลกชันทรัพยากร Microsoft Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม ช่วยให้สามารถบูรณาการและจัดการข้อมูลโปรเจ็กต์ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ความรู้เกี่ยวกับ C# และ .NET Framework: บทช่วยสอนนี้ถือว่ามีความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และ .NET Framework
2. การติดตั้ง Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. การตั้งค่าสภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Visual Studio หรือ IDE ที่ต้องการอื่นๆ

## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
ขั้นแรก โหลดไฟล์ Microsoft Project ลงในออบเจ็กต์โครงการ Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## ขั้นตอนที่ 2: เพิ่มทรัพยากรเปล่า
ต่อไป มาเพิ่มทรัพยากรว่างให้กับโปรเจ็กต์:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## ขั้นตอนที่ 3: เพิ่มทรัพยากรด้วยชื่อ
ตอนนี้ ให้เพิ่มทรัพยากรที่มีชื่อที่ระบุให้กับโครงการ:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## ขั้นตอนที่ 4: เพิ่มทรัพยากรก่อนทรัพยากรอื่น
เพิ่มทรัพยากรที่มีชื่อที่ระบุก่อนทรัพยากรอื่นตามรหัส:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## ขั้นตอนที่ 5: การเข้าถึงทรัพยากรด้วย ID หรือ UID
คุณสามารถเข้าถึงทรัพยากรด้วย ID หรือ UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## ขั้นตอนที่ 6: ข้อมูลทรัพยากรการพิมพ์
พิมพ์ข้อมูลเกี่ยวกับทรัพยากรโครงการ:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## ขั้นตอนที่ 7: การลบทรัพยากร
ลบทรัพยากรออกจากโครงการ:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## บทสรุป
การจัดการคอลเลกชันทรัพยากรของโครงการ Microsoft โดยใช้ Aspose.Tasks สำหรับ .NET ช่วยให้นักพัฒนามีชุดเครื่องมือที่แข็งแกร่งเพื่อจัดการทรัพยากรของโครงการอย่างมีประสิทธิภาพโดยทางโปรแกรม ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจัดการทรัพยากรภายในโปรเจ็กต์ของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพและความยืดหยุ่นในงานการจัดการโปรเจ็กต์
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้หรือไม่

ตอบ: ใช่ Aspose.Tasks ได้รับการออกแบบมาเพื่อจัดการไฟล์โปรเจ็กต์ขนาดใหญ่อย่างมีประสิทธิภาพ โดยให้ประสิทธิภาพและความน่าเชื่อถือสูง

### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่

ตอบ: Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน

### ถาม: ฉันสามารถปรับแต่งคุณสมบัติทรัพยากรโดยใช้ Aspose.Tasks ได้หรือไม่

ตอบ: แน่นอนว่า Aspose.Tasks มีความสามารถที่ครอบคลุมในการปรับแต่งคุณสมบัติของทรัพยากรตามความต้องการของโปรเจ็กต์เฉพาะ

### ถาม: Aspose.Tasks รองรับการทำงานแบบมัลติเธรดสำหรับการดำเนินการพร้อมกันหรือไม่

ตอบ: ใช่ Aspose.Tasks รองรับการทำงานแบบมัลติเธรด ช่วยให้สามารถดำเนินการกับข้อมูลโปรเจ็กต์พร้อมกันเพื่อปรับปรุงประสิทธิภาพได้

### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่

 ตอบ: ได้ ผู้ใช้ Aspose.Tasks สามารถเข้าถึงการสนับสนุนด้านเทคนิคผ่านฟอรัม[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
