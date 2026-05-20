---
date: 2026-05-20
description: เรียนรู้วิธีส่งออกโครงการเป็น PDF ลดช่องว่างส่วนท้าย และบันทึกโครงการเป็นภาพโดยใช้
  Aspose.Tasks for Java ปรับแต่งการจัดวางของ MS Project ของคุณได้อย่างง่ายดาย
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks
url: /th/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks

## บทนำ  
ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีส่งออกโครงการเป็น PDF** พร้อมกับลดช่องว่างที่ไม่ต้องการระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project สุดท้ายของคู่มือคุณจะสามารถสร้าง PDF ที่สะอาด, รูปภาพ PNG, และหน้า HTML ด้วยการจัดวางที่กระชับโดยใช้ Aspose.Tasks สำหรับ Java มาเดินผ่านกระบวนการแบบทีละขั้นตอนและคุณจะเห็นว่าทำไมสิ่งนี้ถึงสำคัญสำหรับการรายงานระดับมืออาชีพ

## คำตอบด่วน  
- **อะไรคือ “export project to PDF” หมายความว่า?** มันแปลงไฟล์ MPP เป็นเอกสาร PDF โดยคงรักษางาน, ไทม์ไลน์, และรูปแบบไว้  
- **ทำไมต้องลดช่องว่างส่วนท้าย?** ช่องว่างที่เล็กลงทำให้รายงานดูกระชับและเป็นมืออาชีพมากขึ้น, โดยเฉพาะสำหรับเอกสารที่พิมพ์หรือดูบนเว็บ  
- **ฉันสามารถบันทึกโครงการเป็นภาพได้หรือไม่?** ใช่ – Aspose.Tasks รองรับ PNG, JPEG, และรูปแบบภาพอื่น ๆ  
- **ต้องการใบอนุญาตพิเศษหรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่าใช้งานได้กับไลบรารี Aspose.Tasks ปัจจุบัน  

## “export project to PDF” คืออะไร?  
การส่งออกโครงการเป็น PDF จะเปลี่ยนโครงสร้าง MPP ภายในให้เป็นเอกสารพกพาที่สามารถเปิดได้บนอุปกรณ์ใดก็ได้โดยไม่ต้องใช้ Microsoft Project ซึ่งเหมาะสำหรับการแชร์รายงานสถานะ, การอัปเดตผู้มีส่วนได้ส่วนเสีย, หรือการเก็บบันทึกแผนโครงการ มันคงรูปแบบต้นฉบับ, สี, และลำดับชั้นของงานไว้, ทำให้ PDF มีลักษณะเหมือนไฟล์ต้นฉบับ  

## ทำไมต้องลดช่องว่างส่วนท้าย?  
ช่องว่างส่วนท้ายเริ่มต้นอาจเพิ่มพื้นที่สีขาวที่ไม่จำเป็น, ทำให้เกิดปัญหาการแบ่งหน้าและลักษณะที่ไม่สมดุล การลดช่องว่างทำให้เนื้อหาของคุณใช้หน้ากระดาษอย่างมีประสิทธิภาพ, ทำให้ PDF หรือภาพสุดท้ายอ่านง่ายขึ้น การจัดวางที่กระชับยังช่วยลดจำนวนหน้าทั้งหมด, ซึ่งสามารถลดค่าใช้จ่ายในการพิมพ์และปรับปรุงการนำทางบนหน้าจอ  

## วิธีลดช่องว่างระหว่างรายการงานกับส่วนท้าย?  
`setReduceFooterGap` เป็นคุณสมบัติแบบ Boolean ที่ควบคุมการเว้นระยะส่วนท้ายระหว่างการส่งออก.  
Aspose.Tasks มีตัวเลือก `setReduceFooterGap(true)` สำหรับการบันทึกเป็นภาพ, PDF, และ HTML. การเปิดใช้งานฟล็กนี้บอกให้เอนจินบีบอัดพื้นที่ระหว่างแถวงานสุดท้ายกับส่วนท้ายของหน้า. เมื่อกำหนดเป็น true, ตัวเรนเดอร์จะตัดขอบโดยอัตโนมัติโดยไม่ตัดข้อมูลงานใด ๆ, ทำให้การจัดหน้าเป็นระเบียบและสะอาดขึ้น.  

## บันทึกโครงการเป็นภาพด้วย Aspose.Tasks  
`ImageSaveOptions` กำหนดวิธีที่โครงการจะถูกเรนเดอร์เป็นไฟล์ภาพ.  
คลาส `ImageSaveOptions` ให้คุณส่งออกภาพสแนปช็อตของกำหนดการเป็น PNG, JPEG, หรือ BMP. เมื่อคุณเปิดใช้งาน `setReduceFooterGap(true)` ด้วย, ภาพที่สร้างขึ้นจะสะท้อนการจัดวาง PDF ที่กระชับ, ให้ภาพที่สะอาดสำหรับการนำเสนอหรือแดชบอร์ด.  

## การส่งออกโครงการ Java เป็น PDF  
ส่วนต่อไปนี้จะอธิบายขั้นตอนการทำงานของ **java project export** อย่างครบถ้วน, ตั้งแต่การโหลดไฟล์ MPP ไปจนถึงการบันทึกในสามรูปแบบที่แตกต่างกัน.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
1. Java Development Kit (JDK) – เวอร์ชัน 8 หรือใหม่กว่า.  
2. Aspose.Tasks for Java Library – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/).  

## นำเข้าแพ็กเกจ  
ก่อนที่จะลงลึกในส่วนของการเขียนโค้ด, ให้เรานำเข้าแพ็กเกจที่จำเป็น:  

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

