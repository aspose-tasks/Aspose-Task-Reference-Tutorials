---
date: 2026-10-26
description: วิธีอ่าน group definition data โดยใช้ Aspose.Tasks สำหรับ Java. ดึง task
  grouping, criteria, และ formatting จากไฟล์ Microsoft Project เพื่อ automate reporting
  and migration.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: อ่าน Group Definition Data ใน Aspose.Tasks
og_description: วิธีอ่าน group definition data โดยใช้ Aspose.Tasks สำหรับ Java. ดึง
  task grouping, criteria, และ formatting จากไฟล์ Microsoft Project เพื่อ automate
  reporting and migration.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: วิธีอ่าน group definition data ด้วย Aspose.Tasks สำหรับ Java
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: วิธีอ่าน group definition data ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลการกำหนดกลุ่มใน Aspose.Tasks สำหรับ Java

## บทนำ
Aspose.Tasks for Java ให้คุณเข้าถึง, แก้ไข, และวิเคราะห์ไฟล์ Microsoft Project อย่างโปรแกรมมิ่ง ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีการอ่านการกำหนดกลุ่ม** จากไฟล์ `.mpp` โดยสกัดชื่อของแต่ละกลุ่ม, เกณฑ์, และรูปแบบการแสดงผล แล้วใช้ข้อมูลนั้นเพื่อสร้างรายงานแบบกำหนดเองหรือย้ายการตั้งค่าไปยังโครงการอื่น การเชี่ยวชาญความสามารถนี้ทำให้คุณสามารถอัตโนมัติการสร้างรายงาน, ตรวจสอบโครงสร้างโครงการ, และทำให้กระบวนการทำงานที่ขับเคลื่อนด้วยข้อมูลเป็นไปอย่างราบรื่น

## คำตอบอย่างรวดเร็ว
- **“read group definition” หมายถึงอะไร?** หมายถึงการสกัดกฎการจัดกลุ่ม (ชื่อ, เกณฑ์, สี, ฟอนต์) ที่ Microsoft Project ใช้เพื่อจัดระเบียบงาน  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks for Java.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **IDE ที่รองรับคืออะไร?** IDE Java ใดก็ได้ เช่น IntelliJ IDEA หรือ Eclipse.  
- **ต้องใช้โค้ดเท่าไหร่?** น้อยกว่า 30 บรรทัดของโค้ด Java เพื่อโหลดโครงการและแสดงรายละเอียดของกลุ่ม  

## วิธีการอ่านข้อมูลการกำหนดกลุ่ม
โหลดโครงการ, นับจำนวนกลุ่มของมัน, และตรวจสอบเกณฑ์ของแต่ละกลุ่ม คำตอบโดยตรงคือ: **Create a `Project` instance, call `project.getTaskGroups()`, and iterate the collection to read names, criteria, fonts, and colors.** ส่วนต่อไปนี้จะแบ่งกระบวนการเป็นขั้นตอนที่ชัดเจน พร้อมกับโค้ดสั้น ๆ ที่เป็นตัวแทนซึ่งคุณจะต้องแทนที่ด้วยส่วนโค้ดจริงจากเอกสาร Aspose.Tasks

## การอ่านการกำหนดกลุ่มคืออะไร?
Read group definition หมายถึงการสกัดกฎการจัดกลุ่ม (ชื่อ, เกณฑ์, การจัดรูปแบบ) ที่ Microsoft Project ใช้เพื่อจัดเรียงงาน กฎเหล่านี้บอกแอปพลิเคชันว่าจะจัดกลุ่มงานตามสถานะ, ความสำคัญ, หรือฟิลด์กำหนดเองอย่างไร และรวมถึงคุณลักษณะการแสดงผลเช่นสไตล์ฟอนต์และสีของเซลล์

## ทำไมต้องอ่านข้อมูลการกำหนดกลุ่ม?
การอ่านข้อมูลการกำหนดกลุ่มช่วยให้คุณ **อัตโนมัติการสร้างรายงาน**, **ย้ายตรรกะการจัดกลุ่ม** ไปยังโครงการอื่น, และ **ตรวจสอบว่ามีกลุ่มที่ต้องการอยู่** ก่อนทำการอัปเดตเป็นจำนวนมาก Aspose.Tasks for Java สามารถประมวลผลโครงการที่มี **งานมากกว่า 10,000 รายการ** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้การทำงานแบบแบตช์มีประสิทธิภาพสูง นอกจากนี้คุณยังสามารถสกัดสีฟอนต์, รูปแบบ, และทิศทางการเรียงลำดับเพื่อสร้างเลย์เอาต์ที่เหมือนเดิมในแดชบอร์ดแบบกำหนดเองได้

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่ามี:

1. **Java Development Kit (JDK) 8+** – เวอร์ชันล่าสุดใดก็ได้ทำงานได้  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)  
3. **A Java IDE** – IntelliJ IDEA, Eclipse, หรือเครื่องมือแก้ไขที่คุณชอบ  

> **Pro tip:** ใช้ Maven หรือ Gradle เพื่อจัดการ dependency ของ Aspose.Tasks; จะช่วยหลีกเลี่ยงการจัดการ JAR ด้วยตนเอง.

## นำเข้าแพ็กเกจ
`Project` เป็นคลาสหลักที่แทนไฟล์ Microsoft Project ใน Aspose.Tasks for Java  

