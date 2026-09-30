---
date: 2026-09-30
description: เรียนรู้วิธีตั้งค่าความคืบหน้าในโครงการ MPP ด้วย Java โดยใช้ Aspose.Tasks
  ซึ่งเป็นไลบรารีการจัดการโครงการ Java ที่แข็งแกร่ง ทำตามคำแนะนำขั้นตอนต่อขั้นตอนนี้
keywords:
- how to set progress
- java project management library
- Aspose.Tasks Java
- MPP project Java
lastmod: 2026-09-30
linktitle: เปลี่ยนความคืบหน้าของงานใน Aspose.Tasks
og_description: วิธีตั้งค่าความคืบหน้าในโครงการ MPP ด้วย Java โดยใช้ Aspose.Tasks
  ไลบรารีการจัดการโครงการ Java ชั้นนำ รับคู่มือเต็มรูปแบบโดยไม่ต้องเขียนโค้ด
og_image_alt: Guide showing how to set task progress in an MPP file using Aspose.Tasks
  for Java
og_title: วิธีตั้งค่าความคืบหน้าในโครงการ MPP ด้วย Java – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  headline: How to set progress in an MPP project using Java and Aspose.Tasks
  type: TechArticle
- description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  name: How to set progress in an MPP project using Java and Aspose.Tasks
  steps:
  - name: Set up your Java project
    text: Create a new Maven or Gradle project and add the Aspose.Tasks JAR to your
      classpath. This gives you access to the `Project`, `Task`, and related classes.
  - name: Define the document directory
    text: Specify where the project file will be stored. Replace the placeholder with
      the actual path on your machine. `dataDir` is a string that specifies the folder
      path where the MPP file will be saved.
  - name: Create a new project (create mpp project java)
    text: '`Project` represents an in‑memory Microsoft Project file that can be saved
      to .mpp format.'
  - name: Add a task to the project (add task project)
    text: '`Task` is an object representing a single work item within a Project.'
  - name: Set the task’s progress
    text: '`Tsk.PERCENT_COMPLETE` is the field that stores a task’s completion percentage.'
  - name: Display the updated progress
    text: Reading `Tsk.PERCENT_COMPLETE` returns the current progress value for the
      task. By following these steps you have successfully **created an MPP project
      in Java**, added a task, and **changed its progress** – all using Aspose.Tasks.
  type: HowTo
- questions:
  - answer: Any recent version (2023‑2025) supports `Project` creation; using the
      latest release ensures you have all bug fixes and performance improvements.
    question: What version of Aspose.Tasks is required to create an MPP file?
  - answer: Yes, call `project.save("output.pdf", SaveFileFormat.PDF);` after setting
      the progress to generate a visual report.
    question: Can I export the project to PDF after updating progress?
  - answer: Loop through `project.getRootTask().getChildren()` and set `Tsk.PERCENT_COMPLETE`
      for each task; the API updates each task efficiently.
    question: Is it possible to batch‑update progress for many tasks?
  - answer: Resources must be added explicitly; task progress does not affect resource
      allocation unless you modify resource‑related fields.
    question: Does the library handle resource assignments automatically?
  - answer: Use `project.setPassword("yourPassword");` before calling `project.save(...)`
      to encrypt the file.
    question: How do I protect the generated MPP file with a password?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task progress
title: วิธีตั้งค่าความคืบหน้าในโครงการ MPP ด้วย Java และ Aspose.Tasks
url: /th/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งความคืบหน้าในโครงการ MPP ด้วย Java และ Aspose.Tasks

## บทนำ
ใน **java project management** สมัยใหม่ การสามารถ **create mpp project java** ไฟล์และรักษาความคืบหน้าของงานให้เป็นปัจจุบันเป็นสิ่งสำคัญสำหรับการส่งมอบตรงเวลา บทเรียนนี้จะแสดงให้คุณเห็น **how to set progress** สำหรับงานโดยใช้โปรแกรมกับ Aspose.Tasks ซึ่งเป็น **java project management library** ที่ทรงพลังและทำงานได้บน Windows, Linux และ macOS คุณจะได้เห็นกระบวนการทั้งหมด—from การสร้างโครงการจนถึงการตรวจสอบเปอร์เซ็นต์ความสำเร็จที่อัปเดต—อธิบายด้วยสไตล์การสนทนาแบบขั้นตอนต่อขั้นตอน