## ขั้นตอนที่ 1: ระบุเส้นทางไปยังไดเรกทอรีข้อมูลของคุณ  
```java
String dataDir = "Your Data Directory";
```  
ตรวจสอบให้แน่ใจว่าได้แทนที่ `"Your Data Directory"` ด้วยเส้นทางไปยังไดเรกทอรีข้อมูลจริงของคุณที่ไฟล์ Microsoft Project (`HomeMovePlan.mpp` ในตัวอย่างนี้) ตั้งอยู่.  

## ขั้นตอนที่ 2: อ่านไฟล์ MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
บรรทัดโค้ดนี้อ่านไฟล์ Microsoft Project ที่ชื่อ `HomeMovePlan.mpp`.  

## ขั้นตอนที่ 3: ตั้งค่า ImageSaveOptions (บันทึกโครงการเป็นภาพ)  
`ImageSaveOptions` กำหนดวิธีที่โครงการจะถูกเรนเดอร์เป็นไฟล์ภาพ.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
กำหนดค่าตัวเลือกการบันทึกภาพ, ตั้งค่า `ReduceFooterGap` เป็น `true` เพื่อ ลดช่องว่างระหว่างรายการงานและส่วนท้าย.  

## ขั้นตอนที่ 4: บันทึกเป็นภาพ  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
บันทึกโครงการเป็นภาพด้วยตัวเลือกที่กำหนดไว้.  

## ขั้นตอนที่ 5: ตั้งค่า PdfSaveOptions (ส่งออกโครงการเป็น PDF)  
`PdfSaveOptions` ระบุการตั้งค่าสำหรับการส่งออกโครงการเป็นรูปแบบ PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
กำหนดตัวเลือกการบันทึก PDF, ตรวจสอบให้ตั้งค่า `ReduceFooterGap` เป็น `true`.  

## ขั้นตอนที่ 6: บันทึกเป็น PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
บันทึกโครงการเป็น PDF ด้วยตัวเลือกที่กำหนดไว้.  

## ขั้นตอนที่ 7: ตั้งค่า HtmlSaveOptions  
`HtmlSaveOptions` ควบคุมการแปลงโครงการเป็น HTML, รวมถึงการจัดสไตล์และตัวเลือกการจัดวาง.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
ระบุตัวเลือกการบันทึก HTML, ตั้งค่า `ReduceFooterGap` เป็น `true`.  

## ขั้นตอนที่ 8: บันทึกเป็น HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
บันทึกโครงการเป็นไฟล์ HTML ด้วยตัวเลือกที่กำหนดไว้.  

## กรณีการใช้งานทั่วไปและเคล็ดลับ  
- **Stakeholder reporting:** ส่งออกเป็น PDF พร้อมลดช่องว่างส่วนท้ายเพื่อทำให้รายงานกระชับและเหมาะกับการพิมพ์.  
- **Dashboard snapshots:** ใช้การส่งออกเป็นภาพเมื่อคุณต้องการภาพเร็วสำหรับ Power BI หรือ Confluence.  
- **Web publishing:** การส่งออกเป็น HTML รักษาการโต้ตอบและสามารถฝังลงในพอร์ทัลอินทราเน็ตได้โดยตรง.  
- **Pro tip:** สำหรับโครงการขนาดใหญ่มาก, เพิ่มค่า `Resolution` ใน `ImageSaveOptions` เป็น 300 dpi เพื่อรักษาความคมชัดพร้อมยังคงได้ประโยชน์จากการลดช่องว่าง.  

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q:** การลดช่องว่างส่วนท้ายส่งผลต่อการแบ่งหน้าอย่างไร?  
**A:** มันลดพื้นที่ว่างที่ด้านล่างของแต่ละหน้า, ทำให้สามารถใส่งานได้มากขึ้นในหนึ่งหน้าและลดจำนวนหน้าทั้งหมด.  

**Q:** ฉันสามารถใช้การตั้งค่าการลดช่องว่างนี้กับหน้าเดียวเท่านั้นได้หรือไม่?  
**A:** ได้, โดยตั้งค่า `setRenderToSinglePage(true)` ใน `ImageSaveOptions` คุณสามารถควบคุมการแบ่งหน้าในขณะที่ยังคงลดช่องว่าง.  

**Q:** ตัวเลือก `setReduceFooterGap` มีให้ใช้กับรูปแบบผลลัพธ์อื่นหรือไม่?  
**A:** ปัจจุบันรองรับการส่งออกเป็น PNG, PDF, และ HTML. สำหรับรูปแบบอื่นคุณอาจต้องปรับการจัดวางด้วยตนเอง.  

**Q:** ถ้าโครงการของฉันมีฟิลด์กำหนดเอง—จะถูกเก็บรักษาไว้หรือไม่?  
**A:** ฟิลด์กำหนดเองทั้งหมดจะถูกเก็บไว้ระหว่างการส่งออก; การปรับการจัดวางมีผลต่อการเว้นระยะเท่านั้น, ไม่กระทบข้อมูล.  

**Q:** ไลบรารีสามารถจัดการโครงการขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่?  
**A:** Aspose.Tasks ใช้การสตรีมข้อมูลและสามารถประมวลผลไฟล์ MPP หลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ; อย่างไรก็ตาม, ควรจัดสรรหน่วยความจำ heap เพียงพอเมื่อส่งออกภาพความละเอียดสูง.  

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

## บทแนะนำที่เกี่ยวข้อง

- [บันทึกโครงการเป็นภาพ – รูปแบบ 24bppRgb ด้วย Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [บันทึกโครงการเป็นเทมเพลต, CSV, และข้อความด้วย Aspose.Tasks สำหรับ Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [วิธีสร้างไฟล์ MPP – สร้างและบันทึกโครงการเปล่าในรูปแบบ MPP ด้วย Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}