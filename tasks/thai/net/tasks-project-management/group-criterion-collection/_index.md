---
title: จัดการเกณฑ์กลุ่มโครงการ MS ด้วย Aspose.Tasks
linktitle: การจัดการการรวบรวมเกณฑ์กลุ่มใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการคอลเลกชัน Group Criterion MS Project โดยใช้ Aspose.Tasks สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา
weight: 28
url: /th/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการเกณฑ์กลุ่มโครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคอลเลกชัน Group Criterion ภายใน MS Project โดยใช้ Aspose.Tasks

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  Aspose.Tasks สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

2. ไฟล์โครงการ Microsoft: เตรียมไฟล์ Microsoft Project (MPP) ให้พร้อมที่จะใช้งาน

## นำเข้าเนมสเปซ

ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นไปยังโค้ด C# ของคุณ ขั้นตอนนี้มีความสำคัญอย่างยิ่งในการเข้าถึงฟังก์ชันการทำงานที่ Aspose.Tasks มอบให้

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

 เริ่มต้นก`Project` วัตถุโดยการโหลดไฟล์ MPP 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## ขั้นตอนที่ 2: เกณฑ์กลุ่มการเข้าถึง

ดึงกลุ่มออกจากโครงการและเข้าถึงเกณฑ์

```csharp
var group = project.TaskGroups.ToList()[0];
```

## ขั้นตอนที่ 3: ทำซ้ำตามเกณฑ์กลุ่ม

วนซ้ำแต่ละเกณฑ์ในกลุ่มและแสดงคุณสมบัติของเกณฑ์นั้น

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## ขั้นตอนที่ 4: ล้างเกณฑ์กลุ่ม

ล้างเกณฑ์กลุ่มที่มีอยู่หากไม่ได้อ่านอย่างเดียว

```csharp
group.GroupCriteria.Clear();
```

## ขั้นตอนที่ 5: เพิ่มเกณฑ์ใหม่

สร้างเกณฑ์กลุ่มใหม่และเพิ่มลงในกลุ่ม

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## ขั้นตอนที่ 6: คัดลอกเกณฑ์ไปยังกลุ่มอื่น

คัดลอกเกณฑ์จากกลุ่มหนึ่งไปยังอีกกลุ่มหนึ่ง

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการคอลเลกชัน Group Criterion MS Project โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการเกณฑ์กลุ่มภายในไฟล์ Microsoft Project ของคุณโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่

ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงปี 2003, 2007, 2010, 2013 และ 2016

### คำถามที่ 2: ฉันสามารถใช้หลายเกณฑ์กับกลุ่มเดียวได้หรือไม่

ตอบ: แน่นอน คุณสามารถเพิ่มหลายเกณฑ์ให้กับกลุ่มได้โดยการวนซ้ำแต่ละรายการและเพิ่มตามลำดับ

### คำถามที่ 3: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ: ได้ คุณสามารถขอรับ Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน

 ตอบ: คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/net/).

### คำถามที่ 5: ฉันจะได้รับความช่วยเหลือได้อย่างไรหากฉันประสบปัญหาใดๆ

 ตอบ: หากคุณมีคำถามหรือประสบปัญหาใดๆ คุณสามารถขอรับการสนับสนุนจากฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
