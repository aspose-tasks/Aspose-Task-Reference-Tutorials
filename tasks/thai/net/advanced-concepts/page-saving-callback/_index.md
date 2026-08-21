---
date: 2026-03-16
description: เรียนรู้วิธีการทำคอลแบ็กการบันทึกหน้าใน Aspose.Tasks สำหรับ .NET เพื่อให้สามารถจัดการสตรีมผลลัพธ์ของเอกสารหลายหน้าได้ตามต้องการ.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: ทำการเรียกกลับการบันทึกหน้าใน Aspose.Tasks
url: /th/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดำเนินการ page saving callback ใน Aspose.Tasks

## บทนำ

ในบทเรียนนี้ คุณจะได้เรียนรู้วิธี **implement page saving callback** ใน Aspose.Tasks สำหรับ .NET คุณลักษณะที่ทรงพลังนี้ช่วยให้คุณกำหนดแต่ละหน้าของเอกสารหลายหน้าไปยังสตรีมที่คุณเลือกได้ ให้คุณควบคุมการจัดเก็บหรือการประมวลผลต่อไปของผลลัพธ์อย่างเต็มที่

## คำตอบด่วน
- **What does the page saving callback do?** มันจับแต่ละหน้าที่เรนเดอร์เป็นสตรีมแยกต่างหากเพื่อให้คุณจัดการได้เป็นรายหน้า.  
- **Which format can I export to?** รูปแบบใดก็ได้ที่ `ImageSaveOptions` รองรับ เช่น PNG, JPEG, PDF.  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **Can I use this with .NET Core?** ใช่, Aspose.Tasks รองรับ .NET Core และ .NET 5/6+ อย่างเต็มที่.  
- **Is the callback thread‑safe?** คอลแบ็กทำงานบนเธรดเดียวกับที่ทำการเรนเดอร์ ดังนั้นกฎความปลอดภัยของเธรดปกติจึงใช้ได้.

## **implement page saving callback** คืออะไร?
แพทเทิร์น **implement page saving callback** ช่วยให้คุณใส่ตรรกะที่กำหนดเองเข้าไปในขั้นตอนการบันทึกของ Aspose.Tasks แทนการเขียนโดยตรงไปยังไฟล์ คุณจะได้รับอ็อบเจ็กต์ `Stream` สำหรับแต่ละหน้า ทำให้คุณสามารถเก็บไว้ในหน่วยความจำ, อัปโหลดไปยังคลาวด์, หรือทำการประมวลผลเพิ่มเติมได้

## ทำไมต้องส่งออกโครงการเป็น PNG ด้วยคอลแบ็ก?
การส่งออกโครงการเป็น PNG จะให้ภาพเรสเตอร์ของแต่ละหน้ากราฟ Gantt ซึ่งเหมาะสำหรับรายงาน, อีเมล, หรือการฝังในหน้าเว็บ การใช้คอลแบ็กหมายความว่าคุณสามารถเก็บแต่ละหน้าใน `MemoryStream` แยกกันโดยไม่ต้องสร้างไฟล์ชั่วคราวบนดิสก์

## ข้อกำหนดเบื้องต้น

1. **C# knowledge** – ความคุ้นเคยพื้นฐานกับคลาส, อินเทอร์เฟซ, และสตรีม.  
2. **Aspose.Tasks for .NET** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider, หรือเครื่องมือแก้ไขที่รองรับ .NET ใดก็ได้.

## นำเข้า Namespaces

เพื่อเริ่มต้น ให้นำเข้า Namespaces ที่จำเป็น:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project

โหลดไฟล์ MPP ที่มีอยู่เข้าสู่อินสแตนซ์ `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## ขั้นตอนที่ 2: กำหนดค่า Image Save Options

ตั้งค่า `ImageSaveOptions` สำหรับการส่งออกเป็น PNG และแนบคอลแบ็กที่กำหนดเอง:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tip:** การตั้งค่า `RenderToSinglePage = false` ทำให้แต่ละหน้ากราฟ Gantt ถูกเรนเดอร์แยกกัน ซึ่งเป็นสิ่งสำคัญสำหรับคอลแบ็กเพื่อรับสตรีมที่แตกต่างกัน.

## ขั้นตอนที่ 3: บันทึก Project ด้วยคอลแบ็ก

เรียกใช้เมธอด `Save` โดยส่ง `Stream.Null` เนื่องจากสตรีมจริงจะถูกจัดหาโดยคอลแบ็ก:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## ขั้นตอนที่ 4: ประมวลผลสตรีมหน้าที่บันทึกไว้

หลังจากการบันทึกเสร็จสมบูรณ์ คอลแบ็กจะเก็บคอลเลกชันของอ็อบเจ็กต์ `MemoryStream` — หนึ่งต่อหนึ่งหน้า คุณสามารถวนลูปผ่านมันได้ตอนนี้:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## ขั้นตอนที่ 5: Implement Custom Page Saving Callback

สร้างคลาส sealed ที่ implements `IPageSavingCallback`. คลาสนี้จะจับสตรีมของแต่ละหน้าและเก็บไว้ในรายการสำหรับใช้งานในภายหลัง.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **No pages are returned** | `RenderToSinglePage` ถูกทิ้งไว้เป็น `true`. | ตั้งค่า `RenderToSinglePage = false` เพื่อสร้างหน้าที่แยกกัน. |
| **Streams are empty** | `KeepStreamOpen` ตั้งเป็น `true` โดยไม่ได้ทำการ dispose หลังจากนั้น. | ตั้งค่าเป็น `false` (ค่าเริ่มต้น) และให้คอลแบ็กปิดสตรีมโดยอัตโนมัติ. |
| **Out‑of‑memory errors** | โครงการขนาดใหญ่มากสร้าง PNG ความละเอียดสูงจำนวนมาก. | ประมวลผลสตรีมทีละหนึ่งหรือเพิ่มขีดจำกัดหน่วยความจำของ VM. |

## คำถามที่พบบ่อย

**Q1: What is a page saving callback in Aspose.Tasks?**  
A: คอลแบ็กการบันทึกหน้าช่วยให้คุณดักจับกระบวนการบันทึกสำหรับแต่ละหน้าของเอกสารหลายหน้า โดยให้ `Stream` ที่กำหนดเองสำหรับหน้านั้น.

**Q2: Can I use different formats for saving pages using this callback?**  
A: ใช่. โดยการเปลี่ยน `SaveFileFormat` คุณสามารถส่งออกเป็น PNG, JPEG, PDF, SVG ฯลฯ

**Q3: Is Aspose.Tasks compatible with .NET Core?**  
A: แน่นอน. Aspose.Tasks รองรับ .NET Core, .NET 5, และ .NET 6.

**Q4: How can I handle errors during the page saving process?**  
A: ห่อหุ้มตรรกะคอลแบ็กด้วยบล็อก try/catch และบันทึกข้อยกเว้น เมธอด `OnFinish` เป็นตำแหน่งที่ดีสำหรับทำความสะอาดขั้นสุดท้าย.

**Q5: Where can I find more resources and support for Aspose.Tasks?**  
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือ, เข้าถึงเอกสาร [here](https://reference.aspose.com/tasks/net/), หรือสำรวจคุณลักษณะเพิ่มเติมและตัวเลือกการให้ใบอนุญาตบน [Aspose.Tasks website](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}