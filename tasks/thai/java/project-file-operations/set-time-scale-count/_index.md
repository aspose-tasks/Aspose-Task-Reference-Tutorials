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

## Introduction
หากคุณต้องการ **ปรับแต่ง Gantt chart** ใน Microsoft Project การควบคุมจำนวน time‑scale เป็นเทคนิคสำคัญ ด้วย Aspose.Tasks for Java คุณสามารถตั้งค่าชั้น time‑scale ด้านล่างและระดับกลางแบบโปรแกรมได้ ปรับการแสดงผลของ tick อย่างละเอียด แล้ว **บันทึกโครงการเป็น PDF** เพื่อแชร์กับผู้มีส่วนได้ส่วนเสีย บทเรียนนี้จะพาคุณผ่านขั้นตอนทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการสร้าง PDF ที่ดูเป็นมืออาชีพซึ่งสะท้อนมุมมอง Gantt ที่คุณปรับแต่ง

## Quick Answers
- **ปรับแต่ง Gantt chart หมายถึงอะไร?** การปรับระดับ time‑scale, สี, และการจัดวางให้ตรงกับความต้องการรายงานของคุณ.  
- **เมธอด API ใดที่ตั้งค่าจำนวนของชั้นล่าง?** `view.getBottomTimescaleTier().setCount(int)`.  
- **ฉันสามารถสร้าง PDF โดยตรงจากโครงการได้หรือไม่?** ใช่ — ใช้ `project.save(..., SaveFileFormat.Pdf)`.  
- **ต้องใช้ลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์; มีเวอร์ชันทดลองฟรีให้ใช้.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือสูงกว่าใช้งานได้กับไลบรารี Aspose.Tasks ล่าสุด.

## What is “customize Gantt chart” in Aspose.Tasks?
การปรับแต่ง Gantt chart ใน Aspose.Tasks หมายถึงการเปลี่ยนแปลงส่วนประกอบภาพของแผนภูมิอย่างโปรแกรม—เช่นช่วงเวลาใน time‑scale, เครื่องหมาย tick, และแถบงาน—เพื่อให้แผนภูมิตรงกับวิธีที่คุณต้องการ **จัดการการแสดงผลโครงการ** โดยการเปลี่ยนจำนวน time‑scale คุณจะควบคุมว่าช่วงวัน, สัปดาห์ หรือเดือนแต่ละส่วนแสดงค่าเท่าใด ทำให้แผนภูชาชัดเจนสำหรับผู้ชมที่แตกต่างกัน

## Prerequisites
Before you begin, make sure you have:

1. **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือใหม่กว่า installed.  
2. **ไลบรารี Aspose.Tasks for Java** – Download it from [here](https://releases.aspose.com/tasks/java/).  
3. **ความรู้พื้นฐานของ Java** – Familiarity with Java syntax and object‑oriented concepts.

## Import Packages
Import the necessary classes into your Java project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
Define where your project files will be read from and written to:

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine.

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object that will hold all tasks and view settings:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
Create a `GanttChartView` object—this is where you’ll **generate Gantt view Java** code to control the chart appearance:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
Adjust the bottom tier to show two intervals and hide the tick marks:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
Apply the same configuration to the middle tier:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
Attach the view you just configured to the `Project` instance:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
Create a couple of tasks with specific durations to illustrate the customized Gantt chart:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
Finally, export the project—including your **customized Gantt chart**—to a PDF file:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

The resulting PDF demonstrates how the bottom and middle time‑scale tiers have been **customized**, giving stakeholders a clear, printable view of the schedule.

## Common Issues & Troubleshooting
- **PDF เป็นสีขาว** – Ensure the `dataDir` path ends with a file separator (`/` or `\`) and that the directory exists.  
- **Ticks ยังแสดง** – Verify that `setShowTicks(false)` is called on both tiers.  
- **ระยะเวลาไม่ได้ถูกนำไปใช้** – Confirm you are using `TimeUnitType.Hour` (or the appropriate unit) when creating durations.

## Frequently Asked Questions

**Q: Aspose.Tasks for Java สามารถจัดการไฟล์โครงการขนาดใหญ่ได้หรือไม่?**  
A: ใช่, ไลบรารีนี้ได้รับการปรับให้ทำงานประมวลผลข้อมูลโครงการขนาดใหญ่ได้อย่างมีประสิทธิภาพสูง.

**Q: Aspose.Tasks for Java รองรับ IDE ของ Java ต่าง ๆ หรือไม่?**  
A: แน่นอน – ทำงานได้อย่างราบรื่นกับ Eclipse, IntelliJ IDEA, NetBeans และ IDE ยอดนิยมอื่น ๆ.

**Q: ฉันสามารถปรับแต่งลักษณะของ Gantt chart นอกเหนือจากการตั้งค่า time‑scale ได้หรือไม่?**  
A: ใช่, Aspose.Tasks มีตัวเลือกการจัดรูปแบบที่หลากหลาย เช่น สีของแถบ, ฟอนต์, และเส้นกริด.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, คุณสามารถรับเวอร์ชันทดลองฟรีจาก [here](https://releases.aspose.com/).

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: คุณสามารถหาการสนับสนุนและความช่วยเหลือได้ในฟอรั่ม Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: ฉันจะเปลี่ยนสีพื้นหลังของ Gantt chart อย่างโปรแกรมได้อย่างไร?**  
A: ใช้เมธอด `view.getGanttChartProperties().setBackgroundColor(Color)` หลังจากนำเข้า `java.awt.Color`.

## Conclusion
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธี **ปรับแต่ง Gantt chart** ชั้น time‑scale, ปรับปรุง **การแสดงผลโครงการ**, และ **บันทึกโครงการเป็น PDF** ด้วย Aspose.Tasks for Java วิธีนี้ให้คุณควบคุมผลลัพธ์ภาพได้อย่างเต็มที่ ทำให้การแชร์ตารางเวลาที่ชัดเจนและเป็นมืออาชีพกับทีมหรือคลายเอนต์ของคุณง่ายขึ้น

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}