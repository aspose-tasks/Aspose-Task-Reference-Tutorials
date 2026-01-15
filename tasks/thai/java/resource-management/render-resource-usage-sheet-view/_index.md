---
date: 2026-01-15
description: เรียนรู้วิธีบันทึกโครงการเป็น PDF และแสดงมุมมอง Resource Usage และ Sheet
  ของ MS Project ด้วย Aspose.Tasks สำหรับ Java ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อส่งออกโครงการเป็น
  PDF อย่างง่ายดาย.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: บันทึกโครงการเป็น PDF – แสดงการใช้ทรัพยากรและมุมมองแผ่นงานใน Aspose.Tasks
url: /th/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็น PDF – แสดงการใช้ทรัพยากรและมุมมองแผ่นใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **บันทึกโครงการเป็น PDF** พร้อมกับการเรนเดอร์มุมมอง Resource Usage และ Sheet ของไฟล์ Microsoft Project ไม่ว่าคุณจะต้องการสร้างรายงานที่พิมพ์ได้สำหรับผู้มีส่วนได้ส่วนเสียหรือแปลงไฟล์ MPP ให้เป็นรูปแบบที่ทุกคนสามารถดูได้ Aspose.Tasks for Java ทำให้กระบวนการนี้ง่ายดาย—ไม่ต้องติดตั้ง Microsoft Project

## คำตอบสั้น
- **“บันทึกโครงการเป็น pdf” ทำอะไร?** แปลงไฟล์ Project (MPP) เป็นเอกสาร PDF โดยคงมุมมองที่เลือกไว้  
- **มุมมองใดบ้างที่สามารถส่งออกได้?** Resource Usage, Sheet, Gantt, Task Usage และอื่น ๆ  
- **สามารถเปลี่ยน Timescale ใน PDF ได้หรือไม่?** ได้ — ตัวเลือกรวม Days, ThirdsOfMonths, และ Months  
- **ต้องติดตั้ง Microsoft Project หรือไม่?** ไม่จำเป็น, Aspose.Tasks ทำงานได้อย่างอิสระ  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่แบบทดลอง

## “บันทึกโครงการเป็น PDF” คืออะไร?
การบันทึกโครงการเป็น PDF จะสร้างภาพคงที่ความละเอียดสูงของมุมมอง Project ที่เลือกไว้ ซึ่งเหมาะสำหรับการแชร์กับลูกค้า, การเก็บรักษา, หรือการพิมพ์โดยไม่ต้องเปิดเผยไฟล์โครงการต้นฉบับ

## ทำไมต้องใช้ Aspose.Tasks เพื่อส่งออกโครงการเป็น PDF?
- **ไม่มีการพึ่งพาภายนอก** – ทำงานบนทุกแพลตฟอร์มที่รองรับ Java  
- **ควบคุมได้ละเอียด** – คุณสามารถเลือกมุมมอง, Timescale, และ Layout ได้ตามต้องการ  
- **ความแม่นยำสูง** – PDF จะสะท้อนลักษณะของมุมมอง Project ดั้งเดิมอย่างครบถ้วน  
- **พร้อมสำหรับการอัตโนมัติ** – สามารถรวมเข้าใน CI pipelines, บริการรายงาน, หรือเครื่องแปลงแบบชุดได้

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – แนะนำให้ใช้เวอร์ชันล่าสุด  
2. **Aspose.Tasks for Java** – ดาวน์โหลดได้จาก [download page](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
เริ่มต้นโดยนำเข้าคลาสที่จำเป็นเข้าสู่โครงการ Java ของคุณ:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: อ่านไฟล์ Project ต้นฉบับ
โหลดไฟล์ MPP ที่ต้องการแปลง

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### ขั้นตอนที่ 2: กำหนด SaveOptions พร้อม Timescale ที่ต้องการ (Export Project to PDF)
ตั้งค่าตัวเลือกการส่งออก PDF และกำหนด Timescale ที่ต้องการ  
*ในตัวอย่างนี้ใช้ **Days** เป็นตัวอย่าง*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### ขั้นตอนที่ 3: ตั้งค่า PresentationFormat เป็น ResourceUsage
เลือกมุมมองที่ต้องการเรนเดอร์ ในกรณีนี้คือมุมมอง **Resource Usage**

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### ขั้นตอนที่ 4: บันทึกโครงการ (แปลง MPP เป็น PDF)
ดำเนินการแปลงและสร้างไฟล์ PDF

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### ขั้นตอนที่ 5: เรนเดอร์มุมมองสำหรับการตั้งค่า Timescale อื่น (Change Timescale PDF)
ทำซ้ำขั้นตอนก่อนหน้าเพื่อสร้าง PDF ด้วย Timescale ต่าง ๆ เช่น **ThirdsOfMonths** และ **Months**

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **ข้อผิดพลาดไฟล์ไม่พบ** – ตรวจสอบให้แน่ใจว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อไฟล์ MPP ตรงกันทุกประการ  
- **PDF ว่างเปล่า** – ตรวจสอบให้ `PresentationFormat` ตรงกับมุมมองที่มีข้อมูล (เช่น ResourceUsage)  
- **Timescale ไม่ถูกต้อง** – ตรวจสอบให้ `options.setTimescale()` ถูกเรียกก่อนแต่ละ `project.save()`

## คำถามที่พบบ่อย

### Aspose.Tasks สามารถเรนเดอร์มุมมองอื่น ๆ นอกจาก Resource Usage และ Sheet ได้หรือไม่?
Aspose.Tasks รองรับการเรนเดอร์มุมมองหลากหลาย เช่น Gantt Chart, Task Usage, และ Calendar เป็นต้น

### Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?
ใช่, Aspose.Tasks รองรับรูปแบบไฟล์ Microsoft Project มากมาย รวมถึง MPP, MPT, และ XML

### สามารถปรับแต่งลักษณะการแสดงผลของมุมมองที่เรนเดอร์ได้ด้วย Aspose.Tasks หรือไม่?
แน่นอน! Aspose.Tasks มีตัวเลือกมากมายสำหรับการปรับแต่งลักษณะและ Layout ของมุมมองที่เรนเดอร์ให้ตรงกับความต้องการของคุณ

### Aspose.Tasks ต้องการให้ติดตั้ง Microsoft Project บนระบบหรือไม่?
ไม่จำเป็น, Aspose.Tasks เป็นไลบรารีสแตนด์อโลนและไม่ต้องการ Microsoft Project เพื่อติดตั้งหรือทำงาน

### มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่?
มี, ผู้ใช้ Aspose.Tasks สามารถรับการสนับสนุนทางเทคนิคผ่าน [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---