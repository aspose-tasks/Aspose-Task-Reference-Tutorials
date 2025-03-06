---
title: แสดงผลการใช้ทรัพยากรและมุมมองชีตใน Aspose.Tasks
linktitle: แสดงผลการใช้ทรัพยากรและมุมมองชีตใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีเรนเดอร์การใช้ทรัพยากรโครงการ MS และมุมมองชีตใน Aspose.Tasks สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อสร้างรายงาน PDF แบบละเอียดได้อย่างง่ายดาย
weight: 16
url: /th/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แสดงผลการใช้ทรัพยากรและมุมมองชีตใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อเรนเดอร์การใช้ทรัพยากรโครงการ MS และมุมมองชีต Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จากเว็บไซต์ Oracle
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## ขั้นตอนที่ 1: อ่านโครงการแหล่งที่มา
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
// อ่านโครงการต้นฉบับ
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
ในขั้นตอนนี้ เราระบุเส้นทางไปยังไฟล์โปรเจ็กต์ต้นทาง (`ResourceUsageView.mpp` ) และใช้`Project` ชั้นเรียนที่จะอ่านมัน
## ขั้นตอนที่ 2: กำหนด SaveOptions ด้วยการตั้งค่า TimeScale ที่จำเป็น
```java
// กำหนด SaveOptions ด้วยการตั้งค่า TimeScale ที่จำเป็นเป็นวัน
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 ในที่นี้เรากำหนด`SaveOptions` ด้วยความจำเป็น`TimeScale` การตั้งค่า. ในตัวอย่างนี้ เราตั้งค่า`TimeScale` ถึงวัน
## ขั้นตอนที่ 3: ตั้งค่ารูปแบบการนำเสนอเป็น ResourceUsage
```java
// ตั้งค่ารูปแบบการนำเสนอเป็น ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 เรากำหนดรูปแบบการนำเสนอเป็น`ResourceUsage`ซึ่งบ่งชี้ว่าเราต้องการสร้างการแสดงผลมุมมองการใช้ทรัพยากร
## ขั้นตอนที่ 4: บันทึกโครงการ
```java
// บันทึกโครงการ
project.save(dataDir + days, options);
```
สุดท้าย เราบันทึกโครงการด้วยตัวเลือกที่ระบุ ในตัวอย่างนี้ ไฟล์เอาต์พุตจะถูกบันทึกเป็น`result_days.pdf`.
## ขั้นตอนที่ 5: แสดงผลมุมมองสำหรับการตั้งค่า TimeScale อื่น ๆ
ทำซ้ำขั้นตอนที่ 2 ถึง 4 สำหรับการเรนเดอร์มุมมองด้วยการตั้งค่า TimeScale ที่แตกต่างกัน (ThirdsOfMonths และ Months)
```java
// ตั้งค่ามาตราส่วนเวลาเป็น ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// บันทึกโครงการ
project.save(thirds, options);
// ตั้งค่าการตั้งค่ามาตราเวลาเป็นเดือน
options.setTimescale(Timescale.Months);
// บันทึกโครงการ
project.save(dataDir + months, options);
```
 รับรองว่าจะเปลี่ยน.`Timescale` การตั้งค่าตามแต่ละมุมมอง

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ Aspose.Tasks สำหรับ Java เพื่อเรนเดอร์การใช้ทรัพยากรโครงการ MS และมุมมองชีต ด้วยการทำตามขั้นตอนที่สรุปไว้ข้างต้น คุณสามารถสร้างมุมมองเหล่านี้ในรูปแบบ PDF ได้อย่างมีประสิทธิภาพ ช่วยให้การแสดงภาพและการวิเคราะห์ข้อมูลโครงการของคุณดีขึ้น
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถแสดงมุมมองอื่นนอกเหนือจากการใช้ทรัพยากรและชีตได้หรือไม่
Aspose.Tasks รองรับการเรนเดอร์มุมมองที่หลากหลาย เช่น แผนภูมิแกนต์ การใช้งาน และมุมมองปฏิทิน และอื่นๆ อีกมากมาย
### Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks รองรับรูปแบบไฟล์ Microsoft Project ที่หลากหลาย รวมถึงรูปแบบ MPP, MPT และ XML
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของมุมมองที่เรนเดอร์โดยใช้ Aspose.Tasks ได้หรือไม่
อย่างแน่นอน! Aspose.Tasks มีตัวเลือกมากมายสำหรับการปรับแต่งรูปลักษณ์และเค้าโครงของมุมมองที่เรนเดอร์เพื่อให้เหมาะกับความต้องการเฉพาะของคุณ
### Aspose.Tasks จำเป็นต้องติดตั้ง Microsoft Project บนระบบหรือไม่
ไม่ Aspose.Tasks เป็นไลบรารีแบบสแตนด์อโลนและไม่จำเป็นต้องมีการติดตั้ง Microsoft Project เพื่อให้ทำงานได้
### มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ใช่ ผู้ใช้ Aspose.Tasks สามารถขอรับการสนับสนุนทางเทคนิคผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
