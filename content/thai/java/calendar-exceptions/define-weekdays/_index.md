---
title: กำหนดวันธรรมดาสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
linktitle: กำหนดวันธรรมดาสำหรับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีกำหนดวันธรรมดาสำหรับข้อยกเว้นปฏิทินในโปรเจ็กต์ Java โดยใช้ Aspose.Tasks เพื่อการกำหนดเวลาโปรเจ็กต์ที่แม่นยำ
type: docs
weight: 11
url: /th/java/calendar-exceptions/define-weekdays/
---
### การแนะนำ
ในการจัดการโครงการ การกำหนดข้อยกเว้นสำหรับปฏิทินเป็นสิ่งสำคัญสำหรับการแสดงวันทำงานหรือวันหยุดที่ไม่ได้มาตรฐานภายในไทม์ไลน์ของโครงการอย่างถูกต้อง Aspose.Tasks for Java มีฟังก์ชันที่มีประสิทธิภาพในการจัดการปฏิทินอย่างมีประสิทธิภาพ รวมถึงการกำหนดข้อยกเว้น เช่น วันหยุดหรือวันทำงานพิเศษ ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีกำหนดวันธรรมดาสำหรับข้อยกเว้นปฏิทินโดยใช้ Aspose.Tasks สำหรับ Java
### ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;

```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
ตั้งค่าเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณที่จะจัดเก็บไฟล์โปรเจ็กต์
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์โปรเจ็กต์
เริ่มต้นอินสแตนซ์ใหม่ของคลาส Project เพื่อเริ่มทำงานกับข้อมูลโปรเจ็กต์
```java
Project project = new Project();
```
## ขั้นตอนที่ 3: กำหนดปฏิทิน
สร้างวัตถุปฏิทินเพื่อกำหนดปฏิทินที่จะเพิ่มข้อยกเว้น
```java
Calendar cal = project.getCalendars().add("Calendar1");
```
## ขั้นตอนที่ 4: กำหนดข้อยกเว้นวันธรรมดา
กำหนดข้อยกเว้นสำหรับวันธรรมดา เช่น วันหยุด ภายในปฏิทิน
```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```
## ขั้นตอนที่ 5: บันทึกโครงการ
บันทึกไฟล์โครงการโดยมีข้อยกเว้นปฏิทินที่กำหนดไว้
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## บทสรุป
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถกำหนดวันธรรมดาสำหรับข้อยกเว้นปฏิทินในโปรเจ็กต์ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java การจัดการข้อยกเว้น เช่น วันหยุดหรือวันทำงานพิเศษช่วยให้มั่นใจได้ถึงกำหนดการและการนำเสนอไทม์ไลน์ของโครงการที่แม่นยำ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถกำหนดข้อยกเว้นหลายรายการสำหรับวันธรรมดาที่แตกต่างกันภายในปฏิทินเดียวกันได้หรือไม่
ตอบ: ได้ คุณสามารถกำหนดข้อยกเว้นได้หลายรายการสำหรับวันธรรมดาต่างๆ ภายในปฏิทินเดียวโดยใช้ Aspose.Tasks สำหรับ Java
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ที่แตกต่างกันหรือไม่
ตอบ: Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ยอดนิยม เช่น IntelliJ IDEA, Eclipse และ NetBeans
### ถาม: ฉันสามารถปรับแต่งประเภทข้อยกเว้นนอกเหนือจากข้อยกเว้นรายวันได้หรือไม่
ตอบ: แน่นอน Aspose.Tasks สำหรับ Java มอบความยืดหยุ่นในการกำหนดข้อยกเว้นตามเกณฑ์ต่างๆ ไม่จำกัดเฉพาะข้อยกเว้นรายวัน
### ถาม: ฉันจะจัดการข้อยกเว้นแบบไดนามิกตามความต้องการของโปรเจ็กต์ได้อย่างไร
ตอบ: คุณสามารถจัดการข้อยกเว้นทางโปรแกรมตามความต้องการโปรเจ็กต์ไดนามิกได้โดยใช้ API ที่ครอบคลุมที่ Aspose.Tasks สำหรับ Java มอบให้
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถใช้ประโยชน์จาก Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
