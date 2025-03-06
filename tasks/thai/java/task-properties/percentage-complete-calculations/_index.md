---
title: เปอร์เซ็นต์การคำนวณที่สมบูรณ์สำหรับงานใน Aspose.Tasks
linktitle: เปอร์เซ็นต์การคำนวณที่สมบูรณ์สำหรับงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจ Aspose.Tasks สำหรับ Java และปรับปรุงการติดตามความคืบหน้าของโครงการ คำนวณเปอร์เซ็นต์งานอย่างง่ายดายเพื่อการจัดการโครงการที่มีประสิทธิภาพ
weight: 25
url: /th/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปอร์เซ็นต์การคำนวณที่สมบูรณ์สำหรับงานใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำเชิงลึกของเราเกี่ยวกับการเรียนรู้การคำนวณเปอร์เซ็นต์งานโดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งออกแบบมาเพื่อทำงานกับไฟล์ Microsoft Project โดยนำเสนอชุดคุณสมบัติที่แข็งแกร่งสำหรับการจัดการโครงการ ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่การคำนวณเปอร์เซ็นต์ที่สมบูรณ์ เพื่อให้คุณมีความรู้ในการติดตามและวิเคราะห์ความคืบหน้าของโครงการอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
-  ไลบรารี Aspose.Tasks: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จาก[ลิงค์นี้](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Aspose.Tasks สำหรับ Java ของคุณ รวมข้อมูลโค้ดต่อไปนี้ในโครงการของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
ตอนนี้เรามาแจกแจงแต่ละขั้นตอนพร้อมคำอธิบายโดยละเอียด
## ขั้นตอนที่ 1: การนำเข้าแพ็คเกจ
ในขั้นตอนแรก เราจะนำเข้าแพ็คเกจที่จำเป็นเพื่อตั้งค่าโปรเจ็กต์ Aspose.Tasks ของเรา
## ขั้นตอนที่ 2: การตั้งค่าไดเรกทอรีเอกสาร
 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณโดยใช้ไฟล์`dataDir`ตัวแปร. ตรวจสอบให้แน่ใจว่าไฟล์ Microsoft Project ของคุณ เช่น "Software Development.mpp" อยู่ในไดเรกทอรีนี้
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 3: กำลังโหลดโครงการ
 เริ่มต้นใหม่`Project` วัตถุและโหลดไฟล์ Microsoft Project ของคุณลงในอินสแตนซ์ของโครงการ
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## ขั้นตอนที่ 4: การดึงชุดงาน
 รับงานรูทของโปรเจ็กต์และดึงรายการย่อยของโปรเจ็กต์เป็นคอลเล็กชันที่ใช้`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## ขั้นตอนที่ 5: เปอร์เซ็นต์การพิมพ์เสร็จสมบูรณ์
วนซ้ำแต่ละงานในคอลเลกชันและพิมพ์เปอร์เซ็นต์ที่เสร็จสมบูรณ์ เปอร์เซ็นต์งานเสร็จสมบูรณ์ และเปอร์เซ็นต์ทางกายภาพที่เสร็จสมบูรณ์
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับแต่ละงานในโครงการของคุณเพื่อรับข้อมูลเชิงลึกเกี่ยวกับความคืบหน้าของแต่ละงาน
## บทสรุป
ยินดีด้วย! คุณเชี่ยวชาญการคำนวณเปอร์เซ็นต์งานโดยใช้ Aspose.Tasks สำหรับ Java ได้สำเร็จ ไลบรารีอันทรงพลังนี้ช่วยให้นักพัฒนาสามารถจัดการและวิเคราะห์ความคืบหน้าของโครงการได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารประกอบ Aspose.Tasks ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: ฉันจะดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/tasks/java/).
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันจะได้รับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
