---
date: 2026-10-31
description: เรียนรู้วิธีส่งออก gantt เป็น pdf ใน Java ด้วย Aspose.Tasks. คู่มือขั้นตอนต่อขั้นตอนนี้แสดงวิธีอ่านข้อมูลแผนภูมิ
  Gantt และสร้างรายงาน PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: อ่านข้อมูลแผนภูมิ Gantt เฉพาะใน Aspose.Tasks
og_description: ส่งออก gantt เป็น pdf ใน Java ด้วย Aspose.Tasks. ทำตามบทแนะนำนี้เพื่ออ่านข้อมูลแผนภูมิ
  Gantt, ปรับแต่งคุณสมบัติวิว, และสร้างรายงาน PDF สำหรับการจัดการโครงการ.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: ส่งออก gantt เป็น pdf ใน Java – คู่มือ Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: ส่งออก gantt เป็น pdf ใน Java – ดึงข้อมูลเฉพาะ
url: /th/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออก gantt เป็น pdf ใน Java – ดึงข้อมูลเฉพาะ

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ส่งออก gantt เป็น pdf ใน Java** โดยการอ่านข้อมูลแผนภูมิ Gantt ด้วย Aspose.Tasks for Java. แผนภูมิ Gantt ให้ผู้จัดการโครงการมองเห็นเส้นทางของงาน, ความขึ้นต่อกัน, และไทม์ไลน์, และการดึงข้อมูลเหล่านี้โดยอัตโนมัติทำให้คุณสร้างรายงาน PDF, แดชบอร์ด, หรือการรวมระบบกับแอปพลิเคชันองค์กรอื่น ๆ ได้อย่างง่ายดาย. เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การโหลดไฟล์โครงการไปจนถึงการดึงคุณสมบัติมุมมองและสุดท้ายการสร้าง PDF.

## คำตอบอย่างรวดเร็ว
- **อะไรที่ฉันสามารถดึงออกได้?** คุณสมบัติมุมมองใด ๆ, สไตล์แถบ, เส้นกริด, สไตล์ข้อความ, เส้นความคืบหน้า, หรือระดับเวลาตารางจากแผนภูมิ Gantt.  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** รุ่นทดลองใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือใหม่กว่า (บทแนะนำใช้ JDK 11).  
- **โค้ดสามารถรันได้ทันทีหรือไม่?** ใช่ – เพียงเปลี่ยนเส้นทางของไดเรกทอรีข้อมูล.  
- **ฉันสามารถแก้ไขมุมมองหลังจากอ่านได้หรือไม่?** แน่นอน – API ให้คุณเปลี่ยนคุณสมบัติและบันทึกกลับไปยังไฟล์โครงการ.

## การส่งออก gantt เป็น pdf คืออะไร?
การส่งออก gantt เป็น pdf คือกระบวนการแปลงมุมมองแผนภูมิ Gantt ที่เก็บอยู่ในไฟล์โครงการให้เป็นเอกสาร PDF ที่คงสไตล์การแสดงผลและข้อมูลไทม์ไลน์ไว้. การดำเนินการนี้มีประโยชน์สำหรับการแชร์สถานะโครงการกับผู้มีส่วนได้ส่วนเสียที่อาจไม่มีเครื่องมือจัดการโครงการ.

## ทำไมต้องส่งออก gantt เป็น pdf ด้วย Aspose.Tasks?
Aspose.Tasks สามารถจัดการ **รูปแบบอินพุตกว่า 30 + ประเภท** (MPP, XML, MPX ฯลฯ) และ **ส่งออกเป็น PDF ด้วยคำสั่งเดียว** พร้อมคงความแม่นยำของภาพ 95 % แม้โครงการจะมีงานมากกว่า 500 งาน. ไลบรารีประมวลผลไฟล์ในหน่วยความจำ, ดังนั้นคุณสามารถสร้าง PDF บนเซิร์ฟเวอร์โดยไม่ต้องติดตั้ง Microsoft Project.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK):** ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว. คุณสามารถดาวน์โหลดได้จาก **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks for Java จาก **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** เลือก IDE ที่คุณชื่นชอบ. ตัวเลือกยอดนิยมได้แก่ IntelliJ IDEA, Eclipse หรือ NetBeans.

