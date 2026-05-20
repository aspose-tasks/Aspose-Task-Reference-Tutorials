---
date: 2026-05-20
description: เรียนรู้วิธีเพิ่มทรัพยากรในโครงการและสร้างการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks
  for Java ซึ่งเป็นไลบรารีการจัดการโครงการ Java ที่แข็งแกร่ง
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: สร้างการมอบหมายทรัพยากรใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีเพิ่มทรัพยากรในโครงการและสร้างการมอบหมายทรัพยากรใน Aspose.Tasks
url: /th/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากรลงในโครงการ – สร้างการมอบหมายทรัพยากรใน Aspose.Tasks

## บทนำ
ในการจัดการโครงการสมัยใหม่, **add resource to project** เป็นหัวใจสำคัญของการกำหนดเวลาและการควบคุมต้นทุนอย่างมีประสิทธิภาพ. Aspose.Tasks for Java มอบวิธีการเชิงโปรแกรมที่มีประสิทธิภาพสูงในการจัดการทรัพยากร, งาน, และการมอบหมายโดยไม่ต้องออกจาก IDE ของคุณ. ในบทเรียนนี้คุณจะได้เห็นวิธีการเพิ่มทรัพยากรลงในโครงการ, แนบเข้ากับงาน, และปรับรายละเอียดการมอบหมายอย่างละเอียด—ทั้งหมดด้วยโค้ด Java ที่สะอาดและพร้อมใช้งานในสภาพการผลิต.

## คำตอบอย่างรวดเร็ว
- **What is the first step?** สร้างอินสแตนซ์ `Project` ที่แสดงไฟล์ .mpp หรือ .xml ของคุณ.  
- **How do I add a task?** ใช้เมธอด `addChild` ของงานรากและตั้งชื่อให้กับงาน.  
- **How can I add a resource?** เรียก `project.getResources().add` พร้อมอ็อบเจ็กต์ `Resource`.  
- **How do I link a resource to a task?** ใช้ `project.getResourceAssignments().add(task, resource)`.  
- **Do I need a license?** ใช่ – จำเป็นต้องมีใบอนุญาต Aspose.Tasks for Java ที่ถูกต้องสำหรับการใช้งานในสภาพการผลิต.

## “add resource to project” คืออะไร
**Add resource to project** หมายถึงการสร้างอ็อบเจ็กต์ `Resource` ในไฟล์โครงการและเชื่อมโยงกับหนึ่งหรือหลายงานเพื่อให้ข้อมูลงาน, ค่าใช้จ่าย, และปฏิทินถูกคำนวณโดยอัตโนมัติ. การดำเนินการนี้เป็นแกนหลักของแอปพลิเคชันที่ขับเคลื่อนด้วยตารางเวลา.

