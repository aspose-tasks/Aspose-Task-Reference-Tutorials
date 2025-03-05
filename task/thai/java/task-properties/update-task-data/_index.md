---
title: อัปเดตข้อมูลงานเป็นรูปแบบ MPP ใน Aspose.Tasks
linktitle: อัปเดตข้อมูลงานเป็นรูปแบบ MPP ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอัปเดตข้อมูลงานเป็นรูปแบบ MPP โดยใช้ Aspose.Tasks สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการโครงการที่มีประสิทธิภาพ
type: docs
weight: 35
url: /th/java/task-properties/update-task-data/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการอัปเดตข้อมูลงานเป็นรูปแบบ MPP โดยใช้ Aspose.Tasks สำหรับ Java ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการ เพื่อให้แน่ใจว่าคุณจะเข้าใจแต่ละขั้นตอนด้วยความชัดเจน Aspose.Tasks for Java มอบโซลูชันที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ Microsoft Project และเมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถอัปเดตข้อมูลงานในรูปแบบ MPP ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Tasks สำหรับ Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Tasks แล้ว คุณสามารถดาวน์โหลดได้จาก[หน้าปล่อย](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE ที่คุณเลือกสำหรับการพัฒนา Java
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ตัวอย่างต่อไปนี้สาธิตวิธีการนำเข้าแพ็คเกจ:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. สร้างและกำหนดค่างานเริ่มต้น
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 2. กำหนดวันที่เริ่มต้นและระยะเวลา
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 3. สร้างงานสรุป
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 4. กำหนดเส้นตายและบันทึกงาน
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 5. กำหนดค่าข้อจำกัดของงาน
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 6. สร้างงานเพิ่มเติม
```java
//สร้างงานใหม่ 10 งาน
for (int i = 0; i < 10; i++) {
    //... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
}
//... (ดำเนินการต่อด้วยโค้ดที่เหลือ)
```
## 7. บันทึกโครงการ
```java
// บันทึกโครงการ
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณได้อัปเดตข้อมูลงานเป็นรูปแบบ MPP โดยใช้ Aspose.Tasks for Java ได้สำเร็จ
## บทสรุป
ยินดีด้วย! คุณได้ทำตามคำแนะนำที่ครอบคลุมเกี่ยวกับการอัปเดตข้อมูลงานในรูปแบบ MPP โดยใช้ Aspose.Tasks สำหรับ Java แล้ว ไลบรารีอันทรงพลังนี้ทำให้งานการจัดการโครงการง่ายขึ้น ทำให้เป็นเครื่องมือที่มีค่าสำหรับนักพัฒนา Java
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารประกอบ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: ฉันจะดาวน์โหลด Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถดาวน์โหลดได้จาก[หน้าปล่อย](https://releases.aspose.com/tasks/java/).
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ตอบ: ได้ คุณสามารถเข้าถึงรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: คุณมีใบอนุญาตชั่วคราวเพื่อการทดสอบหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).