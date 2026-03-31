---
date: 2026-03-21
description: เรียนรู้วิธีการส่งออกภาพและจัดการกับ BitmapInvalidSizeException เมื่อบันทึกโครงการเป็นภาพใน
  Aspose.Tasks for .NET รวมขั้นตอนการบันทึกโครงการเป็นภาพและส่งออกโครงการเป็น PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: วิธีส่งออกภาพและจัดการข้อยกเว้นขนาดไม่ถูกต้อง
url: /th/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการส่งออกภาพ – การจัดการข้อยกเว้นขนาดไม่ถูกต้องสำหรับ Bitmap ใน Aspose.Tasks

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีการส่งออกภาพ** จากไฟล์ Microsoft Project ด้วย Aspose.Tasks สำหรับ .NET และที่สำคัญกว่าคือวิธีการดักจับ `BitmapInvalidSizeException` ที่อาจเกิดขึ้นระหว่างกระบวนการ การส่งออกโครงการเป็นภาพเป็นความต้องการทั่วไปสำหรับแดชบอร์ดรายงาน, เอกสาร, หรือเพียงแค่การแชร์ภาพสแนปช็อตของตารางเวลา เมื่อคุณอ่านจบคู่มือนี้แล้วคุณจะสามารถ **บันทึกโครงการเป็นภาพ** ได้อย่างน่าเชื่อถือและแม้กระทั่ง **ส่งออกโครงการเป็นรูปแบบ PNG** โดยไม่มีการหยุดทำงานที่ไม่คาดคิด

## คำตอบสั้น
- **ข้อยกเว้นใดที่อาจเกิดขึ้นเมื่อส่งออกภาพ?** `BitmapInvalidSizeException`  
- **รูปแบบใดที่ใช้ในตัวอย่าง?** PNG (`SaveFileFormat.Png`)  
- **ต้องใช้ไลเซนส์พิเศษหรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Tasks ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **สามารถเปลี่ยนช่วงเวลา (timescale) ได้หรือไม่?** ได้ – คุณสามารถกำหนดหน่วยช่วงเวลา (นาที, ชั่วโมง, วัน ฯลฯ)  
- **โค้ดนี้เข้ากันได้กับ .NET Core หรือไม่?** แน่นอน – API เดียวกันทำงานบน .NET Framework และ .NET Core

## BitmapInvalidSizeException คืออะไร?
`BitmapInvalidSizeException` จะถูกโยนเมื่อมิติของบิตแมพที่คำนวณสำหรับภาพอยู่นอกช่วงที่สนับสนุน (เช่น ความกว้างหรือความสูงเป็นศูนย์หรือเกินขีดจำกัดภายใน) ปกติแล้วจะเกิดขึ้นเมื่อการตั้งค่าช่วงเวลาหรือมุมมองทำให้ภาพมีขนาดใหญ่หรือเล็กเกินไป

## ทำไมต้องส่งออกโครงการเป็นภาพ?
- **การรายงานเชิงภาพ** – ฝังแผนภูมิ Gantt ลงใน PDF, เอกสาร Word หรือหน้าเว็บ  
- **การแชร์ข้ามแพลตฟอร์ม** – ไฟล์ PNG สามารถดูได้บนอุปกรณ์ใดก็ได้โดยไม่ต้องใช้ Microsoft Project  
- **ประสิทธิภาพ** – ภาพมีขนาดเบากว่าไฟล์โครงการเต็มรูปแบบสำหรับการพรีวิวอย่างรวดเร็ว

## ข้อกำหนดเบื้องต้น
1. ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET  
2. ติดตั้ง Aspose.Tasks สำหรับ .NET (แพ็คเกจ NuGet `Aspose.Tasks`)  
3. มีไฟล์ Microsoft Project ตัวอย่าง (เช่น `Blank2010.mpp`)  

