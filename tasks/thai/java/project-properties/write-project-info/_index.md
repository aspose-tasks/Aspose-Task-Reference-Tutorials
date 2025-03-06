---
title: การเรียนรู้การจัดการโครงการ MS ด้วย Aspose.Tasks สำหรับ Java
linktitle: เขียนข้อมูลโครงการใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีการเขียนข้อมูล MS Project อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา Java
type: docs
weight: 12
url: /th/java/project-properties/write-project-info/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการใช้ Aspose.Tasks สำหรับ Java ซึ่งเป็นไลบรารีที่มีประสิทธิภาพสำหรับการจัดการไฟล์ Microsoft Project โดยทางโปรแกรม เราจะมุ่งเน้นไปที่งานพื้นฐาน: การเขียนข้อมูล MS Project โดยใช้ Aspose.Tasks ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นการเดินทางในการเขียนโปรแกรม Java คู่มือนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ตามที่คุณต้องการ เราขอแนะนำ IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดไดเร็กทอรีที่จะจัดเก็บข้อมูลโครงการของคุณ
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของโครงการ
เริ่มต้นอินสแตนซ์โครงการใหม่
```java
Project project = new Project();
```
## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติข้อมูลโครงการ
ตั้งค่าคุณสมบัติสำหรับโครงการ เช่น วันที่เริ่มต้น กำหนดการตั้งแต่เริ่มต้น และวันที่สถานะ
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## ขั้นตอนที่ 4: บันทึกโครงการเป็น XML
บันทึกโครงการด้วยข้อมูลที่อัปเดตเป็นไฟล์ XML
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเขียนข้อมูล MS Project โดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว ด้วยความรู้ที่เพิ่งค้นพบนี้ คุณสามารถทำงานต่างๆ ที่เกี่ยวข้องกับไฟล์ Microsoft Project ได้โดยอัตโนมัติ ซึ่งจะช่วยเพิ่มประสิทธิภาพการทำงานของคุณในฐานะนักพัฒนา Java
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่ออ่านไฟล์ MS Project ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับทั้งการอ่านและการเขียนไฟล์ MS Project
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับ MS Project เวอร์ชันต่างๆ หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java รองรับ MS Project เวอร์ชันต่างๆ มากมาย จึงรับประกันความเข้ากันได้กับไฟล์รูปแบบต่างๆ
### ถาม: Aspose.Tasks for Java เวอร์ชันทดลองมีข้อจำกัดหรือไม่
ตอบ: แม้ว่าเวอร์ชันทดลองใช้จะช่วยให้คุณสามารถสำรวจความสามารถของไลบรารีได้ แต่ก็มีข้อจำกัดบางประการ เช่น ลายน้ำในไฟล์เอาท์พุต
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถขอความช่วยเหลือได้จากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ ใบอนุญาตชั่วคราวมีให้สำหรับการใช้งานระยะสั้น คุณสามารถรับได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).