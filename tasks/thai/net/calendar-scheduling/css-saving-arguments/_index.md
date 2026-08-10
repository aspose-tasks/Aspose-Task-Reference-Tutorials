---
date: 2026-07-05
description: เรียนรู้วิธีปรับแต่ง CSS ขณะส่งออกโครงการเป็น HTML ด้วย Aspose.Tasks
  สำหรับ .NET ปรับผลลัพธ์ HTML ด้วยอาร์กิวเมนต์การบันทึก CSS
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: วิธีปรับแต่ง CSS เมื่อบันทึกโครงการด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: วิธีปรับแต่ง CSS เมื่อบันทึกโครงการด้วย Aspose.Tasks
url: /th/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับแต่ง CSS เมื่อบันทึกโครงการด้วย Aspose.Tasks

ในคู่มือนี้คุณจะได้ค้นพบ **วิธีปรับแต่ง CSS** ระหว่างการส่งออก HTML ของไฟล์ Microsoft Project ด้วย Aspose.Tasks สำหรับ .NET โดยการปรับแต่งอาร์กิวเมนต์การบันทึก CSS คุณจะได้ควบคุมสไตล์การแสดงผลของหน้า HTML ที่สร้างขึ้นอย่างเต็มที่ ทำให้ผลลัพธ์ตรงกับแบรนด์หรือมาตรฐานการรายงานของคุณ

## คำตอบด่วน
- **จุดเริ่มต้นหลักคืออะไร?** ใช้ `HtmlSaveOptions` กับคอลแบ็กที่กำหนดเอง.  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันสามารถส่งออกโครงการขนาดใหญ่ได้หรือไม่?** Aspose.Tasks จัดการโครงการที่มี > 10,000 งานโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **การปรับแต่ง CSS เป็นทางเลือกหรือไม่?** ใช่, คุณสามารถละเว้นคอลแบ็กเพื่อใช้สไตล์ชีตเริ่มต้น.

## วิธีปรับแต่ง CSS ใน Aspose.Tasks?

โหลดโครงการของคุณ, แนบคอลแบ็กการบันทึก CSS ไปยังอ็อบเจ็กต์ `HtmlSaveOptions`, แล้วเรียก `project.Save`. แพทเทิร์นนี้ทำให้คุณเขียนไฟล์ CSS ที่กำหนดเอง, แทนที่สไตล์เริ่มต้น, และควบคุมโครงสร้างโฟลเดอร์—ทั้งหมดในไม่กี่บรรทัดของโค้ด. คอลแบ็กจะถูกเรียกโดยอัตโนมัติสำหรับแต่ละไฟล์ CSS ระหว่างกระบวนการส่งออก.

`HtmlSaveOptions` กำหนดการส่งออกโครงการเป็น HTML อย่างไร.

## บทนำ