## ทำไมต้องเลือก Aspose.Tasks for Java
Aspose.Tasks for Java รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 30 แบบ** (รวมถึง MPP, XML, และ CSV) และสามารถประมวลผลโครงการที่มี **งานกว่า 10,000 งาน** พร้อมรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า 200 MB. ไลบรารีทำงานบน Java 8‑17, ไม่ต้องติดตั้ง Microsoft Project, และให้ API ที่ปลอดภัยต่อเธรดสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะดำดิ่งเข้าสู่การสร้างการมอบหมายทรัพยากร, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### สภาพแวดล้อมการพัฒนา Java
ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว. คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### ไลบรารี Aspose.Tasks for Java
ดาวน์โหลดไลบรารี Aspose.Tasks for Java จาก [download page](https://releases.aspose.com/tasks/java/). ปฏิบัติตามคำแนะนำการติดตั้งเพื่อกำหนดค่าไลบรารีในโครงการ Java ของคุณ.

## วิธีเพิ่มทรัพยากรลงในโครงการ?
โหลดโครงการของคุณ, สร้างงาน, เพิ่มทรัพยากร, และสุดท้ายเชื่อมโยงพวกมันเข้าด้วยกัน – ทั้งหมดในสี่ขั้นตอนสั้น ๆ. โค้ดสแนปด้านล่าง (ตัวแทน) แสดงการเรียก API อย่างแม่นยำ; คุณเพียงแค่ต้องแทนที่ข้อความตัวแทนด้วยเส้นทางไฟล์และชื่อของคุณเอง.

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Project
คลาส `Project` เป็นคอนเทนเนอร์ระดับบนสุดที่แสดงไฟล์โครงการเดียวในหน่วยความจำ.  
สร้างอ็อบเจ็กต์ `Project` ซึ่งเป็นไฟล์โครงการที่คุณกำลังทำงานอยู่:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### ขั้นตอนที่ 2: เพิ่มงานลงในโครงการ
คลาส `Task` จำลองรายการงานแต่ละรายการภายในตารางเวลา.  
เพิ่มงานลงในโครงการโดยใช้เมธอด `addChild` ของงานราก:
```java
Project project = new Project();
```

### ขั้นตอนที่ 3: เพิ่มทรัพยากรลงในโครงการ
คลาส `Resource` กำหนดบุคคล, อุปกรณ์, หรือวัสดุที่สามารถมอบหมายให้กับงานได้.  
เพิ่มทรัพยากรลงในโครงการโดยใช้เมธอด `add` ของคอลเลกชัน `Resources`:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### ขั้นตอนที่ 4: สร้างการมอบหมายทรัพยากร
คลาส `ResourceAssignment` เชื่อมโยง `Task` กับ `Resource` และเก็บรายละเอียดการจัดสรรเช่นชั่วโมงทำงานและค่าใช้จ่าย.  
สร้างการมอบหมายทรัพยากรสำหรับงานและทรัพยากรโดยใช้เมธอด `add` ของคอลเลกชัน `ResourceAssignments`:
```java
Resource rsc = project.getResources().add("Rsc");
```

## ปัญหาทั่วไปและวิธีแก้
- **NullPointerException on `addChild`** – ตรวจสอบให้แน่ใจว่าคุณเรียก `project.getRootTask()` ก่อนเพิ่มลูก.  
- **License not found** – วางไฟล์ `Aspose.Tasks.lic` ของคุณใน classpath หรือกำหนดใบอนุญาตโดยโปรแกรมด้วย `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Large project slowdown** – ใช้ `project.setReadOnly(true)` เมื่อคุณต้องการอ่านข้อมูลเท่านั้น; นี้จะลดภาระหน่วยความจำ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถแก้ไขการมอบหมายทรัพยากรหลังจากสร้างได้หรือไม่?**  
A: ใช่, คุณสามารถอัปเดตคุณสมบัติการมอบหมาย เช่น `Work`, `Cost`, และ `Start` โดยใช้เมธอด setter ที่คลาส `ResourceAssignment` จัดให้.

**Q: Aspose.Tasks for Java รองรับรูปแบบไฟล์โครงการที่แตกต่างกันหรือไม่?**  
A: แน่นอน, Aspose.Tasks for Java รองรับ MPP, XML, CSV, และรูปแบบอื่น ๆ มากมาย, ทำให้การนำเข้าและส่งออกเป็นไปอย่างราบรื่น.

**Q: Aspose.Tasks for Java ต้องการใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์ที่ถูกต้อง. มีใบอนุญาตทดลองใช้งานฟรีสำหรับการทดสอบ.

**Q: ฉันสามารถใช้ Aspose.Tasks for Java ในแอปพลิเคชันเว็บของฉันได้หรือไม่?**  
A: ใช่, ไลบรารีนี้ปลอดภัยต่อเธรดอย่างเต็มที่และสามารถรวมเข้ากับบริการเว็บที่ใช้ servlet หรือ Spring‑Boot ได้.

**Q: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Tasks for Java ได้จากที่ไหน?**  
A: คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือทางเทคนิคและการสนทนาของชุมชน.

---

**อัปเดตล่าสุด:** 2026-05-20  
**ทดสอบกับ:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้างทรัพยากร – การจัดการทรัพยากรด้วย Aspose.Tasks for Java](/tasks/java/resource-management/)
- [วิธีเพิ่มบันทึกลงในการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติการหน่วงเวลาเลเวลลิงใน Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}