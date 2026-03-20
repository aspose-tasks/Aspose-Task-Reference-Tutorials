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

## การแนะนำ
ในบทแนะนำนี้คุณจะได้รู้ว่า **วิธีการส่งออกโครงการเป็น PDF** สามารถลดพื้นที่ว่างที่ไม่จำเป็นระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project ก่อนอื่นคุณควรเริ่มต้นสร้าง PDF ที่สะอาด, รูปภาพ PNG, และหน้า HTML โดยไม่ต้องวางที่กระชับโครงสร้าง Aspose.Tasks สำหรับ Java มาดำเนินการตามขั้นตอนทีละขั้นตอน

## คำตอบด่วน
- **อะไรหมายถึง “ส่งออกโครงการเป็น PDF”?** มันแปลงไฟล์ MPP เป็นเอกสาร PDF โดยคงรักษางาน, ไทม์ไลน์, และรูปแบบดังกล่าว
- **ทำไมต้องมีช่องลดส่วนท้าย?** พื้นที่ว่างที่ทำให้รายงานดูกระชับและความจำเป็น, เอกสารสำหรับเอกสารที่พิมพ์หรือดูข้อมูล.
- **บันทึกบันทึกโครงการเป็นภาพได้หรือเปล่า?** ตรวจสอบ – Aspose.Tasks รองรับ PNG, JPEG, และรูปแบบต่างๆ ของภาพอื่นๆ
- **ต้องการข้อมูลเพิ่มเติมหรือไม่** ตรวจสอบข้อมูลฟรี; และอีกครั้งหนึ่งในผลิตภัณฑ์
- **ต้องการเซิร์ฟเวอร์ Java ใด ๆ?** Java8 หรือใช้งานได้กับไลบรารี Aspose.Tasks ปัจจุบัน

## “โครงการส่งออกเป็น PDF” คืออะไร?
ในโปรเจ็กต์เป็น PDF จะเปลี่ยนโครงสร้าง MPP ภายในให้เป็นเอกสารพกพาที่สามารถเปิดได้นิดหน่อยโดยไม่ต้องใช้ Microsoft Project นี่คือการแชร์รายงานสถานะ, ในกรณีที่ผู้มีส่วนได้ส่วนเสีย, หรือการจัดเก็บบันทึกแผนโครงการ

## ทำไมต้องลดช่องว่างส่วนท้าย?
พื้นที่ส่วนท้ายเริ่มต้นอาจเพิ่มพื้นที่สีขาวที่ไม่จำเป็น, เพื่อตรวจสอบหน้าและในส่วนที่ไม่สมดุล เนื่องจากช่องว่างจะช่วยให้เนื้อหาของคุณใช้หน้ากระดาษอย่างมีประสิทธิภาพ, อ่าน PDF หรือภาพสุดท้ายอ่านได้ใน

## จะลดช่องว่างระหว่างรายการงานและส่วนท้ายได้อย่างไร
Aspose.Tasks `setReduceFooterGap(true)` สำหรับการวิจัยเป็นภาพ, PDF, และ HTML. ตรวจสอบฟลิกซ์เพื่อตรวจสอบเอนจินพื้นที่ระหว่างแถวงานสุดท้ายกับส่วนท้ายของหน้า

## บันทึกโครงการเป็นรูปภาพด้วย Aspose.Tasks
ตรวจสอบภาพสแนปช็อตของบันทึก, บันทึก ** บันทึกโครงการเป็นภาพ** (PNG) พร้อมใช้คำสั่งในช่องว่างเดียวกัน

## โครงการ Java ส่งออกเป็น PDF
รายละเอียดจะอธิบายขั้นตอนอย่างละเอียด **การส่งออกโปรเจ็กต์ Java** ครบถ้วน, โปรดดูไฟล์ MPP อย่างละเอียดในสามรูปแบบที่แตกต่างกัน

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK) – เบล8 หรือใหม่กว่า.
2. Aspose.Tasks สำหรับ Java Library – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/java/)

## แพคเกจนำเข้า
ก่อนที่จะเจาะลึกในส่วนของการเขียนโค้ด เรามานำเข้าแพ็คเกจที่จำเป็นกันก่อน:
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

