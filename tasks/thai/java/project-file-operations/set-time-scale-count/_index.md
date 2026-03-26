---
date: 2025-12-21
description: เรียนรู้วิธีปรับแต่งมุมมองแผนภูมิแกนท์, จัดการการแสดงผลโครงการ, และบันทึกโครงการเป็น
  PDF ด้วย Aspose.Tasks สำหรับ Java. ปรับจำนวนสเกลเวลาได้อย่างง่ายดาย.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ปรับแต่งแผนภูมิแกนท์ – เชี่ยวชาญการนับสเกลเวลาใน MS Project ด้วย Aspose.Tasks
url: /th/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับแต่ง Gantt Chart – การควบคุมจำนวน Time Scale ของ MS Project ใน Aspose.Tasks

## การแนะนำ
**ปรับแต่งแผนภูมิแกนต์** ใน Microsoft Project ควบคุมจำนวนมาตราส่วนเวลาเป็นเทคนิคสำคัญด้วย Aspose.Tasks สำหรับ Java เพื่อตั้งค่าชั้นเวลา-มาตราส่วนด้านล่างและระดับกลางแบบโปรแกรมได้จานของเห็บแล้วหรือยัง **บันทึกโครงการเป็น PDF** ในแชร์กับผู้มีส่วนได้ส่วนเสีย การประชุมเพื่อให้พาคุณผ่านขั้นตอนทั้งหมดเป็นครั้งแรกที่นวัตกรรมการพัฒนา PDF ซึ่งสะท้อนถึงมุมมอง Gantt ที่คุณปรับแต่ง

## คำตอบด่วน
- ** ปรับแต่งแผนภูมิแกนต์สำหรับอะไร?** การสอบสวนมาตราส่วนเวลา, สี, และวางระบบให้เรียกร้องรายงานของคุณ
- **เมธอด API ใด ๆ ที่เกิดขึ้นมากมาย?** `view.getBottomTimescaleTier().setCount(int)`.
- **ฉันสามารถทำได้ PDF ในโครงการก็ได้ใช่ไหม** ทำได้ — ใช้ `project.save(..., SaveFileFormat.Pdf)`
- **ต้องใช้ลิขสิทธิ์ในผลิตภัณฑ์หรือ?** ต้องมีลิขสิทธิ์อะไรบ้าง; มีการทดลองทดลองฟรีให้
- ** รองรับ Java รองรับอะไร?** Java8 หรือใช้งานได้กับไลบรารี Aspose.Tasks ล่าสุด

## “ปรับแต่งแผนภูมิแกนต์” ใน Aspose.Tasks คืออะไร
แผนภูมิแกนต์ ใน Aspose.Tasks การตรวจสอบการเปลี่ยนแปลงส่วนประกอบต่างๆ ในระดับอุณหภูมิอย่างโปรแกรม—เช่นระยะเวลาในมาตราส่วนเวลา, เห็บ, และการตรวจสอบงาน — เพื่อให้ระดับความเข้มข้นของวิธีการตรวจสอบ **เนื้อความของโครงการ** โดยเฉพาะอย่างยิ่งจำนวนมาตราส่วนเวลาโดยไม่ควบคุมว่าช่วงวัน, สัปดาห์หรือเดือนส่วนแสดงค่าส่วนกลางของเครื่องหมายภูชาที่ชัดเจนสำหรับนักข่าว

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมี:

1. ** ยังคงพัฒนา Java** – JDK 8 หรือใหม่กว่าที่ติดตั้งแล้ว
2. **ไลบรารี Aspose.Tasks for Java** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/tasks/java/)
3. **ความรู้จำลอง Java** – ความคุ้นเคยกับไวยากรณ์ Java และแนวคิดเชิงวัตถุ

## นำเข้าแพ็กเกจ
นำเข้าคลาสที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดตำแหน่งที่จะอ่านและเขียนไฟล์โปรเจ็กต์ของคุณ:

```java
String dataDir = "Your Data Directory";
```

แทนที่ "ไดเร็กทอรีข้อมูลของคุณ" ด้วยพาธแบบเต็มบนเครื่องของคุณ

### ขั้นตอนที่ 2: สร้างอินสแตนซ์โปรเจ็กต์ใหม่
สร้างอ็อบเจ็กต์ `Project` ใหม่ที่จะเก็บงานและการตั้งค่ามุมมองทั้งหมด:

```java
Project project = new Project();
```

### ขั้นตอนที่ 3: กำหนดค่ามุมมองแผนภูมิ Gantt
สร้างอ็อบเจ็กต์ `GanttChartView` — นี่คือที่ที่คุณจะ **สร้างโค้ด Java สำหรับมุมมอง Gantt** เพื่อควบคุมลักษณะของแผนภูมิ:

```java
GanttChartView view = new GanttChartView();
```

### ขั้นตอนที่ 4: ตั้งค่าจำนวนช่วงเวลาสำหรับระดับล่างสุด
ปรับระดับล่างสุดให้แสดงสองช่วงเวลาและซ่อนเครื่องหมายขีด:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### ขั้นตอนที่ 5: ตั้งค่าจำนวนช่วงเวลาสำหรับระดับกลาง
ใช้การกำหนดค่าเดียวกันกับระดับกลาง:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### ขั้นตอนที่ 6: เพิ่มมุมมองที่กำหนดเองลงในโปรเจ็กต์
แนบมุมมองที่คุณเพิ่งกำหนดค่าเข้ากับอินสแตนซ์ `Project`:

```java
project.getViews().add(view);
```

### ขั้นตอนที่ 7: เพิ่มงานตัวอย่าง (ข้อมูลทดสอบ)
สร้างงานสองสามงานที่มีระยะเวลาเฉพาะเพื่อแสดงแผนภูมิ Gantt ที่กำหนดเอง:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### ขั้นตอนที่ 8: บันทึกโปรเจ็กต์เป็น PDF
สุดท้าย ส่งออก แปลงโปรเจ็กต์ของคุณ—รวมถึง **แผนภูมิ Gantt ที่ปรับแต่งเอง**—เป็นไฟล์ PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

ผลลัพธ์ PDF แสดงให้เห็นว่าระดับมาตราส่วนเวลาด้านล่างและระดับกลางได้รับการ **ปรับแต่ง** อย่างไร ทำให้ผู้มีส่วนได้ส่วนเสียมีมุมมองกำหนดการที่ชัดเจนและพิมพ์ได้

## ปัญหาทั่วไปและการแก้ไขปัญหา
- **PDF เป็นสีขาว** – ตรวจสอบให้แน่ใจว่าเส้นทาง `dataDir` ลงท้ายด้วยตัวแยกไฟล์ (`/` หรือ `\`) และมีไดเรกทอรีอยู่
- **Ticks ยังคงแสดง** – ตรวจสอบว่ามีการเรียกใช้ `setShowTicks(false)` ในทั้งสองระดับ
- **ระยะเวลาไม่ได้ใช้ถูก** – ยืนยันว่าคุณกำลังใช้ `TimeUnitType.Hour` (หรือหน่วยที่เหมาะสม) เมื่อสร้างระยะเวลา

## คำถามที่พบบ่อย

**ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการกับไฟล์โครงการขนาดใหญ่ได้ใช่ไหม**
คำตอบ: ไลบรารีนี้จะต้องปรับให้ทำงานเพื่อรองรับข้อมูลโครงการส่วนใหญ่ที่สามารถรองรับได้

**ถาม: Aspose.Tasks สำหรับ Java ที่รองรับ IDE ของ Java ที่แตกต่างกันออกไป?**
ตอบ: ทำงานได้อย่างมีประสิทธิภาพกับ Eclipse, IntelliJ IDEA, NetBeans และ IDE ยอดนิยมอื่นๆ

**ถาม: ฉันอยากจะติดตามแผนภูมิ Gantt แบบเรียลไทม์ในมาตราส่วนเวลา?**
ตอบ: ยืนยัน, Aspose.Tasks ยังคงรูปแบบนี้อยู่นั่นเอง เช่น ไม่สม่ำเสมอ, ฟอนต์, และเส้นตรง

**ถาม: มีทดลองทดลองสำหรับ Aspose.Tasks สำหรับ Java เลเซอร์?**
ตอบ: มีจริงๆ ลองทดลองทดลองฟรีจาก [ที่นี่](https://releases.aspose.com/)

**ถาม: ฉันหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java จากที่ไหน?**
ตอบ: เป็นเวลานานและความช่วยเหลือได้ในฟอรั่ม Aspose.Tasks [ที่นี่](https://forum.aspose.com/c/tasks/15)

**ถาม: สีของการเปลี่ยนแปลงของแผนภูมิ Gantt มีโปรแกรมอย่างไร?**
A: ใช้เมธอด `view.getGanttChartProperties().setBackgroundColor(Color)` หลังจากที่นำเข้า `java.awt.Color`.

## บทสรุป
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธี **ปรับแต่ง Gantt chart** ชั้น time‑scale, ปรับปรุง **การแสดงผลโครงการ**, และ **บันทึกโครงการเป็น PDF** ด้วย Aspose.Tasks for Java วิธีนี้ให้คุณควบคุมผลลัพธ์ภาพได้อย่างเต็มที่ ทำให้การแชร์ตารางเวลาที่ชัดเจนและเป็นมืออาชีพกับทีมหรือคลายเอนต์ของคุณง่ายขึ้น

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}