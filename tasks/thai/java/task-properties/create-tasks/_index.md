---
title: สร้างงานใน Aspose.Tasks
linktitle: สร้างงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: จัดการโปรเจ็กต์ Java ได้อย่างง่ายดายด้วย Aspose.Tasks สร้างงาน งานย่อย และอื่นๆ ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการโครงการที่ราบรื่น
weight: 13
url: /th/java/task-properties/create-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างงานใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่โลกของ Aspose.Tasks สำหรับ Java! หากคุณกำลังมองหาการจัดการงานและโครงการในแอปพลิเคชัน Java ของคุณอย่างมีประสิทธิภาพ คุณมาถูกที่แล้ว ในคู่มือที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างงานโดยใช้ Aspose.Tasks สำหรับ Java โดยแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่าได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว
-  Aspose.Tasks สำหรับ Java Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE ที่เป็นมิตรกับ Java เช่น Eclipse หรือ IntelliJ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มทำงานกับ Aspose.Tasks เพิ่มบรรทัดต่อไปนี้ที่ด้านบนของไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างโครงการใหม่
```java
// สร้างโครงการใหม่
Project project = new Project(dataDir + "project.mpp");
```
## ขั้นตอนที่ 3: เพิ่มงานสรุป
```java
// เพิ่มงานสรุป
Task task = project.getRootTask().getChildren().add("Summary1");
```
## ขั้นตอนที่ 4: เพิ่มงานย่อย
```java
// เพิ่มงานย่อยภายใต้งานสรุป
Task subtask = task.getChildren().add("Subtask1");
```
เพิ่มงานและงานย่อยต่อไปตามจำนวนที่จำเป็นสำหรับโครงการของคุณ แต่ละขั้นตอนมีส่วนช่วยในการสร้างลำดับชั้นของโครงการที่มีโครงสร้าง
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อสร้างงานและจัดการโครงการเรียบร้อยแล้ว ความยืดหยุ่นและความเรียบง่ายของ Aspose.Tasks ทำให้เป็นเครื่องมืออันทรงพลังสำหรับนักพัฒนา Java
## คำถามที่พบบ่อย
### Aspose.Tasks เหมาะสำหรับโครงการขนาดเล็กหรือไม่?
อย่างแน่นอน! Aspose.Tasks มีความหลากหลายและสามารถใช้กับโครงการทุกขนาดได้
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 เยี่ยม[ลิงค์นี้](https://purchase.aspose.com/temporary-license/)เพื่อขอใบอนุญาตชั่วคราว
### ฉันสามารถปรับแต่งคุณลักษณะของงานโดยใช้ Aspose.Tasks ได้หรือไม่
ใช่ คุณสามารถปรับแต่งคุณลักษณะของงานได้อย่างกว้างขวางเพื่อให้เหมาะกับความต้องการของโครงการของคุณ
### มีชุมชนสนับสนุนสำหรับผู้ใช้ Aspose.Tasks หรือไม่?
 อย่างแน่นอน! เข้าร่วมชุมชน Aspose.Tasks บน[ฟอรัมสนับสนุน](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
