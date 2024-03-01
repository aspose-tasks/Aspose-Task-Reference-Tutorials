---
title: จัดการคุณสมบัติการหน่วงเวลาการปรับระดับใน Aspose.Tasks
linktitle: จัดการคุณสมบัติการหน่วงเวลาการปรับระดับสำหรับการกำหนดทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการคุณสมบัติการหน่วงเวลาการปรับระดับสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks for Java ด้วยบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 17
url: /th/java/resource-assignments/leveling-delay-properties/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายกระบวนการจัดการคุณสมบัติการหน่วงเวลาการปรับระดับสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้คุณทำงานกับไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project บนระบบของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java JDK บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้งได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: สร้างวัตถุโครงการ
 ยกตัวอย่าง`Project` วัตถุ:
```java
Project prj = new Project();
```
## ขั้นตอนที่ 2: สร้างงาน
เพิ่มงานในโครงการ:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## ขั้นตอนที่ 3: ตั้งค่าวันที่และระยะเวลาเริ่มต้นงาน
กำหนดวันที่เริ่มต้นและระยะเวลาสำหรับงาน:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## ขั้นตอนที่ 4: เพิ่มทรัพยากร
เพิ่มทรัพยากรให้กับโครงการ:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## ขั้นตอนที่ 5: สร้างการมอบหมายทรัพยากร
สร้างการมอบหมายทรัพยากรสำหรับงานและทรัพยากร:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## ขั้นตอนที่ 6: ตั้งค่าความล่าช้าในการปรับระดับ
ตั้งค่าความล่าช้าในการปรับระดับสำหรับงาน:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## ขั้นตอนที่ 7: แสดงผล
พิมพ์ความล่าช้าในการปรับระดับและข้อมูลที่เกี่ยวข้องอื่นๆ:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการกับคุณสมบัติการหน่วงเวลาการปรับระดับสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการการกำหนดทรัพยากรในโปรเจ็กต์ Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับไลบรารี Java อื่นๆ ได้หรือไม่

ตอบ: ได้ Aspose.Tasks สามารถรวมเข้ากับไลบรารี Java อื่นๆ เพื่อเพิ่มความสามารถในการจัดการโปรเจ็กต์ได้

### ถาม: Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่

ตอบ: ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน

### ถาม: ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน

 ตอบ: คุณสามารถค้นหาการสนับสนุนและแหล่งข้อมูลได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่

 ตอบ: ได้ คุณสามารถขอรับ Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[หน้าเผยแพร่](https://releases.aspose.com/).

### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร

 ตอบ: คุณสามารถขอใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล