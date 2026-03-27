---
date: 2026-03-27
description: เรียนรู้วิธีบันทึกโครงการเป็น PDF ด้วย Aspose.Tasks สำหรับ Java คู่มือแบบง่ายในการแปลง
  MPP เป็น PDF และส่งออกไฟล์โครงการอย่างมีประสิทธิภาพ
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีบันทึกโครงการเป็น PDF ด้วย Aspose.Tasks – คู่มือการส่งออก
url: /th/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบันทึกโครงการเป็น PDF ด้วย Aspise.Tasks – คู่มือการส่งออก

## Introduction
ในบทเรียนนี้ คุณจะได้เรียนรู้ **วิธีบันทึกโครงการเป็น pdf** ด้วย Aspose.Tasks for Java เราจะพาคุณผ่านทุกขั้นตอนตั้งแต่การแปลงด้วยบรรทัดเดียวจนถึงการปรับแต่ง PDF ขั้นสูง เพื่อให้คุณสามารถแปลงไฟล์ MPP (หรือรูปแบบที่รองรับอื่น) ให้เป็นเอกสาร PDF ที่ดูดีและสามารถแชร์ได้ ไม่ว่าคุณต้องการรายงานที่พิมพ์ง่ายหรือแผนภูมิ Gantt ที่มีสไตล์เต็มรูปแบบ ขั้นตอนเหล่านี้จะช่วยคุณทำได้อย่างรวดเร็ว

## Quick Answers
- **What does “export PDF” mean in Aspose.Tasks?** หมายถึงการแปลงไฟล์โครงการ (เช่น MPP) ให้เป็นเอกสาร PDF ที่คงรูปแบบการแสดงผลไว้  
- **Which library version is required?** เวอร์ชันใดของไลบรารีก็ได้ที่รองรับ `PdfSaveOptions` ใน Aspose.Tasks for Java (แนะนำให้ใช้รุ่นล่าสุด)  
- **Do I need a license for this conversion?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **Can I customize the PDF appearance?** ใช่ – คุณสามารถตั้งค่า timescale, legends, และ `PdfSaveOptions` อื่น ๆ  
- **Is the conversion fast for large projects?** ปกติใช้เวลาเป็นวินาที; ประสิทธิภาพขึ้นอยู่กับขนาดของโครงการและตัวเลือกที่เลือกใช้  

## What is “save project as pdf” in the context of Aspose.Tasks?
การบันทึกโครงการเป็น PDF ในบริบทของ Aspose.Tasks หมายถึงการนำไฟล์โครงการ (เช่น `.mpp`, `.xml`, หรือ `.xlsx`) มาสร้าง PDF ที่สะท้อนแผนภูมิ Gantt, มุมมองการใช้งาน (Task Usage) หรือรูปแบบการนำเสนออื่น ๆ ที่คุณกำหนดไว้ ซึ่งเป็นประโยชน์สำหรับการทำรายงาน, เอกสาร, หรือการแชร์มุมมองแบบอ่านอย่างเดียวให้กับผู้มีส่วนได้ส่วนเสียที่ไม่ใช่เทคนิค

## Why Export Gantt Chart to PDF?
- **Universal readability:** PDF สามารถเปิดได้บนอุปกรณ์ใดก็ได้โดยไม่ต้องใช้ซอฟต์แวร์โครงการต้นฉบับ  
- **Professional presentation:** รักษาสี, ฟอนต์, และการจัดวางสำหรับรายงานที่ส่งให้ลูกค้า  
- **Easy distribution:** แชร์ผ่านอีเมล, อินทราเน็ต, หรือคลาวด์สตอเรจโดยไม่ต้องกังวลเรื่องการควบคุมเวอร์ชัน  
- **Compliance & archiving:** PDF เหมาะสำหรับการจัดเก็บระยะยาวและการปฏิบัติตามข้อกำหนดกฎหมาย  

## Prerequisites
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK):** JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ  
2. **Aspose.Tasks for Java Library:** ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/tasks/java/)  
3. **A Project File:** มีไฟล์โครงการที่มีอยู่แล้ว (เช่น `HomeMovePlan.mpp`) พร้อมสำหรับการแปลง  

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มที่ไฟล์ `.mpp` ของคุณอยู่ การทำเช่นนี้จะโหลดโครงการเข้าสู่หน่วยความจำเพื่อให้คุณสามารถจัดการหรือส่งออกได้

