---
title: การใช้ AND Operator ในทุกเงื่อนไขด้วย Aspose.Tasks
linktitle: การใช้ AND Operator ในทุกเงื่อนไขด้วย Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีใช้ตัวดำเนินการ AND ในทุกเงื่อนไขด้วย Aspose.Tasks สำหรับ .NET เพื่อกรองงานโครงการอย่างมีประสิทธิภาพ
type: docs
weight: 11
url: /th/net/advanced-features/and-operator-all-conditions/
---
## การแนะนำ

คุณกำลังมองหาวิธีปรับปรุงงานการจัดการโครงการของคุณอย่างมีประสิทธิภาพหรือไม่? ด้วย Aspose.Tasks สำหรับ .NET คุณสามารถใช้ประโยชน์จากฟังก์ชันการทำงานอันทรงพลังเพื่อจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพ คุณสมบัติอย่างหนึ่งคือความสามารถในการใช้ตัวดำเนินการ AND ในทุกเงื่อนไข ทำให้คุณสามารถกรองงานตามเกณฑ์หลายเกณฑ์พร้อมกันได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการใช้งานฟังก์ชันนี้ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์
2.  Aspose.Tasks สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ติดตั้ง IDE เช่น Visual Studio บนระบบของคุณเพื่อความสะดวกในการเขียนโค้ด

## นำเข้าเนมสเปซ

ประการแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่จำเป็น

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อทำความเข้าใจกระบวนการอย่างชัดเจน

## ขั้นตอนที่ 1: โหลดไฟล์โครงการ

```csharp
// พาธไปยังไดเร็กทอรีเอกสารth
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

 โหลดไฟล์โครงการโดยใช้`Project` ตัวสร้างคลาสระบุเส้นทางของไฟล์

## ขั้นตอนที่ 2: รวบรวมงานโครงการทั้งหมด

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 ใช้`ChildTasksCollector` คลาสเพื่อรวบรวมงานทั้งหมดภายในโครงการ

## ขั้นตอนที่ 3: กำหนดเงื่อนไขตัวกรอง

```csharp
var conditions = new List<ICondition<Task>>
{
    new NotNullCondition(),
    new SummaryCondition()
};
```

สร้างรายการเงื่อนไขเพื่อกรองงาน ในตัวอย่างนี้ เรากรองงานที่ไม่เป็นค่าว่างและเป็นงานสรุป

## ขั้นตอนที่ 4: ใช้และตัวดำเนินการกับเงื่อนไข

```csharp
var joinedCondition = new AndAllCondition<Task>(conditions);
```

 เข้าร่วมเงื่อนไขโดยใช้`AndAllCondition` คลาส การใช้ตัวดำเนินการ AND กับทุกเงื่อนไข

## ขั้นตอนที่ 5: กรองงาน

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

ใช้เงื่อนไขการรวมกับงานที่รวบรวมเพื่อกรองตามนั้น

## ขั้นตอนที่ 6: ประมวลผลงานที่กรองแล้ว

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));
    // ดำเนินการกับงานที่กรองแล้ว
}
```

ทำซ้ำงานที่กรองแล้วและดำเนินการตามที่ต้องการ

## บทสรุป

โดยสรุป การใช้ตัวดำเนินการ AND ในทุกเงื่อนไขกับ Aspose.Tasks สำหรับ .NET ช่วยให้คุณสามารถกรองงานโครงการตามเกณฑ์หลายเกณฑ์พร้อมกันได้อย่างมีประสิทธิภาพ ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับเวิร์กโฟลว์การจัดการโครงการของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพการทำงานและองค์กร

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้เงื่อนไขเพิ่มเติมนอกเหนือจากที่แสดงในตัวอย่างได้หรือไม่

A1: ได้ คุณสามารถกำหนดและใช้เงื่อนไขที่กำหนดเองตามความต้องการของโครงการได้

### คำถามที่ 2: Aspose.Tasks สำหรับ .NET เข้ากันได้กับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่

ตอบ 2: ใช่ Aspose.Tasks รองรับรูปแบบไฟล์โครงการต่างๆ เช่น MPP, XML และ CSV

### คำถามที่ 3: Aspose.Tasks ให้การสนับสนุนอัลกอริธึมการจัดกำหนดการโครงการที่ซับซ้อนหรือไม่

ตอบ 3: แน่นอนว่า Aspose.Tasks นำเสนอคุณสมบัติขั้นสูงสำหรับการจัดการกำหนดการของโครงการ รวมถึงการวิเคราะห์เส้นทางที่สำคัญและการจัดสรรทรัพยากร

### คำถามที่ 4: ฉันสามารถรวม Aspose.Tasks เข้ากับเฟรมเวิร์กหรือไลบรารี .NET อื่นๆ ได้หรือไม่

ตอบ 4: ได้ คุณสามารถรวม Aspose.Tasks เข้ากับเฟรมเวิร์กและไลบรารี .NET อื่นๆ ได้อย่างราบรื่นเพื่อปรับปรุงฟังก์ชันการทำงาน

### คำถามที่ 5: มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับผู้ใช้ Aspose.Tasks หรือไม่

 A5: ใช่ คุณสามารถเข้าถึงฟอรัมชุมชน Aspose.Tasks ได้[ที่นี่](https://forum.aspose.com/c/tasks/15) หากมีข้อสงสัยหรือความช่วยเหลือ