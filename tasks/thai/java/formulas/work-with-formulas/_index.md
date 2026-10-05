---
date: 2026-10-05
description: เรียนรู้วิธีสร้าง test project และคำนวณจำนวนวันระหว่างวันที่โดยใช้ Aspose.Tasks
  for Java, เพิ่ม custom field, และจัดการไฟล์ MPP อย่างมีประสิทธิภาพ.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: ทำงานกับสูตรใน Aspose.Tasks
og_description: สร้าง test project และคำนวณจำนวนวันระหว่างวันที่โดยใช้ Aspose.Tasks
  for Java. คู่มือนี้แสดงวิธีเพิ่ม custom field, ตั้ง task deadlines, และบันทึก project
  เป็นไฟล์ MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: สร้าง test project และคำนวณจำนวนวันระหว่างวันที่
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: สร้าง test project และคำนวณจำนวนวันระหว่างวันที่
url: /th/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างโครงการทดสอบและคำนวณจำนวนวันระหว่างวันที่

ในบทแนะนำนี้คุณจะ **สร้างโครงการทดสอบ** และ **คำนวณจำนวนวันระหว่างวันที่** โดยการเพิ่มฟิลด์กำหนดเอง, กำหนดแอตทริบิวต์ขยาย, และใช้สูตร Microsoft Project ผ่านไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการสร้างตารางเวลา, คำนวณกำหนดส่ง, หรืออัตโนมัติการรายงาน, Aspose.Tasks ช่วยให้คุณจัดการข้อมูล Project ด้วยโปรแกรมโดยไม่ต้องติดตั้งบนเดสก์ท็อป, รองรับรูปแบบเข้า‑ออกกว่า 50 แบบและจัดการไฟล์หลายร้อยหน้าในโหมดใช้หน่วยความจำอย่างมีประสิทธิภาพ

## คำตอบอย่างรวดเร็ว
- **บทแนะนำครอบคลุมอะไรบ้าง?** แสดงวิธีสร้างโครงการทดสอบ, กำหนดแอตทริบิวต์ขยาย, ตั้งกำหนดส่งของงาน, และใช้สูตรเพื่อคำนวณจำนวนวันระหว่างวันที่  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks for Java (เวอร์ชันล่าสุด)  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์จริง  
- **ใช้ IDE ใดได้บ้าง?** IDE ของ Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) ที่รองรับ JDK 8+  
- **ใช้เวลานานเท่าไหร่ในการทำตาม?** ประมาณ 10‑15 นาทีเพื่อคัดลอกโค้ดและรัน

## “คำนวณจำนวนวันระหว่างวันที่” ใน Aspose.Tasks คืออะไร?
ใน Aspose.Tasks, สูตรคือสตริงที่สามารถอ้างอิงฟิลด์ของงานและทำการคำนวณได้ `[Deadline] - [Finish]` เป็นไวยากรณ์สูตรที่ Aspose.Tasks ใช้เพื่อคืนค่าความแตกต่างเป็นจำนวนวันระหว่างฟิลด์วันที่สองฟิลด์ ผลลัพธ์จะถูกเก็บเป็นค่าตัวเลขที่แทนจำนวนวันเต็ม, ซึ่งคุณสามารถแสดงในฟิลด์กำหนดเองหรือใช้ต่อในการคำนวณอื่น ๆ

## ทำไมต้องใช้ Aspose.Tasks เพื่อคำนวณจำนวนวันระหว่างวันที่?
Aspose.Tasks มี **การครอบคลุม API เต็มรูปแบบ** สำหรับทุกคุณสมบัติของ Project, Task, และ Resource, ทำงานบน Windows, Linux, และ macOS, และ **ไม่ต้องการ Microsoft Project หรือ Office** เพื่อติดตั้ง. เครื่องยนต์สามารถประมวลผลโครงการที่มี **500+ งาน** ภายในไม่กี่วินาทีบนเซิร์ฟเวอร์ทั่วไป, ทำให้เหมาะกับ CI pipelines, Docker containers, และการประมวลผลแบบแบตช์ปริมาณมาก

## วิธีตั้งกำหนดส่งสำหรับงาน
`java.util.Calendar` เป็นคลาสของ Java ที่แทนช่วงเวลาหนึ่งในเวลา. คุณตั้งกำหนดส่งโดยกำหนดค่า `java.util.Calendar` ให้กับฟิลด์ `Tsk.DEADLINE` ของงาน. หลังจากสร้างอินสแตนซ์ Calendar, ตั้งปี, เดือน, และวันให้เป็นกำหนดส่งที่ต้องการ, แล้วเรียก `task.set(Tsk.DEADLINE, calendar);`. กำหนดส่งจะถูกเก็บในไฟล์โครงการและสามารถใช้ในสูตรเช่น `[Deadline] - [Finish]`.

