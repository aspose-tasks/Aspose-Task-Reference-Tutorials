---
date: 2026-05-31
description: เรียนรู้วิธีดึงเวอร์ชันของโปรเจกต์และดึงวันที่บันทึกล่าสุดจากไฟล์ MS
  Project ด้วย Aspose.Tasks สำหรับ Java คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: กำหนดเวอร์ชันของโปรเจกต์ด้วย Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีดึงเวอร์ชันของโปรเจกต์ – Aspose Tasks Java บทเรียน
url: /th/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการรับเวอร์ชันของโครงการ – Aspose Tasks Java Tutorial

ใน **Aspose Tasks Java tutorial** นี้ คุณจะได้เรียนรู้ **วิธีการรับเวอร์ชันของโครงการ** ของไฟล์ Microsoft Project และวิธี **ดึงวันที่บันทึกล่าสุด** โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java การรู้เวอร์ชันของไฟล์และเวลาบันทึกช่วยให้คุณหลีกเลี่ยงปัญหาความเข้ากันได้, บังคับใช้นโยบายการย้าย, และเก็บบันทึกการตรวจสอบที่แม่นยำ เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการพิมพ์เวอร์ชันและวันที่—เพื่อให้คุณสามารถฝังการตรวจสอบนี้ลงในแอปพลิเคชัน Java ใดก็ได้ด้วยความมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไรบ้าง?** การกำหนดเวอร์ชันของไฟล์ MS Project และวันที่บันทึกล่าสุดด้วย Aspose.Tasks สำหรับ Java.  
- **ฉันต้องติดตั้ง Microsoft Project หรือไม่?** ไม่จำเป็น, Aspose.Tasks ทำงานโดยอิสระจาก Microsoft Project.  
- **รูปแบบไฟล์ใดที่รองรับ?** ไฟล์ Project ที่ใช้ XML เช่น MPP และ XML ได้รับการสนับสนุนเต็มรูปแบบ.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการตรวจสอบเวอร์ชันพื้นฐาน.  
- **ต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.

## Aspose Tasks Java Tutorial คืออะไร?
บทเรียน `Aspose.Tasks` Java เป็นคู่มือสั้น ๆ ที่ทำให้คุณได้ลงมือจริงซึ่งแสดงวิธีการโต้ตอบกับข้อมูล Microsoft Project อย่างโปรแกรมมิ่ง มันแสดงวิธีการอ่าน, แก้ไข, และวิเคราะห์ข้อมูลโครงการโดยไม่ต้องติดตั้ง Microsoft Project บนเซิร์ฟเวอร์ นอกจากนี้ยังครอบคลุมการโหลดไฟล์, การเข้าถึงคุณสมบัติ, และการบันทึกการเปลี่ยนแปลง, ทำให้ผู้พัฒนาสามารถอัตโนมัติการจัดการโครงการได้อย่างมีประสิทธิภาพ.

## ทำไมต้องใช้ Aspose.Tasks เพื่อกำหนดเวอร์ชันของโครงการ?
Aspose.Tasks ให้ **เมตาดาต้าเวอร์ชันที่แม่นยำ** และ **เวลาบันทึกล่าสุด** ในขณะที่ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java มันประมวลผลไฟล์ได้ถึง **500 หน้าในเวลาน้อยกว่า 2 วินาที** บน CPU มาตรฐาน 2.5 GHz ทำให้เหมาะสำหรับการอัตโนมัติแบบแบตช์และสถานการณ์การย้ายข้อมูลขนาดใหญ่.

