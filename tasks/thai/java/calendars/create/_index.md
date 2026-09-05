---
date: 2026-08-03
description: เรียนรู้วิธีสร้าง ms project calendar, เพิ่ม calendar ไปยังโครงการ, และบันทึกโครงการเป็น
  XML ด้วย Aspose.Tasks for Java
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: เพิ่ม Calendar ไปยัง Project ด้วย Aspose.Tasks
og_description: สร้าง ms project calendar อย่างอัตโนมัติด้วย Aspose.Tasks for Java.
  เพิ่ม calendars, ปรับแต่ง schedules, และส่งออกเป็น XML ภายในไม่กี่นาที.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: สร้าง ms project calendar ด้วย Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: สร้าง ms project calendar ด้วย Aspose.Tasks for Java
url: /th/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างปฏิทิน ms project ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในกระบวนการจัดการโครงการสมัยใหม่ ความสามารถในการ **สร้างปฏิทิน ms project** ด้วยโปรแกรมสามารถประหยัดเวลาการแก้ไขด้วยมือหลายชั่วโมง Aspose.Tasks สำหรับ Java มอบ API ที่สะอาดและปลอดภัยต่อประเภทเพื่อจัดการไฟล์ Microsoft Project โดยไม่ต้องเปิดไคลเอนต์บนเดสก์ท็อป ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเพิ่มปฏิทิน วิธีสร้างปฏิทิน MS Project และวิธีบันทึกโครงการเป็น XML—ทั้งหมดด้วยเพียงไม่กี่บรรทัดของโค้ด Java

## คำตอบสั้น
- **“สร้างปฏิทิน ms project” หมายถึงอะไร?**  
  หมายถึงการแทรกการกำหนดเวลาทำงานใหม่ (ปฏิทิน) ลงในไฟล์ Microsoft Project ผ่านโค้ด  
- **ไลบรารีที่จัดการเรื่องนี้คืออะไร?**  
  Aspose.Tasks สำหรับ Java มีคลาส `Calendar` และคอนเทนเนอร์ `Project` เพื่อจัดการปฏิทิน  
- **ต้องใช้ลิขสิทธิ์หรือไม่?**  
  ลิขสิทธิ์ประเมินชั่วคราวใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถบันทึกไฟล์เป็น XML ได้หรือไม่?**  
  ได้ — ใช้ `SaveFileFormat.Xml` เพื่อส่งออกโครงการเป็นไฟล์ XML  
- **ข้อกำหนดเบื้องต้นคืออะไร?**  
  Java JDK 8+ และไฟล์ JAR ของ Aspose.Tasks สำหรับ Java อยู่ใน classpath ของคุณ

