---
title: การทำงานกับวัตถุ OLE ใน Aspose.Tasks
linktitle: การทำงานกับวัตถุ OLE ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีทำงานอย่างมีประสิทธิภาพกับออบเจ็กต์ OLE ในแอปพลิเคชัน .NET โดยใช้ Aspose.Tasks ซึ่งช่วยเพิ่มความสามารถในการจัดการโครงการ
type: docs
weight: 22
url: /th/net/advanced-concepts/ole-objects/
---
## การแนะนำ

Aspose.Tasks สำหรับ .NET มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการทำงานกับออบเจ็กต์ OLE (Object Linking and Embedding) ภายในไฟล์โครงการ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการจัดการออบเจ็กต์ OLE อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks ในแอปพลิเคชัน .NET ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. การติดตั้ง: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/net/).

2. ความรู้พื้นฐาน: ทำความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และแนวคิดกรอบงาน .NET

3. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม เช่น Visual Studio

## นำเข้าเนมสเปซ

ขั้นแรก นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;


```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน:

## การทำงานกับวัตถุ OLE

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
var project = new Project("TaskImage2010.mpp");
```

### ขั้นตอนที่ 2: เข้าถึงวัตถุ OLE
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

### ขั้นตอนที่ 3: วนซ้ำผ่านวัตถุ OLE
```csharp
foreach (var oleObject in oleObjects)
{
    // เข้าถึงและพิมพ์คุณสมบัติของวัตถุ OLE
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // ดำเนินการต่อสำหรับคุณสมบัติอื่น ๆ
}
```

### ขั้นตอนที่ 4: ดึงข้อมูลไบต์ของเนื้อหา
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

## การล้างวัตถุ OLE

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
var project = new Project("TaskImage2010.mpp");
```

### ขั้นตอนที่ 2: ล้างวัตถุ OLE
```csharp
project.OleObjects.Clear();
```

### ขั้นตอนที่ 3: บันทึกโครงการ
```csharp
project.Save("ClearedProject.mpp");
```

## รับคุณสมบัติการวางวัตถุภาพ

### ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```csharp
var project = new Project("TaskImage2010.mpp");
```

### ขั้นตอนที่ 2: เข้าถึงวัตถุ OLE และการวางตำแหน่งวัตถุภาพ
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

### ขั้นตอนที่ 3: ดึงข้อมูลคุณสมบัติ
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานอย่างมีประสิทธิภาพกับอ็อบเจ็กต์ OLE ใน Aspose.Tasks สำหรับ .NET ด้วยการทำตามตัวอย่างทีละขั้นตอนเหล่านี้ คุณสามารถรวมความสามารถในการจัดการวัตถุ OLE เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพการทำงานและการใช้งาน

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สามารถจัดการรูปแบบวัตถุ OLE ต่างๆ ได้หรือไม่

A1: ใช่ Aspose.Tasks รองรับรูปแบบวัตถุ OLE ที่หลากหลาย รวมถึงรูปภาพ เอกสาร และไฟล์มัลติมีเดีย

### คำถามที่ 2: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่

ตอบ 2: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และการผสานรวมที่ราบรื่น

### คำถามที่ 3: ฉันสามารถจัดการการจัดวางวัตถุ OLE ภายในมุมมองโครงการได้หรือไม่

A3: แน่นอนว่า Aspose.Tasks มี API เพื่อจัดการคุณสมบัติการจัดวางและลักษณะที่ปรากฏของวัตถุ OLE ภายในมุมมองโครงการ

### คำถามที่ 4: Aspose.Tasks เหมาะสำหรับโครงการระดับองค์กรหรือไม่

ตอบ 4: ใช่ Aspose.Tasks เหมาะอย่างยิ่งสำหรับทั้งโครงการขนาดเล็กและระดับองค์กร โดยนำเสนอฟีเจอร์ที่แข็งแกร่งและประสิทธิภาพที่เชื่อถือได้

### คำถามที่ 5: Aspose.Tasks ให้การสนับสนุนลูกค้าและทรัพยากรด้านเอกสารประกอบหรือไม่

ตอบ 5: ใช่ Aspose.Tasks มีเอกสาร ฟอรัม และการสนับสนุนลูกค้าที่ครอบคลุม เพื่อช่วยนักพัฒนาในการใช้คุณสมบัติต่างๆ ได้อย่างมีประสิทธิภาพ