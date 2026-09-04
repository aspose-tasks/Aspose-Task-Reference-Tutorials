---
date: 2026-06-10
description: เรียนรู้วิธีสร้างแอตทริบิวต์ขยายใน Java, โหลดไฟล์ Microsoft Project,
  ตั้งค่าตัวเลข, และบันทึกโปรเจกต์เป็น XML ด้วย Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: จัดการแอตทริบิวต์ทรัพยากรขยายใน Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีสร้างแอตทริบิวต์ขยายใน Java ด้วย Aspose.Tasks
url: /th/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างแอตทริบิวต์ขยายใน Java ด้วย Aspose.Tasks

## บทนำ
ในคู่มือเชิงปฏิบัตินี้คุณจะ **สร้างแอตทริบิวต์ขยายใน Java** สำหรับไฟล์ Microsoft Project โดยใช้ Aspose.Tasks เราจะอธิบายขั้นตอนการโหลดโครงการที่มีอยู่, กำหนดแอตทริบิวต์ตัวเลขใหม่, กำหนดค่าให้กับทรัพยากร, และสุดท้ายบันทึกการเปลี่ยนแปลงเป็นไฟล์ XML เมื่อเสร็จคุณจะมีรูปแบบโค้ดที่สามารถนำไปใช้ซ้ำได้ในโซลูชันการจัดการโครงการที่พัฒนาด้วย Java

## คำตอบอย่างรวดเร็ว
- **อะไรคือแอตทริบิวต์ขยาย?**  
  ฟิลด์ที่ผู้ใช้กำหนด (เช่น อายุ, ระดับทักษะ) ที่เก็บข้อมูลเพิ่มเติมสำหรับทรัพยากรหรืองาน.  
- **API ใดที่สร้างมัน?**  
  Aspose.Tasks for Java มีคลาส `ExtendedAttributeDefinition` เพื่อกำหนดและจัดการแอตทริบิวต์ที่กำหนดเอง.  
- **ฉันต้องการไลเซนส์หรือไม่?**  
  ไลเซนส์ทดลองชั่วคราวใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถเก็บตัวเลขได้หรือไม่?**  
  ได้ – ใช้ `setNumericValue(BigDecimal)` เพื่อกำหนดค่าทศนิยมที่แม่นยำ.  
- **ฉันจะบันทึกการเปลี่ยนแปลงอย่างไร?**  
  เรียก `project.save("output.xml", SaveFileFormat.Xml)` เพื่อบันทึกโครงการที่อัปเดตเป็นรูปแบบ XML.

## แอตทริบิวต์ที่กำหนดเองคืออะไร?
**custom attribute** (หรือที่เรียกว่าแอตทริบิวต์ขยาย) คือคอลัมน์เพิ่มเติมที่คุณสามารถเพิ่มให้กับทรัพยากรหรืองานใน Microsoft Project มันช่วยให้คุณบันทึกข้อมูลที่ไม่ได้อยู่ในฟิลด์มาตรฐาน เช่น อายุของพนักงาน, ระดับการรับรอง, หรือเมตริกเฉพาะธุรกิจใด ๆ

## ทำไมต้องสร้างแอตทริบิวต์ขยายใน Java?
การสร้างแอตทริบิวต์ขยายใน Java ช่วยให้คุณเพิ่มข้อมูลโครงการโดยอัตโนมัติ, ทำให้ข้อมูลสอดคล้องกันระหว่างไฟล์และสนับสนุนการสร้างรายงานอัตโนมัติ โดยการกำหนดแอตทริบิวต์เพียงครั้งเดียว คุณสามารถนำไปใช้กับทรัพยากรหรืองานจำนวนใดก็ได้โดยไม่ต้องป้อนข้อมูลด้วยตนเอง, ประหยัดเวลาและลดข้อผิดพลาด.

- **ปรับข้อมูลให้เข้ากับองค์กรของคุณ** – เก็บเมตริกใด ๆ ที่สำคัญต่อคุณโดยไม่ต้องใช้วิธีแก้ปัญหาใน Excel ด้วยตนเอง.  
- **เปิดใช้งานการรายงานที่ละเอียดขึ้น** – คำถามฟิลด์ที่กำหนดเองในภายหลังสำหรับแดชบอร์ดหรือการวิเคราะห์.  
- **รักษาความสอดคล้อง** – ใช้การกำหนดเดียวกันผ่านโปรแกรมในหลายสิบโครงการ, ขจัดข้อผิดพลาดของมนุษย์.  
- **ทดสอบประสิทธิภาพ** – Aspose.Tasks ประมวลผลโครงการที่มีงานสูงสุด 10,000 งานและทรัพยากร 5,000 รายการโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ตามผลการทดสอบของผลิตภัณฑ์.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit** – JDK 8 หรือใหม่กว่า ที่ติดตั้งแล้ว.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA หรือสภาพแวดล้อมการพัฒนาที่รองรับ Java ใด ๆ.  

## วิธีสร้างแอตทริบิวต์ขยายใน Java?
โหลดโครงการของคุณ, กำหนดแอตทริบิวต์, แนบเข้ากับทรัพยากร, และบันทึกไฟล์ – ทั้งหมดในไม่กี่ขั้นตอนที่ง่ายดาย ส่วนต่อไปนี้จะแบ่งแต่ละขั้นตอนเป็นคำอธิบายสั้น ๆ ตามด้วยตัวแทนที่โค้ดจริงของคุณจะอยู่.