## ข้อกำหนดเบื้องต้น
Before we begin, ensure you have:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java JAR** – ดาวน์โหลดจาก [website](https://releases.aspose.com/tasks/java/) และเพิ่มไปยัง classpath ของโปรเจกต์ของคุณ.  
3. **MS Project file** – ไฟล์ Project ที่ใช้ XML (เช่น `input.xml`) ที่คุณต้องการตรวจสอบ.  

> **Pro tip:** เก็บไฟล์ Project ไว้ในโฟลเดอร์ `data` แยกเฉพาะเพื่อให้เส้นทางเป็นระเบียบและหลีกเลี่ยงการเขียนทับโดยบังเอิญ.

## นำเข้าแพ็กเกจ
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## วิธีตั้งค่าไดเรกทอรีโครงการ
To correctly locate your project files, create a dedicated directory within your application structure and store all input files there. This keeps the code clean and avoids path‑related errors when loading files. Use a clear variable name for the directory path, which can be absolute or relative to the project root.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ที่ไฟล์ `input.xml` อยู่.

## วิธีโหลดโครงการ
`Project` is the primary Aspose.Tasks object that represents a Microsoft Project file in memory, giving you access to all project properties and collections. After creating the `Project` instance, you can query its fields, iterate over tasks, or modify data before saving the file back to disk.

```java
Project project = new Project(dataDir + "input.xml");
```

หากไฟล์ของคุณมีชื่อแตกต่างกัน ให้ปรับ `"input.xml"` ตามนั้น.

## วิธีกำหนดเวอร์ชันของโครงการ
`Prj.SAVE_VERSION` is a property that indicates the version number of Microsoft Project that saved the file. `Prj.LAST_SAVED` is a property that stores the date and time when the file was last saved. `Prj.SAVE_VERSION` returns the numeric version of the Microsoft Project application that saved the file (e.g., 12 for Project 2010). `Prj.LAST_SAVED` provides the exact date and time of the most recent save operation.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

These values let you programmatically enforce version‑specific business rules or generate audit reports.

## วิธีแสดงผลลัพธ์
After retrieving the version and last‑saved information, you typically want to output it to the console or a log file. Use `System.out.println` to display the values, formatting the date as needed. This confirms that the extraction succeeded and provides immediate feedback during development or in automated scripts.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | เหตุผล | วิธีแก้ |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | ไฟล์ไม่พบหรือเส้นทางไม่ถูกต้อง | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้เส้นทางแบบ absolute สำหรับการทดสอบ. |
| หมายเลขเวอร์ชันที่ไม่คาดคิด (เช่น 0) | กำลังโหลดไฟล์ XML ที่ไม่ใช่ Project | ตรวจสอบว่าไฟล์เป็นไฟล์ Microsoft Project ที่ถูกต้อง (MPP/XML). |
| ข้อยกเว้นใบอนุญาต | ใช้รุ่นทดลองโดยไม่มีใบอนุญาตที่ถูกต้องในสภาพการผลิต | ใช้ใบอนุญาต Aspose.Tasks ของคุณ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับ .NET, Java, และ C++ รวมถึงอื่น ๆ  

**Q: Aspose.Tasks เหมาะกับโครงการขนาดใหญ่หรือไม่?**  
A: แน่นอน; มันสามารถประมวลผลโครงการหลายร้อยหน้าในไม่กี่วินาทีโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ  

**Q: ฉันสามารถปรับแต่งข้อมูลโครงการโดยใช้ Aspose.Tasks ได้หรือไม่?**  
A: ใช่, คุณสามารถแก้ไขงาน, ทรัพยากร, ปฏิทิน, และองค์ประกอบโครงการอื่น ๆ ผ่าน API  

**Q: Aspose.Tasks ต้องการการติดตั้ง Microsoft Project หรือไม่?**  
A: ไม่, ไลบรารีทำงานโดยอิสระและไม่ต้องการ Microsoft Project บนเครื่องโฮสต์  

**Q: มีการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks หรือไม่?**  
A: มี, คุณสามารถขอความช่วยเหลือจากฟอรัม Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).  

**คำถามเพิ่มเติม**

**Q: ฉันจะดึงคุณสมบัติโครงการอื่น (เช่น ผู้เขียน, บริษัท) อย่างไร?**  
A: ใช้ `project.get(Prj.AUTHOR)` หรือ `project.get(Prj.COMPANY)` ในลักษณะเดียวกับการดึงเวอร์ชัน  

**Q: ฉันสามารถตรวจสอบเวอร์ชันของไฟล์ MPP (ไบนารี) ได้หรือไม่?**  
A: ใช่, Aspose.Tasks โหลดไฟล์ `.mpp` โดยตรง; คุณสมบัติ `Prj.SAVE_VERSION` ทำงานกับรูปแบบไบนารีเช่นกัน  

**Q: มีวิธีอัปเกรดไฟล์โครงการเก่าเป็นเวอร์ชันใหม่โดยโปรแกรมได้หรือไม่?**  
A: โหลดไฟล์เก่า, แล้วบันทึกด้วย `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks จะเขียนไฟล์ในรูปแบบล่าสุดโดยค่าเริ่มต้น  

## สรุป
You’ve now mastered **how to get project version** and **retrieve last saved date** from MS Project files using Aspose.Tasks for Java. Incorporate these snippets into automation pipelines, reporting tools, or migration utilities to guarantee you always know the exact Project version you’re handling.

---

**อัปเดตล่าสุด:** 2026-05-31  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [ตั้งค่าวันเริ่มต้นของโครงการใน MS Project ด้วย Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [อ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks for Java](/tasks/java/project-data-reading/read-project-database/)
- [บันทึกโครงการเป็นเทมเพลต, CSV, และข้อความด้วย Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}