---
date: 2026-04-06
description: เรียนรู้วิธีเปลี่ยนสไตล์ของแถบและปรับแต่งสีของแถบใน Aspose.Tasks สำหรับ
  .NET เพื่อเพิ่มการมองเห็นของโครงการ.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: แถบการจัดรูปแบบใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีเปลี่ยนการจัดรูปแบบแถบใน Aspose.Tasks
url: /th/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการเปลี่ยนแปลงการจัดรูปแบบแถบใน Aspose.Tasks

## บทนำ

หากคุณต้องการ **วิธีการเปลี่ยนแปลงแถบ** ในไฟล์ Microsoft Project, Aspose.Tasks for .NET ให้การควบคุมเต็มรูปแบบเหนือสีของแถบ, รูปร่าง, และสไตล์ข้อความ. โดยการปรับแต่งสีของแถบและคุณลักษณะภาพอื่น ๆ คุณสามารถทำให้แผนโครงการอ่านง่ายขึ้นและสอดคล้องกับแบรนด์ขององค์กรของคุณมากขึ้น. ในบทแนะนำนี้เราจะเดินผ่านตัวอย่างครบถ้วนแบบขั้นตอนต่อขั้นตอนที่แสดงวิธีการเปลี่ยนแปลงการจัดรูปแบบแถบ, ตั้งแต่การโหลดโครงการจนถึงการส่งออกพร้อมกฎภาพใหม่ที่ถูกนำไปใช้.

## คำตอบด่วน

- **อะไรที่ฉันสามารถจัดรูปแบบได้?** Bars, milestones, and task text in Gantt charts.  
- **ฟอร์แมตใดสนับสนุนแถบที่จัดรูปแบบ?** PDF, XLSX, HTML and native MPP when saved with `PdfSaveOptions`.  
- **ฉันต้องการไลเซนส์หรือไม่?** A commercial license is required for production use; a free trial works for testing.  
- **ฉันสามารถใช้หลายสไตล์ได้หรือไม่?** Yes – add as many `BarStyle` objects as you need.  
- **มันเข้ากันได้กับ .NET Core หรือไม่?** Absolutely – works with .NET Framework and .NET Core/5/6+.

## การจัดรูปแบบแถบใน Aspose.Tasks คืออะไร?

การจัดรูปแบบแถบช่วยให้คุณกำหนดกฎภาพที่เครื่อง Aspose.Tasks ใช้เมื่อเรนเดอร์แผนภูมิ Gantt. แต่ละกฎ (เป็น **BarStyle**) จะมุ่งเป้าไปที่ประเภทรายการเฉพาะ—tasks, milestones, or summary tasks—and lets you set colors, shapes, and even custom text.

## ทำไมต้องปรับแต่งสีของแถบ?

การปรับแต่งสีของแถบช่วยให้ผู้มีส่วนได้ส่วนเสียระบุเส้นทางสำคัญ, งานที่ล่าช้า, หรือไมล์สโตนได้ทันที. นอกจากนี้ยังทำให้คุณสามารถจับคู่โทนสีขององค์กร, ทำให้รายงานดูเป็นมืออาชีพและสอดคล้องกับแบรนด์.

## ข้อกำหนดเบื้องต้น