### คู่มือขั้นตอนต่อขั้นตอน

#### นำเข้าแพ็กเกจ
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` และคลาสที่เกี่ยวข้องอยู่ในเนมสเปซ `com.aspose.tasks`. นำเข้าพวกมันที่ส่วนหัวของไฟล์ Java ของคุณ.

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

#### ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
`Paths` เป็นคลาสยูทิลิตี้ที่ให้เมธอดเพื่อรับเส้นทางไฟล์ระบบในรูปแบบที่ไม่ขึ้นกับแพลตฟอร์ม.

```java
String dataDir = "Your Data Directory";
```

#### ขั้นตอนที่ 2: โหลดไฟล์ Microsoft Project
`Project` แทนไฟล์ Microsoft Project ในหน่วยความจำ, ให้การเข้าถึงแบบอ่านและเขียนเนื้อหาของไฟล์.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### ขั้นตอนที่ 3: กำหนดแอตทริบิวต์ที่กำหนดเอง
`ExtendedAttributeDefinition` กำหนดสคีมของฟิลด์ที่กำหนดเองใหม่ที่สามารถแนบเข้ากับทรัพยากรหรืองาน.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### ขั้นตอนที่ 4: ตั้งค่าตัวเลขใน Java
`ExtendedAttributeResource` เก็บค่าของแอตทริบิวต์ที่กำหนดเองสำหรับอินสแตนซ์ทรัพยากรเฉพาะ.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### ขั้นตอนที่ 5: เพิ่มทรัพยากรและแนบแอตทริบิวต์ที่กำหนดเอง
`Resource` จำลองทรัพยากรของโครงการ เช่น บุคคล, อุปกรณ์, หรือวัสดุ.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### ขั้นตอนที่ 6: บันทึกโครงการเป็น XML
`SaveFileFormat` แสดงรายการรูปแบบเอาต์พุตที่รองรับสำหรับการบันทึกโครงการ, รวมถึง XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### ขั้นตอนที่ 7: แสดงผลลัพธ์
`System.out.println` พิมพ์บรรทัดข้อความไปยังคอนโซลมาตรฐาน.

```java
System.out.println("Process completed Successfully");
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ความขัดแชนของ ID แอตทริบิวต์:** ควรเรียก `project.getExtendedAttributes().getById(id)` ก่อนสร้างการกำหนดใหม่เพื่อป้องกันตัวระบุซ้ำ.  
- **การจัดการความแม่นยำ:** แนะนำให้ใช้ `BigDecimal` แทน `float`/`double` สำหรับค่าตัวเลขที่แม่นยำ; นี้ช่วยหลีกเลี่ยงข้อผิดพลาดการปัดเศษในการรายงาน.  
- **ความน่าเชื่อถือของเส้นทางไฟล์:** ใช้ `Paths.get(...).toAbsolutePath()` หรือกำหนดค่าไดเรกทอรีทำงานของ IDE เพื่อขจัด `FileNotFoundException`.  

## คำถามที่พบบ่อย
**Q: ฉันสามารถสร้างแอตทริบิวต์ที่กำหนดเองสำหรับงานได้เช่นเดียวกับทรัพยากรหรือไม่?**  
A: ใช่ – ใช้ `ExtendedAttributeTask` แทน `ExtendedAttributeResource` เมื่อกำหนดสคีมของแอตทริบิวต์.

**Q: สามารถเพิ่มแอตทริบิวต์ที่กำหนดเองหลายรายการพร้อมกันได้หรือไม่?**  
A: ได้แน่นอน. สร้างอ็อบเจ็กต์ `ExtendedAttributeDefinition` แยกกันสำหรับแต่ละแอตทริบิวต์และแนบเข้ากับทรัพยากรหรืองานที่ต้องการ.

**Q: ฉันสามารถบันทึกโครงการในรูปแบบใดได้บ้าง?**  
A: Aspose.Tasks รองรับ XML, MPP, PDF, HTML, และรูปแบบเพิ่มเติมกว่า 30 รูปแบบ. ในตัวอย่างนี้เราใช้ `SaveFileFormat.Xml`.

**Q: ฉันต้องการไลเซนส์สำหรับการสร้างเวอร์ชันพัฒนาหรือไม่?**  
A: ไลเซนส์ทดลองชั่วคราวเพียงพอสำหรับการทดสอบ. สำหรับการใช้งานในสภาพแวดล้อมการผลิต จำเป็นต้องมีไลเซนส์เชิงพาณิชย์เต็มรูปแบบ.

**Q: ฉันจะอ่านค่าของแอตทริบิวต์ที่กำหนดเองในภายหลังได้อย่างไร?**  
A: เรียก `resource.getExtendedAttributes()` และวนลูปผ่านคอลเลกชัน; ดึงค่าที่เก็บไว้ด้วย `getNumericValue()` หรือ `getTextValue()`.

---

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างทรัพยากร – การจัดการทรัพยากรด้วย Aspose.Tasks for Java](/tasks/java/resource-management/)
- [สร้างฟิลด์ที่กำหนดเอง Aspose - จัดการแอตทริบิวต์ขยาย](/tasks/java/project-management/extended-attributes/)
- [วิธีสร้างโครงการ – ตั้งค่าแอตทริบิวต์งานใหม่ด้วย Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}