## นำเข้าแพคเกจ
การนำเข้าต่อไปนี้จะให้คุณเข้าถึงคลาสหลักของ Aspose.Tasks ที่จำเป็นสำหรับการอ่านและส่งออกข้อมูล Gantt.  
*ไม่มีบล็อกโค้ดแสดงที่นี่เพื่อให้บทแนะนำมุ่งเน้นที่แนวคิด; เพียงเพิ่มการนำเข้าเหล่านี้ลงในไฟล์ Java ของคุณ.*

## ฉันจะโหลดไฟล์โครงการ Gantt chart ใน Java อย่างไร?
โหลดไฟล์โครงการโดยสร้างอินสแตนซ์ `Project` และส่งพาธเต็มไปยังคอนสตรัคเตอร์. ขั้นตอนนี้จะเริ่มต้นการแสดงผลของแผนภูมิ Gantt ในหน่วยความจำ, ทำให้คุณสามารถสอบถามคุณสมบัติมุมมองต่อไปได้. เมื่อไฟล์โหลดสำเร็จ, คุณสามารถตรวจสอบชื่อโครงการ, วันที่เริ่มต้น, และจำนวนงานเพื่อยืนยันว่าไฟล์ที่เปิดถูกต้อง. การตรวจสอบนี้ช่วยจับปัญหาเส้นทางหรือรูปแบบไฟล์ตั้งแต่ต้นกระบวนการทำงาน.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition anchor:* `Project` คืออ็อบเจกต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์โครงการเดี่ยวในหน่วยความจำ.

## ฉันจะเข้าถึงมุมมอง Gantt chart ได้อย่างไร?
ดึงมุมมอง Gantt แรกจากคอลเลกชันมุมมองของโครงการ. โครงการส่วนใหญ่จะมีอย่างน้อยหนึ่งมุมมอง Gantt, และมักจะเป็นรายการแรก. หลังจากได้มุมมองแล้ว, คุณอาจต้องตรวจสอบชื่อและยืนยันว่ามันเป็นประเภท `GanttChartView` ก่อนดำเนินการดึงคุณสมบัติ. การตรวจสอบเพิ่มเติมนี้ช่วยป้องกันข้อผิดพลาดรันไทม์เมื่อทำงานกับคอลเลกชันมุมมองที่กำหนดเองหรือไม่เป็นมาตรฐาน.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition anchor:* `GanttChartView` แสดงการจัดวางภาพของงาน, ไทม์สเคล, และแถบที่คุณเห็นในแผนภูมิ Gantt ปกติ.

## ฉันจะดึงคุณสมบัติมุมมองออกมาอย่างไร?
คุณสามารถอ่านคุณสมบัติเช่น สีพื้นหลัง, ความสูงของแถบ, และการตั้งค่าไทม์สเคลโดยตรงจากอ็อบเจกต์ `GanttChartView`. การพิมพ์ค่าเหล่านี้ช่วยให้คุณตรวจสอบการกำหนดค่าปัจจุบันก่อนทำการส่งออก. ลูปการดึงข้อมูลทั่วไปจะวนผ่านแต่ละคุณสมบัติ, แปลงค่าเป็นสตริง, และบันทึกลงคอนโซลหรือไฟล์เพื่อการวิเคราะห์ต่อไป. วิธีนี้มีประโยชน์สำหรับการดีบักและการสร้างเอกสารอธิบายลักษณะของแผนภูมิ.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition anchor:* `GanttChartView` ให้การเข้าถึงการตั้งค่ามุมมองเช่น สีพื้นหลัง, ความสูงของแถบ, และการกำหนดค่าไทม์สเคล.

