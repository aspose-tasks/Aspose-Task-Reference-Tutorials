---
title: บันทึกเป็น PDF ใน Aspose.Tasks
linktitle: บันทึกเป็น PDF ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแปลงไฟล์โปรเจ็กต์เป็น PDF โดยใช้ Aspose.Tasks สำหรับ Java ขั้นตอนง่ายๆ เพื่อการแปลงที่มีประสิทธิภาพ
weight: 17
url: /th/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกเป็น PDF ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการบันทึกโปรเจ็กต์เป็น PDF โดยใช้ Aspose.Tasks สำหรับ Java ด้วย Aspose.Tasks คุณสามารถแปลงไฟล์โครงการของคุณเป็นรูปแบบ PDF ได้อย่างมีประสิทธิภาพ รับประกันความเข้ากันได้และการแบ่งปันที่ง่ายดาย มาดำดิ่งสู่ขั้นตอนต่างๆ:
## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ไฟล์โครงการ: เตรียมไฟล์โครงการ (เช่น HomeMovePlan.mpp) ให้พร้อมที่คุณต้องการแปลงเป็น PDF

## แพ็คเกจนำเข้า
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## ขั้นตอนที่ 1: อ่านไฟล์โครงการอินพุต
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 ให้แน่ใจว่าคุณเปลี่ยน`"Your Data Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณที่มีไฟล์โครงการ
## ขั้นตอนที่ 2: บันทึกโครงการเป็น PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
ข้อมูลโค้ดนี้จะบันทึกโปรเจ็กต์เป็นไฟล์ PDF ชื่อ "Project5.pdf"
## ขั้นตอนที่ 3: ปรับเนื้อหาให้เหมาะสมกับขนาดเซลล์
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
ที่นี่ เราได้กำหนดตัวเลือกสำหรับการบันทึก PDF รวมถึงเนื้อหาที่เหมาะสม มาตราส่วนเวลา และรูปแบบการนำเสนอ
## ขั้นตอนที่ 4: ซ่อนตำนาน
```java
o.setLegendOnEachPage(false);
```
ขั้นตอนนี้จะซ่อนคำอธิบายในแต่ละหน้าของ PDF
## ขั้นตอนที่ 5: บันทึกโครงการด้วยตัวเลือกที่ประยุกต์
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
สุดท้ายนี้ โค้ดนี้จะบันทึกโปรเจ็กต์พร้อมตัวเลือกที่นำไปใช้กับไฟล์ PDF

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อบันทึกโปรเจ็กต์เป็น PDF ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถแปลงไฟล์โครงการของคุณได้อย่างมีประสิทธิภาพเพื่อการแชร์และแจกจ่ายที่ง่ายดาย
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับ Java ทุกเวอร์ชันหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับเวอร์ชัน Java ที่เริ่มต้นจาก JDK 6 ขึ้นไป
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอาต์พุต PDF ได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks มีตัวเลือกมากมายในการปรับแต่งเอาต์พุต PDF ตามความต้องการของคุณ
### ถาม: Aspose.Tasks รองรับไฟล์รูปแบบอื่นสำหรับการแปลงหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบไฟล์ที่หลากหลาย รวมถึง MPP, XML, XLSX และอื่นๆ
### ถาม: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.Tasks ได้ฟรีจาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: สำหรับการสนับสนุนและความช่วยเหลือ คุณสามารถไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
