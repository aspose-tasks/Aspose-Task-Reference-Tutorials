---
date: 2026-06-25
description: เรียนรู้วิธีเพิ่มงานและอัปเดตไฟล์ MPP โดยใช้ Aspose.Tasks for Java, ไลบรารีการจัดการโครงการ
  Java ที่ให้คุณสร้างไฟล์ Microsoft Project งานและบันทึกโครงการเป็น MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: วิธีเพิ่มงานและอัปเดตไฟล์ MPP ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีเพิ่มงานและอัปเดตไฟล์ MPP ใน Aspose.Tasks
url: /th/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มงานและอัปเดตไฟล์ MPP ใน Aspose.Tasks

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **how to add task** ไปยังไฟล์ Microsoft Project (MPP) ที่มีอยู่แล้วและจากนั้นบันทึกกำหนดการที่อัปเดตโดยใช้ Aspose.Tasks for Java ซึ่งเป็น **java project management library** ชั้นนำ ไม่ว่าคุณจะกำลังสร้างตัวจัดตารางแบบกำหนดเอง, ทำการอัปเดตเป็นกลุ่มอัตโนมัติ, หรือบูรณาการข้อมูลโครงการเข้ากับระบบขนาดใหญ่ คำแนะนำแบบขั้นตอนต่อขั้นตอนด้านล่างจะแสดงอย่างชัดเจนว่าต้องโหลดโครงการ, แทรกงานใหม่, ตั้งค่าวันที่, และบันทึกผลลัพธ์เป็นเอกสาร MPP ใหม่อย่างไร

## คำตอบอย่างรวดเร็ว
- **What does “how to add task” mean in this context?** หมายถึงการสร้างรายการงานใหม่โดยโปรแกรมภายในไฟล์ MPP ที่มีอยู่  
- **Which library handles the operation?** Aspose.Tasks for Java, a robust java project management library.  
- **Do I need a license?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **Can I save the result as MPP?** ได้—ใช้ `project.save(..., SaveFileFormat.Mpp)` เพื่อ **save project as mpp**.  
- **What Java version is required?** Java 8 หรือใหม่กว่า  

## อะไรคือ “how to add task” ในไฟล์ MPP?
การเพิ่มงานหมายถึงการแทรกรายการงานใหม่เข้าไปในโครงสร้างโครงการ, กำหนดวันที่เริ่มต้น/สิ้นสุด, และบันทึกการเปลี่ยนแปลงกลับไปยังไฟล์ MPP. Aspose.Tasks แยกรายละเอียดระดับต่ำของรูปแบบไฟล์ออก, ทำให้คุณมุ่งเน้นที่ตรรกะธุรกิจในขณะที่จัดการการมอบหมายทรัพยากร, ปฏิทิน, และการคำนวณความขึ้นต่อกันโดยอัตโนมัติ นอกจากนี้ยังอัปเดตการมอบหมายที่เกี่ยวข้องและคำนวณกำหนดการโครงการใหม่เพื่อรักษาความสอดคล้องระหว่างงานที่ขึ้นต่อกัน

## ทำไมต้องใช้ Aspose.Tasks for Java?
- **Full compatibility**: รองรับคุณสมบัติ 100% ของ Microsoft Project 2007‑2021 (มีประเภทงานมากกว่า 150 ประเภทและฟิลด์ทรัพยากรกว่า 200 ฟิลด์)  
- **Zero‑dependency**: ไม่ต้องใช้ COM, Office, หรือไลบรารีเนทีฟ—API Java แท้ทำงานได้ทุกที่ที่ JRE ทำงาน  
- **Rich feature set**: มีการเชื่อมโยงงาน, การจัดสรรทรัพยากร, ฟิลด์กำหนดเอง, และการรายงานในตัว  
- **High performance**: ประมวลผลโครงการที่มีงานสูงสุด 10,000 งานโดยใช้หน่วยความจำต่ำกว่า 200 MB ทำให้เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์  

## ข้อกำหนดเบื้องต้น
1. **Java Development Environment** – ติดตั้งและกำหนดค่า JDK 8+ แล้ว  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/)  
3. **Basic Java knowledge** – ความคุ้นเคยกับคลาส, อ็อบเจ็กต์, และการจัดการวันที่  

