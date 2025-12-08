---
date: 2025-12-07
description: เรียนรู้วิธี **สร้างโครงการทดสอบ** และ **เพิ่มฟิลด์กำหนดเอง** ขณะจัดการไฟล์
  Microsoft Project ด้วย Aspose.Tasks สำหรับ Java.
language: th
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: สร้างโครงการทดสอบและใช้สูตรกับ Aspose.Tasks สำหรับ Java
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างโครงการทดสอบและใช้สูตรกับ Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะ **สร้างไฟล์โครงการทดสอบ** เพิ่มฟิลด์กำหนดเอง และทำงานกับสูตรของ MS Project โดยใช้ไลบรารี Aspose.Tasks สำหรับ Java Aspose.Tasks ทำให้การ **จัดการข้อมูล Microsoft Project** ด้วยโปรแกรมเป็นเรื่องง่าย—ไม่ว่าคุณจะต้องการสร้างตารางเวลา คำนวณวันที่ หรืออัตโนมัติการรายงานก็ตาม เมื่อจบคู่มือคุณจะมีตัวอย่างที่สามารถรันได้ซึ่งกำหนดแอตทริบิวต์ขยาย ตั้งค่ากำหนดเส้นตายสำหรับงานหนึ่ง และบันทึกโครงการเป็นไฟล์ MPP

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การสร้างโครงการทดสอบ การเพิ่มฟิลด์กำหนดเอง การกำหนดแอตทริบิวต์ขยาย และการตั้งกำหนดเส้นตายของงานด้วยสูตร  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Tasks สำหรับ Java (เวอร์ชันล่าสุด)  
- **ต้องมีไลเซนส์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **ใช้ IDE ใดได้บ้าง?** IDE ของ Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) ที่รองรับ JDK 8+  
- **ใช้เวลานานเท่าไหร่ในการทำ?** ประมาณ 10‑15 นาทีสำหรับคัดลอกโค้ดและรัน

## “โครงการทดสอบ” ใน Aspose.Tasks คืออะไร?
**โครงการทดสอบ** คือไฟล์ Microsoft Project ขนาดเล็กที่สร้างขึ้นโดยโปรแกรมเพื่อสาธิตหรือทดสอบฟังก์ชันการทำงาน มันมีชุดงาน, ทรัพยากร, และฟิลด์กำหนดเองขั้นต่ำที่คุณสามารถจัดการได้โดยไม่กระทบต่อข้อมูลโครงการจริง

## ทำไมต้องใช้ Aspose.Tasks เพื่อจัดการ Microsoft Project?
- **ครอบคลุม API ทั้งหมด** – เข้าถึงคุณสมบัติของ Project, Task, และ Resource ทุกอย่าง  
- **ไม่ต้องติดตั้ง Office** – ทำงานบนเซิร์ฟเวอร์, CI pipeline, และ Docker container  
- **ข้ามแพลตฟอร์ม** – รันบน Windows, Linux, และ macOS ด้วยโค้ด Java เดียวกัน  
- **เครื่องมือสูตรที่แข็งแรง** – คำนวณวันที่, ระยะเวลา, และฟิลด์กำหนดเองโดยตรงในไฟล์โครงการ

## สิ่งที่ต้องเตรียม
ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

- **Java Development Kit (JDK) 8+** – ดาวน์โหลดจากเว็บไซต์ Oracle หรือใช้ OpenJDK  
- **Aspose.Tasks สำหรับ Java** – รับไฟล์ JAR ล่าสุดจาก [หน้าดาวน์โหลด Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) แล้วเพิ่มลงใน classpath ของโปรเจกต์หรือใน dependency ของ Maven/Gradle

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างโครงการทดสอบพร้อมฟิลด์กำหนดเอง
เราจะ **สร้างโครงการทดสอบ** และเพิ่มฟิลด์กำหนดเองที่จะใช้เก็บผลลัพธ์สูตรในภายหลัง

```java
Project project = CreateTestProjectWithCustomField();
```

