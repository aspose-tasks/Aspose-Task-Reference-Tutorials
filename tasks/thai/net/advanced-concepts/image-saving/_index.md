---
date: 2026-03-05
description: เรียนรู้วิธีบันทึกรูปภาพ, สร้าง HTML พร้อมรูปภาพ, และปรับแต่งการส่งออกรูปภาพโดยใช้
  Aspose.Tasks สำหรับ .NET. คู่มือขั้นตอนต่อขั้นตอนในการบันทึกโครงการเป็น HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: วิธีบันทึกรูปภาพด้วย Aspose.Tasks สำหรับ .NET
url: /th/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบันทึกรูปภาพด้วย Aspose.Tasks สำหรับ .NET

## คำแนะนำ

ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีบันทึกรูปภาพ** จากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks API สำหรับ .NET ไม่ว่าคุณจะต้องการฝังแผนภูมิในรายงาน, สร้างหน้า HTML ที่มีภาพโครงการ, หรือเพียงแค่ส่งออกทรัพยากรแบบแผนภาพ ขั้นตอนต่อไปนี้จะนำคุณผ่านกระบวนการทั้งหมด — ตั้งแต่การตั้งค่าอ็อบเจ็กต์โปรเจกต์จนถึงการปรับแต่ง callback การส่งออกรูปภาพ

## คำตอบด่วน
- **“how to save images” หมายถึงอะไรใน Aspose.Tasks?**  
  หมายถึงการใช้ interface `IImageSavingCallback` เพื่อควบคุมว่าทรัพยากรภาพจะถูกเขียนลงดิสก์ที่ไหนและอย่างไร
- **ฉันสามารถบันทึกโครงการเป็น HTML พร้อมรูปภาพฝังได้หรือไม่?**  
  ได้, โดยใช้ `HtmlSaveOptions` ร่วมกับ image‑saving callbacks คุณสามารถ **บันทึกโครงการเป็น HTML** ที่รวมรูปภาพที่สร้างทั้งหมด
- **ฉันต้องการไลเซนส์สำหรับการส่งออกรูปภาพหรือไม่?**  
  ไลเซนส์ทดลองชั่วคราวใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมจริง
- **เวอร์ชัน .NET ไหนที่รองรับ?**  
  Aspose.Tasks for .NET รองรับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+
- **สามารถปรับแต่งการส่งออกรูปภาพ (รูปแบบ, โฟลเดอร์, ชื่อไฟล์) ได้หรือไม่?**  
  แน่นอน – callback ให้คุณควบคุมชื่อไฟล์, รูปแบบ, และตำแหน่งปลายทางได้อย่างเต็มที่

## “how to save images” คืออะไรในบริบทของ Aspose.Tasks?
การบันทึกรูปภาพหมายถึงการสกัดองค์ประกอบภาพ (แผนภูมิ, แถบ Gantt, กราฟิกทรัพยากร) จากไฟล์ Project แล้วเขียนลงไฟล์รูปภาพ (PNG, JPEG ฯลฯ) Aspose.Tasks มีกลไก callback ที่ยืดหยุ่นให้คุณกำหนดตำแหน่งที่แน่นอน, รูปแบบการตั้งชื่อ, และแม้กระทั่งรูปแบบไฟล์ภาพได้

## ทำไมต้องใช้ Aspose.Tasks เพื่อบันทึกรูปภาพ?
- **การควบคุมผ่านโปรแกรมเต็มรูปแบบ** – ไม่ต้องมีการโต้ตอบ UI ด้วยตนเอง  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS ผ่าน .NET Core  
- **การเรนเดอร์คุณภาพสูง** – รูปภาพคงคุณภาพเดียวกับมุมมอง Project ดั้งเดิม  
- **การสร้าง HTML อย่างง่าย** – ผสาน `HtmlSaveOptions` กับ image callbacks เพื่อ **สร้าง HTML พร้อมรูปภาพ** อัตโนมัติ

## ข้อกำหนดเบื้องต้น