## นำเข้าชุดแพ็กเกจ
ก่อนแรกให้ทำการนำเข้าคลาสที่คุณต้องการ ซึ่งจะทำให้คุณเข้าถึงการจัดการโครงการ, คุณสมบัติงาน, และการจัดการวันที่

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` แสดงถึงไฟล์ Microsoft Project ที่โหลดอยู่ในหน่วยความจำ `SaveFileFormat` ระบุรูปแบบที่คุณสามารถบันทึกได้ เช่น MPP หรือ PDF `Task` เป็นโมเดลของรายการงานแต่ละรายการในโครงสร้างโครงการ `Tsk` ให้ค่าคงที่สำหรับฟิลด์งานที่ใช้เมื่อกำหนดหรือดึงค่าต่าง ๆ `Calendar` มียูทิลิตี้วันที่‑เวลาเพื่อกำหนดกำหนดการ  

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```  
แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มที่ไฟล์ MPP ต้นฉบับของคุณตั้งอยู่

## ขั้นตอนที่ 2: อ่านโครงการที่มีอยู่
คลาส `Project` เป็นอ็อบเจ็กต์หลักของ Aspose.Tasks ที่แสดงถึงไฟล์ Microsoft Project ในหน่วยความจำ  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
คอนสตรัคเตอร์โหลด **SampleMSP2010.mpp**, ให้คุณได้โมเดลอ็อบเจ็กต์ที่สามารถจัดการได้อย่างเต็มที่

## ขั้นตอนที่ 3: สร้างงานใหม่ (how to add task)
คลาส `Task` แสดงถึงรายการงานแต่ละรายการภายในโครงสร้างโครงการ  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
บรรทัดนี้ **creates task in mpp** โดยการเพิ่มลูกชื่อ *Task1* ไปยังงานราก

## ขั้นตอนที่ 4: ตั้งค่าวันที่เริ่มต้นและสิ้นสุด
คลาส `Calendar` มียูทิลิตี้วันที่‑เวลา; เดือนเริ่มจากศูนย์ (เช่น `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
ที่นี่เรากำหนดกำหนดการสำหรับงานที่เพิ่มใหม่ ปรับวันที่ให้ตรงกับไทม์ไลน์ของโครงการของคุณ

## ขั้นตอนที่ 5: บันทึกโครงการ (save project as mpp)
`SaveFileFormat.Mpp` บอก Aspose.Tasks ให้เขียนไฟล์กลับเป็นรูปแบบ Microsoft Project ดั้งเดิม  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
โครงการที่อัปเดตแล้ว ซึ่งตอนนี้มีงานใหม่อยู่ จะถูกบันทึกเป็น **AfterLinking.mpp**.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **File not found** | ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`) และชื่อไฟล์ถูกต้อง |
| **Incorrect dates** | จำไว้ว่ารายการเดือนของ `Calendar` เริ่มจากศูนย์; `Calendar.JULY` ถูกต้องสำหรับเดือนกรกฎาคม |
| **License exception** | ติดตั้งลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องก่อนเรียกใช้ API ใด ๆ เพื่อหลีกเลี่ยงลายน้ำการประเมิน |

## คำถามที่พบบ่อย
**Q: ฉันจะเพิ่มหลายงานพร้อมกันได้อย่างไร?**  
A: วนลูปผ่านคอลเลกชันของชื่องานและทำซ้ำบล็อก “create task” ภายในลูป  

**Q: ฉันสามารถตั้งค่าฟิลด์กำหนดเองสำหรับงานใหม่ได้หรือไม่?**  
A: ได้—ใช้ `task.set(Tsk.CUSTOM_FIELD_x, value)` โดยที่ *x* คือดัชนีของฟิลด์  

**Q: สามารถคัดลอกงานที่มีอยู่เป็นเทมเพลตได้หรือไม่?**  
A: คัดลอกงานต้นฉบับ (`Task cloned = sourceTask.clone();`) แล้วเพิ่มไปยังพาเรนต์ที่ต้องการ  

**Q: ถ้าฉันต้องอัปเดตงานที่มีอยู่แทนการเพิ่มงานใหม่จะทำอย่างไร?**  
A: ดึงงานโดย ID (`Task existing = project.getRootTask().getChildren().getById(id);`) แล้วแก้ไขคุณสมบัติของมัน  

**Q: Aspose.Tasks รองรับการบันทึกเป็นรูปแบบอื่นเช่น PDF หรือ PNG หรือไม่?**  
A: ได้—ใช้ `project.save("output.pdf", SaveFileFormat.Pdf);` หรือ `SaveFileFormat.Png` สำหรับการแสดงผลภาพ  

---

**อัปเดตล่าสุด:** 2026-06-25  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างไฟล์ MPP – สร้างและบันทึกโครงการเปล่าในรูปแบบ MPP ด้วย Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [วิธีสร้างโครงการ – ตั้งค่าแอตทริบิวต์งานใหม่ด้วย Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [สร้างรายการงาน Java – ฐานข้อมูลโครงการ MS ด้วย Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}