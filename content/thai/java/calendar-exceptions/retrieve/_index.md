---
title: รับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
linktitle: รับข้อยกเว้นปฏิทินด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีดึงข้อมูลข้อยกเว้นปฏิทินจาก MS Project โดยใช้ Aspose.Tasks สำหรับ Java บทช่วยสอนทีละขั้นตอนเพื่อการผสานรวมที่ราบรื่น
type: docs
weight: 13
url: /th/java/calendar-exceptions/retrieve/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีดึงข้อมูลข้อยกเว้นปฏิทินจาก MS Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อให้เข้าใจได้ง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): คุณสามารถใช้ IDE ใดก็ได้ตามที่คุณต้องการ เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูลของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Data Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีของคุณที่มีไฟล์ MS Project
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ MS
```java
Project project = new Project(dataDir + "project.mpp");
```
 บรรทัดนี้เริ่มต้นใหม่`Project` วัตถุโดยการโหลดไฟล์ MS Project ที่ระบุโดยเส้นทาง
## ขั้นตอนที่ 3: ดึงข้อมูลข้อยกเว้นของปฏิทิน
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
ที่นี่ เราวนซ้ำแต่ละปฏิทินในโครงการ จากนั้นจึงวนซ้ำแต่ละปฏิทินยกเว้นภายในปฏิทินนั้น เราพิมพ์วันที่เริ่มต้นและสิ้นสุดของข้อยกเว้นแต่ละข้อ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงข้อมูลข้อยกเว้นปฏิทินจาก MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.Tasks สามารถจัดการไฟล์ MS Project เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน[ที่นี่](https://forum.aspose.com/c/tasks/15).
### มีตัวเลือกสำหรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).