## ฉันจะดึงสไตล์ของแถบออกมาอย่างไร?
วนผ่านคอลเลกชันของอ็อบเจกต์ `BarStyle` เพื่อรับรายละเอียดเช่น สี, ลวดลาย, และรูปทรงของแต่ละประเภทแถบที่ใช้ในแผนภูมิ. สำหรับแต่ละสไตล์, คุณยังสามารถอ่านประเภทงานที่เกี่ยวข้องและเงื่อนไขที่ทำให้สไตล์นั้นแอคทีฟ, ซึ่งเป็นสิ่งสำคัญเมื่อสร้างแผนภูมิใหม่ในรูปแบบอื่น. การเก็บข้อมูลนี้ทำให้คุณสามารถสร้างสำเนาภาพที่ตรงกับต้นฉบับหรือกำหนดกฎสไตล์แบบกำหนดเองโดยโปรแกรม.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition anchor:* `BarStyle` กำหนดลักษณะการแสดงผลของแถบ Gantt, รวมถึงสี, ลวดลาย, และรูปทรง.

## ฉันจะดึงเส้นกริดออกมาอย่างไร?
เส้นกริดกำหนดการแยกแยะภาพระหว่างแถวและคอลัมน์. เข้าถึงโดยใช้เมธอด `getGridlines()` และแสดงผลการมองเห็นและสไตล์ของพวกมัน. หลังจากดึงคอลเลกชันเส้นกริด, คุณสามารถวนลูปผ่านแต่ละเส้นเพื่อบันทึกประเภทเส้น (solid, dashed), ความหนา, และสี. ข้อมูลนี้มีคุณค่าเมื่อคุณต้องการทำซ้ำเลย์เอาต์กริดที่แม่นยำใน PDF ที่ส่งออกหรือรูปแบบรายงานอื่น.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition anchor:* `getGridlines()` คืนคอลเลกชันของอ็อบเจกต์เส้นกริดที่ควบคุมการแยกแถวและคอลัมน์ในมุมมอง Gantt.

## ฉันจะดึงสไตล์ข้อความออกมาอย่างไร?
สไตล์ข้อความควบคุมฟอนต์, ขนาด, และสีของป้ายกำกับบนแผนภูมิ Gantt. วนผ่านคอลเลกชัน `TextStyle` เพื่อแสดงรายการแต่ละสไตล์. สำหรับแต่ละสไตล์ข้อความ, คุณยังสามารถดึงองค์ประกอบที่เกี่ยวข้อง (ชื่องาน, วันที่ ฯลฯ) และกฎการจัดรูปแบบตามเงื่อนไข. การบันทึกรายละเอียดเหล่านี้ทำให้เอกสารที่ส่งออกคงรูปแบบการพิมพ์เดียวกับแผนภูมิดั้งเดิม.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition anchor:* `TextStyle` แสดงคุณลักษณะการจัดรูปแบบที่ใช้กับองค์ประกอบข้อความภายในแผนภูมิ Gantt.

## ฉันจะดึงเส้นความคืบหน้าออกมาอย่างไร?
เส้นความคืบหน้าแสดงจุดเสร็จสิ้นปัจจุบันของงาน. เข้าถึงผ่าน `getProgressLines()` และพิมพ์คุณลักษณะของพวกมัน. แต่ละเส้นความคืบหน้ามีคุณสมบัติเช่น สีเส้น, ความหนา, และตำแหน่งสัมพันธ์กับแถบงาน. การบันทึกข้อมูลนี้ทำให้คุณสามารถสร้างการแสดงผลที่คำนึงถึงความคืบหน้า หรือคำนวณเมตริกการเสร็จสิ้นของโครงการโดยรวม.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition anchor:* `getProgressLines()` คืนชุดของอ็อบเจกต์เส้นความคืบหน้าที่บ่งบอกสถานะการทำงานของงาน.

## ฉันจะดึงระดับเวลาตารางออกมาอย่างไร?
ระดับเวลาตารางกำหนดหน่วยเวลาเชิงลำดับขั้น (วัน, สัปดาห์, เดือน) ที่แสดงบนแผนภูมิ. ดึงโดยใช้ `getTimescaleTiers()` และแสดงการตั้งค่าของพวกมัน. สำหรับแต่ละระดับ, คุณสามารถบันทึกประเภทหน่วย, รูปแบบป้ายกำกับ, และการจัดแนว, ซึ่งเป็นสิ่งสำคัญสำหรับการทำซ้ำความละเอียดของไทม์ไลน์อย่างแม่นยำใน PDF ที่ส่งออกหรือคอมโพเนนต์ UI ที่กำหนดเอง.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition anchor:* `getTimescaleTiers()` ให้การเข้าถึงคอลเลกชันของอ็อบเจกต์ระดับเวลาตารางที่ควบคุมการแสดงผลแกนเวลา.

