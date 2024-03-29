---
title: การตั้งค่าแอตทริบิวต์โครงการ MS สำหรับงานใหม่ใน Aspose.Tasks
linktitle: ตั้งค่าคุณสมบัติสำหรับงานใหม่ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีตั้งค่าแอตทริบิวต์ MS Project สำหรับงานใหม่โดยใช้ Aspose.Tasks สำหรับ Java ปรับแต่งคุณสมบัติของงานได้อย่างง่ายดายด้วยคำแนะนำที่ครอบคลุมนี้
type: docs
weight: 21
url: /th/java/project-file-operations/set-attributes-new-tasks/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมของเราเกี่ยวกับการตั้งค่าคุณลักษณะ MS Project สำหรับงานใหม่ใน Aspose.Tasks สำหรับ Java! ในคู่มือนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถจัดการและปรับแต่งงานของคุณได้อย่างง่ายดายด้วยไลบรารี Java อันทรงพลังนี้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ และคุณคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java พื้นฐาน
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/).
3. Java IDE: เลือก Java Integrated Development Environment (IDE) เช่น Eclipse หรือ IntelliJ IDEA สำหรับการเขียนโค้ด

## แพ็คเกจนำเข้า
ก่อนที่เราจะเริ่มตั้งค่าแอตทริบิวต์ MS Project สำหรับงานใหม่ เรามานำเข้าแพ็คเกจที่จำเป็นก่อน:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
ขั้นแรก ระบุเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์โปรเจ็กต์ของคุณ:
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์โปรเจ็กต์
สร้างอินสแตนซ์ของวัตถุโปรเจ็กต์ใหม่เพื่อเริ่มทำงานกับโปรเจ็กต์ของคุณ:
```java
Project prj = new Project();
```
สิ่งนี้จะสร้างอินสแตนซ์โครงการใหม่
## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติงานใหม่
ตอนนี้ เรามากำหนดวันเริ่มต้นสำหรับงานใหม่กันดีกว่า ในตัวอย่างนี้ เราตั้งค่าเป็นวันที่ปัจจุบัน:
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
 บรรทัดนี้ตั้งค่าคุณสมบัติ`NEW_TASK_START_DATE` ถึง`TaskStartDateType.CurrentDate`.
## ขั้นตอนที่ 4: บันทึกโครงการ
บันทึกโครงการด้วยแอตทริบิวต์งานใหม่ในรูปแบบ XML:
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
บรรทัดนี้จะบันทึกโปรเจ็กต์ด้วยชื่อไฟล์ที่ระบุในไดเร็กทอรีที่กำหนดไว้ก่อนหน้านี้
## ขั้นตอนที่ 5: แสดงผล
สุดท้ายนี้ มาพิมพ์ข้อความเพื่อยืนยันว่าไฟล์โครงการถูกสร้างขึ้นสำเร็จแล้ว:
```java
System.out.println("Project file generated Successfully");
```
บรรทัดนี้แสดงข้อความแสดงความสำเร็จในคอนโซล

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่าแอตทริบิวต์ MS Project สำหรับงานใหม่โดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว ด้วยความรู้นี้ คุณสามารถปรับแต่งคุณสมบัติของงานได้ตามความต้องการของคุณ ซึ่งช่วยเพิ่มความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อจัดการไฟล์โปรเจ็กต์ที่มีอยู่ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java มีฟังก์ชันการทำงานที่ครอบคลุมในการจัดการไฟล์โปรเจ็กต์ที่มีอยู่ รวมถึงการอ่าน การแก้ไข และการบันทึกไฟล์ในรูปแบบต่างๆ
### ถาม: ฉันจะหาเอกสารและทรัพยากรเพิ่มเติมสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถสำรวจเอกสารและแหล่งข้อมูลได้ที่[Aspose.Tasks สำหรับหน้าเอกสารประกอบ Java](https://reference.aspose.com/tasks/java/).
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับสิทธิ์ใช้งานชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: สามารถรับสิทธิ์ใช้งานชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับปัญหาหรือการสอบถามที่เกี่ยวข้องกับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: คุณสามารถรับการสนับสนุนและโต้ตอบกับชุมชนได้ที่[Aspose.Tasks สำหรับฟอรัมสนับสนุน Java](https://forum.aspose.com/c/tasks/15).