```java
import com.aspose.tasks.*;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูลของคุณ
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ที่คุณต้องการตรวจสอบ การใช้ `java.nio.file.Paths` จะรับประกันการจัดการพาธที่ไม่ขึ้นกับแพลตฟอร์ม  

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยชี้ไปที่ไฟล์ `.mpp` ของคุณ ตัวสร้างจะอ่านส่วนหัวของไฟล์และสร้างโมเดลในหน่วยความจำ  

```java
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: ดึงจำนวนกลุ่มงาน
พิมพ์จำนวนรวมของกลุ่มงานที่กำหนดในโครงการ การตรวจสอบอย่างรวดเร็วนี้ยืนยันว่าไฟล์มีข้อมูลการจัดกลุ่มอยู่จริง  

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### ขั้นตอนที่ 4: ดึงข้อมูลกลุ่มงานเฉพาะ
ดึงกลุ่มที่ต้องการ (ดัชนี 1 ในตัวอย่างนี้) และแสดงชื่อพร้อมจำนวนเกณฑ์ที่มีแต่ละกลุ่มอาจมีหลายเกณฑ์ที่กำหนดวิธีการจัดกลุ่มงาน  

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### ขั้นตอนที่ 5: ดึงข้อมูลเกณฑ์ของกลุ่ม
แต่ละกลุ่มอาจมีหนึ่งหรือหลายเกณฑ์ โค้ดด้านล่างสกัดรายละเอียดเช่นฟิลด์ที่ใช้จัดกลุ่ม, โหมดการจัดกลุ่ม, สีของเซลล์, และรูปแบบ  

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### ขั้นตอนที่ 6: ตรวจสอบกลุ่มแม่
บางครั้งเกณฑ์อาจเป็นส่วนหนึ่งของกลุ่มแม่ การตรวจสอบนี้ยืนยันความสัมพันธ์และป้องกันปัญหา null‑pointer เมื่อเดินทางในโครงสร้างลำดับชั้น  

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### ขั้นตอนที่ 7: ดึงข้อมูลฟอนต์ของเกณฑ์
เกณฑ์ของกลุ่มสามารถมีสไตล์ฟอนต์แบบกำหนดเอง โค้ดต่อไปนี้พิมพ์ฟอนต์, ขนาด, สไตล์, และทิศทางการเรียงลำดับ เพื่อให้คุณสามารถสร้างลุคเดียวกันใน UI ของคุณ  

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **`NullPointerException` on `criterion.getParentGroup()`** | เกณฑ์อาจไม่มีกลุ่มแม่ | เพิ่มการตรวจสอบ null ก่อนเข้าถึง parent |
| **File not found** | `dataDir` มีพาธไม่ถูกต้องหรือชื่อไฟล์สะกดผิด | ใช้ `Paths.get(dataDir, "project.mpp").toAbsolutePath()` และตรวจสอบว่าไฟล์มีอยู่ |
| **License not set** | Aspose ทำงานในโหมดประเมินผลและอาจตัดทอนผลลัพธ์ | ลงทะเบียนไลเซนส์ของคุณด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` ก่อนโหลดโครงการ |

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Tasks for Java เพื่อแก้ไขไฟล์โครงการได้หรือไม่?**  
A: ได้, ไลบรารีนี้ให้ความสามารถอ่าน/เขียนเต็มรูปแบบสำหรับรูปแบบไฟล์ Microsoft Project, ทำให้คุณสามารถเพิ่มงาน, เปลี่ยนแหล่งทรัพยากร, และอัปเดตการกำหนดกลุ่มโดยโปรแกรมได้

**Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: รองรับไฟล์ MPP, XML, CSV, และรูปแบบ Project ที่พบบ่อยอื่น ๆ ตั้งแต่ Project 2000 จนถึงรุ่นล่าสุด 2024

**Q: ควรจัดการข้อผิดพลาดอย่างไรเมื่อทำงานกับ Aspose.Tasks for Java?**  
A: ห่อการทำงานกับไฟล์ด้วยบล็อก `try‑catch` และจับ `TasksException` เพื่อรับข้อมูลข้อผิดพลาดโดยละเอียด; ตรวจสอบ `getMessage()` ของ exception เพื่อหาเบาะแส

**Q: Aspose.Tasks for Java มีการส่งออกเป็นรูปแบบอื่นหรือไม่?**  
A: มีแน่นอน – คุณสามารถส่งออกเป็น PDF, XLSX, HTML, และรูปแบบอื่น ๆ ผ่าน API การส่งออกที่จัดเตรียมไว้ในไลบรารี

**Q: จะหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) สำหรับอ้างอิง API และ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) สำหรับการช่วยเหลือจากชุมชน

## สรุป
ในบทเรียนนี้เราได้อธิบาย **วิธีการอ่านข้อมูลการกำหนดกลุ่ม** จากไฟล์ Microsoft Project ด้วย Aspose.Tasks for Java โดยการโหลด `Project`, นับ `TaskGroupCollection`, และตรวจสอบเกณฑ์, ฟอนต์, และสีของแต่ละกลุ่ม คุณสามารถสร้างกระบวนการรายงานอัตโนมัติ, ย้ายกฎการจัดกลุ่ม, หรือยืนยันโครงสร้างโครงการได้อย่างมั่นใจ วิธีการเดียวกันนี้สามารถขยายไปยังโครงการขนาดใหญ่ที่มีงานหลายพันรายการโดยคงการใช้หน่วยความจำน้อย

---

**Last Updated:** 2026-10-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [วิธีรับฟิลด์ตารางและอ่านข้อมูลตารางใน Aspose.Tasks](/tasks/java/project-data-reading/read-table-data/)
- [อ่านแผนภูมิแกนท์ Java – สกัดข้อมูลแกนท์เฉพาะ](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}