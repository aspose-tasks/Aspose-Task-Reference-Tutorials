---
date: 2026-03-24
description: เรียนรู้การจัดการหน่วยความจำเต็มและวิธีบันทึกรูปภาพโครงการโดยใช้ Aspose.Tasks
  Layout Builder ใน .NET คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: การจัดการหน่วยความจำเต็มด้วย Aspose.Tasks Layout Builder (C#)
url: /th/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการหน่วยความจำที่หมดกับ Aspose.Tasks Layout Builder

## บทนำ

การจัดการหน่วยความจำที่หมดเป็นส่วนสำคัญของการสร้างแอปพลิเคชัน .NET ที่เชื่อถือได้ซึ่งทำงานกับไฟล์โครงการขนาดใหญ่ เมื่อคุณสร้างการแสดงผลด้วย Aspose.Tasks Layout Builder คุณอาจเจอข้อยกเว้นที่เกี่ยวกับหน่วยความจำอย่างรวดเร็ว โดยเฉพาะกับแผนภูมิ Gantt ที่ซับซ้อน ในบทแนะนำนี้เราจะพาคุณผ่านวิธี **จัดการข้อยกเว้นหน่วยความจำ**, **ปรับแต่งมุมมอง Gantt**, และ **บันทึกรูปภาพโครงการ** อย่างปลอดภัย เพื่อให้แอปพลิเคชันของคุณตอบสนองได้แม้กับตารางเวลาขนาดมหาศาล

## คำตอบอย่างรวดเร็ว
- **What is out of memory handling?** การจัดการการใช้หน่วยความจำและการจับข้อผิดพลาดประเภท `OutOfMemoryException` เมื่อประมวลผลข้อมูลขนาดใหญ่.
- **Which API helps?** Aspose.Tasks Layout Builder สำหรับ .NET.
- **Typical scenario?** การเรนเดอร์แผนภูมิ Gantt ความละเอียดสูงเป็น PNG.
- **Key prerequisite?** .NET (Framework 4.5+ หรือ .NET 6) พร้อมติดตั้ง Aspose.Tasks.
- **How to catch errors?** ใช้บล็อก `try…catch` สำหรับ `ApsLayoutBuilderOutOfMemoryException` และข้อยกเว้นที่เกี่ยวข้อง.

## ข้อกำหนดเบื้องต้น

ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

1. **C# basics** – คุณควรคุ้นเคยกับไวยากรณ์มาตรฐานของ C#.
2. **Aspose.Tasks for .NET** ติดตั้งแล้ว หากคุณยังไม่ได้เพิ่มมัน ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/net/).
3. **An IDE** เช่น Visual Studio (หรือ VS Code พร้อมส่วนขยาย C#) สำหรับคอมไพล์และรันตัวอย่าง.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอน 1: โหลดโครงการ

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

บรรทัดนี้โหลด **Blank2010.mpp** เข้าไปในอินสแตนซ์ `Project` เพื่อเตรียมการแสดงผล.

### ขั้นตอน 2: ปรับแต่งมุมมองแผนภูมิ Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

ที่นี่เราจะ **ปรับแต่งมุมมอง Gantt** โดยการปรับระดับ timescale กลางและล่าง การเปลี่ยนระดับเหล่านี้จะลดปริมาณข้อมูลที่เรนเดอร์พร้อมกัน ซึ่งช่วยบรรเทาแรงกดดันของหน่วยความจำได้.

### ขั้นตอน 3: ตั้งค่าตัวเลือกการบันทึกรูปภาพ

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` บอก Aspose.Tasks ว่าจะเรนเดอร์แผนภูมิอย่างไร เราเลือก PNG เป็นรูปแบบผลลัพธ์และผูก timescale กับมุมมองที่เพิ่งปรับแต่ง.

### ขั้นตอน 4: บันทึกโครงการเป็นรูปภาพ

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

การเรียก `Save` **บันทึกรูปภาพโครงการ** โดยใช้ตัวเลือกที่กำหนดข้างต้น หากโครงการมีขนาดใหญ่มาก นี่คือจุดที่สภาวะหน่วยความจำหมดมักจะเกิดขึ้น.

### ขั้นตอน 5: จัดการข้อยกเว้น

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

โดยการจับ `ApsLayoutBuilderOutOfMemoryException` คุณจะ **จัดการข้อยกเว้นหน่วยความจำ** อย่างราบรื่น โดยให้ข้อความชัดเจนแทนการทำให้แอปพลิเคชันพัง ส่วนการจับข้อยกเว้นที่สองจัดการกับปัญหา bitmap ขนาดที่อาจเกิดขึ้นเมื่อต้องเรนเดอร์แผนภูมิขนาดใหญ่.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **OutOfMemoryException** | การเรนเดอร์ภาพความละเอียดสูงมากใช้ RAM มากกว่าที่กระบวนการสามารถจัดสรรได้ | ลดขนาดภาพ, ทำให้ระดับ timescale ง่ายขึ้น, หรือแยกแผนภูมิเป็นหลายภาพ |
| **BitmapInvalidSizeException** | ขนาด bitmap ที่ร้องขอเกินขีดจำกัดสูงสุดของแพลตฟอร์ม | จำกัดความกว้าง/สูงใน `ImageSaveOptions` หรือเรนเดอร์เป็นส่วน ๆ |
| **Slow performance** | ไฟล์โครงการขนาดใหญ่ต้องการการประมวลผลมาก | เปิดใช้งาน `project.Set(Prj.SaveToCache, true)` ก่อนการเรนเดอร์ หรือใช้เธรดพื้นหลัง |

## คำถามที่พบบ่อย

### Q1: Aspose.Tasks สำหรับ .NET คืออะไร?

A1: Aspose.Tasks สำหรับ .NET เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project อย่างโปรแกรมเมติกในแอปพลิเคชัน .NET.

### Q2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?

A2: คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้โดยไปที่ [this link](https://purchase.aspose.com/temporary-license/).

### Q3: Aspose.Tasks เหมาะกับการจัดการไฟล์โครงการขนาดใหญ่หรือไม่?

A3: ใช่, Aspose.Tasks มีฟีเจอร์และการปรับประสิทธิภาพเพื่อจัดการไฟล์โครงการขนาดใหญ่อย่างมีประสิทธิภาพ แต่ผู้พัฒนายังควรพิจารณากลยุทธ์การจัดการหน่วยความจำ.

### Q4: ฉันสามารถปรับแต่งลักษณะของแผนภูมิ Gantt ด้วย Aspose.Tasks ได้หรือไม่?

A4: แน่นอน! Aspose.Tasks มีความสามารถอย่างกว้างขวางในการปรับแต่งลักษณะและการจัดวางของแผนภูมิ Gantt ตามความต้องการของคุณ.

### Q5: ฉันจะหาแนวทางช่วยเหลือและสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้จากที่ไหน?

A5: คุณสามารถหาแนวทางช่วยเหลือและสนับสนุนเพิ่มเติม รวมถึงเข้าร่วมชุมชนได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## คำถามที่พบบ่อย

**Q: ฉันจะลดการใช้หน่วยความจำเมื่อบันทึกรูปภาพโครงการได้อย่างไร?**  
A: ลดความละเอียดของภาพ, จำกัดช่วง timescale, หรือบันทึกแผนภูมิเป็นหลายส่วนย่อยที่เล็กลง.

**Q: สามารถสตรีมภาพโดยตรงไปยังการตอบสนองเว็บได้หรือไม่?**  
A: ได้, คุณสามารถใช้ `project.Save(stream, options)` แล้วเขียนสตรีมไปยังการตอบสนอง HTTP.

**Q: Aspose.Tasks รองรับ .NET Core และ .NET 5/6 หรือไม่?**  
A: ไลบรารีนี้เข้ากันได้เต็มที่กับ .NET Core, .NET 5, และ .NET 6.

**Q: ควรทำอย่างไรหากยังพบข้อผิดพลาดหน่วยความจำหมดหลังจากปรับแต่งแล้ว?**  
A: พิจารณาประมวลผลโครงการบนเครื่องที่มี RAM มากขึ้น หรือย้ายการเรนเดอร์ไปยังบริการพื้นหลัง.

**Q: ฉันสามารถส่งออกแผนภูมิ Gantt ไปยังรูปแบบอื่นนอกจาก PNG ได้หรือไม่?**  
A: ได้, `ImageSaveOptions` รองรับ JPEG, BMP, และ TIFF นอกเหนือจาก PNG.

---

**อัปเดตล่าสุด:** 2026-03-24  
**ทดสอบกับ:** Aspose.Tasks 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}