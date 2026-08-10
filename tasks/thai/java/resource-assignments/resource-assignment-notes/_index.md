---
date: 2026-07-19
description: เรียนรู้วิธีเพิ่ม aspose tasks resource notes ไปยังการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks for Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อปรับปรุงการสื่อสารในโครงการ.
keywords:
- aspose tasks resource notes
- resource assignment notes
- aspose.tasks java
lastmod: 2026-07-19
linktitle: วิธีเพิ่ม Notes ลงในการมอบหมายทรัพยากรใน Aspose.Tasks
og_description: เรียนรู้วิธีเพิ่ม aspose tasks resource notes ไปยังการมอบหมายทรัพยากรโดยใช้
  Aspose.Tasks for Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อปรับปรุงการสื่อสารในโครงการ.
og_image_alt: 'Guide: Adding resource assignment notes with Aspose.Tasks for Java'
og_title: aspose tasks resource notes – เพิ่มบันทึกลงในการมอบหมายงาน
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  headline: aspose tasks resource notes – Add Notes to Assignments
  type: TechArticle
- description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  name: aspose tasks resource notes – Add Notes to Assignments
  steps:
  - name: Set Data Directory
    text: Set the path to your data directory where your project files are located.
  - name: Load Project File
    text: Load the project file into your Java application.
  - name: Get Task and Resource
    text: Retrieve the task and resource to which you want to add notes.
  - name: Create Resource Assignment
    text: Create a resource assignment for the task and resource.
  - name: Set Notes
    text: Set the notes for the resource assignment.
  - name: Display Notes
    text: Display the notes text and RTF format.
  - name: Process Completion
    text: Print a success message indicating the completion of the process.
  type: HowTo
- questions:
  - answer: Yes, simply call `assn.set(Asn.NOTES_TEXT, "Updated note")` again with
      the new content.
    question: Can I edit notes after they have been set?
  - answer: Absolutely. When you save the `Project` object, the notes become part
      of the assignment data inside the file.
    question: Are notes stored in the .mpp file?
  - answer: You must open the project with the correct password using the appropriate
      `Project` constructor overload before accessing assignments.
    question: Does this work with encrypted project files?
  - answer: Practically, notes can be several kilobytes long; extremely large notes
      may affect performance when loading the project.
    question: Is there a limit to the length of a note?
  - answer: Yes, iterate over `prj.getResourceAssignments()` and set `Asn.NOTES_TEXT`
      for each assignment as needed.
    question: Can I add notes to multiple assignments in a loop?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- resource notes
- java project management
- resource assignments
- aspose tasks java
title: aspose tasks resource notes – เพิ่มบันทึกลงในการมอบหมายงาน
url: /th/java/resource-assignments/resource-assignment-notes/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากรใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากร** ด้วย Aspose.Tasks for Java – ไลบรารีชั้นนำที่จัดการไฟล์การจัดการโครงการ โดยเมื่ออ่านจบคุณจะสามารถแนบความคิดเห็นแบบข้อความธรรมดาหรือข้อความรูปแบบ RTF ลงในลิงก์ระหว่างงานและทรัพยากรได้ ทำให้ข้อมูลโครงการของคุณสื่อสารได้ชัดเจนและพร้อมสำหรับการตรวจสอบ

## คำตอบสั้น
- **อะไรที่ “add notes” มีผล?** It stores plain‑text and RTF notes on a resource assignment.  
- **คลาสใดที่เก็บข้อมูลบันทึกย่อ?** The `Asn` class (e.g., `Asn.NOTES_TEXT`).  
- **ฉันต้องมีลิขสิทธิ์เพื่อทดสอบหรือไม่?** No, a free trial is available from the Aspose website.  
- **ฉันสามารถดึงบันทึกย่อในรูปแบบ RTF ได้หรือไม่?** Yes, use `Asn.NOTES_RTF`.  
- **ฟีเจอร์นี้เข้ากันได้กับ IDE ของ Java ทั้งหมดหรือไม่?** Absolutely – IntelliJ IDEA, Eclipse, NetBeans, etc.  

## การเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากรคืออะไร?
การเพิ่มบันทึกย่อหมายถึงการแนบข้อความอธิบาย—ไม่ว่าจะเป็นข้อความธรรมดาหรือข้อความรูปแบบ RTF—ไปยังลิงก์ระหว่างงานและทรัพยากร ฟีเจอร์นี้ช่วยให้ผู้จัดการโครงการฝังบริบท คำแนะนำพิเศษ หรือความคิดเห็นบันทึกการเปลี่ยนแปลงโดยตรงบนการมอบหมาย ทำให้ผู้ที่ตรวจสอบตารางเวลาเข้าใจ “ทำไม” ของแต่ละการจัดสรรได้ทันที

## ทำไมต้องเพิ่มบันทึกย่อ?
การเพิ่มบันทึกย่อสร้างช่องทางการสื่อสารภายในไฟล์โครงการทันที ลดความจำเป็นในการใช้สเปรดชีตหรืออีเมลภายนอก ให้มีร่องรอยการตรวจสอบในตัว และด้วยการสนับสนุน RTF คุณสามารถเน้นข้อมูลสำคัญด้วยการทำตัวหนา หรือเอียง—ทั้งหมดโดยไม่ต้องออกจากสภาพแวดล้อมการจัดการโครงการ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

