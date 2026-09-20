---
date: 2026-09-20
description: เรียนรู้วิธีจัดการการขึ้นต่อกันของงานโครงการโดยใช้ Aspose.Tasks for Java
  คู่มือนี้จะแสดงวิธีเพิ่ม predecessor links, พิมพ์ task names, และตั้งค่า task dependencies
  อย่างมีประสิทธิภาพ
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: จัดการการขึ้นต่อกันของงานโครงการผ่าน Aspose.Tasks for Java
og_description: เรียนรู้วิธีจัดการการขึ้นต่อกันของงานโครงการโดยใช้ Aspose.Tasks for
  Java คู่มือนี้จะแสดงวิธีเพิ่ม predecessor links, พิมพ์ task names, และตั้งค่า task
  dependencies อย่างมีประสิทธิภาพ
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: จัดการการขึ้นต่อกันของงานโครงการผ่าน Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: จัดการการขึ้นต่อกันของงานโครงการผ่าน Aspose.Tasks for Java
url: /th/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการการขึ้นต่อกันของงานโครงการผ่าน Aspose.Tasks สำหรับ Java

## บทนำ
การขึ้นต่อกันของงานโครงการเป็นโครงกระดูกของกำหนดการที่เป็นจริงใด ๆ ทำให้คุณสามารถจำลองว่าการทำงานใดต้องเสร็จสิ้นก่อนที่งานอื่นจะเริ่มได้ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีจัดการ **project task dependencies** ด้วย Aspose.Tasks สำหรับ Java รวมถึงวิธีเพิ่มลิงก์ผู้ก่อนหน้า, พิมพ์ชื่องาน, และตั้งค่าการขึ้นต่อกันของงานโดยใช้โปรแกรม

## คำตอบอย่างรวดเร็ว
- **ขั้นตอนแรกคืออะไร?** โหลดไฟล์ MPP ของคุณเข้าสู่วัตถุ `Project`.  
- **คุณจะเพิ่มผู้ก่อนหน้าอย่างไร?** Create a `TaskLink` and set its `PredecessorTaskUid` and `SuccessorTaskUid`.  
- **คุณสามารถแสดงรายการลิงก์ทั้งหมดได้หรือไม่?** Use `project.getTaskLinks()` and iterate over the collection.  
- **ฉันต้องการใบอนุญาตหรือไม่?** A temporary license works for evaluation; a full license is required for production.  
- **รองรับเวอร์ชัน Java ใด?** Java 8 or higher.

## การขึ้นต่อกันของงานโครงการคืออะไร?
การขึ้นต่อกันของงานโครงการกำหนดความสัมพันธ์เชิงตรรกะระหว่างสองงาน เช่น Finish‑to‑Start หรือ Start‑to‑Start และกำหนดลำดับที่งานต้องทำ การสร้างลิงก์เหล่านี้ทำให้กำหนดการอัตโนมัติเคารพข้อจำกัดในโลกจริง ป้องกันกิจกรรมที่ทับซ้อน และทำให้แน่ใจว่างานต่อไปจะเริ่มก็ต่อเมื่อเงื่อนไขเบื้องต้นของมันครบถ้วน

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
Aspose.Tasks สำหรับ Java รองรับรูปแบบไฟล์โครงการมากกว่าสามสิบรูปแบบ รวมถึงเวอร์ชันล่าสุดของ Microsoft Project และสามารถประมวลผลไฟล์ขนาดถึงสองกิกะไบต์โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ความสามารถประสิทธิภาพสูงนี้ทำให้คุณสามารถจัดการกำหนดการขนาดใหญ่ สร้างรายงาน และทำการอัปเดตเป็นกลุ่มได้อย่างมีประสิทธิภาพ ทำให้เป็นโซลูชันที่เหมาะสำหรับการจัดการโครงการระดับองค์กร

## ข้อกำหนดเบื้องต้น
- สภาพแวดล้อมการพัฒนา Java: Java 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): Eclipse, IntelliJ IDEA หรือ IDE ที่รองรับ Java ใด ๆ ที่คุณต้องการ.

## นำเข้าแพ็กเกจ
คุณต้องนำเข้าคลาสหลักที่ทำให้สามารถจัดการโครงการได้

คลาส `Project` เป็นจุดเริ่มต้นสำหรับการโหลดและบันทึกไฟล์ Microsoft Project.  
คลาส `TaskLink` แสดงถึงการขึ้นต่อกันระหว่างสองงาน.

## วิธีเพิ่มลิงก์ผู้ก่อนหน้าระหว่างสองงาน?
สร้างอินสแตนซ์ของ `TaskLink` กำหนด UID ของงานผู้ก่อนหน้าและ UID ของงานผู้ตามเลือก `TaskLinkType` ที่เหมาะสม เช่น Finish‑to‑Start แล้วเพิ่มลิงก์ไปยังคอลเลกชันลิงก์งานของโครงการ เมื่อเพิ่มแล้วกำหนดการจะสะท้อนความสัมพันธ์การขึ้นต่อกันใหม่โดยทันที.

### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจกต์โปรเจกต์
สร้างอินสแตนซ์ใหม่ของคลาส `Project` และระบุพาธไปยังไฟล์โครงการของคุณ (เช่น `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### ขั้นตอนที่ 2: เข้าถึงลิงก์งาน
ดึงลิงก์งานทั้งหมดจากโครงการโดยใช้เมธอด `getTaskLinks()`.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: วนลูปผ่านลิงก์งาน
ใช้ลูปเพื่อวนผ่านแต่ละลิงก์งานในคอลเลกชันและพิมพ์ข้อมูลเกี่ยวกับงานผู้ก่อนหน้าและผู้ตาม.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### ขั้นตอนที่ 4: เพิ่มลิงก์ผู้ก่อนหน้าใหม่ (ไม่บังคับ)
หากคุณต้องการสร้างการขึ้นต่อกันใหม่ ให้สร้างอินสแตนซ์ของ `TaskLink` ตั้งค่า `PredecessorTaskUid`, `SuccessorTaskUid` และ `LinkType` แล้วเพิ่มลงในคอลเลกชันลิงก์ของโครงการ.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

ทำซ้ำขั้นตอนเหล่านี้ตามความต้องการของโครงการของคุณ.

## ปัญหาทั่วไปและวิธีแก้
- **ไม่มีผู้ก่อนหน้าหลังจากเพิ่มลิงก์** – Ensure you call `project.updateTaskLinks()` (or save and reload) so the internal graph refreshes.  
- **ประสิทธิภาพช้าลงเมื่อไฟล์ขนาดใหญ่** – Use `project.setReadOnly(true)` before bulk operations to reduce memory overhead.  
- **ประเภทลิงก์ไม่ถูกต้อง** – Verify that you use the correct `TaskLinkType` enum value (e.g., `FinishToStart`) to match your schedule logic.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java ในโครงการ Java ที่มีอยู่ของฉันได้หรือไม่?**  
A: ใช่ เพียงแค่เพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath หรือ dependencies ของ Maven/Gradle.

**Q: Aspose.Tasks รองรับรูปแบบไฟล์โครงการต่าง ๆ หรือไม่?**  
A: ใช่ รองรับ MPP, XML, CSV และรูปแบบเพิ่มเติมกว่า 30 รูปแบบ.

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: รับใบอนุญาตชั่วคราวจาก [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน?**  
A: เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนจากชุมชนและการสนทนา.

**Q: ฉันสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
A: ใช่ ดาวน์โหลดรุ่นทดลองฟรีจาก [Aspose free trial page](https://releases.aspose.com/).

---

**อัปเดตล่าสุด:** 2026-09-20  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างการขึ้นต่อกันของงานการจัดการโครงการใน Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [ตั้งค่าวันเริ่มต้นของโครงการและจัดการงานพาเรนท์และชิลด์ใน Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [อ่านและตั้งค่าลำดับความสำคัญของงานด้วย Aspose.Tasks สำหรับ Java](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}