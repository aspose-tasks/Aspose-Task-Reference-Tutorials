---
title: กำหนดประเภทลิงก์ใน Aspose.Tasks
linktitle: กำหนดประเภทลิงก์ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจพลังของ Aspose.Tasks สำหรับ Java ในการจัดการโครงการ กำหนดและปรับแต่งประเภทลิงก์ได้อย่างง่ายดายด้วยบทช่วยสอนทีละขั้นตอนของเรา
weight: 13
url: /th/java/task-links/define-link-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดประเภทลิงก์ใน Aspose.Tasks

## การแนะนำ
ยินดีต้อนรับสู่โลกแห่งการจัดการโครงการที่มีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java! หากคุณกำลังมองหาความคล่องตัวในการจัดการโครงการและเพิ่มประสิทธิภาพการทำงาน คุณมาถูกที่แล้ว ในบทช่วยสอนที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการกำหนดประเภทลิงก์ใน Aspose.Tasks สำหรับ Java ซึ่งจะช่วยเพิ่มความสามารถในการจัดการโปรเจ็กต์ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้ติดตั้งอยู่บนระบบของคุณ
-  ไลบรารี Aspose.Tasks: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/).
- ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีที่คุณจะจัดเก็บเอกสารโครงการของคุณ
## แพ็คเกจนำเข้า
ในขั้นตอนนี้ เราจะนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นโครงการของเรา สิ่งนี้ทำให้แน่ใจได้ว่าสภาพแวดล้อม Java ของคุณพร้อมที่จะรวมฟังก์ชันการทำงานของ Aspose.Tasks ได้อย่างราบรื่น
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```
## กำหนดประเภทลิงก์ใน Aspose.Tasks
ตอนนี้ มาดูฟังก์ชันหลักกัน - การกำหนดประเภทลิงก์ใน Aspose.Tasks สำหรับ Java
## ขั้นตอนที่ 1: การตั้งค่าประเภทลิงก์
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```
ในขั้นตอนนี้ เราสร้างโปรเจ็กต์ใหม่ เพิ่มงานสองรายการ และสร้างลิงก์ระหว่างงานเหล่านั้นด้วยประเภทลิงก์ที่ระบุ (ในกรณีนี้คือ เริ่มถึงเริ่ม)
## ขั้นตอนที่ 2: รับประเภทลิงก์
```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```
ที่นี่ เราโหลดโปรเจ็กต์ที่มีอยู่จากไฟล์ XML และวนซ้ำผ่านลิงก์งานทั้งหมด โดยพิมพ์ประเภทลิงก์ตามลำดับ
ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะกำหนดและเรียกข้อมูลประเภทลิงก์สำหรับงานในโปรเจ็กต์ Aspose.Tasks for Java ได้สำเร็จ
## บทสรุป
ยินดีด้วย! ตอนนี้คุณเชี่ยวชาญศิลปะในการกำหนดประเภทลิงก์ใน Aspose.Tasks สำหรับ Java แล้ว เครื่องมืออันทรงพลังนี้เปิดโอกาสใหม่สำหรับการจัดการโครงการอย่างมีประสิทธิภาพ ทดลองใช้ลิงก์ประเภทต่างๆ เพื่อปรับแต่งเวิร์กโฟลว์โปรเจ็กต์ของคุณให้สมบูรณ์แบบ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับสภาพแวดล้อม Java ที่แตกต่างกันหรือไม่
ตอบ: ใช่ Aspose.Tasks ได้รับการออกแบบมาเพื่อผสานรวมกับสภาพแวดล้อมการพัฒนา Java ต่างๆ ได้อย่างราบรื่น
### ถาม: ฉันสามารถปรับแต่งประเภทลิงก์ตามความต้องการของโปรเจ็กต์ของฉันได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks มอบความยืดหยุ่น ช่วยให้คุณสามารถกำหนดและปรับแต่งประเภทลิงก์ให้เหมาะกับความต้องการของโปรเจ็กต์ของคุณ
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Tasks for Java ได้ที่ไหน
 ตอบ: โปรดดูที่[Aspose.Tasks สำหรับเอกสาร Java](https://reference.aspose.com/tasks/java/) สำหรับคำแนะนำเชิงลึก
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: เยี่ยมชม[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวเพื่อการทดสอบ
### ถาม: ฉันจะรับการสนับสนุนสำหรับการสืบค้นที่เกี่ยวข้องกับ Aspose.Tasks ได้ที่ไหน
 ตอบ: เข้าร่วมชุมชน Aspose.Tasks บน[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/tasks/15) เพื่อขอความช่วยเหลือและหารือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