## “สร้างปฏิทิน ms project” คืออะไร?
การสร้างปฏิทิน MS Project หมายถึงการเพิ่มการกำหนดปฏิทินใหม่ลงในไฟล์ Project ด้วยโปรแกรม โดยระบุวันทำงาน, ข้อยกเว้น, และชั่วโมงทำงานต่อวัน แล้วกำหนดปฏิทินนั้นให้กับงาน, ทรัพยากร, หรือโครงการทั้งหมด เพื่อให้การคำนวณกำหนดเวลาอิงตามเวลาทำงานที่กำหนดไว้

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java เพื่อเพิ่มปฏิทินในโครงการ?
คุณควรใช้ Aspose.Tasks สำหรับ Java เพราะให้ API ที่ปลอดภัยต่อประเภทเต็มรูปแบบ ทำงานได้โดยไม่ต้องติดตั้ง Microsoft Project, รองรับเวอร์ชัน Project หลักทั้งหมด (2007‑2021, ครอบคลุม 5+ รุ่น) และสามารถส่งออกเป็น XML, MPP, และ **10+** ฟอร์แมตอื่น ๆ ทำให้สามารถสร้างปฏิทินจำนวนมากโดยอัตโนมัติบนเซิร์ฟเวอร์ใดก็ได้

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8 หรือใหม่กว่า** ที่ติดตั้งและกำหนดค่าเรียบร้อย  
- **ไลบรารี Aspose.Tasks สำหรับ Java** – ดาวน์โหลดจาก [เว็บไซต์อย่างเป็นทางการ](https://releases.aspose.com/tasks/java/) และเพิ่มไฟล์ JAR ไปยัง classpath ของโปรเจกต์ของคุณ  
- IDE หรือเครื่องมือสร้าง (Maven/Gradle) ตามที่คุณเลือกใช้

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: นำเข้าแพ็กเกจ Aspose.Tasks ที่จำเป็น
แรกเริ่ม นำคลาสของ Aspose.Tasks เข้ามาในสโคปเพื่อให้คุณสามารถทำงานกับโครงการและปฏิทินได้

```java
import com.aspose.tasks.*;
```

### ขั้นตอนที่ 2: ตั้งค่าพาธไดเรกทอรีข้อมูล
กำหนดตำแหน่งที่ไฟล์โครงการที่สร้างขึ้นจะถูกเขียนออกไป แทนที่ตัวแปรตำแหน่งที่เก็บไว้ด้วยพาธแบบสัมพัทธ์หรือแบบเต็มบนเครื่องของคุณ

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 3: สร้างอินสแตนซ์ Project ใหม่
`Project` คือคลาสหลักที่แทนไฟล์ Microsoft Project ในหน่วยความจำ

```java
Project prj = new Project();
```

### ขั้นตอนที่ 4: กำหนดปฏิทินที่ต้องการเพิ่ม
`Calendar` กำหนดตารางเวลาที่มีวันทำงาน, ข้อยกเว้น, และเวลาทำงานต่อวันสำหรับโครงการ

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **เคล็ดลับ:** หลังจากเพิ่มปฏิทินแล้ว คุณสามารถปรับวันทำงานด้วย `cal1.getWeekDays().add(...)` และตั้งชั่วโมงทำงานต่อวันโดยใช้ `cal1.getBaseCalendar().setWorkingTime(...)`

### ขั้นตอนที่ 5: บันทึกโครงการ (บันทึกโครงการเป็น XML)
`SaveFileFormat.Xml` บอก Aspose.Tasks ให้เขียนโครงการในรูปแบบ XML

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### ขั้นตอนที่ 6: แสดงข้อความเสร็จสิ้น
แจ้งผู้ใช้ว่าการดำเนินการเสร็จสมบูรณ์แล้ว

```java
System.out.println("Process completed Successfully");
```

โดยทำตามหกขั้นตอนสั้น ๆ นี้ คุณได้ **เพิ่มปฏิทินลงในโครงการ** และบันทึกผลลัพธ์เป็นไฟล์ XML เรียบร้อยแล้ว

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`NullPointerException` ที่ `prj.getCalendars()`** | วัตถุ Project ไม่ได้ถูกสร้างอย่างถูกต้อง | ตรวจสอบให้แน่ใจว่าเรียก `new Project()` ก่อนเข้าถึงปฏิทิน |
| **ไฟล์ไม่พบเมื่อบันทึก** | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | สร้างโฟลเดอร์ก่อนหรือใช้พาธแบบเต็ม |
| **ชื่อปฏิทินแสดงเป็น “no info”** | ใช้ชื่อแทนในตัวอย่าง | แทนที่ด้วยชื่อที่มีความหมายสื่อถึงตารางเวลา (เช่น “US Holiday Calendar”) |
| **XML ที่บันทึกไม่เปิดใน MS Project** | ใช้เวอร์ชัน Aspose.Tasks ที่ล้าสมัย | อัปเดตเป็นเวอร์ชันล่าสุดของ Aspose.Tasks สำหรับ Java |

## คำถามที่พบบ่อย

**ถาม: Aspose.Tasks สามารถจัดการปฏิทินที่ซับซ้อนพร้อมหลายข้อยกเว้นได้หรือไม่?**  
ตอบ: ได้ – หลังจากเพิ่มปฏิทินแล้ว คุณสามารถกำหนดข้อยกเว้น, ชั่วโมงทำงาน, และวันหยุดโดยใช้คลาส `WeekDay` และ `Exception`

**ถาม: สามารถกำหนดปฏิทินใหม่ให้กับงานเฉพาะได้หรือไม่?**  
ตอบ: แน่นอน. ดึงงานด้วย `prj.getRootTask().getChildren().add("Task Name")` แล้วตั้งค่า `task.set(Tsk.CALENDAR, cal3);`

**ถาม: ไลบรารีรองรับการบันทึกในฟอร์แมตอื่น ๆ เช่น MPP หรือไม่?**  
ตอบ: ได้. แทนที่ `SaveFileFormat.Xml` ด้วย `SaveFileFormat.Mpp` หรือ `SaveFileFormat.P6` ตามต้องการ; Aspose.Tasks รองรับ **12** ฟอร์แมตผลลัพธ์

**ถาม: จำเป็นต้องมีลิขสิทธิ์สำหรับการสร้างบิลด์หรือไม่?**  
ตอบ: ลิขสิทธิ์ประเมินชั่วคราวเพียงพอสำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต

**ถาม: จะหาความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?**  
ตอบ: ฟอรั่มชุมชนของ Aspose.Tasks เป็นแหล่งข้อมูลที่ยอดเยี่ยม: [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)

---

**อัปเดตล่าสุด:** 2026-08-03  
**ทดสอบด้วย:** Aspose.Tasks สำหรับ Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีกำหนดวันทำงานในปฏิทิน MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [วิธีตั้งค่าปฏิทินโครงการ Java ด้วย Aspose.Tasks](/tasks/java/calendars/properties/)
- [สร้างข้อยกเว้นปฏิทินแบบกำหนดเองด้วย Aspose.Tasks สำหรับ Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}