## วิธีกำหนดแอตทริบิวต์ขยาย
แอตทริบิวต์ขยายคือฟิลด์กำหนดเองที่เก็บผลลัพธ์ของสูตรของคุณ. คุณสร้างมันครั้งเดียว, ตั้งชื่อแทนที่เป็นมิตร, และผูกนิพจน์ `[Deadline] - [Finish]` เพื่อให้ทุกงานคำนวณช่วงเวลาโดยอัตโนมัติ. สร้างโดยการสร้างอินสแตนซ์ `ExtendedAttribute`, ตั้งค่า Alias, กำหนดสูตร, แล้วเพิ่มลงในคอลเลกชันของโครงการ.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK) 8+** – ดาวน์โหลดจากเว็บไซต์ Oracle หรือใช้ OpenJDK  
- **Aspose.Tasks for Java** – รับ JAR ล่าสุดจาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) แล้วเพิ่มลงใน classpath ของโครงการหรือใน dependencies ของ Maven/Gradle

## นำเข้าแพ็กเกจ
แรกเริ่ม, นำเข้าคลาสที่เราต้องการใช้:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างโครงการทดสอบพร้อมฟิลด์กำหนดเอง
เราจะเริ่มด้วยการ **สร้างโครงการทดสอบ** และเพิ่มฟิลด์กำหนดเองที่ภายหลังจะเก็บผลลัพธ์สูตรของเรา

```java
Project project = CreateTestProjectWithCustomField();
```

> *เคล็ดลับ:* `CreateTestProjectWithCustomField()` เป็นเมธอดช่วยที่สร้างตารางเวลาขั้นต่ำและลงทะเบียนแอตทริบิวต์ขยายพร้อมสำหรับการกำหนดสูตร

### ขั้นตอนที่ 2: กำหนดแอตทริบิวต์ขยาย (เพิ่มฟิลด์กำหนดเอง)
ต่อไปเราจะ **กำหนดแอตทริบิวต์ขยาย** – ซึ่งก็คือฟิลด์กำหนดเอง – และตั้งชื่อแทนที่เป็นมิตร. ที่นี่เราจะ **เพิ่มตรรกะฟิลด์กำหนดเอง**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** ทำให้ฟิลด์อ่านง่ายใน Project  
- **Formula** คำนวณจำนวนวันระหว่างวันที่ *Finish* ของงานและ *Deadline* – เป็นแกนหลักของ *คำนวณจำนวนวันระหว่างวันที่*

### ขั้นตอนที่ 3: ตั้งกำหนดส่งสำหรับงาน (เพิ่มงานกำหนดส่ง & ตั้งกำหนดส่งงาน)
ตอนนี้เราจะ **เพิ่มข้อมูลงานกำหนดส่ง** โดยตั้งค่าคุณสมบัติ *Deadline* ให้กับงานที่ระบุ

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- อินสแตนซ์ `Calendar` กำหนดช่วงเวลากำหนดส่งที่แน่นอน  
- `set(Tsk.DEADLINE, …)` **ตั้งกำหนดส่งของงาน** สำหรับงานที่เลือก

### ขั้นตอนที่ 4: บันทึกโครงการ (จัดการไฟล์ Microsoft Project)
สุดท้าย, เราจะ **จัดการ Microsoft Project** โดยบันทึกการเปลี่ยนแปลงลงในไฟล์ MPP

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

คุณสามารถเปิด `SaveFile.mpp` ใน Microsoft Project เพื่อดูฟิลด์กำหนดเอง, ผลลัพธ์สูตร, และกำหนดส่งที่แสดงในตารางเวลา

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **สูตรไม่ทำงาน** | ตรวจสอบให้แน่ใจว่า string `Formula` ของแอตทริบิวต์ใช้ชื่อฟิลด์ที่ถูกต้อง (เช่น `[Deadline]`, `[Finish]`) |
| **ไม่พบงาน** | ยืนยันว่า ID ของงาน (`1` ในตัวอย่าง) มีอยู่; ใช้ `project.getRootTask().getChildren().size()` เพื่อตรวจสอบ |
| **ข้อยกเว้นลิขสิทธิ์** | ใส่ลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องก่อนเรียกเมธอด API ใด ๆ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) |

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ได้, Aspose.Tasks มี API สำหรับ .NET, Java, และแพลตฟอร์มอื่น ๆ, ให้คุณจัดการไฟล์ Microsoft Project ในภาษาที่คุณเลือก

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks หรือไม่?**  
A: มีแน่นอน. ดาวน์โหลดรุ่นทดลองเต็มฟังก์ชันจาก [Aspose.Tasks download page](https://releases.aspose.com/)

**Q: จะหาเอกสารรายละเอียดของ Aspose.Tasks ได้จากที่ไหน?**  
A: เอกสารอย่างเป็นทางการอยู่ที่ [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)

**Q: จะรับการสนับสนุนสำหรับ Aspose.Tasks อย่างไร?**  
A: เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อถามคำถามและแบ่งปันประสบการณ์กับชุมชน

**Q: ต้องการลิขสิทธิ์ชั่วคราวสำหรับการประเมินหรือไม่?**  
A: มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบระยะสั้น; คุณสามารถขอได้จาก [temporary license request page](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-10-05  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (เวอร์ชันล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [How to create extended attribute in Java with Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}