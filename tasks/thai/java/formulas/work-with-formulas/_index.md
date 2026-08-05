---
date: 2026-02-13
description: เรียนรู้วิธีคำนวณจำนวนวันระหว่างวันที่, สร้างโครงการทดสอบ, และเพิ่มฟิลด์กำหนดเองขณะจัดการไฟล์
  Microsoft Project ด้วย Aspose.Tasks for Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: คำนวณจำนวนวันระหว่างวันที่ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณจำนวนวันระหว่างวันที่ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะ **คำนวณจำนวนวันระหว่างวันที่** โดยการสร้างโครงการทดสอบ, เพิ่มฟิลด์กำหนดเอง, และใช้สูตร Microsoft Project ผ่านไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะต้องการสร้างตารางเวลา, คำนวณกำหนดเวลา, หรืออัตโนมัติการรายงาน, Aspose.Tasks ช่วยให้คุณจัดการข้อมูล Project ด้วยโปรแกรมโดยไม่ต้องติดตั้งบนเครื่องเดสก์ท็อป. เมื่อจบคู่มือคุณจะมีตัวอย่างที่สามารถรันได้ซึ่งกำหนดแอตทริบิวต์ขยาย, ตั้งวันกำหนดเส้นตายสำหรับงาน, และบันทึกโครงการเป็นไฟล์ MPP.

## คำตอบสั้น
- **บทเรียนครอบคลุมอะไร?** การสร้างโครงการทดสอบ, การเพิ่มฟิลด์กำหนดเอง, การกำหนดแอตทริบิวต์ขยาย, และการตั้งวันกำหนดเส้นตายของงานด้วยสูตรเพื่อคำนวณจำนวนวันระหว่างวันที่.  
- **ไลบรารีที่ต้องใช้คืออะไร?** Aspose.Tasks สำหรับ Java (เวอร์ชันล่าสุด).  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง.  
- **ใช้ IDE ไหนได้บ้าง?** IDE ของ Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) ที่รองรับ JDK 8+.  
- **ใช้เวลานานเท่าไหร่ในการทำตาม?** ประมาณ 10‑15 นาทีเพื่อคัดลอกโค้ดและรัน.

## “คำนวณจำนวนวันระหว่างวันที่” ใน Aspose.Tasks คืออะไร?
การคำนวณจำนวนวันระหว่างวันที่หมายถึงการใช้สูตร Project ที่ลบฟิลด์วันที่หนึ่ง (เช่น **Finish**) จากอีกฟิลด์หนึ่ง (เช่น **Deadline**) แล้วคืนค่าต่างกันเป็นจำนวนวัน. สิ่งนี้มีประโยชน์สำหรับการติดตามการล่าช้าของกำหนดเวลา, วัดเวลาบัฟเฟอร์, หรือสร้างรายงานกำหนดเอง.

## ทำไมต้องใช้ Aspose.Tasks เพื่อคำนวณจำนวนวันระหว่างวันที่?
- **Full API coverage** – เข้าถึงคุณสมบัติของ Project, Task, และ Resource ทุกอย่าง.  
- **No Office installation required** – ทำงานบนเซิร์ฟเวอร์, ไทม์ไลน์ CI, และคอนเทนเนอร์ Docker.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วยโค้ด Java เดียวกัน.  
- **Robust formula engine** – ให้คุณกำหนดการคำนวณเช่น `[Deadline] - [Finish]` ภายในไฟล์โครงการโดยตรง.

## วิธีตั้งวันกำหนดเส้นตายสำหรับงาน
การตั้งวันกำหนดเส้นตายเป็นขั้นตอนแรกก่อนที่คุณจะคำนวณช่วงเวลา. วันกำหนดเส้นตายถูกเก็บในฟิลด์ `Tsk.DEADLINE` ของงานและสามารถกำหนดค่าได้โดยใช้อินสแตนซ์ `java.util.Calendar`.

## วิธีกำหนดแอตทริบิวต์ขยาย
แอตทริบิวต์ขยายคือฟิลด์กำหนดเองที่จะเก็บผลลัพธ์ของสูตรของคุณ. คุณกำหนดมันครั้งเดียว, ตั้งชื่อแทนเพื่อให้อ่านง่าย, แล้วแนบสูตรที่ทำการลบวันที่.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK) 8+** – ดาวน์โหลดจากเว็บไซต์ Oracle หรือใช้ OpenJDK.  
- **Aspose.Tasks สำหรับ Java** – รับไฟล์ JAR ล่าสุดจาก [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) แล้วเพิ่มลงใน classpath ของโครงการหรือใน dependencies ของ Maven/Gradle.

