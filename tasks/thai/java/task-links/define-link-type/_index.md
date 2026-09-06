---
date: 2026-08-29
description: เรียนรู้วิธีตั้งค่า link types และจัดการ task dependencies ด้วย Aspose.Tasks
  for Java ในบทแนะนำแบบ step‑by‑step
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: วิธีตั้งค่า Link Types ใน Aspose.Tasks for Java
og_description: เรียนรู้วิธีตั้งค่า link types และจัดการ task dependencies ด้วย Aspose.Tasks
  for Java. คู่มือแบบ step‑by‑step สำหรับนักพัฒนา
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: วิธีตั้งค่า link types ใน Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: วิธีตั้งค่า Link Types ใน Aspose.Tasks for Java
url: /th/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่าประเภทลิงก์ใน Aspose.Tasks สำหรับ Java

## บทนำ
หากคุณกำลังสงสัย **วิธีตั้งค่าลิงก์** ระหว่างงานขณะคุณ *จัดการการพึ่งพางาน* ในโครงการ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนการสร้างโครงการใหม่ เพิ่มงาน และกำหนดประเภทลิงก์ (Start‑to‑Start, Finish‑to‑Start เป็นต้น) โดยใช้ Aspose.Tasks สำหรับ Java เมื่อเสร็จแล้วคุณจะมั่นใจในการปรับแต่งความสัมพันธ์ของงานให้ตรงกับความต้องการการวางแผนในโลกจริงและคุณจะเห็นว่า API จัดการแผนขนาดใหญ่ที่มีงานสูงสุดถึง 10,000 งานได้อย่างไร

## คำตอบสั้น
- **คลาสใดที่เป็นตัวแทนของการพึ่งพา?** `TaskLink` คืออ็อบเจกต์หลักที่จำลองลิงก์ระหว่างงานสองงาน.  
- **enum ใดกำหนดประเภทความสัมพันธ์?** `TaskLinkType` (เช่น `StartToStart`, `FinishToStart`).  
- **ฉันสามารถอ่านประเภทลิงก์ที่มีอยู่ได้หรือไม่?** ได้ – ทำการวน `Project.getTaskLinks()` และเรียก `getLinkType()`.  
- **ฉันต้องใช้ไลเซนส์สำหรับโค้ดนี้หรือไม่?** ไลเซนส์ชั่วคราวทำงานสำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการผลิต.  
- **นี่เข้ากันได้กับ Java 8+ หรือไม่?** แน่นอน – Aspose.Tasks รองรับ Java 8 ถึง Java 21, ครอบคลุม 13 รุ่นหลัก.

## ลิงก์งานคืออะไร
**ลิงก์งาน** จำลองการพึ่งพาระหว่างงานสองงานในกำหนดการของโครงการ.  
คุณสามารถสร้าง, แก้ไข หรือ ลบ `TaskLink` เพื่อสะท้อนความสัมพันธ์ของงานก่อนหน้า‑งานต่อไป, ทำให้ตัวจัดตารางคำนวณวันที่เริ่มและสิ้นสุดโดยอัตโนมัติ.

## ทำไมต้องใช้ประเภทลิงก์ของ Aspose.Tasks?
Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 30 แบบ** และสามารถประมวลผลโครงการที่มี **งานสูงสุดถึง 10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ความสามารถที่วัดได้นี้รับประกันประสิทธิภาพที่เร็วแม้สำหรับแผนระดับองค์กร, และไลบรารียังคงรักษาฟีเจอร์ทั้งหมดของ Microsoft Project เช่น ฟิลด์กำหนดเองและการมอบหมายทรัพยากร.

## ข้อกำหนดเบื้องต้น
- **Java Development Environment** – JDK 8 หรือใหม่กว่า ติดตั้งและกำหนดค่าแล้ว.  
- **Aspose.Tasks Library** – ดาวน์โหลด JAR ล่าสุดจาก [download link](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – สร้างโฟลเดอร์บนเครื่องของคุณเพื่อเก็บไฟล์ตัวอย่างของโครงการ.

## นำเข้าแพ็กเกจ
เราเริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นของ Aspose.Tasks. สิ่งนี้เตรียม IDE ให้รับรู้การเรียกใช้ API ที่เราจะใช้ต่อไป.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## วิธีตั้งค่าประเภทลิงก์ใน Aspose.Tasks สำหรับ Java?
โหลดอินสแตนซ์ `Project` ใหม่, เพิ่มงานสองงาน, แล้วสร้าง `TaskLink` ด้วย `TaskLinkType` ที่ต้องการ. รูปแบบสองขั้นตอนนี้ทำให้คุณกำหนดประเภทการพึ่งพามาตรฐานสี่ประเภทใดก็ได้ในหนึ่งการเรียก. `Project` แทนไฟล์โครงการทั้งหมดและกำหนดการของมัน. `Task` คือรายการงานแต่ละรายการภายในโครงการ. `TaskLink` เชื่อมต่องานก่อนหน้ากับงานต่อไป. `TaskLinkType` เป็น enumeration ที่ระบุความสัมพันธ์ (Start‑to‑Start, Finish‑to‑Start, เป็นต้น).

### ขั้นตอนที่ 1: ตั้งค่าประเภทลิงก์
`TaskLink` แสดงถึงการพึ่งพารหว่างงานสองงาน, ในขณะที่ `TaskLinkType` แสดงประเภทความสัมพันธ์ที่เป็นไปได้เช่น `StartToStart`. ในขั้นตอนนี้เราจะสร้างโครงการใหม่, เพิ่มงานสองงาน, และเชื่อมต่อพวกมันโดยใช้ความสัมพันธ์ **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **เคล็ดลับ:** คุณสามารถแทนที่ `StartToStart` ด้วย `FinishToStart`, `StartToFinish`, หรือ `FinishToFinish` ขึ้นอยู่กับการพึ่งพาที่คุณต้องการ **จัดการการพึ่งพางาน**.

### ขั้นตอนที่ 2: ดึงประเภทลิงก์
`Project.getTaskLinks()` คืนค่าคอลเลกชันของอ็อบเจกต์ `TaskLink` ทั้งหมดในกำหนดการ. โดยการวนคอลเลกชันนี้คุณสามารถอ่าน `TaskLinkType` ของแต่ละลิงก์และตรวจสอบว่าความสัมพันธ์ที่ถูกต้องได้ถูกบันทึกไว้หรือไม่.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

คอนโซลจะพิมพ์ค่าต่าง ๆ เช่น `StartToStart`, `FinishToStart` เป็นต้น, ยืนยันประเภทลิงก์ที่คุณตั้งค่าไว้ก่อนหน้านี้.

## ปัญหาทั่วไปและวิธีแก้
- **NullPointerException เมื่อเพิ่มลิงก์** – ตรวจสอบให้แน่ใจว่าทั้งงานก่อนหน้าและงานต่อไปถูกเพิ่มลงในโครงการก่อนสร้าง `TaskLink`.  
- **ประเภทลิงก์ไม่ถูกต้องหลังการบันทึก** – เรียก `project.save("output.mpp")` เสมอ (หรือรูปแบบที่รองรับอื่น) หลังจากตั้งค่าประเภทลิงก์เพื่อบันทึกการเปลี่ยนแปลง.  
- **ไม่พบไลเซนส์** – วางไฟล์ไลเซนส์ Aspose.Tasks ของคุณใน classpath ของโครงการและโหลดด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## คำถามที่พบบ่อย

**Q: Aspose.Tasks เข้ากันได้กับสภาพแวดล้อม Java ต่าง ๆ หรือไม่?**  
A: ใช่, Aspose.Tasks ผสานรวมกับ Java SE มาตรฐาน, Java EE, และชุดพัฒนา Android โดยไม่มีการพึ่งพาเพิ่มเติม.

**Q: ฉันสามารถปรับแต่งประเภทลิงก์ตามความต้องการของโครงการได้หรือไม่?**  
A: แน่นอน. enum `TaskLinkType` ให้สี่ประเภทมาตรฐาน, และคุณสามารถรวมกับค่าความล่าช้าเพื่อจำลองตารางเวลาที่ซับซ้อนได้.

**Q: ฉันจะหาเอกสารรายละเอียดของ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
A: ดูที่ [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) สำหรับคำแนะนำเชิงลึก, การอ้างอิง API, และตัวอย่างโค้ด.

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: เยี่ยมชม [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อรับไลเซนส์ชั่วคราวสำหรับการทดสอบ.

**Q: ฉันจะรับการสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.Tasks ได้จากที่ไหน?**  
A: เข้าร่วมชุมชน Aspose.Tasks ใน [support forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือและการสนทนา.

**Q: ฉันสามารถเปลี่ยนประเภทลิงก์หลังจากบันทึกโครงการได้หรือไม่?**  
A: ได้. โหลดโครงการ, ดึง `TaskLink`, เรียก `setLinkType()` ด้วยค่า enum ใหม่, แล้วบันทึกโครงการอีกครั้ง.

**Q: Aspose.Tasks รองรับการอ่านไฟล์ Microsoft Project (MPP) หรือไม่?**  
A: รองรับ. ใช้ `new Project("file.mpp")` เพื่อโหลดไฟล์ MPP และทำงานกับลิงก์งานของมันเช่นเดียวกับตัวอย่าง XML ด้านบน.

---

**อัปเดตล่าสุด:** 2026-08-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างลิงก์งานข้ามโครงการใน Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [ตั้งค่าวันเริ่มต้นโครงการและจัดการงานพาเรนท์และชิลด์ใน Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [โหลดไฟล์ MPP ด้วย Java - จัดการคุณสมบัติโครงการด้วย Aspose.Tasks](/tasks/java/project-management/default-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}