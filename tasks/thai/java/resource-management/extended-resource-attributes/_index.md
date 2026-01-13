---
date: 2026-01-13
description: เรียนรู้วิธีสร้างแอตทริบิวต์ที่กำหนดเอง, โหลดไฟล์ Microsoft Project,
  ตั้งค่าตัวเลขใน Java, และบันทึกโครงการเป็น XML ด้วย Aspose.Tasks สำหรับ Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีสร้างแอตทริบิวต์ที่กำหนดเองใน MS Project ด้วย Aspose.Tasks
url: /th/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง Custom Attribute ใน MS Project ด้วย Aspose.Tasks

## Introduction
ในบทแนะนำนี้, **คุณจะได้เรียนรู้วิธีสร้าง custom attribute** สำหรับทรัพยากรในไฟล์ Microsoft Project ด้วย Aspose.Tasks for Java. เราจะอธิบายขั้นตอนการโหลดไฟล์ Microsoft Project, กำหนด custom attribute แบบตัวเลขใหม่, กำหนดค่า, และสุดท้ายบันทึกโครงการเป็น XML. เมื่อเสร็จคุณจะมีตัวอย่างที่ชัดเจนและทำได้จริงที่คุณสามารถปรับใช้กับโซลูชันการจัดการโครงการของคุณเอง.

## Quick Answers
- **custom attribute** คืออะไร?  
  ฟิลด์ที่ผู้ใช้กำหนดเองเพื่อเก็บข้อมูลเพิ่มเติม (เช่น Age, Skill Level) สำหรับทรัพยากรหรืองาน.  
- **ไลบรารีที่จัดการเรื่องนี้คืออะไร?**  
  Aspose.Tasks for Java ให้ API แบบ fluent เพื่อสร้างและจัดการ custom attributes.  
- **ฉันต้องการไลเซนส์หรือไม่?**  
  ไลเซนส์ชั่วคราวฟรีใช้ได้สำหรับการประเมิน; ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถตั้งค่าตัวเลขได้หรือไม่?**  
  ได้ – ใช้ `setNumericValue` กับ `BigDecimal` (เช่น `30.5345`).  
- **โครงการจะถูกบันทึกอย่างไร?**  
  ไฟล์ที่แก้ไขสามารถบันทึกเป็น XML ด้วย `SaveFileFormat.Xml`.

## What is a Custom Attribute?
**custom attribute** (หรือที่เรียกว่า extended attribute) คือคอลัมน์เพิ่มเติมที่คุณสามารถเพิ่มให้กับทรัพยากรหรืองานใน Microsoft Project. มันช่วยให้คุณบันทึกข้อมูลที่ไม่ได้อยู่ในฟิลด์มาตรฐาน เช่น อายุของพนักงาน, ระดับใบรับรอง, หรือเมตริกเฉพาะธุรกิจใด ๆ.

## Why Create a Custom Attribute in MS Project?
- **ปรับข้อมูลโครงการ** ให้สอดคล้องกับความต้องการขององค์กรของคุณ.  
- **เปิดใช้งานการรายงานขั้นสูง** โดยการเก็บค่าที่สามารถสืบค้นได้ในภายหลัง.  
- **รักษาความสอดคล้อง** ระหว่างหลายโครงการโดยการกำหนด attribute เดียวกันผ่านโปรแกรม.

## Prerequisites
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Environment** – ติดตั้ง JDK 8 หรือสูงกว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA หรือ IDE ที่รองรับ Java ใด ๆ.  

## Step‑by‑Step Guide

### Import Packages
ขั้นแรก, นำเข้า (import) คลาสของ Aspose.Tasks ที่คุณต้องการ. คลาสเหล่านี้ให้ฟังก์ชันหลักสำหรับการจัดการโครงการ, ทรัพยากร, และ extended attributes.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Step 1: Define Data Directory
กำหนดโฟลเดอร์ที่ไฟล์โครงการต้นฉบับของคุณอยู่และที่ผลลัพธ์จะถูกเขียนออกไป.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load Microsoft Project File
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ที่มีอยู่. นี่คือขั้นตอน **load Microsoft project file** ที่ให้คุณเข้าถึงเนื้อหาทั้งหมดของไฟล์.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Step 3: Define the Custom Attribute
เราจะกำหนด custom attribute แบบตัวเลขใหม่ชื่อ **Age**. API จะตรวจสอบว่าการกำหนดนี้มีอยู่แล้วหรือไม่; หากไม่มีจะสร้างใหม่.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Step 4: Set Numeric Value in Java
สร้างอินสแตนซ์ของ attribute สำหรับทรัพยากรเฉพาะและกำหนดค่าตัวเลขโดยใช้ `setNumericValue`. นี้เป็นการสาธิต **set numeric value java** ในการทำงาน.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Step 5: Add Resource and Attach the Custom Attribute
เพิ่มทรัพยากรใหม่ชื่อ **R1** และแนบ custom attribute ที่สร้างไว้ก่อนหน้านี้เข้ากับมัน.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Step 6: Save Project as XML
สุดท้าย, บันทึกการเปลี่ยนแปลงโดยการบันทึกโครงการ. นี่คือขั้นตอน **save project as xml** ที่สร้างไฟล์ XML ที่สะอาดของไฟล์ที่อัปเดต.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Step 7: Display Result
พิมพ์ข้อความยืนยันที่เป็นมิตรเพื่อให้คุณทราบว่ากระบวนการเสร็จสมบูรณ์โดยไม่มีข้อผิดพลาด.

```java
System.out.println("Process completed Successfully");
```

โดยทำตามขั้นตอนเหล่านี้, คุณได้ **สร้าง custom attribute** สำเร็จ, โหลดไฟล์ Microsoft Project, ตั้งค่าตัวเลขด้วย Java, และบันทึกโครงการเป็น XML.

## Common Pitfalls & Tips
- **Attribute ID conflicts:** Always check `getById` before creating a new definition to avoid duplicate IDs.  
- **Precision handling:** `BigDecimal` preserves decimal precision; avoid using `float` or `double` for exact values.  
- **File paths:** Use absolute paths or configure your IDE’s working directory to prevent `FileNotFoundException`.  

## Frequently Asked Questions

**Q: Can I create custom attributes for tasks as well as resources?**  
A: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource` when defining the attribute.

**Q: Is it possible to add multiple custom attributes at once?**  
A: Absolutely. Create separate `ExtendedAttributeDefinition` objects for each attribute and attach them to the desired resources or tasks.

**Q: What formats can I save the project in?**  
A: Aspose.Tasks supports XML, MPP, and several other formats like PDF and HTML. In this example we used `SaveFileFormat.Xml`.

**Q: Do I need to license Aspose.Tasks for development builds?**  
A: A temporary license is sufficient for evaluation. For production deployments, a full license is required.

**Q: How do I read back the custom attribute values later?**  
A: Use `resource.getExtendedAttributes()` to iterate over attached attributes and retrieve their values with `getNumericValue()` or `getTextValue()`.

## Conclusion
Creating a **custom attribute** in Microsoft Project with Aspose.Tasks for Java is straightforward once you understand the workflow: load the project, define the attribute, set its value, attach it to a resource, and save the file. This approach empowers you to extend project data models programmatically, enabling richer reporting and tighter integration with your business processes.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}