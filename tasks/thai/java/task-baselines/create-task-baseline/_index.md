---
date: 2026-08-29
description: เรียนรู้วิธีเพิ่ม task ไปยัง project ใน Java, สร้าง task list, และตั้งค่า
  baseline โดยไม่ต้องใช้ Microsoft Project ด้วย Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: การสร้าง Task Baseline ใน Aspose.Tasks
og_description: เรียนรู้วิธีเพิ่ม task ไปยัง project ใน Java และตั้งค่า baseline ด้วย
  Aspose.Tasks. คู่มือนี้แสดงโค้ดขั้นตอนต่อขั้นตอนโดยไม่ต้องใช้ Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: วิธีเพิ่ม task ไปยัง project ใน Java และตั้งค่า baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: วิธีเพิ่ม task ไปยัง project ใน Java และตั้งค่า baseline
url: /th/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มงานในโครงการด้วย Java และตั้งค่า baseline

## บทนำ
ในบทเรียนนี้คุณจะ **add task to project** ด้วยโปรแกรม, สร้าง baseline ของงานใน Microsoft Project, และบันทึกไฟล์—ทั้งหมดโดยไม่ต้องเปิด Microsoft Project เลย Aspose.Tasks for Java ให้ API แบบ pure‑Java ที่ทำงานบนทุกแพลตฟอร์ม ทำให้เหมาะสำหรับ pipeline การสร้างอัตโนมัติ, บริการรายงาน, หรือโซลูชันฝั่งเซิร์ฟเวอร์ใด ๆ ที่ต้องจัดการไฟล์ .mpp

## คำตอบสั้น
- **Aspose.Tasks ทำอะไร?** มันให้ Java API สำหรับสร้าง, อ่าน, และแก้ไขไฟล์ Microsoft Project โดยไม่ต้องการ Microsoft Project  
- **ฉันต้องติดตั้ง Microsoft Project หรือไม่?** ไม่, ไลบรารีทำงานอย่างอิสระโดยสมบูรณ์  
- **ต้องใช้เวอร์ชัน Java ใด?** JDK 8 หรือสูงกว่า  
- **ฉันสามารถตั้ง baseline สำหรับงานเดียวได้หรือไม่?** ใช่ – เรียก `setBaseline` บนรายการที่มีเฉพาะงานที่คุณต้องการ  
- **ต้องมีใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่, ใบอนุญาตเชิงพาณิชย์จะลบข้อจำกัดการประเมินและเปิดใช้งานคุณสมบัติทั้งหมด  

## Baseline ของงานคืออะไร?
Baseline ของงานบันทึกวันที่เริ่มต้นที่วางแผนไว้เดิม, วันที่สิ้นสุด, และปริมาณงานสำหรับงานในขณะที่กำหนดการถูกบันทึกเป็นครั้งแรก ภาพถ่ายนี้ทำหน้าที่เป็นจุดอ้างอิง ช่วยให้ผู้จัดการโครงการเปรียบเทียบความคืบหน้าและค่าใช้จ่ายจริงกับแผนเริ่มต้น, และคำนวณความแตกต่างสำหรับการวิเคราะห์ประสิทธิภาพ