1. **Java Development Kit (JDK)** – version 8 หรือสูงกว่า, ตั้งค่าอย่างถูกต้องบนเครื่องของคุณ.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [เว็บไซต์อย่างเป็นทางการ](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, หรือเครื่องมือแก้ไขที่รองรับ Java ใด ๆ ที่คุณต้องการ.  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## วิธีเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากร
ในส่วนนี้เราจะอธิบายขั้นตอนการทำงานเต็มรูปแบบสำหรับการแนบบันทึกย่อไปยังการมอบหมายทรัพยากร ตั้งแต่การกำหนดไดเรกทอรีข้อมูล, การโหลดโครงการ, การดึงงานและทรัพยากรที่เกี่ยวข้อง, การสร้างการมอบหมาย, และสุดท้ายการตั้งค่าและแสดงบันทึกย่อทั้งแบบข้อความธรรมดาและ RTF แต่ละขั้นตอนจะมีตัวอย่างโค้ดที่คุณสามารถแทนที่ด้วยสคริปต์จริงได้

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดเส้นทางไปยังไดเรกทอรีข้อมูลที่เก็บไฟล์โครงการของคุณ.
```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการเข้าสู่แอปพลิเคชัน Java ของคุณ.
```java
Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");
```

### ขั้นตอนที่ 3: ดึงงานและทรัพยากร
ดึงงานและทรัพยากรที่คุณต้องการเพิ่มบันทึกย่อ.
```java
Task task = prj.getRootTask().getChildren().getById(1);
Resource rsc = prj.getResources().getById(1);
```

### ขั้นตอนที่ 4: สร้างการมอบหมายทรัพยากร
สร้างการมอบหมายทรัพยากรสำหรับงานและทรัพยากรนั้น.
```java
ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);
```

### ขั้นตอนที่ 5: ตั้งค่าบันทึกย่อ
ตั้งค่าบันทึกย่อสำหรับการมอบหมายทรัพยากร.
```java
assn.set(Asn.NOTES_TEXT, "Newly added assignment");
```

### ขั้นตอนที่ 6: แสดงบันทึกย่อ
แสดงข้อความบันทึกย่อและรูปแบบ RTF.
```java
System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));
```

### ขั้นตอนที่ 7: การทำงานเสร็จสิ้น
พิมพ์ข้อความแสดงความสำเร็จเพื่อบ่งบอกว่ากระบวนการเสร็จสมบูรณ์.
```java
System.out.println("Process completed Successfully");
```

## คลาส Asn คืออะไร?
คลาส `Asn` กำหนดค่าคงที่ที่แทนฟิลด์บนการมอบหมายทรัพยากร เช่น บันทึกย่อ, ค่าใช้จ่าย, และงาน คุณใช้ค่าคงที่เหล่านี้ร่วมกับเมธอด `set` และ `get` บนวัตถุ `ResourceAssignment` เพื่ออ่านหรือเขียนข้อมูลที่สอดคล้อง ตัวอย่างเช่น `Asn.NOTES_TEXT` เก็บบันทึกย่อแบบข้อความธรรมดา ส่วน `Asn.NOTES_RTF` เก็บเวอร์ชันข้อความรูปแบบ RTF

## ปัญหาที่พบบ่อยและวิธีแก้ไข
- **NullPointerException when retrieving task/resource:** Verify that the IDs (`1` in the example) actually exist in your `.mpp` file.  
- **Notes not appearing in the UI:** Ensure you are viewing the assignment notes pane in Microsoft Project or another viewer that supports assignment notes.  
- **RTF output looks empty:** The API only returns RTF if the notes contain rich‑text formatting; plain text will result in an empty RTF string.  

## คำถามที่พบบ่อย
**Q: ฉันสามารถแก้ไขบันทึกย่อหลังจากตั้งค่าแล้วได้หรือไม่?**  
A: Yes, simply call `assn.set(Asn.NOTES_TEXT, "Updated note")` again with the new content.

**Q: บันทึกย่อถูกเก็บไว้ในไฟล์ .mpp หรือไม่?**  
A: Absolutely. When you save the `Project` object, the notes become part of the assignment data inside the file.

**Q: ฟีเจอร์นี้ทำงานกับไฟล์โครงการที่เข้ารหัสหรือไม่?**  
A: You must open the project with the correct password using the appropriate `Project` constructor overload before accessing assignments.

**Q: มีขีดจำกัดความยาวของบันทึกย่อหรือไม่?**  
A: Practically, notes can be several kilobytes long; extremely large notes may affect performance when loading the project.

**Q: ฉันสามารถเพิ่มบันทึกย่อให้กับหลายการมอบหมายในลูปได้หรือไม่?**  
A: Yes, iterate over `prj.getResourceAssignments()` and set `Asn.NOTES_TEXT` for each assignment as needed.

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากร** ด้วย Aspose.Tasks for Java การใช้บันทึกย่อของทรัพยากรใน Aspose ช่วยเพิ่มความชัดเจนของโครงการ สร้างร่องรอยการตรวจสอบในตัว และให้คุณฝังความคิดเห็นรูปแบบ RTF ได้โดยไม่ต้องออกจากไฟล์ตารางเวลา สำรวจฟีเจอร์ API เพิ่มเติมเช่น การอัปเดตเป็นกลุ่ม, ฟิลด์กำหนดเอง, และการผสานรวมกับระบบการจัดการโครงการที่คุณใช้อยู่

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มทรัพยากรลงในโครงการด้วย Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติการหน่วงเวลาเลเวลใน Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)
- [วิธีหยุดการมอบหมายและทำการมอบหมายทรัพยากรต่อใน Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}