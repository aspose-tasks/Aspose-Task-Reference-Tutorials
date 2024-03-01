---
title: การเรียนรู้การนับมาตราส่วนเวลาของโครงการ MS ใน Aspose.Tasks
linktitle: ตั้งค่าการนับมาตราส่วนเวลาใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการการนับมาตราส่วนเวลาอย่างมีประสิทธิภาพใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java เพิ่มประสิทธิภาพการแสดงภาพและการจัดการโครงการได้อย่างง่ายดาย
type: docs
weight: 22
url: /th/java/project-file-operations/set-time-scale-count/
---
## การแนะนำ
การจัดการการนับมาตราส่วนเวลาใน MS Project อาจส่งผลกระทบอย่างมากต่อการแสดงภาพและการจัดการโครงการ ด้วย Aspose.Tasks สำหรับ Java ซึ่งเป็น API ที่มีประสิทธิภาพสำหรับการจัดการงานการจัดการโครงการโดยทางโปรแกรม คุณสามารถจัดการการนับมาตราส่วนเวลาได้อย่างมีประสิทธิภาพเพื่อปรับแต่งมุมมองโครงการให้ตรงกับความต้องการเฉพาะของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความรู้พื้นฐานของการเขียนโปรแกรม Java: ความคุ้นเคยกับภาษาการเขียนโปรแกรม Java จะเป็นประโยชน์

## แพ็คเกจนำเข้า
นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีข้อมูลที่จะจัดเก็บไฟล์โครงการของคุณ:
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของโครงการ
 สร้างอินสแตนซ์ใหม่`Project` วัตถุ:
```java
Project project = new Project();
```
สิ่งนี้จะสร้างวัตถุโครงการใหม่
## ขั้นตอนที่ 3: กำหนดค่ามุมมองแผนภูมิแกนต์
 สร้างก`GanttChartView` วัตถุเพื่อกำหนดค่ามุมมองแผนภูมิแกนต์:
```java
GanttChartView view = new GanttChartView();
```
## ขั้นตอนที่ 4: ตั้งค่าการนับมาตราส่วนเวลาสำหรับชั้นล่างสุด
ตั้งค่าการมองเห็นการนับและทำเครื่องหมายสำหรับระดับมาตราส่วนเวลาด้านล่าง:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
นี่เป็นการระบุการนับช่วงเวลาและจะแสดงเครื่องหมายสำหรับชั้นล่างสุดหรือไม่
## ขั้นตอนที่ 5: ตั้งค่าการนับมาตราส่วนเวลาสำหรับระดับกลาง
ในทำนองเดียวกัน ให้กำหนดค่าระดับช่วงเวลากลาง:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## ขั้นตอนที่ 6: เพิ่มมุมมองให้กับโครงการ
เพิ่มมุมมองที่กำหนดค่าให้กับโครงการ:
```java
project.getViews().add(view);
```
นี่เป็นการเพิ่มมุมมองที่กำหนดเองให้กับโปรเจ็กต์
## ขั้นตอนที่ 7: เพิ่มข้อมูลการทดสอบลงในโครงการ
เพิ่มข้อมูลการทดสอบบางส่วนให้กับโครงการเพื่อการสาธิต:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
สิ่งนี้จะสร้างงานสองงานโดยมีระยะเวลาที่กำหนด
## ขั้นตอนที่ 8: บันทึกโครงการเป็น PDF
บันทึกโครงการเป็นไฟล์ PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
สิ่งนี้จะบันทึกโปรเจ็กต์ด้วยการกำหนดค่าที่ใช้กับไฟล์ PDF

## บทสรุป
การจัดการการนับมาตราส่วนเวลาอย่างมีประสิทธิภาพใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java ช่วยให้คุณสามารถปรับแต่งมุมมองโครงการเพื่อการแสดงภาพและการจัดการที่ดีขึ้น
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java สามารถจัดการไฟล์โปรเจ็กต์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ที่แตกต่างกันหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java ทำงานได้อย่างราบรื่นกับ Java Integrated Development Environments (IDE) ยอดนิยม เช่น Eclipse และ IntelliJ IDEA
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิแกนต์โดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java มีความสามารถที่ครอบคลุมในการปรับแต่งรูปลักษณ์ของแผนภูมิ Gantt ตามความต้องการของคุณ
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).