## คำตอบอย่างรวดเร็ว
- **“create mpp project java” หมายความว่าอะไร?**  
  หมายถึงการสร้างไฟล์ Microsoft Project (.mpp) โดยใช้โค้ด Java อย่างอัตโนมัติ
- **ไลบรารีใดที่ช่วยในเรื่องนี้?**  
  Aspose.Tasks for Java, ซึ่งเป็น **java project management library** ที่เฉพาะเจาะจง
- **ต้องใช้บรรทัดโค้ดกี่บรรทัดในการตั้งความคืบหน้าของงาน?**  
  น้อยกว่า 10 บรรทัดเมื่อโครงการถูกสร้างขึ้นแล้ว
- **ต้องการใบอนุญาตสำหรับการใช้งานในสภาพแวดล้อมการผลิตหรือไม่?**  
  ใช่ จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้
- **ฉันสามารถรันโค้ดนี้บน IDE ของ Java ใดก็ได้หรือไม่?**  
  แน่นอน – IDE ใดก็ได้ที่รองรับ Java 8+ จะทำงานได้

## “create mpp project java” คืออะไร?
การสร้างโครงการ MPP ด้วย Java หมายถึงการใช้โค้ดเพื่อสร้างไฟล์ Microsoft Project (`.mpp`) ที่สามารถเปิดได้ใน Microsoft Project หรือโปรแกรมดูไฟล์ที่เข้ากันได้ นี่ทำให้สามารถสร้างตารางเวลาอัตโนมัติ, สร้างงานเป็นจำนวนมาก, และการผสานรวมกับระบบองค์กรได้อย่างราบรื่น

## ทำไมต้องใช้ Aspose.Tasks เป็น java project management library?
Aspose.Tasks ให้ **full API coverage** สำหรับการสร้างโครงการ, การจัดการงาน, และการรายงาน รองรับ **30+ input and output formats** และสามารถจัดการโครงการที่มี **up to 10,000 tasks** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ส่งมอบการประมวลผลที่มีประสิทธิภาพสูงบนฮาร์ดแวร์ที่จำกัด

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Environment** – JDK 8 หรือสูงกว่า ที่ติดตั้งและกำหนดค่าแล้ว.  
2. **Aspose.Tasks for Java Library** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Document Directory** – โฟลเดอร์บนเครื่องของคุณที่ไฟล์ `.mpp` ที่สร้างจะถูกบันทึกไว้.

## นำเข้าแพ็กเกจ
ขั้นแรก, นำเข้าคลาสของ Aspose.Tasks ที่คุณต้องการ ตัวอย่างโค้ดนี้ตั้งค่าสภาพแวดล้อมและต่อมาจะเพิ่มงานที่มีความคืบหน้า 50 %

`com.aspose.tasks.*` ให้คลาสหลักเช่น **Project**, **Task**, และ **Tsk** สำหรับทำงานกับไฟล์ MPP.

```java
import com.aspose.tasks.*;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ
สร้างโครงการ Maven หรือ Gradle ใหม่และเพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath ของคุณ ซึ่งจะทำให้คุณเข้าถึง `Project`, `Task` และคลาสที่เกี่ยวข้อง

### ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร
ระบุที่ตั้งที่ไฟล์โครงการจะถูกบันทึก แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ

`dataDir` เป็นสตริงที่ระบุพาธของโฟลเดอร์ที่ไฟล์ MPP จะถูกบันทึก

```java
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 3: สร้างโครงการใหม่ (create mpp project java)
`Project` แทนไฟล์ Microsoft Project ที่อยู่ในหน่วยความจำซึ่งสามารถบันทึกเป็นรูปแบบ .mpp

