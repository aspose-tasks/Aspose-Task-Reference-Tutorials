---
date: 2026-06-05
description: เรียนรู้วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks for Java, ปรับแต่ง filter
  criteria, และ filter tasks ตามวันที่เพื่อเพิ่มประสิทธิภาพการจัดการโครงการ
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks for Java
url: /th/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีกรองไฟล์ MPP ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
หากคุณกำลังทำงานกับไฟล์ Microsoft Project (*.mpp*) ในแอปพลิเคชัน Java คุณมักจะต้อง **filter MPP files** เพื่อแยกงาน, ทรัพยากร, หรือการมอบหมายที่สำคัญที่สุด ในบทเรียนนี้เราจะอธิบาย **how to filter mpp** อย่างโปรแกรมโดยใช้ Aspose.Tasks สำหรับ Java, แสดงวิธี **customize filter criteria**, และสาธิตสถานการณ์จริง “filter tasks by date” เมื่อเสร็จคุณจะมีโค้ดสั้นที่พร้อมใช้งานซึ่งสามารถนำไปใส่ในโครงการ Java ใด ๆ

## คำตอบสั้น
- **What does “filter mpp” mean?** หมายถึงการสกัดส่วนย่อยของข้อมูลโครงการตามเงื่อนไขที่กำหนด  
- **Which library handles this?** Aspose.Tasks for Java มี API ครบวงจรสำหรับสร้างและใช้ตัวกรอง  
- **Do I need a license?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **Can I filter tasks, resources, and assignments?** ได้ – แต่ละประเภทเอนทิตีมีคอลเลกชันตัวกรองของตนเอง  
- **Is Java 8 or higher required?** Aspose.Tasks รองรับ Java 8 และเวอร์ชันที่ใหม่กว่า  

## “how to filter mpp” คืออะไรใน Java?
`How to filter mpp` คือกระบวนการใช้วัตถุ `Filter` ของ Aspose.Tasks เพื่อเลือกเฉพาะองค์ประกอบของโครงการที่ตรงตามเงื่อนไขเช่น วันที่เริ่มต้น, ค่าใช้จ่าย, หรือฟิลด์กำหนดเอง โหลด `Project`, ดึง `Filter`, แล้ว API จะคืนคอลเลกชันที่ตรงกับเกณฑ์ของคุณ ทำให้สามารถสร้างรายงานที่มุ่งเน้นหรือการบูรณาการต่อไปได้

