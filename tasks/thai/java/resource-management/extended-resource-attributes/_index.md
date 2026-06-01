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

## การแนะนำ
ในบทแนะนำนี้ ** เราจะสร้างแอตทริบิวต์ที่กำหนดเอง** สำหรับทรัพยากรในไฟล์ Microsoft Project ด้วย Aspose.Tasks สำหรับ Java คำอธิบายขั้นตอนการโหลดไฟล์ Microsoft Project, กำหนดแอตทริบิวต์ที่กำหนดเองแบบตัวเลขใหม่, เจล, และสุดท้ายบันทึกโครงการเป็น XML เมื่อเสร็จสิ้นคุณจะต้องมีตัวอย่างที่ชัดเจนและทำได้จริงและสามารถจัดการกับโครงการใหญ่ได้

## คำตอบด่วน
- **แอตทริบิวต์ที่กำหนดเอง** มีอะไรอีกบ้าง? 
สิ่งที่ผู้ใช้จำเป็นต้องใช้เพื่อเก็บข้อมูลเพิ่มเติม (เช่น อายุ, ระดับทักษะ) สำหรับทรัพยากรหรืองาน
- **ไลบรารีที่เกี่ยวข้องเรื่องนี้คืออะไร?** 
Aspose.Tasks สำหรับ Java ให้ API แบบคล่องแคล่วเพื่อสร้างและจัดการแอตทริบิวต์ที่กำหนดเอง
- ** ยืนยันไลเซนส์หรือไม่?** 
ไลเซนส์ชั่วคราวฟรีใช้ได้สำหรับกฎหมาย; ต้องมีเซนส์เต็มเลยจริง.
- **การตั้งค่าตัวเลขทำได้?** 
ได้ – ใช้ `setNumericValue` กับ `BigDecimal` (เช่น `30.5345`).
- **โครงการจะได้รับบันทึกอย่างไร?** 
แก้ไขที่สามารถบันทึกเป็น XML ได้ด้วย `SaveFileFormat.Xml`

## แอตทริบิวต์ที่กำหนดเองคืออะไร
**แอตทริบิวต์ที่กำหนดเอง** (หรือที่เรียกว่าแอตทริบิวต์เพิ่มเติม) นั่นคือคำอธิบายเพิ่มเติมเพื่อให้ทรัพยากรหรืองานใน Microsoft Project มันช่วยให้บันทึกข้อมูลสามารถตรวจสอบมาตรฐานได้ เช่น รายงานของพนักงาน, ระดับความเข้มข้น, หรือมัลติฟังก์ชั่นเฉพาะธุรกิจใด ๆ.

## เหตุใดจึงต้องสร้างแอตทริบิวต์ที่กำหนดเองใน MS Project
- **ปรับข้อมูลโครงการ** ทั้งนี้เพื่อเรียกร้องให้องค์กรของคุณ
- **ความรู้ความเข้าใจขั้นสูง** โดยการเก็บค่าสืบค้นนักสืบได้ด้วยตนเอง
- **รักษาความเคลื่อนไหว** และมีหลายโครงการโดยกำหนดแอตทริบิวต์เดียวกันผ่านโปรแกรม

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, เครือข่ายคุณ:

1. **Java Development Environment** – ติดตั้ง JDK 8 หรืออื่นๆ.
2. **Aspose.Tasks for Java** – ดาวน์โหลดล่าสุดจาก [ที่นี่](https://releases.aspose.com/tasks/java/)
3. **IDE** – Eclipse, IntelliJ IDEA หรือ IDE รองรับ Java ใดๆ

## คำแนะนำทีละขั้นตอน

### แพ็คเกจนำเข้า
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

### ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดโฟลเดอร์ที่ไฟล์โครงการต้นฉบับของคุณอยู่และที่ผลลัพธ์จะถูกเขียนออกไป.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์ Microsoft Project
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ที่มีอยู่. นี่คือขั้นตอน **load Microsoft project file** ที่ให้คุณเข้าถึงเนื้อหาทั้งหมดของไฟล์.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### ขั้นตอนที่ 3: กำหนดแอตทริบิวต์แบบกำหนดเอง
เราจะกำหนด custom attribute แบบตัวเลขใหม่ชื่อ **Age**. API จะตรวจสอบว่าการกำหนดนี้มีอยู่แล้วหรือไม่; หากไม่มีจะสร้างใหม่.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### ขั้นตอนที่ 4: กำหนดค่าตัวเลขใน Java
สร้างอินสแตนซ์ของ attribute สำหรับทรัพยากรเฉพาะและกำหนดค่าตัวเลขโดยใช้ `setNumericValue`. นี้เป็นการสาธิต **set numeric value java** ในการทำงาน.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### ขั้นตอนที่ 5: เพิ่มทรัพยากรและแนบแอตทริบิวต์แบบกำหนดเอง
เพิ่มทรัพยากรใหม่ชื่อ **R1** และแนบ custom attribute ที่สร้างไว้ก่อนหน้านี้เข้ากับมัน.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### ขั้นตอนที่ 6: บันทึกโปรเจ็กต์เป็น XML
สุดท้าย, บันทึกการเปลี่ยนแปลงโดยการบันทึกโครงการ. นี่คือขั้นตอน **save project as xml** ที่สร้างไฟล์ XML ที่สะอาดของไฟล์ที่อัปเดต.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### ขั้นตอนที่ 7: แสดงผลลัพธ์
พิมพ์ข้อความยืนยันที่เป็นมิตรเพื่อให้คุณทราบว่ากระบวนการเสร็จสมบูรณ์โดยไม่มีข้อผิดพลาด.

```java
System.out.println("Process completed Successfully");
```

โดยทำตามขั้นตอนเหล่านี้, คุณได้ **สร้าง custom attribute** สำเร็จ, โหลดไฟล์ Microsoft Project, ตั้งค่าตัวเลขด้วย Java, และบันทึกโครงการเป็น XML.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ความขัดแย้งของรหัสแอตทริบิวต์:** ตรวจสอบ `getById` เสมอก่อนสร้างคำจำกัดความใหม่เพื่อหลีกเลี่ยงรหัสซ้ำกัน
- **การจัดการความแม่นยำ:** `BigDecimal` รักษาความแม่นยำของทศนิยม หลีกเลี่ยงการใช้ `float` หรือ `double` สำหรับค่าที่แน่นอน
- **เส้นทางไฟล์:** ใช้เส้นทางสัมบูรณ์หรือกำหนดค่าไดเร็กทอรีการทำงานของ IDE เพื่อป้องกัน `FileNotFoundException`

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถสร้างแอตทริบิวต์แบบกำหนดเองสำหรับงานและทรัพยากรได้หรือไม่?**
ตอบ: ได้ – ใช้ `ExtendedAttributeTask` แทน `ExtendedAttributeResource` เมื่อกำหนดแอตทริบิวต์

**ถาม: สามารถเพิ่มแอตทริบิวต์แบบกำหนดเองหลายรายการพร้อมกันได้หรือไม่?**
ตอบ: ได้อย่างแน่นอน สร้างออบเจ็กต์ `ExtendedAttributeDefinition` แยกต่างหากสำหรับแต่ละแอตทริบิวต์และแนบเข้ากับทรัพยากรหรืองานที่ต้องการ

**ถาม: ฉันสามารถบันทึกโปรเจ็กต์ในรูปแบบใดได้บ้าง?**
ตอบ: Aspose.Tasks รองรับ XML, MPP และรูปแบบอื่นๆ อีกหลายรูปแบบ เช่น PDF และ HTML ในตัวอย่างนี้ เราใช้ `SaveFileFormat.Xml`

**ถาม: ฉันจำเป็นต้องซื้อลิขสิทธิ์ Aspose.Tasks สำหรับการสร้างเวอร์ชันพัฒนาหรือไม่?**
ตอบ: ลิขสิทธิ์ชั่วคราวเพียงพอสำหรับการประเมินผล สำหรับการใช้งานจริง จำเป็นต้องมีลิขสิทธิ์แบบเต็ม

**ถาม: ฉันจะอ่านค่าแอตทริบิวต์แบบกำหนดเองกลับมาได้อย่างไรในภายหลัง?**
ตอบ: ใช้ `resource.getExtendedAttributes()` เพื่อวนซ้ำแอตทริบิวต์ที่แนบมาและดึงค่าของแอตทริบิวต์เหล่านั้นด้วย `getNumericValue()` หรือ `getTextValue()`

## สรุป
การสร้าง **แอตทริบิวต์แบบกำหนดเอง** ใน Microsoft Project ด้วย Aspose.Tasks สำหรับ Java นั้นง่ายดายเมื่อคุณเข้าใจขั้นตอนการทำงาน: โหลดโปรเจ็กต์ กำหนดแอตทริบิวต์ ตั้งค่าแอตทริบิวต์ แนบแอตทริบิวต์เข้ากับทรัพยากร และบันทึกไฟล์ แนวทางนี้ช่วยให้คุณสามารถขยายโมเดลข้อมูลโครงการได้โดยอัตโนมัติ ทำให้สามารถสร้างรายงานที่สมบูรณ์ยิ่งขึ้นและผสานรวมเข้ากับกระบวนการทางธุรกิจของคุณได้อย่างแน่นแฟ้นยิ่งขึ้น

---

**อัปเดตล่าสุด:** 2026-01-13
**ทดสอบกับ:** Aspose.Tasks for Java 24.12
**ผู้เขียน:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}