## ทำไมต้องใช้ Aspose.Tasks เพื่อเพิ่มงานในโครงการด้วย Java?
คุณสามารถสร้าง, แก้ไข, และตั้งค่า baseline ของงานได้โดยไม่ต้องติดตั้งบนเดสก์ท็อป, ซึ่งทำให้เวิร์กโฟลว์อัตโนมัติโดยสมบูรณ์ Aspose.Tasks รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ** และสามารถจัดการโครงการที่มี **งานหลายร้อยรายการ** พร้อมรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า 200 MB ทำให้เหมาะสำหรับบริการคลาวด์และ pipeline CI/CD

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – ติดตั้ง JDK 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจาก [download link](https://releases.aspose.com/tasks/java/).  

## นำเข้าแพ็กเกจ
เพื่อเริ่มทำงานกับ Aspose.Tasks ในโครงการ Java ของคุณ, ให้นำเข้าแพ็กเกจที่จำเป็น:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจกต์โปรเจกต์
`Project` class เป็นอ็อบเจกต์ระดับบนสุดของ Aspose.Tasks ที่แสดงไฟล์ Microsoft Project ในหน่วยความจำ การสร้างอินสแตนซ์จะให้โปรเจกต์เปล่าที่คุณสามารถเติมด้วยงาน, ทรัพยากร, และปฏิทิน
```java
Project project = new Project();
```
ที่นี่เราสร้างอินสแตนซ์ของอ็อบเจกต์ `Project` ใหม่ – ซึ่งเป็นไฟล์ MS Project ที่จะเก็บรายการงานของเรา.

## ขั้นตอนที่ 2: เพิ่มงานลงในโปรเจกต์
`Task` class แสดงรายการงานแต่ละรายการในกำหนดการของโครงการ แต่ละ `Task` สามารถมีระยะเวลา, วันที่เริ่มต้น, และการมอบหมายทรัพยากรของตนเอง
```java
Task task = project.getRootTask().getChildren().add("Task");
```
โดยใช้ `getRootTask()` เราเข้าถึงรากของโครงสร้างโครงการและ **add task to Microsoft Project**. สตริง `"Task"` คือชื่อของงาน; คุณสามารถเปลี่ยนเป็นคำอธิบายใดก็ได้ที่ต้องการ

## ขั้นตอนที่ 3: ตั้งค่า baseline สำหรับงานที่ระบุ
`BaselineType` เป็น enumeration ที่กำหนดว่าต้องการเขียน baseline ช่องใด (Baseline, Baseline1 … Baseline10) โดยการส่งรายการงานคุณสามารถตั้ง baseline เฉพาะรายการที่เลือกได้
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
เพื่อ **set baseline without MS Project**, สร้างรายการของงานที่คุณต้องการตั้ง baseline (ที่นี่คือ `myList`) และส่งให้ `setBaseline`. เติม `myList` ด้วยงานที่คุณเพิ่มไว้หากต้องการ baseline แบบเลือกเท่านั้น.

## ขั้นตอนที่ 4: ตั้งค่า baseline สำหรับโครงการทั้งหมด
`setBaseline` จะเขียนค่าที่เลือกเป็น baseline ไปยังทุกงานในโครงการ  
หากคุณต้องการตั้ง baseline ให้กับโครงการทั้งหมดในครั้งเดียว, เพียงเรียก `setBaseline` พร้อมกับ `BaselineType` ที่ต้องการ
```java
project.setBaseline(BaselineType.Baseline);
```
การเรียกนี้จะเขียนค่าที่เลือกเป็น baseline สำหรับ **ทุกงาน** ในโครงการ, ทำให้ได้ภาพถ่ายครบถ้วนของกำหนดการต้นฉบับ

## วิธีเพิ่มงานลงใน Microsoft Project ด้วย Aspose.Tasks
`add()` สร้างงานลูกใหม่ภายใต้งานพาเรนต์ที่ระบุและคืนค่าอ็อบเจกต์ `Task` ที่สร้างใหม่  
คุณเพิ่มงานโดยเรียก `add()` บนอ็อบเจกต์ `Task` พาเรนต์ (โดยทั่วไปคือ root task) วิธีนี้จะคืนอินสแตนซ์ `Task` ใหม่ที่คุณสามารถกำหนดค่าเพิ่มเติม—ระยะเวลา, วันที่เริ่มต้น, ทรัพยากร, หรือฟิลด์กำหนดเอง—ก่อนบันทึกไฟล์โครงการ

## วิธีตั้ง baseline โดยไม่ใช้ MS Project
Aspose.Tasks ทำให้การสร้าง baseline ทำได้ทั้งหมดผ่านโค้ด เลือก `BaselineType` (เช่น `BaselineType.Baseline`) แล้วเรียก `setBaseline` คุณสามารถทำซ้ำกับ `Baseline1`‑`Baseline10` เพื่อเก็บ baseline หลายรุ่น, ทั้งหมดโดยไม่ต้องเปิด Microsoft Project

## ปัญหาที่พบบ่อยและวิธีแก้
- **Baseline ไม่แสดง:** ตรวจสอบว่าคุณเรียก `project.save("output.mpp")` หลังจากตั้ง baseline (ขั้นตอนการบันทึกถูกละไว้เพื่อความกระชับ).  
- **รายการงานแสดงเป็นค่าว่าง:** ตรวจสอบว่าคุณกำลังเพิ่มงานไปยังพาเรนต์ที่ถูกต้อง (`getRootTask()` หรือ sub‑task).  
- **ข้อผิดพลาดการไม่ตรงกันของเวอร์ชัน:** ใช้ Aspose.Tasks JAR เวอร์ชันล่าสุดเพื่อรับประกันความเข้ากันได้กับรูปแบบ .mpp ที่ใหม่กว่า.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java ได้โดยไม่ต้องติดตั้ง Microsoft Project หรือไม่?**  
A: ใช่, Aspose.Tasks ทำงานอย่างอิสระและไม่ต้องการ Microsoft Project บนเครื่องโฮสต์  

**Q: Aspose.Tasks สำหรับ Java รองรับเวอร์ชันต่าง ๆ ของ Microsoft Project หรือไม่?**  
A: แน่นอน. ไลบรารีรองรับไฟล์ Project ตั้งแต่ปี 2007 จนถึงรุ่นล่าสุดปี 2024  

**Q: ฉันสามารถจัดการทรัพยากรของโครงการโดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
A: ใช่, คุณสามารถเพิ่ม, ปรับปรุง, และลบทรัพยากรผ่านโปรแกรมได้เช่นเดียวกับงาน  

**Q: Aspose.Tasks สำหรับ Java รองรับการตั้งค่าการขึ้นต่อกันของงานหรือไม่?**  
A: ใช่, คุณสามารถกำหนดความสัมพันธ์ predecessor‑successor ด้วยคลาส `TaskLink`  

**Q: มีการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks สำหรับ Java หรือไม่?**  
A: มี, คุณสามารถขอความช่วยเหลือผ่าน [support forum](https://forum.aspose.com/c/tasks/15) ซึ่งพนักงาน Aspose และชุมชนจะตอบคำถาม  

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณได้เรียนรู้วิธี **add task to project** ด้วย Java, สร้างรายการงาน, และ **set baseline without MS Project** ด้วย Aspose.Tasks วิธีการนี้ทำให้การอัตโนมัติโครงการเป็นเรื่องง่าย, ลบความจำเป็นในการติดตั้ง Project บนเดสก์ท็อป, และให้คุณควบคุมโปรแกรมได้เต็มที่ในทุกด้านของกำหนดการของคุณ.

---

**อัปเดตล่าสุด:** 2026-08-29  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้าง Project aspose.tasks – ตั้งค่าคุณลักษณะงานใหม่](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [วิธีตั้งค่า Baseline Duration ใน Aspose.Tasks สำหรับ Java](/tasks/java/task-baselines/task-baseline-duration/)
- [สร้างงาน Aspose Java – คุณสมบัติงาน](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}