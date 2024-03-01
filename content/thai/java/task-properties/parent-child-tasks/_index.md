---
title: จัดการงานหลักและงานรองใน Aspose.Tasks
linktitle: จัดการงานหลักและงานรองใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เพิ่มประสิทธิภาพการจัดการโครงการด้วย Aspose.Tasks สำหรับ Java เรียนรู้การจัดการงานของผู้ปกครองและเด็กทีละขั้นตอน เริ่มตอนนี้เลย!
type: docs
weight: 24
url: /th/java/task-properties/parent-child-tasks/
---
## การแนะนำ
ในขอบเขตของการจัดการโครงการ การจัดระเบียบงานที่มีประสิทธิผลเป็นสิ่งสำคัญ Aspose.Tasks สำหรับ Java มอบโซลูชันที่มีประสิทธิภาพในการจัดการงานหลักและงานรองอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการใช้ Aspose.Tasks สำหรับ Java เพื่อปรับปรุงงานโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
- การตั้งค่า Java Integrated Development Environment (IDE) บนระบบของคุณ
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้อำนวยความสะดวกในการผสานรวมกับ Aspose.Tasks สำหรับฟังก์ชัน Java ได้อย่างราบรื่น
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
## ขั้นตอนที่ 1: กำหนดวันที่เริ่มต้นโครงการ
เริ่มต้นด้วยการตั้งค่าวันที่เริ่มต้นของโครงการและพารามิเตอร์อื่นๆ ที่เกี่ยวข้อง
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// คุณสามารถเพิ่มรหัสเพิ่มเติมสำหรับการนำเข้าแพ็คเกจได้ที่นี่
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## ขั้นตอนที่ 2: เพิ่มงานหลัก (งานที่ 1)
สร้างงานหลักชื่อ "งาน 1" และกำหนดค่าคุณสมบัติ
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## ขั้นตอนที่ 3: เพิ่มงานหลัก (งาน 2) ด้วยงานลูก
ตอนนี้ เพิ่มงานหลักอื่นชื่อ "งาน 2" และรวมงานย่อย (งาน 3 และงาน 4)
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// เพิ่มงานย่อยในงานที่ 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// สามารถเพิ่มการกำหนดค่าเพิ่มเติมสำหรับภารกิจที่ 3 และภารกิจที่ 4 ได้ที่นี่
```
## ขั้นตอนที่ 4: กำหนดค่างานย่อย
ระบุวันที่เริ่มต้น ระยะเวลา และข้อจำกัดสำหรับงานที่ 3 และงานที่ 4
```java
// กำหนดค่างาน 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// กำหนดค่างาน 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## ขั้นตอนที่ 5: อัปเดตเปอร์เซ็นต์ความสำเร็จของงาน
ปรับเปอร์เซ็นต์ความสำเร็จของภารกิจที่ 3 และภารกิจที่ 4
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## ขั้นตอนที่ 6: บันทึกโครงการ
สุดท้าย ให้บันทึกโปรเจ็กต์พร้อมกับการเปลี่ยนแปลงที่นำไปใช้
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
คำแนะนำทีละขั้นตอนนี้สาธิตวิธีจัดการงานหลักและงานรองอย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java ทดลองใช้การกำหนดค่าต่างๆ เพื่อให้เหมาะกับความต้องการของโครงการของคุณ
## บทสรุป
โดยสรุป Aspose.Tasks สำหรับ Java ช่วยให้นักพัฒนาสามารถจัดการงานโครงการได้อย่างมีประสิทธิภาพ ช่วยให้มั่นใจได้ว่าองค์กรและการติดตามจะราบรื่น ใช้ขั้นตอนที่ระบุไว้เพื่อปรับปรุงความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ Java เข้ากันได้กับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks สำหรับ Java รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP และ XML
### ฉันสามารถปรับแต่งคุณสมบัติของงานนอกเหนือจากที่กล่าวถึงในบทช่วยสอนนี้ได้หรือไม่
อย่างแน่นอน! Aspose.Tasks for Java มีตัวเลือกการปรับแต่งที่ครอบคลุมสำหรับคุณสมบัติของงาน
### มีฟอรัมชุมชนสำหรับ Aspose.Tasks ที่ฉันสามารถขอรับการสนับสนุนได้หรือไม่
 ใช่ คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อสนับสนุนชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/tasks/java/).