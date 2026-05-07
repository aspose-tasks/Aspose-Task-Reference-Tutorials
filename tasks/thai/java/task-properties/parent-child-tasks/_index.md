---
date: 2026-02-23
description: เรียนรู้วิธีตั้งค่าวันเริ่มต้นของโครงการ, ตั้งระยะเวลาของงาน, และบันทึกโครงการเป็นไฟล์
  MPP ด้วย Aspose.Tasks สำหรับ Java. จัดการงานแม่และงานลูกอย่างมีประสิทธิภาพ.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ตั้งค่าวันเริ่มต้นของโครงการและจัดการงานแม่และงานลูกใน Aspose.Tasks
url: /th/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าวันเริ่มต้นของโครงการและจัดการงานพาเรนต์และชิลด์ใน Aspose.Tasks

## Introduction
การจัดระเบียบงานอย่างมีประสิทธิภาพเป็นโครงกระดูกของการจัดการโครงการที่ประสบความสำเร็จ และ **การตั้งค่าวันเริ่มต้นของโครงการ** อย่างถูกต้องเป็นขั้นตอนแรกสู่ตารางเวลาที่มีโครงสร้างดี ในบทเรียนนี้คุณจะได้เห็นวิธี **ตั้งค่าวันเริ่มต้นของโครงการ**, กำหนดระยะเวลาของงาน, และจัดการความสัมพันธ์พาเรนต์‑ชิลด์โดยใช้ Aspose.Tasks for Java. เมื่อเสร็จสิ้น คุณจะพร้อม **บันทึกโครงการเป็น MPP**, อัปเดตเปอร์เซ็นต์การทำงานของงาน, และปรับแต่งคุณสมบัติงานให้เข้ากับสถานการณ์จริงใด ๆ

## Quick Answers
- **ฉันจะตั้งค่าวันเริ่มต้นของโครงการอย่างไร?** ใช้ `proj.set(Prj.START_DATE, startDate);` หลังจากสร้างอ็อบเจ็กต์ `Project`.  
- **ฉันสามารถเพิ่มงานชิลด์ภายใต้งานพาเรนต์ได้หรือไม่?** ใช่ – เรียก `parentTask.getChildren().add("Child Task")`.  
- **Aspose.Tasks บันทึกไฟล์ในรูปแบบใด?** ใช้ `SaveFileFormat.Mpp` เพื่อ **บันทึกโครงการเป็น MPP**.  
- **ฉันจะอัปเดตการทำงานของงานอย่างไร?** ตั้งค่า `Tsk.PERCENT_COMPLETE` บนวัตถุของงาน.  
- **ฉันสามารถรับใบอนุญาตชั่วคราวได้จากที่ไหน?** เยี่ยมชมหน้าลิขสิทธิ์ชั่วคราวที่เชื่อมโยงในคำถามที่พบบ่อย.