1. ติดตั้ง Visual Studio บนเครื่องพัฒนาของคุณ  
2. ดาวน์โหลด Aspose.Tasks for .NET จาก [here](https://releases.aspose.com/tasks/net/)  
3. มีความคุ้นเคยพื้นฐานกับ C# และโครงสร้างโปรเจกต์ .NET  

## นำเข้า Namespaces

แรก, นำ namespaces ที่จำเป็นเข้าไปในไฟล์ซอร์สของคุณ:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project

โหลดไฟล์ Microsoft Project ที่คุณต้องการทำงานด้วย:

```csharp
var project = new Project("Project1.mpp");
```

## ขั้นตอนที่ 2: กำหนด Save Options

สร้าง HTML save options ที่จะเก็บ image‑saving callbacks ของเรา:

```csharp
var options = GetSaveOptions(1);
```

## ขั้นตอนที่ 3: บันทึกโครงการเป็น HTML (save project as html)

ตอนนี้ส่งออกโครงการเป็นไฟล์ HTML. รูปภาพที่อ้างอิงใน HTML จะถูกสร้างโดย callback ที่เราจะกำหนดต่อไป:

```csharp
project.Save("document_out.html", options);
```

## ขั้นตอนที่ 4: Implement Image Saving Callback (ปรับแต่งการส่งออกรูปภาพ)

Implement interface `IImageSavingCallback`. ที่นี่คุณสามารถ **ปรับแต่งการส่งออกรูปภาพ** ได้:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## ขั้นตอนที่ 5: บันทึกรูปภาพไปยังไดเรกทอรีที่ระบุ

ภายในเมธอด `ImageSaving`, ตัดสินใจว่ารูปภาพแต่ละภาพจะถูกจัดเก็บที่ไหน. ตัวอย่างด้านล่างแยกแยะทรัพยากร PNG จากรูปแบบอื่น:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## ขั้นตอนที่ 6: ระบุ Save Options (รวมถึง callbacks)

เชื่อมต่อ callbacks สำหรับฟอนต์, CSS, และรูปภาพ. สิ่งนี้ทำให้ทุกองค์ประกอบภาพถูกจัดการอย่างสม่ำเสมอ:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|--------|
| รูปภาพไม่แสดงใน HTML ที่สร้าง | Callback ไม่ได้กำหนดเส้นทางไฟล์ที่ถูกต้อง | ตรวจสอบให้ `args.Path` ชี้ไปยังโฟลเดอร์ที่สามารถเขียนได้และตั้งค่า `args.ImageStream` อย่างถูกต้อง |
| ไฟล์ PNG ถูกบันทึกด้วยนามสกุลผิด | ตรรกะเงื่อนไขตรวจสอบเฉพาะส่วนต่อท้าย “png” | ใช้ `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` เพื่อการตรวจจับที่มั่นคง |
| การอ้างอิง HTML แตกหักหลังจากย้ายไฟล์ | เส้นทางสัมพันธ์เปลี่ยนหลังจากย้ายโฟลเดอร์ผลลัพธ์ | เก็บโฟลเดอร์ HTML และรูปภาพไว้ด้วยกันหรืออัปเดต `options.ImageFolder` ให้สอดคล้อง |

## สรุป

โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีบันทึกรูปภาพ** จากไฟล์ Project, **บันทึกโครงการเป็น HTML**, และ **ปรับแต่งการส่งออกรูปภาพ** ให้สอดคล้องกับโครงสร้างโฟลเดอร์ของแอปพลิเคชันของคุณ วิธีนี้ทำให้คุณ **สร้าง HTML พร้อมรูปภาพ** ที่สามารถฝังในรายงาน, พอร์ทัลเอกสาร, หรือแดชบอร์ดเว็บได้อย่างราบรื่น

## คำถามที่พบบ่อย

**Q1: ฉันสามารถใช้ Aspose.Tasks เพื่อจัดการไฟล์โครงการในรูปแบบอื่นนอกจาก HTML ได้หรือไม่?**  
A1: ได้, Aspose.Tasks รองรับรูปแบบต่าง ๆ เช่น PDF, XLSX, และ MPP.

**Q2: Aspose.Tasks มีการสนับสนุนการรวมกับคลาวด์สตอเรจหรือไม่?**  
A2: ได้, Aspose.Tasks มี API สำหรับทำงานกับบริการคลาวด์สตอเรจยอดนิยมเช่น Amazon S3 และ Google Drive.

**Q3: Aspose.Tasks รองรับ .NET Core หรือไม่?**  
A3: ได้, Aspose.Tasks รองรับ .NET Core ทำให้คุณพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มได้.

**Q4: ฉันสามารถปรับแต่งลักษณะของรูปภาพที่บันทึกได้หรือไม่?**  
A4: ได้, คุณสามารถปรับแต่งลักษณะของรูปภาพที่บันทึกโดยแก้ไขตรรกะการบันทึกรูปภาพภายในเมธอด callback.

**Q5: Aspose.Tasks มีเวอร์ชันทดลองสำหรับการประเมินหรือไม่?**  
A5: ได้, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Tasks จาก [here](https://releases.aspose.com/).

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}