## ขั้นตอนที่ 1: ระบุเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณ
ตรวจสอบให้แน่ใจว่าได้แทนที่ `"Your Data Directory"` ด้วยเส้นทางไปยังไดเรกทอรีข้อมูลจริงของคุณที่ไฟล์ Microsoft Project (`HomeMovePlan.mpp` ในตัวอย่างนี้) อยู่.
```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: อ่านไฟล์ MPP
บรรทัดโค้ดนี้อ่านไฟล์ Microsoft Project ที่ชื่อ `HomeMovePlan.mpp`.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## ขั้นตอนที่ 3: ตั้งค่า ImageSaveOptions (บันทึกโปรเจ็กต์เป็นรูปภาพ)
กำหนดค่าตัวเลือกการบันทึกภาพ, ตั้งค่า `ReduceFooterGap` เป็น `true` เพื่อ ลดช่องว่างระหว่างรายการงานกับส่วนท้าย.
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```

## ขั้นตอนที่ 4: บันทึกเป็นรูปภาพ
บันทึกโครงการเป็นภาพด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```

## ขั้นตอนที่ 5: ตั้งค่า PdfSaveOptions (ส่งออกโปรเจ็กต์เป็น PDF)
กำหนดตัวเลือกการบันทึก PDF, ตรวจสอบให้ตั้งค่า `ReduceFooterGap` เป็น `true`.
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```

## ขั้นตอนที่ 6: บันทึกเป็น PDF
บันทึกโครงการเป็น PDF ด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```

## ขั้นตอนที่ 7: ตั้งค่า HtmlSaveOptions
ระบุตัวเลือกการบันทึก HTML, ตั้งค่า `ReduceFooterGap` เป็น `true`.
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```

## ขั้นตอนที่ 8: บันทึกเป็น HTML
บันทึกโครงการเป็นไฟล์ HTML ด้วยตัวเลือกที่กำหนดไว้.
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```

## บทสรุป
ยืนยันแล้วช่องว่างระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project จะขึ้นอยู่กับ Aspose.Tasks สำหรับ Java ขั้นตอนที่อธิบายในบทแนะนำนี้, ไม่เคย **ส่งออกโครงการเป็น PDF** อย่างมีประสิทธิภาพ, บันทึกเป็นภาพ, หรือสร้าง HTML พร้อมคงสภาพวางให้กระชับและส่วนประกอบ

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: พื้นที่เก็บข้อมูลส่วนท้ายมีลักษณะของหน้าอย่างไร?**
ตอบ: จะลดพื้นที่อย่างสม่ำเสมอทุกวันหน้า, โดยเฉพาะอย่างยิ่งสามารถใส่งานได้โดยตรงเพียงเท่านั้นจำนวนหน้าทั้งหมด.

**Q: ฉันสามารถทำได้ในช่องว่างนี้กับหน้าเดียวเท่านั้นที่ทำได้?**
ตอบ: เป็นไปได้ โดยการตั้งค่า `setRenderToSinglePage(true)` ใน `ImageSaveOptions` เคยควบคุมการเข้าถึงหน้าโบสถ์เดียวกันแต่ยังคงลดช่องว่างได้

**คำถาม: `setReduceFooterGap` มีให้ในรูปแบบผลลัพธ์อื่นๆ หรือไม่**
ตอบ: ปัจจุบันรองรับสำหรับแขกที่เป็น PNG, PDF, และ HTML สำหรับรูปแบบอื่นอาจต้องปรับไลเนอร์อื่นๆ

**คำถาม: หากโครงการของฉันมีหลายแห่งที่จัดเก็บข้อมูลหรือไม่**
ตอบ: สนามกีฬาทั้งหมดจะถูกเก็บไว้ระหว่างนั้น; ดินเอาต์จะเน้นไปที่ช่องว่างเท่านั้น, ไม่มีการเก็บข้อมูล.

**ถาม: ไลบรารีนี้เองมีโครงการขนาดใหญ่ที่มีประสิทธิภาพหรือไม่?**
ตอบ: Aspose.Tasks ใช้การสตรีมข้อมูลเพื่อดูไฟล์ MPP ขนาดใหญ่ได้; อย่างไรก็ตามควรตรวจสอบให้ดีกว่านี้เมื่อส่งออกเป็นภาพความละเอียดสูง

**อัปเดตล่าสุด:** 17-12-2568
**ทดสอบกับ:** Aspose.Tasks 24.11 สำหรับ Java
**ผู้เขียน:** สมมติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}