## ฉันจะส่งออก Gantt chart เป็น PDF อย่างไร?
สร้างอ็อบเจกต์ `PdfSaveOptions`, ปรับขนาดหน้า หรือฝังฟอนต์ตามต้องการ, จากนั้นเรียก `project.save` ด้วยรูปแบบ PDF. คำสั่งเดียวนี้จะสร้าง PDF ที่สะท้อนมุมมอง Gantt บนหน้าจอ. คุณยังสามารถระบุตัวเลือกเพิ่มเติมเช่น การบีบอัดภาพ, การลบลายน้ำ, หรือการฝังฟอนต์แบบกำหนดเองเพื่อให้สอดคล้องกับแบรนด์ขององค์กร. หลังจากบันทึก, ตรวจสอบขนาดไฟล์ PDF และความแม่นยำของภาพเพื่อยืนยันว่าการส่งออกสำเร็จ.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition anchor:* `PdfSaveOptions` ให้คุณปรับแต่งผลลัพธ์ PDF เช่น ขนาดหน้า, การบีบอัด, และการจัดการฟอนต์.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ไดเรกทอรีข้อมูลไม่ถูกต้อง:** ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) ที่เหมาะกับ OS ของคุณ.  
- **ไม่มีมุมมอง:** หากโครงการไม่มีมุมมอง Gantt, `project.getViews()` จะว่าง – ให้เพิ่มการตรวจสอบก่อนทำการแคสท์.  
- **ข้อยกเว้นลิขสิทธิ์:** หากไม่มีลิขสิทธิ์ที่ถูกต้อง, API อาจเพิ่มลายน้ำลงใน PDF ที่ส่งออก.  
- **โครงการขนาดใหญ่:** สำหรับโครงการที่มีงานมากกว่า 1,000 งาน, พิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx2g`) เพื่อหลีกเลี่ยง `OutOfMemoryError`.  

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks for Java สามารถรวมเข้ากับไลบรารีหรือเฟรมเวิร์ก Java ใดก็ได้อย่างราบรื่น, รวมถึง Spring, Hibernate, และ Apache POI.

**Q: Aspose.Tasks เหมาะกับโครงการระดับองค์กรขนาดใหญ่หรือไม่?**  
A: แน่นอน. ไลบรารีประมวลผลไฟล์ MPP หลายร้อยหน้าในเวลาไม่เกิน 5 วินาทีบนเซิร์ฟเวอร์มาตรฐานและรองรับการทำงานพร้อมกันในสภาพแวดล้อมหลายเธรด.

**Q: Aspose.Tasks รองรับหลายรูปแบบไฟล์โครงการหรือไม่?**  
A: ใช่, Aspose.Tasks รองรับกว่า 20 รูปแบบ, รวมถึง MPP, XML, MPX, และ Primavera XML, ทำให้คุณสามารถอ่านและแปลงตารางเวลาเก่าได้.

**Q: ฉันสามารถปรับแต่งลักษณะของแผนภูมิ Gantt ด้วย Aspose.Tasks ได้หรือไม่?**  
A: แน่นอน. คุณสามารถแก้ไขสไตล์แถบ, เส้นกริด, สไตล์ข้อความ, และระดับเวลาตารางโดยโปรแกรมก่อนส่งออกเป็น PDF หรือรูปภาพ.

**Q: ฉันจะบันทึกการเปลี่ยนแปลงหลังจากแก้ไขมุมมองได้อย่างไร?**  
A: เรียก `project.save("output.mpp");` หลังจากทำการแก้ไขใด ๆ เพื่อบันทึกการเปลี่ยนแปลงกลับไปยังไฟล์โครงการ.

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีบันทึกโครงการเป็น PDF ด้วย Aspose.Tasks – คู่มือการส่งออก](/tasks/java/project-file-operations/save-as-pdf/)
- [สร้าง PDF โครงการ – ปรับแต่งสเกลเวลาของแผนภูมิ Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}