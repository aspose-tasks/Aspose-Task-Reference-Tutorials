---
title: การลดช่องว่างระหว่างรายการงานและส่วนท้ายใน Aspose.Tasks
linktitle: การลดช่องว่างระหว่างรายการงานและส่วนท้ายใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีลดช่องว่างระหว่างรายการงาน MS Project และส่วนท้ายโดยใช้ Aspose.Tasks สำหรับ Java ปรับเค้าโครงเอกสารโครงการให้เหมาะสมได้อย่างง่ายดาย
weight: 10
url: /th/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การลดช่องว่างระหว่างรายการงานและส่วนท้ายใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการลดช่องว่างระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับเค้าโครงเอกสารโครงการของคุณให้เหมาะสมได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
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
```java
String dataDir = "Your Data Directory";
```
 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Data Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีข้อมูลจริงของคุณที่ไฟล์ Microsoft Project ของคุณ (`HomeMovePlan.mpp` ในตัวอย่างนี้) ตั้งอยู่
## ขั้นตอนที่ 2: อ่านไฟล์ MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 บรรทัดโค้ดนี้อ่านชื่อไฟล์ Microsoft Project`HomeMovePlan.mpp`.
## ขั้นตอนที่ 3: ตั้งค่า ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 กำหนดตัวเลือกการบันทึกรูปภาพ การตั้งค่า`ReduceFooterGap` ถึง`true` เพื่อลดช่องว่างระหว่างรายการงานและส่วนท้าย
## ขั้นตอนที่ 4: บันทึกเป็นรูปภาพ
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
บันทึกโปรเจ็กต์เป็นรูปภาพพร้อมตัวเลือกที่กำหนดค่าไว้
## ขั้นตอนที่ 5: ตั้งค่า PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 กำหนดตัวเลือกการบันทึก PDF เพื่อให้แน่ใจว่าจะตั้งค่า`ReduceFooterGap` ถึง`true`.
## ขั้นตอนที่ 6: บันทึกเป็น PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
บันทึกโครงการเป็น PDF ด้วยตัวเลือกที่กำหนดค่าไว้
## ขั้นตอนที่ 7: ตั้งค่า HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // ตั้งเป็นจริง
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 ระบุตัวเลือกการบันทึก HTML การตั้งค่า`ReduceFooterGap` ถึง`true`.
## ขั้นตอนที่ 8: บันทึกเป็น HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
บันทึกโครงการเป็นไฟล์ HTML ด้วยตัวเลือกที่กำหนดค่าไว้

## บทสรุป
โดยสรุป การลดช่องว่างระหว่างรายการงานและส่วนท้ายในไฟล์ Microsoft Project นั้นเป็นกระบวนการที่ไม่ซับซ้อนกับ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถปรับเลย์เอาต์ของเอกสารโครงการของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่

ตอบ: Aspose.Tasks รองรับรูปแบบ Microsoft Project 2003-2019 ทำให้มั่นใจได้ถึงความเข้ากันได้ในเวอร์ชันต่างๆ

### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของส่วนท้ายในเอกสารโปรเจ็กต์ของฉันได้หรือไม่

ตอบ: ได้ Aspose.Tasks มีตัวเลือกมากมายสำหรับการปรับแต่งรูปลักษณ์ของส่วนท้าย รวมถึงการลดช่องว่างและการปรับตำแหน่งเนื้อหา

### ถาม: Aspose.Tasks รองรับการบันทึกโปรเจ็กต์ในรูปแบบอื่นที่ไม่ใช่ PNG, PDF และ HTML หรือไม่

ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบที่หลากหลาย รวมถึง XLSX, XML และ MPP และอื่นๆ

### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### ถาม: ฉันจะรับการสนับสนุนได้ที่ไหน หากฉันประสบปัญหาใดๆ ขณะใช้งาน Aspose.Tasks

 ตอบ: คุณสามารถรับความช่วยเหลือได้จากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
