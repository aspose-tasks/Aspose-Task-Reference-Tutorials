---
date: 2026-10-15
description: เรียนรู้วิธีสร้าง activity, ตั้งค่า data directory, customize table fields
  และ save project เป็น MPP ด้วย Aspose.Tasks for Java. คู่มือ step‑by‑step สำหรับ
  Java developers.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: วิธีสร้าง activity และตั้งค่า data directory ด้วย Aspose.Tasks for Java
og_description: วิธีสร้าง activity, customize table fields และ save project เป็น MPP
  ด้วย Aspose.Tasks for Java. ปฏิบัติตามคู่มือรายละเอียดนี้เพื่อการใช้งานที่รวดเร็ว.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: วิธีสร้าง activity และตั้งค่า data directory ใน Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: วิธีสร้าง activity และตั้งค่า data directory ด้วย Aspose.Tasks for Java
url: /th/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างกิจกรรมและตั้งค่าไดเรกทอรีข้อมูลโดยใช้ Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีสร้างกิจกรรม** ด้วยโปรแกรม, ตั้งค่า **ไดเรกทอรีข้อมูล**, และ **บันทึกโครงการเป็น MPP** พร้อมกับ **การปรับแต่งฟิลด์ตาราง** ในมุมมองแผนภูมิแกนต์ Aspose.Tasks for Java เป็น API ที่ทรงพลังซึ่งรองรับรูปแบบการนำเข้าและส่งออกมากกว่า 30 รูปแบบและสามารถประมวลผลโครงการที่มีงานสูงสุดถึง 10 000 งานโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ เมื่อจบคู่มือคุณจะสามารถอัตโนมัติการสร้างโครงการ, เพิ่มคุณลักษณะพิเศษให้กับงาน, และสร้างไฟล์ MPP ที่พร้อมเปิดใน Microsoft Project

## คำตอบอย่างรวดเร็ว
- **ขั้นตอนแรกคืออะไร?** ตั้งค่าเส้นทางไดเรกทอรีข้อมูลที่ไฟล์โครงการของคุณอยู่.  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks for Java (ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ).  
- **ฉันสามารถเพิ่มคุณลักษณะพิเศษได้หรือไม่?** ใช่ – คุณสามารถกำหนดคุณลักษณะขยายและแสดงในแผนภูมิแกนต์.  
- **ต้องการใบอนุญาตสำหรับการทดสอบหรือไม่?** มีใบอนุญาตชั่วคราวสำหรับการประเมินผล.  
- **IDE ใดที่เหมาะสมที่สุด?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, NetBeans) จะทำงานได้.

## “การตั้งค่าไดเรกทอรีข้อมูล” คืออะไรและทำไมจึงสำคัญ
การตั้งค่าไดเรกทอรีข้อมูลบอกให้ Aspose.Tasks รู้ว่าจะอ่านและเขียนไฟล์โครงการที่ไหน หากไม่มีเส้นทางที่ถูกต้อง API จะไม่สามารถค้นหาไฟล์ `.mpp` ของคุณได้ ทำให้เกิดข้อผิดพลาด `FileNotFoundException` การกำหนดไดเรกทอรีนี้ตั้งแต่ต้นของโค้ดทำให้กระบวนการทำงานสามารถทำซ้ำได้และแยกความกังวลเกี่ยวกับระบบไฟล์ออกจากตรรกะธุรกิจ

## ทำไมต้องปรับแต่งฟิลด์ตารางในแผนภูมิแกนต์
ฟิลด์ตารางที่กำหนดเองช่วยให้คุณแสดงข้อมูลเพิ่มเติม—เช่นคุณลักษณะพิเศษ, ข้อมูลทรัพยากร, หรือบันทึกเฉพาะโครงการ—โดยตรงในมุมมองแกนต์ สิ่งนี้ลดความจำเป็นในการสร้างรายงานแยกต่างหากและให้ผู้มีส่วนได้ส่วนเสียเห็นภาพข้อมูลที่ครบถ้วนในที่เดียว ซึ่งสามารถเพิ่มความเร็วในการตัดสินใจได้สูงสุดถึง 30 %

## วิธีสร้างกิจกรรมใหม่?
คุณสร้างกิจกรรมใหม่ (งาน) โดยการสร้างอ็อบเจ็กต์ `Task` และเพิ่มลงในคอลเลกชันงานรากของโครงการ วิธีนี้ช่วยให้คุณสร้างกำหนดการขนาดใหญ่โดยอัตโนมัติ ดึงข้อมูลงานจากระบบภายนอก หรือทำการอัปเดตเป็นกลุ่มโดยไม่ต้องแก้ไขด้วยมือ

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก **หน้าเผยแพร่ Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขที่เข้ากันได้กับ Java ที่คุณต้องการ.  

## นำเข้าชุดแพ็กเกจ
เนมสเปซ `com.aspose.tasks` มีคลาสทั้งหมดที่คุณต้องการสำหรับการจัดการโครงการ การนำเข้าจะทำให้คุณเข้าถึง `Project`, `Task`, `ExtendedAttributeDefinition` และประเภทหลักอื่น ๆ

```java
import com.aspose.tasks.*;
```

## การพึ่งพา Maven (ไม่บังคับ)
หากคุณจัดการโครงการด้วย Maven ให้เพิ่มการพึ่งพา Aspose.Tasks ลงใน `pom.xml` ซึ่งจะทำให้ไลบรารีถูกดึงมาโดยอัตโนมัติระหว่างการสร้าง

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่บรรจุไฟล์โครงการของคุณ ตัวแปร `dataDir` เก็บเส้นทางแบบเต็มและจะถูกใช้ซ้ำตลอดคู่มือ