1. **Aspose.Tasks for .NET** – ดาวน์โหลดได้จาก [download page](https://releases.aspose.com/tasks/net/).  
2. สภาพแวดล้อมการพัฒนาที่รองรับ .NET (Framework 4.6+, .NET Core 3.1+ หรือใหม่กว่า).  
3. ความคุ้นเคยพื้นฐานกับ C# – ตัวอย่างใช้โค้ดที่ง่ายและเป็นอิสระ.

## นำเข้า Namespaces

ก่อนอื่น, ให้นำเข้า namespaces ที่มีคลาสที่เราจะใช้:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## ขั้นตอนที่ 1: โหลดโครงการ

โหลดไฟล์ MPP ที่มีอยู่ (หรือสร้างใหม่) เพื่อให้คุณมีอ็อบเจ็กต์โครงการที่ทำงานด้วย:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## ขั้นตอนที่ 2: กำหนดค่า Save Options

สร้างอินสแตนซ์ของ `PdfSaveOptions` และเริ่มต้นคอลเลกชัน `BarStyles` ที่เราจะเก็บสไตล์ที่กำหนดเองของเรา:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## ขั้นตอนที่ 3: กำหนด Bar Style

ตอนนี้เราจะสร้างอ็อบเจ็กต์ `BarStyle` และตั้งค่าคุณสมบัติที่ควบคุมลักษณะของแถบ. ที่นี่คือจุดที่เราจะ **ปรับแต่งสีของแถบ** และรูปร่าง:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## ขั้นตอนที่ 4: ปรับแต่ง Text Converter (ไม่บังคับ)

หากคุณต้องการปรับแต่งข้อความที่ปรากฏบนแถบ, คุณสามารถกำหนดตัวแปลงแบบกำหนดเอง. ตัวอย่างนี้จะเพิ่มคำนำหน้าชื่องานที่ยังไม่ได้เริ่มต้นด้วย “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## ขั้นตอนที่ 5: เพิ่ม Bar Style ไปยัง Options

เพิ่มสไตล์ที่กำหนดค่าเต็มรูปแบบไปยังคอลเลกชัน `BarStyles` ของตัวเลือกการบันทึก:

```csharp
options.BarStyles.Add(style);
```

## ขั้นตอนที่ 6: บันทึกโครงการ

สุดท้าย, ส่งออกโครงการ. PDF (หรือฟอร์แมตอื่น) จะเรนเดอร์แผนภูมิ Gantt โดยใช้สไตล์แถบที่เรากำหนด:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่พบการใช้สไตล์แถบ** | คอลเลกชัน `BarStyles` ว่างเปล่าหรือไม่ได้แนบกับตัวเลือกการบันทึก. | ตรวจสอบให้แน่ใจว่าคุณได้เพิ่ม `BarStyle` ไปยัง `options.BarStyles` ก่อนเรียก `Save`. |
| **สีดูแตกต่างใน PDF** | การเรนเดอร์ PDF อาจใช้โปรไฟล์สีที่แตกต่าง. | ใช้ค่า `System.Drawing.Color` มาตรฐานหรือกำหนดสี ARGB แบบกำหนดเอง. |
| **ตัวแปลงข้อความทำให้เกิด null reference** | คุณสมบัติของงาน `Tsk.Name` มีค่า null สำหรับบางงาน. | เพิ่มการตรวจสอบ null ก่อนเข้าถึง `task.Get(Tsk.Name)`. |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้หลายสไตล์แถบกับโครงการเดียวได้หรือไม่?

A1: ใช่, คุณสามารถกำหนดและใช้หลายสไตล์แถบกับประเภทงานที่แตกต่างกันภายในโครงการเดียวได้.

### Q2: สามารถเปลี่ยนสไตล์แถบแบบไดนามิกระหว่างการทำงานได้หรือไม่?

A2: ใช่, คุณสามารถแก้ไขสไตล์แถบแบบไดนามิกตามเงื่อนไขบางอย่างหรือความต้องการของผู้ใช้ภายในแอปพลิเคชันของคุณ.

### Q3: Aspose.Tasks รองรับการส่งออกโครงการที่มีแถบจัดรูปแบบไปยังฟอร์แมตไฟล์ต่าง ๆ หรือไม่?

A3: ใช่, Aspose.Tasks รองรับการส่งออกโครงการที่มีแถบจัดรูปแบบไปยังฟอร์แมตต่าง ๆ เช่น PDF, XLSX, และ HTML.

### Q4: มีสไตล์แถกที่กำหนดล่วงหน้าใน Aspose.Tasks หรือไม่?

A4: แม้ว่า Aspose.Tasks จะมีสไตล์แถบเริ่มต้น, นักพัฒนายังสามารถสร้างสไตล์แถบแบบกำหนดเองให้ตรงกับความต้องการของโครงการได้.

### Q5: ฉันสามารถดึงและแก้ไขสไตล์แถบที่มีอยู่ในโครงการโดยใช้ API ได้หรือไม่?

A5: ใช่, คุณสามารถดึงและแก้ไขสไตล์แถบที่มีอยู่โดยใช้ Aspose.Tasks for .NET API.

## คำถามที่พบบ่อย

**Q: ฉันจะเปลี่ยนสีของแถบสำหรับงานปกติแทนไมล์สโตนอย่างไร?**  
A: ตั้งค่า `style.ItemType = BarItemType.Task;` และกำหนด `style.BarColor` ให้เป็น `Color` ที่ต้องการ.

**Q: ฉันสามารถใช้วิธีนี้เพื่อจัดรูปแบบแถบเมื่อส่งออกเป็น HTML ได้หรือไม่?**  
A: ใช่. ใช้ `HtmlSaveOptions` และเติมคอลเลกชัน `BarStyles` ของมันในลักษณะเดียวกัน.

**Q: มีขีดจำกัดจำนวนสไตล์แถบที่ฉันสามารถกำหนดได้หรือไม่?**  
A: โดยหลักไม่มี; คุณสามารถเพิ่มได้ตามต้องการ, แต่ควรคำนึงถึงประสิทธิภาพเมื่อคอลเลกชันมีขนาดใหญ่มาก.

**Q: ฉันต้องเรียก `project.Calculate()` หลังจากเปลี่ยนสไตล์หรือไม่?**  
A: ไม่จำเป็น, สไตล์จะถูกนำไปใช้ระหว่างการบันทึก; การคำนวณใหม่จำเป็นเฉพาะเมื่อมีการเปลี่ยนแปลงตารางเวลา.

---

**อัปเดตล่าสุด:** 2026-04-06  
**ทดสอบด้วย:** Aspose.Tasks 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}