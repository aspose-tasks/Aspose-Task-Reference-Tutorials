---
title: คุณสมบัติวันธรรมดาใน Aspose.Tasks
linktitle: คุณสมบัติวันธรรมดาใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการคุณสมบัติวันทำงานอย่างมีประสิทธิภาพใน Aspose.Tasks สำหรับ Java ปรับแต่งวันที่เริ่มต้นสัปดาห์ วันต่อเดือน และอื่นๆ ได้อย่างง่ายดาย
weight: 25
url: /th/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คุณสมบัติวันธรรมดาใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ Java เป็น API อันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถทำงานกับไฟล์ Microsoft Project โดยไม่ต้องติดตั้ง Microsoft Project บนเครื่อง หนึ่งในฟังก์ชันหลักคือการจัดการคุณสมบัติวันทำงาน ช่วยให้ผู้ใช้ปรับแต่งวันที่เริ่มต้นสัปดาห์ วันต่อเดือน นาทีต่อวัน และนาทีต่อสัปดาห์ได้ บทช่วยสอนนี้จะให้คำแนะนำโดยละเอียดเกี่ยวกับวิธีการใช้คุณสมบัติเหล่านี้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึก Aspose.Tasks สำหรับ Java ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### ชุดพัฒนาจาวา (JDK)
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ล่าสุดได้จากเว็บไซต์ Oracle
### Aspose.Tasks สำหรับไลบรารี Java
 ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จากเว็บไซต์ คุณสามารถเข้าถึงลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/java/).
### สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)
เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java ตัวเลือกยอดนิยม ได้แก่ IntelliJ IDEA, Eclipse หรือ NetBeans
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจ Aspose.Tasks ที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ มีวิธีดังนี้:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้น
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
ขั้นตอนนี้เกี่ยวข้องกับการโหลดไฟล์โครงการชื่อ "project.mpp" จากไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 2: แสดงคุณสมบัติวันทำงาน
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
ที่นี่ เราจะดึงข้อมูลและพิมพ์คุณสมบัติวันที่เริ่มต้นสัปดาห์ วันต่อเดือน นาทีต่อวัน และนาทีต่อสัปดาห์ของโครงการที่โหลด
## ขั้นตอนที่ 3: การตั้งค่าคุณสมบัติวันทำงาน
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
ขั้นตอนนี้เกี่ยวข้องกับการสร้างอินสแตนซ์โปรเจ็กต์ใหม่และการตั้งค่าคุณสมบัติวันทำงานที่กำหนดเอง เช่น วันเริ่มต้นสัปดาห์ วันต่อเดือน นาทีต่อวัน และนาทีต่อสัปดาห์
## ขั้นตอนที่ 4: บันทึกโครงการ
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
สุดท้าย เราจะบันทึกโปรเจ็กต์ที่แก้ไขด้วยคุณสมบัติวันทำงานที่อัปเดตเป็นไฟล์ XML
## ขั้นตอนที่ 5: แสดงผล
```java
System.out.println("Process completed Successfully");
```
ขั้นตอนนี้เป็นการยืนยันความสำเร็จของกระบวนการ
## บทสรุป
การเรียนรู้คุณสมบัติวันทำงานอย่างเชี่ยวชาญใน Aspose.Tasks สำหรับ Java เป็นสิ่งสำคัญสำหรับการจัดการโครงการที่มีประสิทธิภาพ เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดการและปรับแต่งคุณสมบัติของวันทำงานได้อย่างง่ายดาย สำรวจเอกสารและตัวอย่างเพิ่มเติมเพื่อปรับปรุงความสามารถในการจัดการโครงการของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java ให้การสนับสนุนที่ครอบคลุมสำหรับการจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้อย่างง่ายดาย
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ มากมาย จึงรับประกันความเข้ากันได้ข้ามแพลตฟอร์ม
### ถาม: ฉันสามารถผสานรวม Aspose.Tasks สำหรับ Java เข้ากับแอปพลิเคชัน Java ที่มีอยู่ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java นำเสนอความสามารถในการบูรณาการที่ราบรื่น ช่วยให้คุณสามารถปรับปรุงแอปพลิเคชัน Java ของคุณด้วยคุณสมบัติการจัดการโครงการอันทรงพลัง
### ถาม: Aspose.Tasks for Java มีเอกสารประกอบและการสนับสนุนหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึงเอกสารที่ครอบคลุมและการสนับสนุนชุมชนสำหรับ Aspose.Tasks สำหรับ Java บนเอกสารเหล่านั้น[เว็บไซต์](https://releases.aspose.com/).
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จากที่นี่[เว็บไซต์](https://reference.aspose.com/tasks/java/) เพื่อสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