## ทำไมต้องปรับแต่งเงื่อนไขการกรอง?
เงื่อนไขการกรองที่กำหนดเองช่วยให้คุณมุ่งเป้าไปที่งานที่มีความเสี่ยงสูง, รายการล่าช้า, หรือทรัพยากรที่เกินงบประมาณ, ทำให้ไฟล์โครงการขนาดใหญ่กลายเป็นมุมมองที่กระชับและนำไปปฏิบัติได้ Aspose.Tasks รองรับ **50+ predefined filter types** และให้คุณสร้างตัวกรองกำหนดเองได้ไม่จำกัด ลดเวลาการคัดกรองข้อมูลด้วยมือได้ถึง 70 %

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [download page](https://releases.aspose.com/tasks/java/)  
3. **An IDE** – IntelliJ IDEA, Eclipse, หรือ NetBeans จะทำงานได้ดี  

## นำเข้าแพ็กเกจ
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType`, และ `Project` เป็นคลาสหลักที่ใช้กำหนดและใช้ตัวกรองกับข้อมูลโครงการ

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์
ก่อนอื่นให้สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ MPP ที่คุณต้องการวิเคราะห์, จากนั้นโหลดเข้าหน่วยความจำ ขั้นตอนเดียวนี้เตรียมโมเดลโครงการทั้งหมดสำหรับการกรอง, การตรวจสอบ, และการจัดการต่อไป, ทำให้คุณสามารถเข้าถึงงาน, ทรัพยากร, และการมอบหมายผ่าน API

### ฉันจะตั้งค่าโปรเจกต์เพื่อกรองไฟล์ MPP อย่างไร?
คลาส `Project` โหลดและแสดงไฟล์ MPP ในหน่วยความจำ สร้างอินสแตนซ์ `Project` ที่ชี้ไปยังไฟล์ MPP ที่คุณต้องการวิเคราะห์, แล้วโหลดเข้าหน่วยความจำ ขั้นตอนเดียวนี้เตรียมโมเดลโครงการทั้งหมดสำหรับการกรอง, การตรวจสอบ, และการจัดการต่อไป, ทำให้คุณสามารถเข้าถึงงาน, ทรัพยากร, และการมอบหมายผ่าน API

### ฉันจะดึงและตรวจสอบตัวกรองได้อย่างไร?
`Filter` เป็นอ็อบเจ็กต์ที่บรรจุคำนิยามตัวกรองที่ใช้เลือกรายการในโครงการ Aspose.Tasks มีตัวกรองที่กำหนดไว้ล่วงหน้าเช่น “All Tasks” หรือ “Critical Tasks”. ใช้ `project.getTaskFilters().getByName("My Filter")` หรือการเข้าถึงตามดัชนีเพื่อรับอ็อบเจ็กต์ `Filter`, จากนั้นตรวจสอบคอลเลกชัน `FilterCriteria` เพื่อดูแต่ละกฎและตัวดำเนินการเชิงตรรกะ (AND/OR) ที่รวมเข้าด้วยกัน, เพื่อให้แน่ใจว่าตัวกรองตรงตามความต้องการของคุณ

### วิธีวนลูปผ่านแถวเงื่อนไขที่ซ้อนกัน?
`FilterCriteriaGroup` แทนกลุ่มของเงื่อนไขการกรองที่รวมด้วยตัวดำเนินการเชิงตรรกะ ตัวกรองสามารถมีกลุ่มของเงื่อนไข, แต่ละกลุ่มมีตัวดำเนินการของตนเอง วนลูปผ่าน `filter.getCriteria().getRows()` และสำหรับแถวใดที่เป็น `FilterCriteriaGroup` ให้ทำการเรียกซ้ำไปยังแถวลูก การเดินทางนี้ช่วยให้คุณเข้าใจตรรกะตัวกรองที่ซับซ้อนเช่น “(Start < today AND Cost > 1000) OR Priority = High” อย่างเต็มที่และปรับเงื่อนไขตามต้องการ

### ฉันจะพิมพ์ข้อมูลเงื่อนไขสำหรับการดีบักอย่างไร?
หลังจากเดินทางผ่านต้นไม้ของเงื่อนไขแล้ว, ให้แสดงชื่อฟิลด์, ตัวดำเนินการทดสอบ, และค่า ของแต่ละแถวไปยังคอนโซล การแสดงผลแบบง่ายนี้ช่วยให้คุณตรวจสอบว่าตัวกรองตรงกับกฎธุรกิจที่ตั้งใจก่อนนำไปใช้กับโครงการขนาดใหญ่, และทำให้ค้นหาตัวดำเนินการหรือค่าที่ไม่ถูกต้องได้ง่ายขึ้น

### ฉันจะสร้างตัวกรองใหม่จากโปรแกรมอย่างไร?
สร้างอินสแตนซ์ `Filter` ด้วย `new Filter("My Filter")`, จากนั้นเพิ่มลงในคอลเลกชันตัวกรองงานของโปรเจกต์โดยใช้ `project.getTaskFilters().add(filter)`. หลังจากนั้นให้เติมคอลเลกชัน `FilterCriteria` ของมันด้วยแถวที่ต้องการ, ระบุชื่อฟิลด์, ตัวดำเนินการทดสอบ, และค่า เพื่อกำหนดอย่างชัดเจนว่าหน้าที่ใดควรรวมเมื่อใช้ตัวกรอง

### ฉันสามารถใช้ตัวกรองกับทรัพยากรแทนงานได้หรือไม่?
คอลเลกชัน `ResourceFilters` เก็บคำนิยามตัวกรองที่ใช้กับทรัพยากร ได้ – ใช้ `project.getResourceFilters()` เพื่อทำงานกับตัวกรองเฉพาะทรัพยากรในลักษณะเดียวกับตัวกรองงาน หลังจากเพิ่มหรือดึงตัวกรอง, ตั้งค่า `FilterCriteria` ของมันเช่นเดียวกับงาน, แล้วนำไปใช้กับคอลเลกชันทรัพยากรเพื่อรับชุดทรัพยากรที่กรองแล้ว

### สามารถรวมหลายตัวกรองด้วยตรรกะ OR ได้หรือไม่?
สร้าง `FilterCriteriaGroup` พาเรนท์โดยตั้งค่า `Operation` เป็น `OR`, จากนั้นเพิ่มอ็อบเจ็กต์ `FilterCriteria` แต่ละตัวเป็นลูก กลุ่มนี้จะประเมินแต่ละเกณฑ์ลูกและคืนรายการที่ตรงกับใดก็ได้, ทำให้คุณสามารถรวมหลายตัวกรองง่าย ๆ เป็นการเลือกที่กว้างขึ้น

### Aspose.Tasks รองรับการกรองบนฟิลด์กำหนดเองหรือไม่?
`CustomField` enum ให้ตัวระบุสำหรับฟิลด์กำหนดเองที่กำหนดในโครงการ แน่นอน. สามารถอ้างอิงฟิลด์กำหนดเองผ่าน `CustomField` enum, และพวกมันทำงานเหมือนฟิลด์ในตัวกรองทั่วไป คุณสามารถรวมพวกมันในแถว `FilterCriteria` โดยใช้ตัวดำเนินการและค่าที่เหมือนกัน, ทำให้สามารถทำคิวรีที่มีประสิทธิภาพบนข้อมูลที่ผู้ใช้กำหนดพร้อมกับคุณลักษณะมาตรฐานของโครงการ

### การกรองมีผลต่อประสิทธิภาพอย่างไรกับไฟล์ MPP ขนาดใหญ่?
การกรองทำงานทั้งหมดในหน่วยความจำและโดยทั่วไปจะประมวลผลโครงการที่มี 1,000 งานในเวลาน้อยกว่า 200 ms สำหรับไฟล์หลายพันงาน, ควรพิจารณาโหลดเฉพาะส่วนที่ต้องการโดยใช้ `ProjectReader` และใช้ตัวกรองหลังจากการโหลดแบบเลือก, ซึ่งช่วยลดการใช้หน่วยความจำและรักษาเวลาในการตอบสนองที่เร็วแม้กับโครงการขนาดใหญ่มาก

---

**อัปเดตล่าสุด:** 2026-06-05  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [โหลดไฟล์ MPP ด้วย Java - จัดการคุณสมบัติโครงการด้วย Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - การอ่านข้อมูล MS Project Online อย่างง่ายดาย](/tasks/java/project-data-reading/read-project-online/)
- [ตั้งค่าวันที่เริ่มต้นของโครงการใน MS Project ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```