---
title: ระยะเวลางานในหน่วยต่าง ๆ ด้วย Aspose.Tasks
linktitle: ระยะเวลางานในหน่วยต่าง ๆ ด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจการจัดการระยะเวลางานในโปรเจ็กต์ Java ด้วย Aspose.Tasks คำนวณและแปลงระยะเวลาอย่างแม่นยำเป็นนาที วัน ชั่วโมง สัปดาห์ และเดือน
weight: 32
url: /th/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระยะเวลางานในหน่วยต่าง ๆ ด้วย Aspose.Tasks

## การแนะนำ
ในขอบเขตของการจัดการโครงการ การทำความเข้าใจและการจัดการระยะเวลาของงานเป็นสิ่งสำคัญ Aspose.Tasks for Java มอบชุดเครื่องมืออันทรงพลังเพื่อจัดการสิ่งนี้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการดึงข้อมูลระยะเวลางานในหน่วยต่างๆ โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
-  Aspose.Tasks สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้รวมไลบรารี Aspose.Tasks เพิ่มคำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของรหัสของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ Java ใหม่ใน Integrated Development Environment (IDE) ที่คุณต้องการ ตรวจสอบให้แน่ใจว่าได้รวมไลบรารี Aspose.Tasks ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: อ่านเทมเพลตโครงการ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// อ่านไฟล์เทมเพลต MS Project
String fileName = dataDir + "project.xml";
// อ่านไฟล์อินพุตเป็นโครงการ
Project project = new Project(fileName);
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์โครงการของคุณ
## ขั้นตอนที่ 3: ดึงข้อมูลงาน
```java
// รับงานเพื่อคำนวณระยะเวลาในรูปแบบต่างๆ
Task task = project.getRootTask().getChildren().getById(1);
```
 ที่นี่ เราได้รับงานจากโครงการ ปรับ`getById(1)` ตามรหัสงานของโครงการของคุณ
## ขั้นตอนที่ 4: ระยะเวลาเป็นนาที
```java
// รับระยะเวลาเป็นนาที
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
ขั้นตอนนี้จะคำนวณระยะเวลาของงานเป็นนาที
## ขั้นตอนที่ 5: ระยะเวลาเป็นวัน
```java
// รับระยะเวลาเป็นวัน
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
ขั้นตอนนี้จะคำนวณระยะเวลาของงานเป็นวัน
## ขั้นตอนที่ 6: ระยะเวลาเป็นชั่วโมง
```java
// รับระยะเวลาเป็นชั่วโมง
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
ขั้นตอนนี้จะคำนวณระยะเวลาของงานเป็นชั่วโมง
## ขั้นตอนที่ 7: ระยะเวลาเป็นสัปดาห์
```java
// รับระยะเวลาเป็นสัปดาห์
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
ขั้นตอนนี้จะคำนวณระยะเวลาของงานเป็นสัปดาห์
## ขั้นตอนที่ 8: ระยะเวลาเป็นเดือน
```java
// รับระยะเวลาเป็นเดือน
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
ขั้นตอนนี้จะคำนวณระยะเวลาของงานเป็นเดือน
## บทสรุป
การจัดการระยะเวลาของงานทำได้ง่ายด้วย Aspose.Tasks สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยให้ความชัดเจนในหน่วยเวลาต่างๆ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับ Java IDE ใดๆ ได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java Integrated Development Environment (IDE)
### ถาม: ฉันจะรับ ID ของงานในไฟล์ Microsoft Project ได้อย่างไร
คุณสามารถตรวจสอบไฟล์โปรเจ็กต์หรือใช้ Aspose.Tasks API เพื่อดึงรหัสงานโดยทางโปรแกรม
### ถาม: Aspose.Tasks เหมาะสำหรับการจัดการโครงการขนาดใหญ่หรือไม่
อย่างแน่นอน. Aspose.Tasks ได้รับการออกแบบมาเพื่อจัดการโครงการที่มีขนาดแตกต่างกันได้อย่างมีประสิทธิภาพ
### ถาม: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/tasks/java/)เพื่อทรัพยากรที่ครอบคลุม
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถสำรวจได้[ทดลองฟรี](https://releases.aspose.com/) เพื่อประเมินความสามารถของตน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
