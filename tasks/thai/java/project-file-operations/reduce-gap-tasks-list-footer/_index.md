---
date: 2025-12-17
description: เรียนรู้วิธีส่งออกโครงการเป็น PDF, ลดช่องว่างของส่วนท้าย, และบันทึกโครงการเป็นภาพโดยใช้
  Aspose.Tasks for Java. ปรับแต่งเลย์เอาต์ของ MS Project ของคุณได้อย่างง่ายดาย.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks
url: /th/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks

## Introduction  
ในบทแนะนำนี้คุณจะค้นพบ **วิธีการส่งออกโครงการเป็น PDF** พร้อมทั้งลดพื้นที่ว่างที่ไม่ต้องการระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project. เมื่อจบคู่มือคุณจะสามารถสร้าง PDF ที่สะอาด, รูปภาพ PNG, และหน้า HTML ด้วยการจัดวางที่กระชับโดยใช้ Aspose.Tasks สำหรับ Java. มาดำเนินการตามขั้นตอนทีละขั้นตอน.

## Quick Answers  
- **อะไรหมายถึง “export project to PDF”?** มันแปลงไฟล์ MPP เป็นเอกสาร PDF โดยคงรักษางาน, ไทม์ไลน์, และการจัดรูปแบบ.  
- **ทำไมต้องลดช่องว่างส่วนท้าย?** ช่องว่างที่น้อยลงทำให้รายงานดูกระชับและเป็นมืออาชีพมากขึ้น, โดยเฉพาะสำหรับเอกสารที่พิมพ์หรือดูบนเว็บ.  
- **ฉันสามารถบันทึกโครงการเป็นภาพได้หรือไม่?** ใช่ – Aspose.Tasks รองรับ PNG, JPEG, และรูปแบบภาพอื่น ๆ.  
- **ต้องการใบอนุญาตพิเศษหรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่าใช้งานได้กับไลบรารี Aspose.Tasks ปัจจุบัน.

## What is “export project to PDF”?  
การส่งออกโครงการเป็น PDF จะเปลี่ยนโครงสร้าง MPP ภายในให้เป็นเอกสารพกพาที่สามารถเปิดได้บนอุปกรณ์ใด ๆ โดยไม่ต้องใช้ Microsoft Project. สิ่งนี้เหมาะสำหรับการแชร์รายงานสถานะ, การอัปเดตผู้มีส่วนได้ส่วนเสีย, หรือการเก็บบันทึกแผนโครงการ.

## Why Reduce Footer Gap?  
ช่องว่างส่วนท้ายเริ่มต้นอาจเพิ่มพื้นที่สีขาวที่ไม่จำเป็น, ทำให้เกิดปัญหาการแบ่งหน้าและรูปลักษณ์ที่ไม่สมดุล. การลดช่องว่างจะทำให้เนื้อหาของคุณใช้หน้ากระดาษอย่างมีประสิทธิภาพ, ทำให้ PDF หรือภาพสุดท้ายอ่านง่ายขึ้น.

## How to Reduce Gap Between Tasks List and Footer?  
Aspose.Tasks มีตัวเลือก `setReduceFooterGap(true)` สำหรับการบันทึกเป็นภาพ, PDF, และ HTML. การเปิดใช้งานฟลักนี้จะบอกให้เอนจินบีบอัดพื้นที่ระหว่างแถวงานสุดท้ายกับส่วนท้ายของหน้า.

## Save Project as Image with Aspose.Tasks  
หากคุณต้องการภาพสแนปช็อตของกำหนดการ, คุณสามารถ **บันทึกโครงการเป็นภาพ** (PNG) พร้อมใช้การตั้งค่าการลดช่องว่างเดียวกัน.

## Java Project Export to PDF  
ส่วนต่อไปนี้จะอธิบายขั้นตอนการทำงานของ **java project export** อย่างครบถ้วน, ตั้งแต่การโหลดไฟล์ MPP ไปจนถึงการบันทึกในสามรูปแบบต่าง ๆ.

## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK) – เวอร์ชัน 8 หรือใหม่กว่า.  
2. Aspose.Tasks for Java Library – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/tasks/java/).  

## Import Packages
Before diving into the coding part, let's import the necessary packages:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step 1: Provide the Path to Your Data Directory
ตรวจสอบให้แน่ใจว่าได้แทนที่ `"Your Data Directory"` ด้วยเส้นทางไปยังไดเรกทอรีข้อมูลจริงของคุณที่ไฟล์ Microsoft Project (`HomeMovePlan.mpp` ในตัวอย่างนี้) อยู่.
```java
String dataDir = "Your Data Directory";
```

