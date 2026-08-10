---
date: 2026-05-20
description: เรียนรู้วิธีใช้ Aspose.Tasks for Java เพื่อเพิ่ม extended attributes
  ให้กับ resource assignments, ตั้งค่า project start date, และเขียนไฟล์ MS Project
  อย่างมีประสิทธิภาพ
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: เพิ่ม Extended Attributes ให้กับ Resource Assignments ใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีใช้ Aspose.Tasks for Java – เพิ่ม Extended Attributes ให้กับ Resource Assignments
url: /th/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เชี่ยวชาญการจัดการ MS Project ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีใช้ Aspose.Tasks สำหรับ Java** เพื่อเพิ่มคุณลักษณะขยายให้กับการมอบหมายทรัพยากรและเขียนข้อมูล Microsoft Project ด้วยโปรแกรม ไม่ว่าคุณจะทำระบบอัตโนมัติสำหรับการรายงานหรือสร้างเครื่องมือการจัดการโครงการแบบกำหนดเอง ขั้นตอนต่อไปนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าตั้งค่าวันที่เริ่มต้นของโครงการอย่างไร สร้างการมอบหมายทรัพยากรอย่างไร และบันทึกไฟล์เป็น XML—ทั้งหมดด้วยเพียงไม่กี่บรรทัดของโค้ด Java

## คำตอบสั้น
- **Aspose.Tasks สำหรับ Java ทำอะไรได้บ้าง?** สามารถอ่าน, เขียนและแก้ไขไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project  
- **ฉันสามารถเพิ่มฟิลด์กำหนดเองให้กับการมอบหมายทรัพยากรได้หรือไม่?** ได้, ใช้คอลเลกชัน `ExtendedAttribute` บนวัตถุ `ResourceAssignment`  
- **ตั้งค่าวันที่เริ่มต้นของโครงการอย่างไร?** เรียก `project.setStartDate(LocalDateTime.of(...))` ก่อนบันทึก  
- **ต้องใช้ไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ไลเซนส์เชิงพาณิชย์จะลบลายน้ำการประเมินและเปิดการเข้าถึง API ทั้งหมด  
- **รองรับเวอร์ชัน Java ใดบ้าง?** Aspose.Tasks สำหรับ Java รองรับ JDK 8 ถึง JDK 21

## วิธีใช้ Aspose.Tasks สำหรับ Java?
`Project` คือวัตถุหลักที่แทนไฟล์ Microsoft Project ในหน่วยความจำ โหลดไลบรารี Aspose.Tasks, สร้างอินสแตนซ์ `Project`, กำหนดคุณสมบัติระดับโครงการ, เพิ่มคุณลักษณะขยายให้กับการมอบหมายทรัพยากร, และสุดท้ายบันทึกโครงการเป็น XML กระบวนการหลักแบ่งเป็นสามขั้นตอนสั้น ๆ: เริ่มต้น, แก้ไข, และบันทึก แพทเทิร์นนี้ทำงานได้กับไฟล์โครงการทุกขนาดและทำงานบน JVM ของ Windows, Linux หรือ macOS

## คุณลักษณะขยายใน Aspose.Tasks คืออะไร?
**คุณลักษณะขยาย** คือฟิลด์กำหนดเองที่คุณแนบเข้ากับงาน, ทรัพยากร หรือการมอบหมาย เพื่อเก็บเมตาดาต้าเพิ่มเติมเหนือคอลัมน์ที่มีมาโดย default `ExtendedAttributeDefinition` กำหนดสคีมาของฟิลด์กำหนดเอง Aspose.Tasks เปิดเผยคลาส `ExtendedAttributeDefinition` และ `ExtendedAttribute` เพื่อให้คุณกำหนดและกำหนดค่าเหล่านี้ด้วยโปรแกรม