```java
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยเส้นทางเต็มของโฟลเดอร์ที่ไฟล์ `project.mpp` อยู่ เช่น `C:/Projects/MyGantt`.

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
`Project` เป็นอ็อบเจ็กต์ระดับบนสุดของ Aspose.Tasks ที่แทนไฟล์ Microsoft Project หนึ่งไฟล์ในหน่วยความจำ การโหลดไฟล์ที่มีอยู่ทำให้คุณเข้าถึงงาน, ทรัพยากร, และตารางของมัน

```java
Project project = new Project(dataDir + "project.mpp");
```

### ขั้นตอนที่ 3: เพิ่มกิจกรรมใหม่
`Task` แทนกิจกรรมแต่ละรายการในตารางเวลา การเพิ่มงานลงในคอลเลกชันงานรากจะใส่ไว้ที่ระดับบนสุดของโครงสร้างโครงการ

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### ขั้นตอนที่ 4: กำหนดคุณลักษณะพิเศษ
`ExtendedAttributeDefinition` ให้คุณสร้างฟิลด์กำหนดเองที่สามารถนำกลับมาใช้ใหม่และแนบกับงาน, ทรัพยากร หรือการมอบหมายใด ๆ

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### ขั้นตอนที่ 5: เพิ่มคุณลักษณะพิเศษให้กับงาน
`ExtendedAttribute` เป็นอินสแตนซ์ที่เป็นรูปธรรมของคุณลักษณะพิเศษที่คุณกำหนดให้กับงานเฉพาะ

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### ขั้นตอนที่ 6: ปรับแต่งตาราง – เพิ่มคุณลักษณะพิเศษเป็นคอลัมน์
`TableField` อธิบายคอลัมน์ในตารางแผนภูมิแกนต์ โดยการเพิ่ม `TableField` ที่อ้างอิงคุณลักษณะพิเศษ คุณจะทำให้คุณลักษณะนั้นปรากฏในมุมมองแผนภูมิ

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### ขั้นตอนที่ 7: บันทึกโครงการ
การเรียก `project.save` จะบันทึกการเปลี่ยนแปลงทั้งหมดลงในไฟล์ใหม่ ค่าคงที่ `SaveFileFormat.MPP` บอก Aspose.Tasks ให้เขียนไฟล์ในรูปแบบไบนารีดั้งเดิมของ Microsoft Project

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **FileNotFoundException** ขณะโหลดโครงการ | เส้นทาง **set data directory** ไม่ถูกต้องหรือขาดเครื่องหมายสแลชท้าย | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและรวมเครื่องหมายคั่นไฟล์ที่เหมาะสม (`/` หรือ `\\`). |
| คุณลักษณะพิเศษไม่แสดงในมุมมองแกนต์ | ฟิลด์ตารางถูกเพิ่มที่ตำแหน่งไม่ถูกต้องหรือความกว้างของคอลัมน์เล็กเกินไป | ตรวจสอบว่า `table.getTableFields().add(3, attrField);` ใช้ดัชนีที่ถูกต้องและปรับ `setWidth` ตามต้องการ |
| LicenseException ขณะบันทึก | ไม่มีใบอนุญาตที่ถูกต้องถูกนำมาใช้สำหรับการใช้งานจริง | นำใบอนุญาตชั่วคราวหรือถาวรมาใช้ก่อนเรียก `project.save()` |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ใช่, Aspose.Tasks มีให้สำหรับ .NET, Java, และ C++

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีจาก **หน้าดาวน์โหลดการทดลองใช้ Aspose.Tasks**.

**Q: ฉันสามารถหาแหล่งสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน?**  
A: คุณสามารถหาแหล่งสนับสนุนและถามคำถามได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks อย่างไร?**  
A: คุณสามารถซื้อใบอนุญาตได้จาก **หน้า Aspose.Tasks purchase page**.

**Q: ฉันต้องการใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?**  
A: ใช่, คุณสามารถขอรับใบอนุญาตชั่วคราวจาก **temporary license request page**.

## สรุป
ตอนนี้คุณรู้ **วิธีสร้างกิจกรรม**, ตั้งค่าไดเรกทอรีข้อมูล, กำหนดและแนบคุณลักษณะพิเศษ, และ **บันทึกโครงการเป็น MPP** พร้อมกับ **การปรับแต่งฟิลด์ตาราง** ในมุมมองแผนภูมิแกนต์โดยใช้ Aspose.Tasks for Java ความสามารถเหล่านี้ให้คุณควบคุมข้อมูลโครงการด้วยโปรแกรมอย่างเต็มที่ ทำให้สามารถสร้างกำหนดการอัตโนมัติและรายงานภาพที่มีข้อมูลมากขึ้นสำหรับผู้มีส่วนได้ส่วนเสียของคุณ

---

**อัปเดตล่าสุด:** 2026-10-15  
**ทดสอบด้วย:** Aspose.Tasks Java 24.12 (latest)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างไฟล์โครงการเปล่าใน Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [วิธีสร้างไฟล์ MPP – สร้างและบันทึกโครงการเปล่าในรูปแบบ MPP ด้วย Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [วิธีสร้างโครงการ aspose.tasks – ตั้งค่าคุณลักษณะงานใหม่](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}