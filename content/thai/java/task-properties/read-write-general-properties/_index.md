---
title: การเรียนรู้คุณสมบัติของงานใน Aspose.Tasks
linktitle: อ่านและเขียนคุณสมบัติทั่วไปของงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจพลังของ Aspose.Tasks สำหรับ Java ในการจัดการคุณสมบัติงานได้อย่างง่ายดาย อ่านและเขียนอย่างง่ายดายโดยใช้คำแนะนำทีละขั้นตอนของเรา
type: docs
weight: 26
url: /th/java/task-properties/read-write-general-properties/
---
## การแนะนำ
ปลดล็อกศักยภาพสูงสุดของการจัดการงานใน Java ด้วย Aspose.Tasks ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกเกี่ยวกับการอ่านและการเขียนคุณสมบัติทั่วไปของงานโดยใช้ Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ บทช่วยสอนนี้จะช่วยให้คุณมีทักษะในการจัดการคุณสมบัติของงานได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Tasks สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่า คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/tasks/java/).
- โปรแกรมแก้ไขโค้ดเช่น IntelliJ IDEA หรือ Eclipse
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงฟังก์ชัน Aspose.Tasks ได้ นี่เป็นตัวอย่างเพื่อแนะนำคุณ:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## การอ่านคุณสมบัติทั่วไปของงาน
## ขั้นตอนที่ 1: สร้างงาน
เริ่มต้นด้วยการสร้างงานในโครงการของคุณ ซึ่งเกี่ยวข้องกับการตั้งชื่องาน วันที่เริ่มต้น และรายละเอียดอื่นๆ ที่เกี่ยวข้อง นี่คือตัวอย่าง:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## ขั้นตอนที่ 2: อ่านคุณสมบัติของงาน
ตอนนี้คุณได้สร้างงานแล้ว มาเรียกดูและแสดงคุณสมบัติทั่วไปของงานกันดีกว่า ข้อมูลโค้ดต่อไปนี้ทำให้สิ่งนี้สำเร็จ:
```java
// การอ่านคุณสมบัติทั่วไปของงาน
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## การเขียนคุณสมบัติทั่วไปของงาน
## ขั้นตอนที่ 3: โหลดโปรเจ็กต์และสร้าง Collector
 หากต้องการเขียนคุณสมบัติทั่วไป ให้โหลดโปรเจ็กต์ที่มีอยู่แล้วตั้งค่า`ChildTasksCollector`: :
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## ขั้นตอนที่ 4: แยกวิเคราะห์และแสดงคุณสมบัติ
สุดท้าย แยกวิเคราะห์งานที่รวบรวมและแสดงคุณสมบัติ:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
ยินดีด้วย! คุณได้อ่านและเขียนคุณสมบัติทั่วไปของงานโดยใช้ Aspose.Tasks สำหรับ Java สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจขั้นตอนพื้นฐานในการจัดการคุณสมบัติของงานอย่างราบรื่นด้วย Aspose.Tasks สำหรับ Java เมื่อเชี่ยวชาญเทคนิคเหล่านี้ คุณจะยกระดับทักษะการพัฒนา Java และปรับปรุงการจัดการงานในโครงการของคุณได้
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Tasks เข้ากันได้กับ Java 11 และเวอร์ชันที่ใหม่กว่า
### ฉันสามารถใช้ Aspose.Tasks สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 อย่างแน่นอน! Aspose.Tasks เป็นเครื่องมืออันทรงพลังสำหรับทั้งโครงการส่วนตัวและเชิงพาณิชย์ เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) เพื่อสำรวจตัวเลือกการออกใบอนุญาต
### ฉันจะรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล
### ฉันจะหาการสนับสนุนชุมชนสำหรับ Aspose.Tasks ได้ที่ไหน
 เข้าร่วมการอภิปรายชุมชนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือและความร่วมมือ
### มีโครงการตัวอย่างสำหรับการอ้างอิงหรือไม่?
 สำรวจส่วนตัวอย่างของเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/) สำหรับโปรเจ็กต์ตัวอย่างและข้อมูลโค้ด