## Prerequisites
ก่อนจะลงลึกในบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อม:
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Tasks for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ [here](https://releases.aspose.com/tasks/java/).  
- สภาพแวดล้อมการพัฒนา Java (IDE) ตั้งค่าไว้บนระบบของคุณ.

## Import Packages
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ แพ็กเกจเหล่านี้ช่วยให้การบูรณาการกับฟังก์ชันของ Aspose.Tasks for Java เป็นไปอย่างราบรื่น.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
เริ่มต้นด้วยการตั้งค่าวันเริ่มต้นของโครงการและพารามิเตอร์ที่เกี่ยวข้องอื่น ๆ.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
สร้างงานพาเรนต์ชื่อ "Task 1" และกำหนดคุณสมบัติของมัน รวมถึง **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
ต่อไป เพิ่มงานพาเรนต์อีกงานชื่อ "Task 2" และรวมงานชิลด์ (Task 3 และ Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
ระบุวันเริ่มต้น, ระยะเวลา, และข้อจำกัดสำหรับ Task 3 และ Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
ปรับเปอร์เซ็นต์การทำงานสำหรับ Task 3 และ Task 4 – นี่คือวิธีที่คุณ **update task completion**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
สุดท้าย, **save project as MPP** พร้อมกับการเปลี่ยนแปลงที่ได้ทำ.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

คำแนะนำแบบขั้นตอนนี้แสดงวิธีการจัดการงานพาเรนต์และชิลด์อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks for Java. ทดลองปรับแต่งการตั้งค่าต่าง ๆ เพื่อให้สอดคล้องกับความต้องการของโครงการของคุณ.

## Why Customize Task Properties?
ทำไมต้องปรับแต่งคุณสมบัติงาน?
การปรับแต่งคุณสมบัติงาน เช่น วันเริ่มต้น, ระยะเวลา, ข้อจำกัด, และเปอร์เซ็นต์การทำงาน ให้คุณควบคุมพฤติกรรมของตารางเวลาได้อย่างละเอียด ไม่ว่าคุณจะต้องการให้งานสอดคล้องกับความพร้อมของทรัพยากรหรือบังคับใช้กฎธุรกิจ, Aspose.Tasks ให้คุณ **customize task properties** ผ่านโปรแกรมได้.

## Common Issues and Solutions
| ปัญหา | วิธีแก้ |
|-------|----------|
| **วันเริ่มต้นไม่ถูกนำไปใช้** | ตรวจสอบว่าคุณเรียก `proj.set(Prj.START_DATE, …)` **หลัง** จากการสร้างอ็อบเจ็กต์ `Project` และก่อนเพิ่มงาน. |
| **งานชิลด์สืบทอดข้อจำกัดที่ผิด** | กำหนด `ConstraintType` และ `ConstraintDate` ของแต่ละชิลด์อย่างชัดเจน ตามที่แสดงในขั้นตอน 4. |
| **ไฟล์ที่บันทึกไม่สามารถเปิดใน MS Project** | ตรวจสอบว่าคุณใช้เวอร์ชันล่าสุดของ Aspose.Tasks และบันทึกด้วย `SaveFileFormat.Mpp`. |
| **เปอร์เซ็นต์ไม่แสดงใน UI** | หลังจากตั้งค่า `Tsk.PERCENT_COMPLETE` ให้เรียก `proj.calculateTaskSchedule()` หากต้องการคำนวณวันที่ใหม่. |

## FAQs
### Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?
ใช่, Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการหลายรูปแบบ รวมถึง MPP และ XML.

### ฉันสามารถปรับแต่งคุณสมบัติงานได้เกินกว่าที่ครอบคลุมในบทเรียนนี้หรือไม่?
ได้เลย! Aspose.Tasks for Java มีตัวเลือกการปรับแต่งคุณสมบัติงานอย่างกว้างขวาง.

### มีฟอรั่มชุมชนสำหรับ Aspose.Tasks ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่?
ใช่, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับการสนับสนุนจากชุมชน.

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for Java ได้อย่างไร?
คุณสามารถรับใบอนุญาตชั่วคราวได้ [here](https://purchase.aspose.com/temporary-license/).

### ฉันจะหาเอกสารประกอบที่ครอบคลุมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?
เอกสารพร้อมใช้งาน [here](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: ฉันจะรับใบอนุญาตชั่วคราวโดยโปรแกรมได้อย่างไร?**  
A: โหลดไฟล์ใบอนุญาตชั่วคราวด้วย `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: ฉันสามารถเปลี่ยนหน่วยระยะเวลางานเริ่มต้นได้หรือไม่?**  
A: ได้ – แก้ไขอาร์กิวเมนต์ `TimeUnitType` ใน `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: เวอร์ชันของ Aspose.Tasks ที่ต้องการเพื่อใช้ `SaveFileFormat.Mpp` คืออะไร?**  
A: ทุกเวอร์ชันล่าสุด (2022‑2026) รองรับการบันทึกเป็น MPP; ตรวจสอบบันทึกการปล่อยเวอร์ชันสำหรับการเปลี่ยนแปลงที่อาจทำให้แตกหัก.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}