## นำเข้าแพ็กเกจ
ก่อนอื่น, นำเข้าคลาสที่เราต้องใช้:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างโครงการทดสอบพร้อมฟิลด์กำหนดเอง
เราจะเริ่มด้วย **การสร้างโครงการทดสอบ** และเพิ่มฟิลด์กำหนดเองที่จะใช้เก็บผลลัพธ์สูตรในภายหลัง.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` เป็นเมธอดช่วยเหลือที่สร้างตารางเวลาขั้นต่ำและลงทะเบียนแอตทริบิวต์ขยายพร้อมสำหรับการกำหนดสูตร.

### ขั้นตอนที่ 2: กำหนดแอตทริบิวต์ขยาย (เพิ่มฟิลด์กำหนดเอง)
ต่อไป, เรา **กำหนดแอตทริบิวต์ขยาย** – ซึ่งก็คือฟิลด์กำหนดเอง – และตั้งชื่อแทนให้เข้าใจง่าย. ที่นี่เราจะ **เพิ่มฟิลด์กำหนดเอง** ด้วยตรรกะของสูตร.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** ทำให้ฟิลด์อ่านง่ายใน Project.  
- **Formula** คำนวณจำนวนวันระหว่างวันที่ *Finish* ของงานและ *Deadline* – เป็นหัวใจของ *คำนวณจำนวนวันระหว่างวันที่*.

### ขั้นตอนที่ 3: ตั้งวันกำหนดเส้นตายสำหรับงาน (เพิ่มงานกำหนดเส้นตาย & ตั้งวันกำหนดเส้นตายของงาน)
ตอนนี้เราจะ **เพิ่มข้อมูลงานกำหนดเส้นตาย** โดยตั้งค่าคุณสมบัติ *Deadline* บนงานที่ระบุ.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- อินสแตนซ์ `Calendar` กำหนดช่วงเวลาที่แน่นอนของวันกำหนดเส้นตาย.  
- `set(Tsk.DEADLINE, …)` **ตั้งวันกำหนดเส้นตายของงาน** สำหรับงานที่เลือก.

### ขั้นตอนที่ 4: บันทึกโครงการ (จัดการไฟล์ Microsoft Project)
สุดท้าย, เราจะ **จัดการไฟล์ Microsoft Project** โดยบันทึกการเปลี่ยนแปลงลงในไฟล์ MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

คุณสามารถเปิด `SaveFile.mpp` ใน Microsoft Project เพื่อดูฟิลด์กำหนดเอง, ผลลัพธ์สูตร, และวันกำหนดเส้นตายที่แสดงในตารางเวลา.

## ปัญหาที่พบบ่อยและวิธีแก้ไข
| Issue | Solution |
|-------|----------|
| **Formula not evaluating** | ตรวจสอบให้แน่ใจว่า string `Formula` ของแอตทริบิวต์ใช้ชื่อฟิลด์ที่ถูกต้อง (เช่น `[Deadline]`, `[Finish]`). |
| **Task not found** | ยืนยันว่า ID ของงาน (`1` ในตัวอย่าง) มีอยู่; ใช้ `project.getRootTask().getChildren().size()` เพื่อตรวจสอบ. |
| **License exception** | ใส่ลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องก่อนเรียกใช้เมธอด API ใด ๆ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ได้, Aspose.Tasks มี API สำหรับ .NET, Java, และแพลตฟอร์มอื่น ๆ, ให้คุณ **จัดการไฟล์ Microsoft Project** ในภาษาที่คุณเลือก.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.Tasks หรือไม่?**  
A: มีแน่นอน. ดาวน์โหลดรุ่นทดลองเต็มฟังก์ชันจาก [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: จะหาเอกสารประกอบละเอียดของ Aspose.Tasks ได้จากที่ไหน?**  
A: เอกสารอย่างเป็นทางการอยู่ที่ [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อถามคำถามและแบ่งปันประสบการณ์กับชุมชน.

**Q: ต้องการลิขสิทธิ์ชั่วคราวสำหรับการประเมินหรือไม่?**  
A: มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบระยะสั้น; คุณสามารถขอได้จาก [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}