## นำเข้า Namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: เริ่มต้น Project และเลือก View
ก่อนอื่นให้สร้างอินสแตนซ์ `Project` แล้วเลือก view ที่ต้องการเรนเดอร์ (ในที่นี้เราใช้ Gantt chart view แรก)

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### ขั้นตอนที่ 2: กำหนด Image Save Options (ส่งออกโครงการเป็น PNG)
ตั้งค่ารูปแบบภาพที่ต้องการและบอก Aspose.Tasks ให้ใช้ช่วงเวลาที่กำหนดใน view

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### ขั้นตอนที่ 3: ปรับหน่วย Timescale (ควบคุมขนาดภาพ)
การเปลี่ยนช่วงเวลา (timescale) มีผลต่อมิติของบิตแมพ ตัวอย่างนี้เราใช้ **นาที** เพื่อให้ขนาดภาพอยู่ในระดับที่จัดการได้

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### ขั้นตอนที่ 4: พยายามบันทึกโครงการเป็นภาพ
บรรทัดนี้ทำการ **บันทึกโครงการเป็นภาพ** จริง ๆ

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### ขั้นตอนที่ 5: ดักจับและจัดการ BitmapInvalidSizeException
ห่อการเรียกบันทึกด้วยบล็อก `try / catch` เพื่อให้แอปพลิเคชันของคุณตอบสนองอย่างราบรื่นหากขนาดบิตแมพไม่ถูกต้อง

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| ยังคงเกิดข้อยกเว้นหลังปรับ timescale | Timescale ยังคงทำให้บิตแมพใหญ่เกินไป | ลด `view.MiddleTimescaleTier.Count` หรือเปลี่ยนเป็น `TimescaleUnit` ที่หยาบกว่า (เช่น ชั่วโมง) |
| ไฟล์ผลลัพธ์ว่างเปล่า | เส้นทางไฟล์ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่า `DataDir` ชี้ไปยังโฟลเดอร์ที่เขียนได้และชื่อไฟล์ลงท้ายด้วย `.png` หากเปลี่ยนรูปแบบ |
| คุณภาพภาพแย่ | DPI เริ่มต้นอาจต่ำ | ตั้งค่า `options.DpiX` และ `options.DpiY` ให้สูงขึ้น (เช่น 300) |

## คำถามที่พบบ่อย

**ถาม: สิ่งใดทำให้เกิด BitmapInvalidSizeException ใน Aspose.Tasks?**  
ตอบ: เกิดขึ้นเมื่อมิติของบิตแมพที่คำนวณได้ไม่ถูกต้อง — ส่วนใหญ่เพราะช่วงเวลาทำให้ภาพใหญ่เกินไปหรือมีความกว้าง/สูงเป็นศูนย์

**ถาม: สามารถปรับแต่ง timescale เมื่อส่งออกภาพได้หรือไม่?**  
ตอบ: ได้ คุณสามารถแก้ไข `view.MiddleTimescaleTier.Unit` และ `Count` ตามความต้องการ ตามที่แสดงในบทแนะนำ

**ถาม: Aspose.Tasks รองรับรูปแบบภาพอื่น ๆ นอกจาก PNG หรือไม่?**  
ตอบ: แน่นอน `SaveFileFormat` ยังรวม JPEG, BMP, GIF, และ TIFF คุณเพียงแค่เปลี่ยนค่า enum ใน `ImageSaveOptions`

**ถาม: จำเป็นต้องมีไลเซนส์สำหรับการส่งออกภาพในสภาพแวดล้อมการผลิตหรือไม่?**  
ตอบ: ใช่ แม้ไลบรารีจะทำงานในโหมดประเมินผล แต่ไลเซนส์เชิงพาณิชย์จะลบข้อจำกัดการประเมินผลและให้การสนับสนุนเต็มรูปแบบ

**ถาม: จะปรับปรุงคุณภาพของ PNG ที่ส่งออกได้อย่างไร?**  
ตอบ: เพิ่มค่าการตั้งค่า DPI (`options.DpiX` และ `options.DpiY`) หรือปรับช่วงเวลาของ view เพื่อสร้างบิตแมพที่ใหญ่ขึ้น

## สรุป
โดยทำตามขั้นตอนข้างต้น คุณจะรู้ **วิธีการส่งออกภาพ** จากไฟล์ Project, **วิธีบันทึกโครงการเป็นภาพ**, และวิธีจัดการ `BitmapInvalidSizeException` อย่างราบรื่น เทคนิคเหล่านี้ทำให้สายงานการรายงานของคุณแข็งแรงขึ้นและรับประกันว่าการส่งออกเชิงภาพทำงานได้อย่างน่าเชื่อถือในทุกขนาดโครงการและช่วงเวลา

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-21  
**ทดสอบด้วย:** Aspose.Tasks 24.12 for .NET  
**ผู้เขียน:** Aspose  

---