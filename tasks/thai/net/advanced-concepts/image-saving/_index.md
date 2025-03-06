---
title: การจัดการการบันทึกรูปภาพใน Aspose.Tasks
linktitle: การจัดการการบันทึกรูปภาพใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีจัดการการบันทึกรูปภาพใน Aspose.Tasks สำหรับ .NET โดยใช้คำแนะนำทีละขั้นตอน ผสานรวมฟังก์ชันการบันทึกรูปภาพเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
weight: 10
url: /th/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการการบันทึกรูปภาพใน Aspose.Tasks

## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการจัดการการบันทึกรูปภาพใน Aspose.Tasks สำหรับ .NET Aspose.Tasks เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม งานทั่วไปอย่างหนึ่งเมื่อทำงานกับไฟล์โปรเจ็กต์คือจำเป็นต้องบันทึกรูปภาพ ซึ่งอาจรวมถึงแผนภูมิ กราฟ หรือองค์ประกอบภาพอื่นๆ เราจะแจกแจงกระบวนการทีละขั้นตอนเพื่อให้มั่นใจในความชัดเจนและความเข้าใจตลอด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ
2.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
3. ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเข้าสู่โปรเจ็กต์ของเรา:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: สร้างวัตถุโครงการ

เริ่มต้นด้วยการสร้างออบเจ็กต์ Project จากไฟล์ Microsoft Project ของคุณ:

```csharp
var project = new Project("Project1.mpp");
```

## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึก

กำหนดตัวเลือกการบันทึกสำหรับโปรเจ็กต์ของคุณ โดยระบุเพจและการตั้งค่าอื่นๆ:

```csharp
var options = GetSaveOptions(1);
```

## ขั้นตอนที่ 3: บันทึกโครงการเป็น HTML

บันทึกโครงการเป็น HTML ด้วยตัวเลือกที่ระบุ:

```csharp
project.Save("document_out.html", options);
```

## ขั้นตอนที่ 4: ใช้การโทรกลับการบันทึกรูปภาพ

ใช้อินเทอร์เฟซ ImageSavingCallback เพื่อจัดการการบันทึกรูปภาพ:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // ตรรกะในการบันทึกรูปภาพอยู่ที่นี่
    }
}
```

## ขั้นตอนที่ 5: บันทึกรูปภาพไปยังไดเรกทอรีที่ระบุ

ภายในวิธี ImageSaving ให้ระบุตรรกะในการบันทึกภาพไปยังไดเร็กทอรีที่ต้องการ:

```csharp
if (args.FileName.EndsWith("png"))
{
    // บันทึกทรัพยากรที่ซ้อนกัน
}
else
{
    // ประหยัดทรัพยากรปกติ
}
```

## ขั้นตอนที่ 6: ระบุตัวเลือกการบันทึก

ระบุตัวเลือกการบันทึก รวมถึงการเรียกกลับสำหรับ CSS แบบอักษร และรูปภาพ:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // ระบุตัวเลือกการบันทึกที่นี่
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## บทสรุป

โดยสรุป การจัดการการบันทึกรูปภาพใน Aspose.Tasks สำหรับ .NET เกี่ยวข้องกับการกำหนดตัวเลือกการบันทึกและการดำเนินการโทรกลับเพื่อจัดการกระบวนการบันทึกอย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันการบันทึกรูปภาพเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks เพื่อจัดการไฟล์โปรเจ็กต์ในรูปแบบอื่นนอกเหนือจาก HTML ได้หรือไม่

A1: ใช่ Aspose.Tasks รองรับรูปแบบต่างๆ เช่น PDF, XLSX และ MPP

### คำถามที่ 2: Aspose.Tasks ให้การสนับสนุนสำหรับการผสานรวมพื้นที่จัดเก็บข้อมูลบนคลาวด์หรือไม่

ตอบ 2: ใช่ Aspose.Tasks มี API สำหรับการทำงานกับบริการจัดเก็บข้อมูลบนคลาวด์ยอดนิยม เช่น Amazon S3 และ Google Drive

### คำถามที่ 3: Aspose.Tasks เข้ากันได้กับ .NET Core หรือไม่

ตอบ 3: ใช่ Aspose.Tasks เข้ากันได้กับ .NET Core ทำให้คุณสามารถพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มได้

### คำถามที่ 4: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของภาพที่บันทึกไว้ได้หรือไม่?

A4: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของภาพที่บันทึกไว้ได้โดยการปรับเปลี่ยนตรรกะในการบันทึกรูปภาพภายในวิธีการโทรกลับ

### คำถามที่ 5: Aspose.Tasks มีเวอร์ชันทดลองใช้งานเพื่อการประเมินหรือไม่

 A5: ได้ คุณสามารถขอรับ Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
