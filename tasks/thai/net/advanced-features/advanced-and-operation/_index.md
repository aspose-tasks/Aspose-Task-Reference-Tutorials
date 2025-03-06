---
title: ขั้นสูงและการดำเนินการใน Aspose.Tasks
linktitle: ขั้นสูงและการดำเนินการใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีดำเนินการ AND ขั้นสูงใน Aspose.Tasks สำหรับ .NET เพื่อกรองงานโครงการตามเกณฑ์ต่างๆ ได้อย่างมีประสิทธิภาพ
weight: 10
url: /th/net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ขั้นสูงและการดำเนินการใน Aspose.Tasks

## การแนะนำ

 ในบทช่วยสอนนี้ เราจะเจาะลึกการดำเนินการ AND ขั้นสูงใน Aspose.Tasks สำหรับ .NET ซึ่งเป็นเครื่องมืออันทรงพลังสำหรับการจัดการงานและโปรเจ็กต์ เราจะสำรวจวิธีการกรองงานโครงการตามเงื่อนไขต่างๆ โดยใช้`Util.And` ระดับ.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
2.  ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของเรา:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## ขั้นตอนที่ 1: เริ่มต้นโครงการและรวบรวมงาน

เริ่มต้นด้วยการเริ่มต้นโปรเจ็กต์ Aspose.Tasks ใหม่และรวบรวมงานทั้งหมดที่อยู่ภายใน:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## ขั้นตอนที่ 2: กำหนดเงื่อนไขตัวกรอง

ถัดไป กำหนดเงื่อนไขตัวกรอง สำหรับตัวอย่างนี้ เราจะสร้างเงื่อนไขสองข้อ: เงื่อนไขหนึ่งเพื่อกรองงานสรุป และอีกเงื่อนไขหนึ่งเพื่อกรองงานที่ไม่เป็นค่าว่าง:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## ขั้นตอนที่ 3: รวมเงื่อนไขเข้ากับการดำเนินการ AND

 ตอนนี้รวมเงื่อนไขโดยใช้`Util.And` คลาสเพื่อสร้างเงื่อนไขแบบผสม:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## ขั้นตอนที่ 4: ใช้เงื่อนไขและงานตัวกรอง

ใช้เงื่อนไขรวมกับงานที่รวบรวมและกรองตาม:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## ขั้นตอนที่ 5: ส่งออกงานที่ถูกกรอง

สุดท้าย ส่งออกงานที่กรองแล้ว:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // การประมวลผลเพิ่มเติมสามารถทำได้ที่นี่
}
```

## บทสรุป

 ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดำเนินการ AND ขั้นสูงใน Aspose.Tasks สำหรับ .NET โดยการรวมเงื่อนไขโดยใช้`Util.And`ชั้นเรียนเราสามารถกรองงานได้อย่างมีประสิทธิภาพตามเกณฑ์หลายเกณฑ์

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET คืออะไร

ตอบ: Aspose.Tasks สำหรับ .NET เป็น API ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรมในแอปพลิเคชัน .NET

### คำถามที่ 2: ฉันสามารถใช้เงื่อนไขมากกว่าสองเงื่อนไขโดยใช้ Util และได้หรือไม่

ตอบ: ได้ Util และสามารถใช้เพื่อรวมเงื่อนไขจำนวนเท่าใดก็ได้เพื่อสร้างเกณฑ์การกรองที่ซับซ้อน

### คำถามที่ 3: Aspose.Tasks สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะหาเอกสารสำหรับ Aspose.Tasks for .NET ได้ที่ไหน

 ตอบ: คุณสามารถค้นหาเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/net/).

### คำถามที่ 5: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ .NET ได้อย่างไร

ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