> *เคล็ดลับ:* `CreateTestProjectWithCustomField()` เป็นเมธอดช่วยเหลือที่สร้างตารางเวลาขั้นต่ำและลงทะเบียนแอตทริบิวต์ขยายพร้อมสำหรับการกำหนดสูตร

### ขั้นตอนที่ 2: กำหนดแอตทริบิวต์ขยาย (เพิ่มฟิลด์กำหนดเอง)
ต่อไปเราจะ **กำหนดแอตทริบิวต์ขยาย** – ซึ่งก็คือฟิลด์กำหนดเอง – และตั้งชื่อแทนที่เป็นมิตร นี่คือจุดที่เราจะ **เพิ่มฟิลด์กำหนดเอง** ลงในโค้ด

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** ทำให้ฟิลด์อ่านง่ายใน Project  
- **Formula** คำนวณจำนวนวันระหว่างวันที่ *Finish* ของงานกับ *Deadline* ของงานนั้น

### ขั้นตอนที่ 3: ตั้งกำหนดเส้นตายสำหรับงาน (เพิ่มงานกำหนดเส้นตาย & ตั้งกำหนดเส้นตายของงาน)
ตอนนี้เราจะ **เพิ่มข้อมูลงานกำหนดเส้นตาย** โดยตั้งค่า property `Deadline` ให้กับงานที่ต้องการ

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- อินสแตนซ์ `Calendar` กำหนดช่วงเวลากำหนดเส้นตายที่แน่นอน  
- `set(Tsk.DEADLINE, …)` **ตั้งกำหนดเส้นตายของงาน** สำหรับงานที่เลือก

### ขั้นตอนที่ 4: บันทึกโครงการ (จัดการไฟล์ Microsoft Project)
สุดท้ายเราจะ **จัดการไฟล์ Microsoft Project** โดยบันทึกการเปลี่ยนแปลงลงไฟล์ MPP

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

คุณสามารถเปิด `SaveFile.mpp` ด้วย Microsoft Project เพื่อดูฟิลด์กำหนดเอง, ผลลัพธ์สูตร, และกำหนดเส้นตายที่ปรากฏในตารางเวลา

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **สูตรไม่ทำงาน** | ตรวจสอบว่า string ของ `Formula` ใช้ชื่อฟิลด์ที่ถูกต้อง (เช่น `[Deadline]`, `[Finish]`) |
| **ไม่พบงาน** | ยืนยันว่า ID ของงาน (`1` ในตัวอย่าง) มีอยู่; ใช้ `project.getRootTask().getChildren().size()` เพื่อตรวจสอบ |
| **ข้อยกเว้นไลเซนส์** | ใส่ไลเซนส์ Aspose.Tasks ที่ถูกต้องก่อนเรียกใช้เมธอดใด ๆ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
ตอบ: ใช่, Aspose.Tasks มี API สำหรับ .NET, Java, และแพลตฟอร์มอื่น ๆ ทำให้คุณสามารถ **จัดการไฟล์ Microsoft Project** ด้วยภาษาที่คุณเลือกได้

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks หรือไม่?**  
ตอบ: มีแน่นอน. ดาวน์โหลดรุ่นทดลองเต็มฟังก์ชันจาก [หน้าดาวน์โหลด Aspose.Tasks](https://releases.aspose.com/)  

**ถาม: จะหาเอกสารรายละเอียดของ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: เอกสารอย่างเป็นทางการอยู่ที่ [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)  

**ถาม: จะขอรับการสนับสนุนสำหรับ Aspose.Tasks อย่างไร?**  
ตอบ: เยี่ยมชม [ฟอรัม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อถามคำถามและแบ่งปันประสบการณ์กับชุมชน  

**ถาม: ต้องการไลเซนส์ชั่วคราวสำหรับการประเมินหรือไม่?**  
ตอบ: มีไลเซนส์ชั่วคราวสำหรับการทดสอบระยะสั้น; คุณสามารถขอได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  

---

**อัปเดตล่าสุด:** 2025-12-07  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (เวอร์ชันล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}