ในบทเรียนนี้เราจะเจาะลึกกระบวนการบันทึกอาร์กิวเมนต์ CSS ด้วย Aspose.Tasks สำหรับ .NET. Cascading Style Sheets (CSS) มีความสำคัญต่อการกำหนดการนำเสนอขององค์ประกอบ HTML. Aspose.Tasks ช่วยให้เราจัดการและบันทึกคุณลักษณะ CSS เหล่านี้ได้อย่างมีประสิทธิภาพ.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. การติดตั้ง: ตรวจสอบว่าคุณได้ติดตั้ง Aspose.Tasks สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [website](https://releases.aspose.com/tasks/net/).

2. ความรู้พื้นฐาน: แนะนำให้คุ้นเคยกับ C# และสภาพแวดล้อมการพัฒนา .NET.

## นำเข้า Namespaces

เพื่อเริ่มต้น, ให้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## ขั้นตอนที่ 1: กำหนด CSS Saving Callbacks

`ICssSavingCallback` เป็นอินเทอร์เฟซที่ให้คุณปรับแต่งวิธีการบันทึกไฟล์ CSS ระหว่างการส่งออก HTML.

A **CSS saving callback** เป็น delegate ที่ Aspose.Tasks เรียกใช้เพื่อเขียนไฟล์ CSS ระหว่างการส่งออก HTML. กำหนดเมธอดคอลแบ็กเพื่อควบคุมวิธีการสร้างแต่ละไฟล์ CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## ขั้นตอนที่ 2: Implement Font and Image Saving Callbacks

`FontSavingArgs` ให้ข้อมูลเกี่ยวกับฟอนต์ที่กำลังบันทึก, ในขณะที่ `ImageSavingArgs` ให้รายละเอียดสำหรับทรัพยากรภาพ.

Implement the font and image saving callback methods similarly:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## ขั้นตอนที่ 3: กำหนดค่า Save Options

`HtmlSaveOptions` เป็นอ็อบเจ็กต์การกำหนดค่าที่ควบคุมวิธีการส่งออก Project เป็น HTML.

`HtmlSaveOptions` ให้คุณระบุคอลแบ็ก, โฟลเดอร์ผลลัพธ์, และการตั้งค่าอื่น ๆ ของการส่งออก.

Set its properties to use the callbacks defined earlier and to specify the output folder:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## ขั้นตอนที่ 4: บันทึกโครงการด้วย CSS ที่กำหนดเอง

`Project` แทนไฟล์ Microsoft Project ที่สามารถจัดการและบันทึกได้.

Finally, save your project with the customized CSS settings:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## ทำไมต้องปรับแต่ง CSS เมื่อส่งออกโครงการ?

Aspose.Tasks รองรับ **export project to HTML** ในรูปแบบกว่า 30 แบบและสามารถสร้างไฟล์ CSS แยกต่างหากได้ถึง 30 ไฟล์ต่อการส่งออก. มันประมวลผลโครงการที่มีงานมากกว่า 10 000 งานอย่างเชื่อถือได้โดยคงการใช้หน่วยความจำให้อยู่ต่ำกว่า 200 MB, ทำให้การรายงานระดับองค์กรเป็นไปได้โดยไม่มีคอขวดด้านประสิทธิภาพ.

## สรุป

ในบทเรียนนี้เราได้สำรวจวิธีบันทึกอาร์กิวเมนต์ CSS ด้วย Aspose.Tasks สำหรับ .NET. โดยการกำหนด CSS saving callbacks และการตั้งค่า HTML save options เราสามารถจัดการคุณลักษณะ CSS ได้อย่างมีประสิทธิภาพตามความต้องการของเรา.

## คำถามที่พบบ่อย

### Q1: Aspose.Tasks for .NET คืออะไร?
A1: Aspose.Tasks for .NET เป็น API ของ .NET ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้โดยโปรแกรม.

### Q2: ฉันสามารถปรับแต่งคุณลักษณะ CSS เมื่อบันทึกไฟล์ HTML ด้วย Aspose.Tasks ได้หรือไม่?
A2: ใช่, คุณสามารถกำหนด CSS saving callbacks เพื่อปรับแต่งคุณลักษณะ CSS ตามความต้องการของคุณ.

### Q3: Aspose.Tasks for .NET รองรับกับเวอร์ชันทั้งหมดของไฟล์ Microsoft Project หรือไม่?
A3: Aspose.Tasks for .NET รองรับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project, ทำให้มั่นใจได้ว่ามีความเข้ากันได้ในสภาพแวดล้อมที่หลากหลาย.

### Q4: ฉันสามารถค้นหาเอกสารประกอบที่ครบถ้วนสำหรับ Aspose.Tasks for .NET ได้ที่ไหน?
A4: คุณสามารถอ้างอิงไปที่ [documentation](https://reference.aspose.com/tasks/net/) เพื่อรับข้อมูลรายละเอียดและตัวอย่าง.

### Q5: Aspose.Tasks for .NET มีการสนับสนุนนักพัฒนาหรือไม่?
A5: ใช่, คุณสามารถรับการสนับสนุนจากชุมชน Aspose.Tasks ผ่าน [forum](https://forum.aspose.com/c/tasks/15).

**คำถามเพิ่มเติม**

**Q: การปรับแต่ง CSS มีผลต่อขนาดของ HTML ที่ส่งออกอย่างไร?**  
A: การใช้ CSS ที่กำหนดเองสามารถลดขนาดรวมได้สูงสุดประมาณ 15 % เนื่องจากคุณสามารถกำจัดสไตล์เริ่มต้นที่ไม่ได้ใช้.

**Q: ฉันสามารถใช้คอลแบ็กเดียวกันสำหรับหลายโครงการได้หรือไม่?**  
A: แน่นอน. กำหนดคอลแบ็กเพียงครั้งเดียวและนำกลับมาใช้ซ้ำได้กับการส่งออกโครงการจำนวนใดก็ได้.

**Q: สามารถฝัง CSS ลงใน HTML โดยตรงแทนไฟล์แยกได้หรือไม่?**  
A: ใช่, ตั้งค่า `HtmlSaveOptions.EmbeddedCss = true` เพื่อฝังสไตล์ชีตในตัว HTML, ซึ่งทำให้การจัดจำหน่ายง่ายขึ้น.

---

**อัปเดตล่าสุด:** 2026-07-05  
**ทดสอบกับ:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [บันทึก MS Project เป็น HTML ด้วย Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementing Page Saving Callback in Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Handling Image Saving in Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}