```java
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 4: เพิ่มงานลงในโครงการ (add task project)
`Task` คืออ็อบเจ็กต์ที่แสดงถึงรายการงานเดียวภายใน Project

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### ขั้นตอนที่ 5: ตั้งค่าความคืบหน้าของงาน
`Tsk.PERCENT_COMPLETE` คือฟิลด์ที่เก็บเปอร์เซ็นต์การทำงานเสร็จของงาน

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### ขั้นตอนที่ 6: แสดงความคืบหน้าที่อัปเดต
การอ่าน `Tsk.PERCENT_COMPLETE` จะคืนค่าความคืบปัจจุบันของงาน

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

โดยทำตามขั้นตอนเหล่านี้ คุณได้ **สร้างโครงการ MPP ด้วย Java** อย่างสำเร็จ, เพิ่มงาน, และ **เปลี่ยนแปลงความคืบหน้า** – ทั้งหมดโดยใช้ Aspose.Tasks

## วิธีตั้งความคืบหน้าสำหรับงานใน Aspose.Tasks?
โหลดอ็อบเจ็กต์ `Project` ที่มีอยู่, ค้นหา `Task` ที่ต้องการ (หรือสร้างใหม่), แล้วกำหนดค่าตัวใหม่ให้กับ `Tsk.PERCENT_COMPLETE` ไลบรารีจะคำนวณค่า roll‑up ของงานแม่โดยอัตโนมัติ ทำให้ตารางเวลาทั้งหมดคงที่ บรรทัดโค้ดเดียวนี้คือทั้งหมดที่คุณต้องการเพื่ออัปเดตความคืบหน้า

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **FileNotFoundException** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\`) และโฟลเดอร์มีอยู่
- **LicenseException** – สำหรับการใช้งานในสภาพแวดล้อมการผลิต, โหลดใบอนุญาต Aspose.Tasks ของคุณก่อนสร้างอ็อบเจ็กต์ `Project`
- **Incorrect percent value** – เมธอด `percent` ต้องการค่าระหว่าง 0 ถึง 100; การส่งค่าที่อยู่นอกช่วงนี้จะทำให้เกิดข้อยกเว้น

## คำถามที่พบบ่อย

**Q: เวอร์ชันของ Aspose.Tasks ที่ต้องการเพื่อสร้างไฟล์ MPP คืออะไร?**  
A: เวอร์ชันล่าสุดใดก็ได้ (2023‑2025) รองรับการสร้าง `Project`; การใช้รุ่นล่าสุดจะทำให้คุณได้รับการแก้ไขบั๊กและการปรับปรุงประสิทธิภาพทั้งหมด

**Q: ฉันสามารถส่งออกโครงการเป็น PDF หลังจากอัปเดตความคืบหน้าได้หรือไม่?**  
A: ใช่, เรียก `project.save("output.pdf", SaveFileFormat.PDF);` หลังจากตั้งค่าความคืบหน้าเพื่อสร้างรายงานแบบภาพ

**Q: สามารถอัปเดตความคืบหน้าเป็นชุดสำหรับหลายงานได้หรือไม่?**  
A: วนลูปผ่าน `project.getRootTask().getChildren()` แล้วตั้งค่า `Tsk.PERCENT_COMPLETE` สำหรับแต่ละงาน; API จะอัปเดตแต่ละงานอย่างมีประสิทธิภาพ

**Q: ไลบรารีจัดการการมอบหมายทรัพยากรโดยอัตโนมัติหรือไม่?**  
A: จำเป็นต้องเพิ่มทรัพยากรอย่างชัดเจน; ความคืบหน้าของงานจะไม่ส่งผลต่อการจัดสรรทรัพยากร เว้นแต่คุณจะปรับเปลี่ยนฟิลด์ที่เกี่ยวข้องกับทรัพยากร

**Q: ฉันจะปกป้องไฟล์ MPP ที่สร้างด้วยรหัสผ่านอย่างไร?**  
A: ใช้ `project.setPassword("yourPassword");` ก่อนเรียก `project.save(...)` เพื่อเข้ารหัสไฟล์

## สรุป
การเชี่ยวชาญ **how to set progress** ในโครงการ MPP ด้วย Java จะทำให้คุณสามารถอัตโนมัติการบำรุงรักษาตารางเวลา, แจ้งผู้มีส่วนได้ส่วนเสีย, และผสานรวมข้อมูลโครงการเข้าสู่กระบวนการทำงานขององค์กรที่ใหญ่ขึ้น Aspose.Tasks, **java project management library** ชั้นนำ, ทำให้ภารกิจเหล่านี้ง่ายและมีประสิทธิภาพ

---

**อัปเดตล่าสุด:** 2026-09-30  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [การจัดการโครงการ Java: งาน % เสร็จสมบูรณ์โดยใช้ Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)
- [วิธีอัปเดตข้อมูลงานเป็นรูปแบบ MPP ด้วย Aspose.Tasks for Java](/tasks/java/task-properties/update-task-data/)
- [อ่านและตั้งค่าความสำคัญของงานด้วย Aspose.Tasks for Java](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}