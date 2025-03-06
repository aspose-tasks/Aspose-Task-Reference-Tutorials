---
title: CSS บันทึกอาร์กิวเมนต์ใน Aspose.Tasks
linktitle: CSS บันทึกอาร์กิวเมนต์ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีบันทึกอาร์กิวเมนต์ CSS ใน Aspose.Tasks สำหรับ .NET เพื่อปรับแต่งเอาต์พุต HTML ปรับปรุงการนำเสนอด้วยการตั้งค่า CSS ที่ปรับแต่งโดยเฉพาะ
weight: 20
url: /th/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# CSS บันทึกอาร์กิวเมนต์ใน Aspose.Tasks

## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการบันทึกอาร์กิวเมนต์ CSS โดยใช้ Aspose.Tasks สำหรับ .NET Cascading Style Sheets (CSS) มีความสำคัญอย่างยิ่งต่อการกำหนดการนำเสนอองค์ประกอบ HTML Aspose.Tasks ช่วยให้เราสามารถจัดการและบันทึกแอตทริบิวต์ CSS เหล่านี้ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  การติดตั้ง: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/net/).

2. ความรู้พื้นฐาน: แนะนำให้คุ้นเคยกับสภาพแวดล้อมการพัฒนา C# และ .NET

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## ขั้นตอนที่ 1: กำหนดการบันทึกการโทรกลับ CSS

ประการแรก เรากำหนดวิธีการโทรกลับเพื่อบันทึก CSS เพื่อจัดการการบันทึกไฟล์ CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // ใช้ตรรกะการบันทึก CSS ของคุณที่นี่
    }
}
```

## ขั้นตอนที่ 2: ใช้การโทรกลับการบันทึกแบบอักษรและรูปภาพ

จากนั้น ใช้วิธีการโทรกลับเพื่อบันทึกแบบอักษรและรูปภาพในทำนองเดียวกัน:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // ใช้ตรรกะการบันทึกแบบอักษรของคุณที่นี่
}

public void ImageSaving(ImageSavingArgs args)
{
    // ใช้ตรรกะการบันทึกรูปภาพของคุณที่นี่
}
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึก

ตอนนี้ กำหนดค่าตัวเลือกการบันทึก HTML เพื่อใช้การโทรกลับที่นำไปใช้:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //กำหนดค่าตัวเลือกการบันทึก HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## ขั้นตอนที่ 4: บันทึกโครงการด้วย CSS ที่กำหนดเอง

สุดท้าย บันทึกโครงการของคุณด้วยการตั้งค่า CSS ที่กำหนดเอง:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการบันทึกอาร์กิวเมนต์ CSS โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยการกำหนดการโทรกลับการบันทึก CSS และการกำหนดค่าตัวเลือกการบันทึก HTML ทำให้เราสามารถจัดการแอตทริบิวต์ CSS ตามความต้องการของเราได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Tasks สำหรับ .NET คืออะไร

คำตอบ 1: Aspose.Tasks สำหรับ .NET เป็น .NET API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรมได้

### คำถามที่ 2: ฉันสามารถปรับแต่งแอตทริบิวต์ CSS เมื่อบันทึกไฟล์ HTML ด้วย Aspose.Tasks ได้หรือไม่

A2: ได้ คุณสามารถกำหนดการเรียกกลับที่บันทึก CSS เพื่อปรับแต่งแอตทริบิวต์ CSS ตามความต้องการของคุณได้

### คำถามที่ 3: Aspose.Tasks สำหรับ .NET เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่

A3: Aspose.Tasks สำหรับ .NET รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน

### คำถามที่ 4: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Tasks for .NET ได้ที่ไหน

A4: คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลโดยละเอียดและตัวอย่าง

### คำถามที่ 5: Aspose.Tasks สำหรับ .NET ให้การสนับสนุนสำหรับนักพัฒนาหรือไม่

 A5: ได้ คุณสามารถรับการสนับสนุนจากชุมชน Aspose.Tasks ผ่านทาง[ฟอรั่ม](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
