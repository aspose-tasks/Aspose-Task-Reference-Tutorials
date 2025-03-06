---
title: จัดการระยะเวลาของงานใน Aspose.Tasks
linktitle: จัดการระยะเวลาของงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจ Aspose.Tasks สำหรับ Java และเรียนรู้การจัดการระยะเวลาของงานได้อย่างง่ายดาย ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการวางแผนและการดำเนินโครงการอย่างมีประสิทธิภาพ
weight: 20
url: /th/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการระยะเวลาของงานใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks for Java มอบโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานโปรเจ็กต์และระยะเวลาอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการระยะเวลาของงานโดยใช้ Aspose.Tasks ซึ่งจะแนะนำคุณตลอดแต่ละขั้นตอน ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คู่มือนี้จะช่วยให้คุณเข้าใจถึงสิ่งสำคัญในการทำงานกับระยะเวลาของงานในโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://www.oracle.com/java/technologies/javase-downloads.html).
- ไลบรารี Aspose.Tasks: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks ในโปรเจ็กต์ของคุณ คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
```java
// สร้างโครงการใหม่
Project project = new Project();
```
## ขั้นตอนที่ 2: เพิ่มงานใหม่
```java
// เพิ่มงานใหม่ให้กับโครงการ
Task task = project.getRootTask().getChildren().add("Task");
```
## ขั้นตอนที่ 3: รับและแปลงระยะเวลางาน
```java
// รับระยะเวลางานเป็นวัน (หน่วยเวลาเริ่มต้น)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// แปลงระยะเวลาเป็นหน่วยเวลาชั่วโมง
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## ขั้นตอนที่ 4: อัปเดตระยะเวลางานเป็น 1 สัปดาห์
```java
// เพิ่มระยะเวลางานเป็น 1 สัปดาห์
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## ขั้นตอนที่ 5: ลดระยะเวลางาน
```java
// ลดระยะเวลาของงาน
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการระยะเวลาของงานในโปรเจ็กต์ Aspose.Tasks สำหรับ Java ของคุณได้สำเร็จ
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการจัดการระยะเวลางานโดยใช้ Aspose.Tasks สำหรับ Java ตอนนี้คุณสามารถนำเทคนิคเหล่านี้ไปใช้ในโครงการของคุณได้อย่างมั่นใจ เพื่อการจัดการระยะเวลาของงานที่มีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ Java เวอร์ชันทั้งหมดหรือไม่
Aspose.Tasks เข้ากันได้กับ Java 6 และเวอร์ชันที่ใหม่กว่า
### ฉันสามารถใช้ Aspose.Tasks สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 ได้ คุณสามารถใช้ Aspose.Tasks สำหรับทั้งโปรเจ็กต์ส่วนตัวและเชิงพาณิชย์ เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) สำหรับรายละเอียดใบอนุญาต
### ฉันจะหาการสนับสนุนและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล
### Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจ Aspose.Task ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