### Step 2: Save the Project as PDF (Basic Conversion)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
บรรทัดด้านบนทำการดำเนินการ **save project as pdf** อย่างง่าย ๆ สร้างไฟล์ `Project5.pdf` ในโฟลเดอร์เดียวกัน

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ที่นี่เราจะแสดงการใช้ **pdf save options** เพื่อควบคุมการจัดวาง:
- `setFitContent(true)` ทำให้เนื้อหาเข้ากับความกว้างของเซลล์  
- `setTimescale(Timescale.Months)` เปลี่ยน timescale เป็นเดือน  
- `setPresentationFormat(PresentationFormat.TaskUsage)` เลือกมุมมอง Task Usage  

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
การปิดการแสดง legends สามารถทำให้ PDF มีขนาดกะทัดรัดมากขึ้น โดยเฉพาะสำหรับโครงการขนาดใหญ่

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
ขั้นตอนสุดท้ายนี้จะเขียนไฟล์ PDF โดยใช้ตัวเลือกที่กำหนดไว้ข้างต้น ผลลัพธ์คือเอกสารที่มีการสเกลเป็นเดือนและไม่มี legends ในแต่ละหน้า ทำให้ดูเรียบร้อย

## Export Gantt Chart to PDF – Custom Styling
หากคุณต้องการส่งออกเฉพาะแผนภูมิ Gantt ด้วยลักษณะเฉพาะ ให้ตั้งค่า `PresentationFormat` เป็น `GanttChart` และปรับตัวเลือกเพิ่มเติมเช่น `setBarColor` หรือ `setShowCriticalTasks` วิธีนี้ทำให้คุณสามารถ **export gantt chart to pdf** ด้วยการควบคุมเต็มรูปแบบขององค์ประกอบภาพ

## Common Issues & Tips
- **File not found:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) และชี้ไปยังไดเรกทอรีที่ถูกต้อง  
- **Blank pages:** ตรวจสอบว่า `PresentationFormat` ที่เลือกตรงกับมุมมองที่คุณต้องการ (เช่น Gantt, Task Usage)  
- **Large files take longer:** พิจารณาตั้งค่า `o.setFitContent(false)` สำหรับโครงการขนาดใหญ่มากเพื่อลดเวลาในการประมวลผล  

## Frequently Asked Questions

**Q: Aspose.Tasks รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Tasks รองรับเวอร์ชัน Java ตั้งแต่ JDK 6 ขึ้นไป  

**Q: ฉันสามารถปรับแต่งลักษณะของ PDF ที่ส่งออกได้หรือไม่?**  
A: แน่นอน! Aspose.Tasks มี **pdf save options** มากมาย เช่น timescale, การแสดงหรือซ่อน legend, และ presentation format เพื่อปรับ PDF ให้ตรงตามความต้องการของคุณ  

**Q: Aspose.Tasks รองรับรูปแบบไฟล์อื่นสำหรับการแปลงหรือไม่?**  
A: ใช่, คุณสามารถแปลงระหว่าง MPP, XML, XLSX และรูปแบบอื่น ๆ มากมาย ทำให้เป็นเครื่องมือที่หลากหลายสำหรับ **convert mpp to pdf** และการแปลงอื่น ๆ  

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks หรือไม่?**  
A: มี, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Tasks ได้จาก [here](https://releases.aspose.com/)  

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
A: สำหรับการสนับสนุนและความช่วยเหลือ ให้เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) อย่างเป็นทางการ  

## Conclusion
โดยทำตามคู่มือนี้ คุณจะทราบ **วิธีบันทึกโครงการเป็น pdf** จากโครงการ Java ใด ๆ ด้วย Aspose.Tasks ตั้งแต่การบันทึกบรรทัดเดียวอย่างง่ายจนถึงการปรับแต่งขั้นสูงด้วย `PdfSaveOptions` ใช้เทคนิคเหล่านี้เพื่อสร้าง PDF ที่ดูดีและสามารถแชร์ได้สำหรับการรายงาน, การนำเสนอให้ลูกค้า หรือการเก็บรักษาเอกสาร

---

**อัปเดตล่าสุด:** 2026-03-27  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}