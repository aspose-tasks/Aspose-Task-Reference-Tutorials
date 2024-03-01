---
title: เปลี่ยนความคืบหน้าของงานใน Aspose.Tasks
linktitle: เปลี่ยนความคืบหน้าของงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: ปรับปรุงการจัดการโครงการ Java ด้วย Aspose.Tasks เรียนรู้การแก้ไขความคืบหน้าของงานได้อย่างราบรื่นในบทช่วยสอนทีละขั้นตอนนี้ ดาวน์โหลดเดี๋ยวนี้!
type: docs
weight: 12
url: /th/java/task-properties/change-progress/
---
## การแนะนำ
ในขอบเขตของการจัดการโครงการแบบไดนามิก การติดตามความคืบหน้าของงานอย่างมีประสิทธิภาพเป็นสิ่งสำคัญ Aspose.Tasks สำหรับ Java มีความโดดเด่นในฐานะโซลูชันที่แข็งแกร่ง ทำให้กระบวนการง่ายขึ้นด้วยคุณสมบัติอันทรงพลัง ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการเปลี่ยนแปลงความคืบหน้าของงานโดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ติดตั้งและตั้งค่าสภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้บนระบบของคุณ
2.  Aspose.Tasks สำหรับ Java Library: ดาวน์โหลดไลบรารีจากไฟล์[ลิงค์](https://releases.aspose.com/tasks/java/).
3. ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีเพื่อจัดเก็บเอกสารโครงการของคุณ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ข้อมูลโค้ดนี้เริ่มต้นโครงการและเพิ่มงานที่มีความคืบหน้า 50%
```java
import com.aspose.tasks.*;

```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ Java ใหม่ในสภาพแวดล้อมการพัฒนาของคุณ
## ขั้นตอนที่ 2: นำเข้าแพ็คเกจที่จำเป็น
 ในคลาส Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็น:`Project` และ`Task`.
## ขั้นตอนที่ 3: ระบุไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณเพื่อจัดเก็บไฟล์โครงการ
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 4: สร้างโครงการใหม่
 ใช้`Project` คลาสเพื่อสร้างโปรเจ็กต์ใหม่
```java
Project project = new Project(dataDir + "project.mpp");
```
## ขั้นตอนที่ 5: เพิ่มงาน
 ใช้`Task` คลาสเพื่อเพิ่มงานใหม่ให้กับโครงการของคุณ
```java
Task task = project.getRootTask().getChildren().add("Task");
```
## ขั้นตอนที่ 6: ตั้งค่าความคืบหน้าของงาน
 กำหนดความคืบหน้าของงานโดยใช้`set` วิธีการและ`Tsk.PERCENT_COMPLETE` คุณลักษณะ.
```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```
### ขั้นตอนที่ 7: แสดงความคืบหน้า
ดึงข้อมูลและแสดงความคืบหน้าของงาน
```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะเปลี่ยนความคืบหน้าของงานโดยใช้ Aspose.Tasks for Java ได้สำเร็จ
## บทสรุป
การติดตามความคืบหน้าของงานให้มีประสิทธิภาพเป็นสิ่งสำคัญในการจัดการโครงการ Aspose.Tasks สำหรับ Java ช่วยให้กระบวนการนี้ง่ายขึ้น โดยมอบอินเทอร์เฟซที่เป็นมิตรต่อผู้ใช้และฟีเจอร์ที่ทรงพลัง การเรียนรู้ขั้นตอนต่างๆ ที่ระบุไว้ในคู่มือนี้ช่วยเพิ่มความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่
ตรวจสอบความเข้ากันได้โดยปฏิบัติตามคำแนะนำในการติดตั้งในเอกสารประกอบ
### ฉันสามารถติดตามความคืบหน้าของหลาย ๆ งานภายในโปรเจ็กต์ได้หรือไม่
ทำซ้ำขั้นตอนสำหรับแต่ละงานที่คุณต้องการตรวจสอบ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 เข้าถึงเวอร์ชันทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 สำรวจเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/tasks/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 เยี่ยมชม[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).