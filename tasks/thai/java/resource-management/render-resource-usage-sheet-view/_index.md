---
date: 2026-06-15
description: เรียนรู้วิธีแปลง mpp เป็น pdf และแสดงมุมมอง Resource Usage และ Sheet
  โดยใช้ Aspose.Tasks สำหรับ Java. ทำตามคู่มือ step‑by‑step ของเราเพื่อกำหนด timescale
  และสร้างรายงาน PDF รายละเอียดอย่างง่ายดาย.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: แปลง MPP เป็น PDF และแสดงมุมมอง Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: แปลง MPP เป็น PDF และแสดงมุมมอง Resource Usage – Aspose.Tasks
url: /th/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง MPP เป็น PDF และแสดงมุมมองการใช้ทรัพยากร – Aspose.Tasks

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแปลง mpp เป็น pdf** พร้อมกับการแสดงมุมมอง Resource Usage และ Sheet ของไฟล์ Microsoft Project การใช้ Aspose.Tasks for Java จะทำให้ไม่ต้องติดตั้ง Microsoft Project บนเซิร์ฟเวอร์ ช่วยให้คุณสร้างรายงาน PDF จากไฟล์ MPP ได้อย่างรวดเร็วและเชื่อถือได้ เราจะยังแสดงให้คุณเห็น **วิธีตั้งค่า timescale** เพื่อให้ผลลัพธ์ตรงกับความต้องการของการรายงานของคุณ.

## คำตอบสั้น
- **Aspose.Tasks ทำอะไร?** It reads, modifies, and converts Microsoft Project (MPP) files without needing MS Project installed.  
- **ฉันสามารถแปลง MPP เป็น PDF ด้วยบรรทัดเดียวของโค้ดได้หรือไม่?** Yes – load the Project, set SaveOptions, and call `save`.  
- **timescales ที่รองรับมีอะไรบ้าง?** Days, ThirdsOfMonths, and Months.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** A commercial license is required for non‑trial deployments.  
- **ไลบรารีนี้เข้ากันได้กับ Java 8+ หรือไม่?** Absolutely – it supports Java 8 and later versions.

## การแปลง mpp เป็น pdf คืออะไร?
*Convert mpp to pdf* หมายถึงกระบวนการนำไฟล์ Microsoft Project (.mpp) มาสร้างเป็น Portable Document Format (PDF) ที่คัดลอกตาราง, กำหนดเวลา, แผนภูมิและการจัดสรรทรัพยากรของโครงการอย่างแม่นยำ PDF ที่ได้สามารถแชร์, พิมพ์และเก็บรักษาได้ง่ายโดยไม่ต้องติดตั้ง Microsoft Project บนเครื่องของผู้รับ.

## ทำไมต้องแปลง Project เป็น PDF ด้วย Aspose.Tasks?
Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50** แบบและสามารถแสดงโครงการหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ลดการใช้ RAM ได้ถึง 70 %. ผลลัพธ์ PDF จะคงตาราง, แผนภูมิและการจัดสรรทรัพยากร ทำให้เหมาะสำหรับการแจกจ่ายให้ผู้มีส่วนได้ส่วนเสียและการเก็บรักษา.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – Java 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [download page](https://releases.aspose.com/tasks/java/).

## วิธีแปลง mpp เป็น pdf ด้วย Aspose.Tasks for Java?
โหลดไฟล์ MPP ต้นฉบับของคุณ, ตั้งค่า timescale ที่ต้องการ, กำหนดรูปแบบการนำเสนอเป็น **ResourceUsage**, แล้วบันทึกผลลัพธ์เป็น PDF กระบวนการครบวงจรนี้ต้องการเพียงไม่กี่คำสั่ง API และทำงานภายในไม่ถึงหนึ่งวินาทีสำหรับขนาดโครงการทั่วไป.

### ขั้นตอนที่ 1: อ่านโครงการต้นฉบับ
คลาส `Project` แสดงไฟล์ Microsoft Project ที่โหลดเข้าสู่หน่วยความจำ, ให้เข้าถึงข้อมูลและโครงสร้างของมัน.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### ขั้นตอนที่ 2: กำหนด SaveOptions พร้อมการตั้งค่า TimeScale ที่ต้องการ
`SaveOptions` กำหนดวิธีการบันทึกโครงการ, ให้คุณระบุการตั้งค่าเฉพาะรูปแบบเช่น timescale.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### ขั้นตอนที่ 3: ตั้งค่า Presentation Format เป็น ResourceUsage
`PresentationFormat` กำหนดว่ามุมมองของ Project (เช่น ResourceUsage) จะถูกแสดงในเอกสารผลลัพธ์.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### ขั้นตอนที่ 4: บันทึกโครงการเป็น PDF
`project.save` เขียนโครงการลงไฟล์โดยใช้ `SaveOptions` ที่ให้มา, สร้าง PDF สุดท้าย.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### ขั้นตอนที่ 5: แสดงมุมมองสำหรับการตั้งค่า TimeScale อื่น
ทำซ้ำขั้นตอนก่อนหน้า, เปลี่ยนค่า `TimeScale` เพื่อแสดงมุมมอง timescale เพิ่มเติม.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### ขั้นตอนที่ 6: ตัวเลือก – แปลงหลายโครงการเป็นชุด
หากคุณต้องการ **แปลง project เป็น pdf** สำหรับหลายไฟล์, ให้วางตรรกะข้างต้นในลูปที่วนผ่านไดเรกทอรีของไฟล์ *.mpp* วิธีนี้ **บันทึกไฟล์ ms project pdf** เป็นจำนวนมากโดยเปลี่ยนแปลงโค้ดเพียงเล็กน้อย.  
โค้ดต่อไปนี้แสดงตัวอย่างเต็มของการแปลงไฟล์ MPP เป็น PDF ด้วยการตั้งค่าที่ต้องการ.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## ปัญหาทั่วไปและวิธีแก้
- **Missing fonts in PDF** – ตรวจสอบให้แน่ใจว่าได้ติดตั้งฟอนต์ที่จำเป็นบนเซิร์ฟเวอร์หรือฝังฟอนต์ผ่าน `PdfSaveOptions`.  
- **Large project files cause OutOfMemoryError** – ใช้ `LoadOptions.setLoadAllResources(false)` เพื่อโหลดทรัพยากรตามต้องการ.  
- **Incorrect timescale rendering** – ตรวจสอบว่า `options.setTimeScale(TimeScale.Days)` (หรือ enum อื่น) ตรงกับความละเอียดที่ต้องการ.

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถแสดงมุมมองอื่นนอกจาก Resource Usage และ Sheet ได้หรือไม่?**  
A: ใช่, ยังรองรับ Gantt Chart, Task Usage, Calendar, และมุมมองเพิ่มเติมหลายรายการ.

**Q: Aspose.Tasks เข้ากันได้กับเวอร์ชันต่าง ๆ ของไฟล์ Microsoft Project หรือไม่?**  
A: แน่นอน – รองรับรูปแบบ MPP, MPT, และ XML ตั้งแต่ Project 2000 ถึง Project 2021.

**Q: ฉันสามารถปรับแต่งลักษณะของมุมมองที่แสดงได้หรือไม่?**  
A: ได้, คุณสามารถแก้ไขสี, ฟอนต์, และการจัดวางคอลัมน์ผ่าน `PdfSaveOptions` และ `PresentationOptions`.

**Q: Aspose.Tasks ต้องการให้ติดตั้ง Microsoft Project หรือไม่?**  
A: ไม่, เป็นไลบรารีแบบสแตนด์อโลนและทำงานบนสภาพแวดล้อมที่รองรับ Java ใด ๆ.

**Q: ฉันสามารถรับการสนับสนุนทางเทคนิคได้จากที่ไหน?**  
A: มีการสนับสนุนผ่าน [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบด้วย:** Aspose.Tasks 24.12 for Java  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [แสดง Resource Usage และ Sheet View ใน Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [วิธีส่งออก PDF ใน Aspose.Tasks – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [วิธีสร้างไฟล์ MPP ด้วย Aspose.Tasks for Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}