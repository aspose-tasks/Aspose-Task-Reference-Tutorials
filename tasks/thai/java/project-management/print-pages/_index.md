---
title: พิมพ์หน้าเพื่อแยกรูปภาพใน Aspose.Tasks
linktitle: พิมพ์หน้าเพื่อแยกรูปภาพใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีพิมพ์หน้าเพื่อแยกรูปภาพใน Aspose.Tasks for Java ปรับปรุงการแสดงภาพโครงการด้วยคำแนะนำทีละขั้นตอนนี้
weight: 22
url: /th/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# พิมพ์หน้าเพื่อแยกรูปภาพใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการพิมพ์หน้าเพื่อแยกรูปภาพโดยใช้ Aspose.Tasks สำหรับ Java ฟังก์ชันการทำงานนี้จะมีประโยชน์อย่างยิ่งเมื่อคุณต้องการแสดงภาพเค้าโครงโครงการหรืองานที่สำคัญแยกกัน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ของคุณ คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็นที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## ขั้นตอนที่ 1: โหลดข้อมูลโครงการ
ขั้นแรก โหลดข้อมูลโครงการจากไฟล์ MPP ของคุณ:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการบันทึกรูปภาพ
กำหนดตัวเลือกสำหรับการบันทึกรูปภาพ รวมถึงวันที่เริ่มต้น วันที่สิ้นสุด งานที่สำคัญ คำอธิบาย และเส้นตาราง:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## ขั้นตอนที่ 3: ปรับแต่งเส้นตาราง
ปรับแต่งเส้นตารางสำหรับรูปภาพ โดยระบุประเภท สี และรูปแบบ:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## ขั้นตอนที่ 4: บันทึกรูปภาพ
บันทึกเค้าโครงโครงการเป็นรูปภาพ ทั้งเป็นไฟล์เดียวและไฟล์แยก:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการพิมพ์หน้าเพื่อแยกรูปภาพโดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถเห็นภาพเค้าโครงโครงการและงานที่สำคัญตามความต้องการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งรูปแบบรูปภาพเมื่อบันทึกเค้าโครงโปรเจ็กต์ได้หรือไม่
 ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับรูปแบบรูปภาพที่หลากหลาย เช่น PNG, JPEG, BMP ฯลฯ คุณสามารถระบุรูปแบบที่ต้องการได้ใน`ImageSaveOptions` ระดับ.
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ที่แตกต่างกันหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ส่วนใหญ่ รวมถึง Eclipse, IntelliJ IDEA และ NetBeans
### ถาม: ฉันสามารถผสานรวม Aspose.Tasks สำหรับ Java เข้ากับโปรเจ็กต์ Maven หรือ Gradle ของฉันได้หรือไม่
ตอบ: ได้ คุณสามารถผสานรวม Aspose.Tasks สำหรับ Java เข้ากับโปรเจ็กต์ Maven หรือ Gradle ของคุณได้อย่างง่ายดายโดยเพิ่มการขึ้นต่อกันที่เหมาะสมใน`pom.xml` หรือ`build.gradle` ไฟล์.
### ถาม: Aspose.Tasks for Java รองรับการส่งออกข้อมูลโปรเจ็กต์เป็นรูปแบบอื่นนอกเหนือจากรูปภาพหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับการส่งออกข้อมูลโปรเจ็กต์เป็นรูปแบบต่างๆ เช่น PDF, HTML, XLSX เป็นต้น ซึ่งให้ความยืดหยุ่นในการแสดงภาพข้อมูลและการรายงาน
### ถาม: มีชุมชนสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 ตอบ: ได้ คุณสามารถค้นหาการสนับสนุนจากชุมชน ถามคำถาม และมีส่วนร่วมกับผู้ใช้รายอื่นได้บน[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