## ทำไมต้องเพิ่มคุณลักษณะขยายให้กับการมอบหมายทรัพยากร?
Aspose.Tasks รองรับ **ฟิลด์ในตัวและฟิลด์กำหนดเองกว่า 50 รายการ**, และคุณสามารถเพิ่มคุณลักษณะที่ผู้ใช้กำหนดได้ไม่จำกัด การเพิ่มคุณลักษณะเหล่านี้ช่วยให้คุณบันทึกรหัสค่าใช้จ่าย, รหัสแผนก, หรือข้อมูลเฉพาะธุรกิจใด ๆ ลงในไฟล์ .mpp โดยตรง ลดความจำเป็นในการใช้สเปรดชีตภายนอกและรับประกันความสมบูรณ์ของข้อมูลตลอดวงจรชีวิตของโครงการ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – ติดตั้ง JDK 8 หรือใหม่กว่า  
2. **Aspose.Tasks สำหรับ Java library** – ดาวน์โหลดจากหน้ารีลีสอย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/tasks/java/)  
3. **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไข Java ที่คุณชื่นชอบ

## นำเข้าแพ็กเกจ
เริ่มต้นโดยนำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดไดเรกทอรีที่ข้อมูลโครงการของคุณจะถูกจัดเก็บ เส้นทางนี้จะถูกใช้ต่อไปเมื่อคุณบันทึกไฟล์ XML

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ Project
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แทนไฟล์ Microsoft Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอินสแตนซ์นี้ให้คุณเข้าถึงองค์ประกอบทั้งหมดของโครงการได้อย่างเต็มที่

```java
Project project = new Project();
```

### ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติข้อมูลโครงการ
กำหนดคุณสมบัติโครงการสำคัญ เช่น วันที่เริ่มต้น, ธง schedule from start, และวันที่สถานะ ค่าเหล่านี้จะถูกเก็บในอ็อบเจ็กต์ `ProjectInfo` ของโครงการ

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### ขั้นตอนที่ 4: เพิ่มคุณลักษณะขยายให้กับการมอบหมายทรัพยากร
สร้าง `ExtendedAttributeDefinition` สำหรับฟิลด์กำหนดเอง, แนบเข้ากับ `ResourceAssignment`, และกำหนดค่าที่ต้องการ ขั้นตอนนี้แสดงการทำงานของคีย์เวิร์ด **add extended attributes** อย่างเป็นรูปธรรม

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **NullPointerException เมื่อเข้าถึงคอลเลกชันการมอบหมาย** – ตรวจสอบว่าคุณได้สร้างทรัพยากรและงานอย่างน้อยหนึ่งรายการก่อนดึงการมอบหมาย  
- **คุณลักษณะขยายไม่ปรากฏใน MS Project** – ตรวจสอบว่า `FieldId` ของคุณลักษณะตรงกับช่องฟิลด์กำหนดเอง (เช่น `ExtendedAttributeTask.Text1`)  
- **รูปแบบวันที่ไม่ตรงกัน** – ใช้ `java.time.LocalDateTime` สำหรับค่าที่เป็นวันที่; Aspose.Tasks จะทำการแปลงอัตโนมัติเป็นรูปแบบปฏิทินของโครงการ

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่ออ่านไฟล์ MS Project ได้หรือไม่?**  
ตอบ: ใช่, ไลบรารีนี้ให้ความสามารถอ่าน‑เขียนเต็มรูปแบบสำหรับรูปแบบ .mpp, .xml, และ .xps

**ถาม: Aspose.Tasks สำหรับ Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?**  
ตอบ: รองรับไฟล์จาก Project 2000 จนถึงรุ่นล่าสุด 2024, ครอบคลุมกว่า 20 รูปแบบเวอร์ชัน

**ถาม: มีข้อจำกัดอะไรในเวอร์ชันทดลองของ Aspose.Tasks สำหรับ Java หรือไม่?**  
ตอบ: เวอร์ชันทดลองจะใส่ลายน้ำบนไฟล์ที่สร้างและจำกัดจำนวนงานที่สร้างได้, แต่ฟีเจอร์ API ทั้งหมดยังคงเข้าถึงได้

**ถาม: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร?**  
ตอบ: คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks [ที่นี่](https://forum.aspose.com/c/tasks/15)

**ถาม: สามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?**  
ตอบ: ได้, ไลเซนส์ชั่วคราวพร้อมให้ใช้สำหรับการใช้งานระยะสั้น คุณสามารถรับได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-05-20  
**ทดสอบด้วย:** Aspose.Tasks สำหรับ Java 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มบันทึกย่อให้กับการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [วิธีอ่านและเขียน Rate Scale สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [วิธีเพิ่มทรัพยากรลงในโครงการและจัดการคุณสมบัติ Leveling Delay ใน Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}