## Step 2: Read the MPP File
บรรทัดโค้ดนี้อ่านไฟล์ Microsoft Project ที่ชื่อ `HomeMovePlan.mpp`.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Step 3: Set ImageSaveOptions (Save Project as Image)
กำหนดค่าตัวเลือกการบันทึกภาพ, ตั้งค่า `ReduceFooterGap` เป็น `true` เพื่อ ลดช่องว่างระหว่างรายการงานกับส่วนท้าย.
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```

## Step 4: Save as Image
บันทึกโครงการเป็นภาพด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```

## Step 5: Set PdfSaveOptions (Export Project to PDF)
กำหนดตัวเลือกการบันทึก PDF, ตรวจสอบให้ตั้งค่า `ReduceFooterGap` เป็น `true`.
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```

## Step 6: Save as PDF
บันทึกโครงการเป็น PDF ด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```

## Step 7: Set HtmlSaveOptions
ระบุตัวเลือกการบันทึก HTML, ตั้งค่า `ReduceFooterGap` เป็น `true`.
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```

## Step 8: Save as HTML
บันทึกโครงการเป็นไฟล์ HTML ด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```

## Conclusion  
สรุปแล้ว, การลดช่องว่างระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project เป็นกระบวนการง่ายดายด้วย Aspose.Tasks สำหรับ Java. ด้วยการทำตามขั้นตอนที่อธิบายในบทแนะนำนี้, คุณสามารถ **export project to PDF** อย่างมีประสิทธิภาพ, บันทึกเป็นภาพ, หรือสร้าง HTML พร้อมคงการจัดวางให้กระชับและเป็นมืออาชีพ.

## FAQ's

### Q: Aspose.Tasks รองรับกับเวอร์ชันทั้งหมดของ Microsoft Project หรือไม่?
A: Aspose.Tasks รองรับรูปแบบ Microsoft Project 2003-2019, ทำให้เข้ากันได้กับหลายเวอร์ชัน.

### Q: ฉันสามารถปรับแต่งลักษณะของส่วนท้ายในเอกสารโครงการของฉันได้หรือไม่?
A: ใช่, Aspose.Tasks มีตัวเลือกมากมายสำหรับการปรับแต่งลักษณะของส่วนท้าย, รวมถึงการลดช่องว่างและการจัดตำแหน่งเนื้อหา.

### Q: Aspose.Tasks รองรับการบันทึกโครงการในรูปแบบอื่นนอกจาก PNG, PDF, และ HTML หรือไม่?
A: ใช่, Aspose.Tasks รองรับรูปแบบหลากหลายรวมถึง XLSX, XML, และ MPP เป็นต้น.

### Q: มีเวอร์ชันทดลองใช้สำหรับ Aspose.Tasks หรือไม่?
A: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีของ Aspose.Tasks จาก [here](https://releases.aspose.com/).

### Q: ฉันจะขอรับการสนับสนุนได้จากที่ไหนหากพบปัญหาในการใช้ Aspose.Tasks?
A: คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions (Additional)

**Q: การลดช่องว่างส่วนท้ายส่งผลต่อการแบ่งหน้าอย่างไร?**  
A: จะลดพื้นที่ว่างที่ด้านล่างของแต่ละหน้า, ทำให้สามารถใส่งานได้มากขึ้นต่อหน้าเดียวและลดจำนวนหน้าทั้งหมด.

**Q: ฉันสามารถใช้การตั้งค่าการลดช่องว่างนี้กับหน้าเดียวเท่านั้นได้หรือไม่?**  
A: ใช่, โดยตั้งค่า `setRenderToSinglePage(true)` ใน `ImageSaveOptions` คุณสามารถควบคุมการแบ่งหน้าในขณะเดียวกันยังคงลดช่องว่างได้.

**Q: ตัวเลือก `setReduceFooterGap` มีให้ใช้กับรูปแบบผลลัพธ์อื่นหรือไม่?**  
A: ปัจจุบันรองรับสำหรับการส่งออกเป็น PNG, PDF, และ HTML. สำหรับรูปแบบอื่นอาจต้องปรับเลย์เอาต์ด้วยตนเอง.

**Q: หากโครงการของฉันมีฟิลด์ที่กำหนดเอง จะถูกเก็บไว้หรือไม่?**  
A: ฟิลด์ที่กำหนดเองทั้งหมดจะถูกเก็บไว้ระหว่างการส่งออก; การปรับแต่งเลย์เอาต์จะส่งผลต่อการจัดช่องว่างเท่านั้น, ไม่กระทบข้อมูล.

**Q: ไลบรารีนี้จัดการกับโครงการขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่?**  
A: Aspose.Tasks ใช้การสตรีมข้อมูลและสามารถประมวลผลไฟล์ MPP ขนาดใหญ่ได้; อย่างไรก็ตามควรตรวจสอบให้มีหน่วยความจำเพียงพอเมื่อส่งออกเป็นภาพความละเอียดสูง.

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}