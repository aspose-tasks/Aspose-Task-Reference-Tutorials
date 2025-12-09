---
date: 2025-12-07
description: เรียนรู้วิธีบันทึกไฟล์โครงการ, เขียนและอ่านสูตร MS Project, และเพิ่มสูตรฟิลด์ที่กำหนดเองโดยใช้
  Aspose.Tasks สำหรับ Java.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: บันทึกไฟล์โครงการและเขียนสูตร MS Project ด้วย Aspose.Tasks
url: /th/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกไฟล์โครงการและเขียนสูตร MS Project ด้วย Aspose.Tasks

## บทนำ
ในวงการการจัดการโครงการ การจัดการข้อมูลอย่างมีประสิทธิภาพเป็นสิ่งสำคัญอย่างยิ่ง Aspose.Tasks for Java เป็นโซลูชันที่แข็งแกร่งซึ่งช่วยให้คุณสามารถจัดการและสกัดข้อมูลจากไฟล์ Microsoft Project ได้ หนึ่งในคุณสมบัติที่ทรงพลังที่มันนำเสนอคือความสามารถในการเขียนและอ่านสูตร MS Project **คุณจะได้เรียนรู้วิธี *บันทึกไฟล์โครงการ* หลังจากใช้สูตรเหล่านั้น** เพื่อให้การเปลี่ยนแปลงของคุณถูกบันทึกไว้สำหรับการวิเคราะห์ในอนาคต คู่มือฉบับนี้จะนำคุณผ่านกระบวนการใช้ฟังก์ชันนี้เพื่อเสริมประสิทธิภาพการทำงานของการจัดการโครงการของคุณ

## คำตอบด่วน
- **“บันทึกไฟล์โครงการ” ทำอะไร?** จะเขียนการเปลี่ยนแปลงทั้งหมดในหน่วยความจำกลับไปยังไฟล์ .mpp บนดิสก์  
- **ฉันสามารถเพิ่มสูตรฟิลด์กำหนดเองได้หรือไม่?** ได้ – คุณสามารถสร้างฟิลด์กำหนดเองและกำหนดสูตรเช่น “double task cost”  
- **ต้องมีไลเซนส์เพื่อรันโค้ดหรือไม่?** ทดลองใช้ฟรีได้สำหรับการประเมินผล; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **IDE ใดทำงานดีที่สุด?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) จะคอมไพล์ตัวอย่างได้  
- **API รองรับเวอร์ชันล่าสุดของ MS Project หรือไม่?** Aspose.Tasks รองรับรูปแบบ .mpp ล่าสุดทั้งหมด  

## “save project file” คืออะไรใน Aspose.Tasks
การบันทึกไฟล์โครงการหมายถึงการทำให้สถานะปัจจุบันของอ็อบเจกต์ `Project` – รวมถึงงาน, ทรัพยากร, และสูตรกำหนดเองใด ๆ – ถูกบันทึกลงในไฟล์ Microsoft Project จริง (`.mpp`) การดำเนินการนี้จำเป็นต้องทำหลังจากที่คุณแก้ไขข้อมูล เช่น การเพิ่มฟิลด์กำหนดเองหรือการเปลี่ยนค่าใช้จ่ายของงาน

## ทำไมต้องเพิ่มฟิลด์กำหนดเองและสร้างสูตรฟิลด์กำหนดเอง
การเพิ่มฟิลด์กำหนดเองให้คุณมีที่เก็บข้อมูลเพิ่มเติมที่ไม่ครอบคลุมโดยฟิลด์มาตรฐานโดยการแนบสูตร – เช่นสูตรที่ **double task cost** – คุณจะทำให้การคำนวณเป็นอัตโนมัติ ลดความผิดพลาดจากการป้อนข้อมูลด้วยมือ และทำให้ข้อมูลตารางเวลาเป็นไปอย่างสอดคล้อง

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – ติดตั้ง Java 8 หรือสูงกว่าในเครื่องของคุณ  
2. **Aspose.Tasks for Java** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/tasks/java/)  
3. **Integrated Development Environment (IDE)** – เลือก IDE ที่คุณชอบสำหรับการพัฒนา Java (IntelliJ IDEA, Eclipse, VS Code ฯลฯ)  

## การนำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์ข้อมูล
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
กำหนดโฟลเดอร์ที่ไฟล์ MS Project ของคุณอยู่ นี่คือที่ที่คุณจะโหลดไฟล์ต้นฉบับและในภายหลัง **บันทึกไฟล์โครงการ**  

## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "project.mpp");
```
โหลดไฟล์ Microsoft Project ที่มีอยู่เข้าสู่อ็อบเจกต์ `Project` เพื่อให้คุณสามารถอ่านหรือแก้ไขเนื้อหาได้  

## ขั้นตอนที่ 3: เพิ่มฟิลด์กำหนดเองและสร้างสูตรฟิลด์กำหนดเอง
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
ในขั้นตอนนี้เราจะ **เพิ่มฟิลด์กำหนดเอง** “Double Costs” และ **สร้างสูตรฟิลด์กำหนดเอง** ที่คูณค่า `[Cost]` ของงานด้วย 2 ทำให้เกิด **double task cost** เมธอด `setFormula` จะฝังการคำนวณนี้ลงในไฟล์โครงการโดยตรง  

## ขั้นตอนที่ 4: เพิ่มงานและกำหนดค่าใช้จ่าย
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
สร้างงานใหม่ แล้วกำหนดค่าใช้จ่ายพื้นฐานเป็น `100` เมื่อบันทึกโครงการ ฟิลด์กำหนดเองจะอัตโนมัติแสดงค่า `200` ตามสูตรที่กำหนดไว้ก่อนหน้า  

## ขั้นตอนที่ 5: บันทึกไฟล์โครงการ
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
สุดท้าย **บันทึกไฟล์โครงการ** พร้อมการแก้ไขทั้งหมด เมธอด `save` จะเขียนโครงการที่อัปเดต รวมถึงฟิลด์กำหนดเองใหม่และค่าที่คำนวณแล้ว ไปยัง `saved.mpp`  

## ปัญหาที่พบบ่อยและวิธีแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **สูตรไม่ทำงาน** | ฟิลด์กำหนดเองไม่ได้เพิ่มเข้าไปในคอลเลกชัน `ExtendedAttributes` ของโครงการ | ตรวจสอบให้แน่ใจว่าได้เรียก `project.getExtendedAttributes().add(attr);` ก่อนบันทึก |
| **ไม่พบไฟล์** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่า string ของไดเรกทอรีลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\\`). |
| **ค่าใช้จ่ายแสดงเป็น 0** | ค่าใช้จ่ายของงานไม่ได้ตั้งค่าก่อนบันทึก | เรียก `task.set(Tsk.COST, ...)` ก่อน `project.save`. |

## คำถามที่พบบ่อย
**Q: Aspose.Tasks รองรับทุกเวอร์ชันของ MS Project หรือไม่?**  
A: รองรับ Aspose.Tasks รองรับช่วงกว้างของเวอร์ชัน MS Project ตั้งแต่รูปแบบ .mpp เก่าไปจนถึงรุ่นล่าสุด  

**Q: ฉันสามารถรวม Aspose.Tasks เข้าในโครงการ Java ที่มีอยู่ของฉันได้หรือไม่?**  
A: แน่นอน API ถูกออกแบบให้รวมได้อย่างราบรื่น; เพียงเพิ่มไฟล์ JAR ของ Aspose.Tasks ไปยัง classpath ของโครงการ  

**Q: มีข้อจำกัดใด ๆ กับประเภทของสูตรที่ฉันสร้างได้หรือไม่?**  
A: ไลบรารีสนับสนุนไวยากรณ์สูตรของ MS Project ส่วนใหญ่ รวมถึงการคำนวณเชิงคณิตศาสตร์, ตรรกะ, และฟังก์ชันในตัว ฟังก์ชันกำหนดเองที่ซับซ้อนอาจต้องใช้วิธีแก้ไขเพิ่มเติม  

**Q: Aspose.Tasks รองรับการปรับใช้หลายแพลตฟอร์มหรือไม่?**  
A: รองรับ ไลบรารีทำงานบนแพลตฟอร์มใด ๆ ที่รองรับ Java รวมถึง Windows, Linux, และ macOS  

**Q: ฉันจะรับการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชน หรือเปิดตั๋วสนับสนุนหากคุณมีไลเซนส์เชิงพาณิชย์  

## สรุป
ในบทเรียนนี้ เราได้ครอบคลุมวิธี **บันทึกไฟล์โครงการ**, **เพิ่มฟิลด์กำหนดเอง**, และ **สร้างสูตรฟิลด์กำหนดเอง** ที่ **double task cost** ด้วย Aspose.Tasks for Java โดยทำตามขั้นตอนเหล่านี้คุณสามารถทำให้การคำนวณเป็นอัตโนมัติ เพิ่มคุณค่าให้ข้อมูลโครงการของคุณ และทำให้การเปลี่ยนแปลงทั้งหมดถูกบันทึกไว้สำหรับการรายงานและวิเคราะห์ในอนาคต  

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}