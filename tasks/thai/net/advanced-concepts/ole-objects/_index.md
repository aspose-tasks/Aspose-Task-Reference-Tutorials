---
date: 2026-03-16
description: เรียนรู้วิธีการลบวัตถุ OLE ด้วย Aspose.Tasks สำหรับ .NET และค้นพบวิธีจัดการ
  OLE และลบ OLE อย่างมีประสิทธิภาพในโครงการของคุณ
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: วิธีลบวัตถุ OLE ใน Aspose.Tasks สำหรับ .NET
url: /th/net/advanced-concepts/ole-objects/
weight: 22
---

 Keep them.

Check that we didn't translate URLs.

Check that we kept markdown formatting.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการลบวัตถุ OLE ใน Aspose.Tasks สำหรับ .NET

## Introduction

Aspose.Tasks for .NET ให้คุณควบคุม OLE (Object Linking and Embedding) อย่างเต็มที่ที่อยู่ภายในไฟล์ Microsoft Project ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีการลบวัตถุ OLE**, วิธี **จัดการเนื้อหา OLE**, และขั้นตอนที่แน่นอนเพื่อ **ล้างข้อมูล OLE** เมื่อไม่ต้องการอีกต่อไป เมื่อเสร็จแล้วคุณจะสามารถโหลดไฟล์โครงการ, ตรวจสอบวัตถุ OLE ที่ฝังอยู่, ลบอย่างปลอดภัย, และบันทึกโครงการที่ทำความสะอาดแล้ว — ทั้งหมดด้วยโค้ด C# ที่สะอาดและอ่านง่าย.

## Quick Answers
- **วิธีหลักในการลบวัตถุ OLE คืออะไร?** Use `project.OleObjects.Clear()` and then save the project.  
- **ฉันต้องการใบอนุญาตพิเศษหรือไม่?** A valid Aspose.Tasks license is required for production use.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันสามารถตรวจสอบเนื้อหา OLE ก่อนลบได้หรือไม่?** Yes, iterate through `project.OleObjects` to read properties or content bytes.  
- **การล้างวัตถุ OLE ในโครงการขนาดใหญ่ปลอดภัยหรือไม่?** Absolutely – the operation is fast and does not affect other project data.

## What is “remove OLE objects” in the context of Aspose.Tasks?

การลบวัตถุ OLE หมายถึงการลบไฟล์ที่ฝังอยู่ (รูปภาพ, แผ่น Excel, เอกสาร Word ฯลฯ) ที่เก็บไว้ภายในไฟล์ Microsoft Project (.mpp) ซึ่งมีประโยชน์เมื่อคุณต้องการลดขนาดไฟล์, กำจัดการอ้างอิงที่ล้าสมัย, หรือปฏิบัติตามนโยบายการเก็บรักษาข้อมูล.

## Why manage OLE objects with Aspose.Tasks?

- **การควบคุมระดับละเอียด** – Access each OLE object’s ID, name, and raw bytes.  
- **การทำงานอัตโนมัติ** – Programmatically clean up dozens of projects without opening them in Microsoft Project.  
- **รองรับหลายเวอร์ชัน** – Works with Project 2007‑2023 files.  

## Prerequisites

Before we begin, make sure you have:

1. **Aspose.Tasks for .NET** installed. You can download it from [here](https://releases.aspose.com/tasks/net/).  
2. Basic knowledge of **C#** and the **.NET** ecosystem.  
3. A development environment such as **Visual Studio** (Community or higher).  

## Import Namespaces

First, import the namespaces that expose the Aspose.Tasks API:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## How to manage OLE objects – Step‑by‑step guide

Below we walk through three common scenarios:

1. **ตรวจสอบวัตถุ OLE** – read their properties and a snippet of the binary content.  
2. **ล้างวัตถุ OLE ทั้งหมด** – the core “remove OLE objects” operation.  
3. **อ่านข้อมูลการวางตำแหน่งเชิงภาพ** – useful when you need to adjust how OLE objects appear in Gantt or other views.

### Scenario 1: Inspect OLE objects

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access OLE objects  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Step 3: Iterate through OLE objects  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Step 4: Retrieve a small chunk of the binary content (optional)  
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

### Scenario 2: How to clear OLE – removing all embedded objects

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Clear OLE objects  
```csharp
project.OleObjects.Clear();
```

#### Step 3: Save the cleaned project  
```csharp
project.Save("ClearedProject.mpp");
```

> **เคล็ดลับมืออาชีพ:** After clearing OLE objects, you can call `project.Save` with a different file name to keep the original untouched.

### Scenario 3: Getting visual object placement properties

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access the first OLE object and its placement in the Gantt view  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Step 3: Retrieve placement properties  
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

## Common pitfalls and troubleshooting

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `project.OleObjects` ว่าง | The source .mpp file contains no OLE objects. | Verify the project file actually embeds OLE data (e.g., an attached Excel sheet). |
| `project.Save` throws an exception | File is locked or you lack write permissions. | Close any open instances of the file and ensure the target folder is writable. |
| Content bytes look corrupted | You are reading the full byte array as text. | Use `Get10Bytes` or write the bytes to a file to inspect them in a proper viewer. |

## Frequently Asked Questions

**ถาม:** Aspose.Tasks สามารถจัดการรูปแบบวัตถุ OLE ต่างๆ ได้หรือไม่?  
**ตอบ:** Yes, it supports images, Office documents, PDFs, and many other OLE formats.

**ถาม:** API รองรับเวอร์ชัน Microsoft Project เก่าได้หรือไม่?  
**ตอบ:** Absolutely – Aspose.Tasks works with Project files from 2007 through the latest 2023 releases.

**ถาม:** ฉันจะลบเฉพาะวัตถุ OLE ที่ต้องการแทนการลบทั้งหมดได้อย่างไร?  
**ตอบ:** Locate the desired `OleObject` by its `Id` or `Name` and call `project.OleObjects.Remove(oleObject)` before saving.

**ถาม:** การล้างวัตถุ OLE มีผลต่อการพึ่งพางานหรือกำหนดเวลาไหม?  
**ตอบ:** No. OLE objects are independent visual elements; removing them does not modify task relationships.

**ถาม:** ฉันจะหา ตัวอย่างเพิ่มเติมเกี่ยวกับการจัดการ OLE ได้จากที่ไหน?  
**ตอบ:** Check the official Aspose.Tasks documentation and the API reference for the `OleObject` and `VisualObjectsPlacements` classes.

## Conclusion

We’ve covered everything you need to **remove OLE objects** and manage OLE content in Aspose.Tasks for .NET. By following the step‑by‑step examples, you can inspect, clear, and adjust visual placement of OLE objects, keeping your project files lean and focused.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-16  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose