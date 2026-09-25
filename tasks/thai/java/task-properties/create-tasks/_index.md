---
date: 2026-09-25
description: เรียนรู้วิธีสร้างกำหนดการโครงการใน Java ด้วย Aspose.Tasks คู่มือนี้จะแสดงวิธีเพิ่ม
  summary tasks, จัดการ project hierarchy, และตั้งค่า document directory อย่างมีประสิทธิภาพ
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: สร้าง Tasks ใน Aspose.Tasks
og_description: เรียนรู้วิธีสร้างกำหนดการโครงการใน Java ด้วย Aspose.Tasks ปฏิบัติตามคำแนะนำแบบขั้นตอนต่อขั้นตอนเพื่อเพิ่ม
  summary tasks, จัดการ hierarchy, และตั้งค่า document directory
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: วิธีสร้างกำหนดการโครงการด้วย Aspose.Tasks สำหรับ Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: วิธีสร้างกำหนดการโครงการด้วย Aspose.Tasks สำหรับ Java
url: /th/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างกำหนดการโครงการด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้างกำหนดการโครงการ** ในแอปพลิเคชัน Java ด้วย Aspose.Tasks ไม่ว่าคุณจะสร้างรายการทำง่าย ๆ หรือเครื่องมือวางแผนระดับองค์กรที่ซับซ้อน ขั้นตอนต่อไปนี้จะพาคุณผ่านการเพิ่มงานสรุป, การจัดการลำดับชั้นของโครงการ, และการตั้งค่าไดเรกทอรีเอกสาร—ทั้งหมดด้วยโค้ดตัวอย่างที่ชัดเจนและสามารถรันได้ เมื่อเสร็จสิ้นคุณจะมีกำหนดการที่มีโครงสร้างครบถ้วนพร้อมสำหรับการจัดการต่อหรือการส่งออก

## คำตอบอย่างรวดเร็ว
- **Aspose.Tasks จัดการอะไร?** มันจัดการลำดับงาน, ทรัพยากร, ปฏิทิน, และรูปแบบไฟล์โครงการ (MS‑Project, Primavera ฯลฯ).  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** ใบอนุญาตชั่วคราวฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 และใหม่กว่าได้รับการสนับสนุนเต็มรูปแบบ.  
- **ฉันสามารถเพิ่มฟิลด์กำหนดเองให้กับงานได้หรือไม่?** ได้, คุณสามารถขยายงานด้วยฟิลด์ที่ผู้ใช้กำหนดผ่าน API.  
- **มีการสนับสนุน Gantt chart ในตัวหรือไม่?** Aspose.Tasks สามารถส่งออกเป็น PDF/HTML ที่รวมการแสดงผล Gantt.

## อะไรคือกำหนดการโครงการใน Aspose.Tasks?
กำหนดการโครงการคือชุดงาน, ความขึ้นต่อกัน, และไทม์ไลน์ทั้งหมดที่กำหนดวิธีการทำงาน Aspose.Tasks เก็บข้อมูลนี้ในอ็อบเจ็กต์ `Project` ที่คุณสามารถอ่าน, แก้ไข, และบันทึกในรูปแบบต่าง ๆ รวมถึงวันที่เริ่มและสิ้นสุด, ข้อจำกัด, และการมอบหมายทรัพยากร เพื่อการวางแผนและรายงานที่ครอบคลุม

## ทำไมต้องใช้ Aspose.Tasks สำหรับการจัดการโครงการ Java?
Aspose.Tasks รองรับ **รูปแบบเข้าและออกกว่า 30 แบบ** และสามารถประมวลผลโครงการที่มี **งานมากถึง 10,000 งาน** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้ประสิทธิภาพสูงสำหรับสถานการณ์การจัดการโครงการ Java ขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- **Java Development Kit (JDK)** – JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
- **Aspose.Tasks for Java library** – ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – ใช้ Eclipse, IntelliJ IDEA, หรือ IDE ที่รองรับ Java ที่คุณชอบ.

## นำเข้าแพ็กเกจ
`Project`, `Task` และคลาสที่เกี่ยวข้องอยู่ในเนมสเปซ `com.aspose.tasks`. นำเข้าที่ส่วนหัวของไฟล์ Java ของคุณ:

คลาส `Project` แสดงกำหนดการโครงการทั้งหมดและให้เมธอดสำหรับจัดการงานและทรัพยากร.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

คลาส `Project` เป็นจุดเริ่มต้นสำหรับการดำเนินการทั้งหมดบนไฟล์โครงการ.

## วิธีสร้างกำหนดการโครงการด้วย Aspose.Tasks?
โหลดอินสแตนซ์ `Project` ใหม่, ตั้งค่าไดเรกทอรีเอกสาร, และเริ่มเพิ่มงาน. ย่อหน้าตอบโดยตรงนี้อธิบายกระบวนการหลัก: คุณสร้าง `Project`, กำหนดค่า `RootFolder` (ไดเรกทอรีเอกสาร), จากนั้นเพิ่มงานสรุปตามด้วยงานย่อย. การเปลี่ยนแปลงทั้งหมดจะอยู่ในหน่วยความจำจนกว่าคุณจะเรียก `save` เพื่อบันทึกกำหนดการลงไฟล์.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดตำแหน่งที่ไฟล์โครงการที่สร้างจะถูกเขียน. การตั้งค่าไดเรกทอรีตั้งแต่ต้นทำให้การบันทึกต่อไปทั้งหมดใช้เส้นทางเดียวกัน.

คุณสมบัติ `RootFolder` ระบุโฟลเดอร์ฐานที่ไฟล์โครงการจะถูกอ่านหรือเขียน.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### ขั้นตอนที่ 2: สร้างโครงการใหม่
สร้างอ็อบเจ็กต์ `Project` ใหม่ที่จะเก็บกำหนดการของคุณ. คุณสามารถส่งพาธไฟล์ที่มีอยู่แล้วเพื่อโหลดกำหนดการที่มีอยู่สำหรับการแก้ไขได้.

คอนสตรัคเตอร์ `Project` สร้างกำหนดการเปล่าที่พร้อมสำหรับการเพิ่มงาน.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 3: เพิ่มงานสรุป
งานสรุปเป็นการจัดกลุ่มงานย่อยที่เกี่ยวข้องและปรากฏเป็นโหนดที่สามารถยุบ/ขยายในแผนภูมิ Gantt. ใช้คลาส `Task` และตั้งค่า `IsSummary` เป็น `true`.

เมธอด `addTask` สร้างงานใหม่ภายใต้พาเรนต์ที่ระบุและคืนค่า ID ของมัน.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 4: เพิ่มงานย่อย
งานย่อยสืบทอดวันที่เริ่ม/สิ้นสุดจากงานสรุปพาเรนต์ เว้นแต่คุณจะกำหนดทับ. การเพิ่มงานย่อยทำได้ง่ายโดยเรียก `addTask` อีกครั้งและระบุ ID ของพาเรนต์.

การเรียก `addTask` พร้อมกับ ID ของพาเรนต์จะเพิ่มงานย่อยภายใต้งานสรุปนั้น.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

ดำเนินการเพิ่มงานและงานย่อยตามที่ต้องการสำหรับโครงการของคุณ. แต่ละขั้นตอนช่วยสร้างโครงสร้างลำดับชั้นของโครงการที่สามารถส่งออกเป็น MS‑Project, PDF หรือรูปแบบที่รองรับอื่น ๆ.

## ปัญหาทั่วไปและวิธีแก้
- **Problem:** “Document directory not found.”  
  **Solution:** ตรวจสอบว่าพาธที่คุณกำหนดให้ `RootFolder` มีอยู่ในระบบไฟล์และกระบวนการ Java ของคุณมีสิทธิ์เขียน.
- **Problem:** งานย่อยไม่แสดงภายใต้งานสรุป.  
  **Solution:** ตรวจสอบว่าคุณส่ง ID ของงานพาเรนต์ที่ถูกต้องเมื่อเรียก `addTask`. API ต้องการพาเรนต์ ID เป็นอาร์กิวเมนต์ที่สอง.
- **Problem:** โครงการขนาดใหญ่ทำให้เกิด OutOfMemoryError.  
  **Solution:** Aspose.Tasks ประมวลผลงานในโหมดสตรีม; เพิ่มขนาด heap ของ JVM (`-Xmx2g`) หรือแยกกำหนดการเป็นหลายไฟล์.

## คำถามที่พบบ่อย
**Q: Aspose.Tasks เหมาะกับโครงการขนาดเล็กหรือไม่?**  
A: แน่นอน. ไลบรารีสามารถขยายจากรายการงานเดียวจนถึงกำหนดการระดับองค์กรที่มีงานหลายพันรายการ.

**Q: ฉันจะหาเอกสารรายละเอียดของ Aspose.Tasks สำหรับ Java ได้ที่ไหน?**  
A: ดูเอกสารที่ [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks อย่างไร?**  
A: เยี่ยมชม [temporary license request page](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตระยะเวลาจำกัดที่ใช้ได้สำหรับการพัฒนาและทดสอบ.

**Q: ฉันสามารถปรับแต่งแอตทริบิวต์ของงานโดยใช้ Aspose.Tasks ได้หรือไม่?**  
A: ได้, คุณสามารถขยายงานด้วยฟิลด์กำหนดเอง, กำหนดทรัพยากร, และแก้ไขปฏิทินโดยโปรแกรม.

**Q: มีชุมชนสนับสนุนสำหรับผู้ใช้ Aspose.Tasks หรือไม่?**  
A: แน่นอน! เข้าร่วมชุมชน Aspose.Tasks ที่ [the support forum](https://forum.aspose.com/c/tasks/15).

**อัปเดตล่าสุด:** 2026-09-25  
**ทดสอบด้วย:** Aspose.Tasks 24.12 for Java  
**ผู้เขียน:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## บทเรียนที่เกี่ยวข้อง

- [ตั้งค่าวันเริ่มต้นของโครงการใน MS Project โดยใช้ Aspose.Tasks สำหรับ Java](/tasks/java/project-properties/write-project-info/)
- [สร้างความสัมพันธ์ของงานในการจัดการโครงการด้วย Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [วิธีเพิ่มทรัพยากรลงในโครงการและสร้างการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}