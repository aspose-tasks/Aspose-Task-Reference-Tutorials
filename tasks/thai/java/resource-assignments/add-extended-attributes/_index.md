---
date: 2026-01-05
description: เรียนรู้วิธีตั้งค่าวันเริ่มต้นของโครงการและบันทึกไฟล์ XML ของ MS Project
  ด้วย Aspose.Tasks สำหรับ Java คู่มือขั้นตอนต่อขั้นตอนสำหรับนักพัฒนา Java
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ตั้งค่าวันเริ่มต้นของโครงการด้วย Aspose.Tasks สำหรับ Java
url: /th/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าวันเริ่มต้นของโครงการด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีตั้งค่าวันเริ่มต้นของโครงการ** ในไฟล์ Microsoft Project แล้ว **บันทึกเป็น MS Project XML** ด้วยไลบรารี Aspose.Tasks สำหรับ Java ไม่ว่าคุณจะทำอัตโนมัติของกระบวนการรายงานหรือสร้างเครื่องมือการจัดการโครงการแบบกำหนดเอง การเชี่ยวชาญงานนี้จะช่วยคุณประหยัดเวลาและขจัดข้อผิดพลาดจากการทำด้วยมือ

## คำตอบสั้น
- **วิธีหลักในการตั้งค่าวันเริ่มต้นคืออะไร?** ใช้ `project.set(Prj.START_DATE, …)`.
- **ควรใช้รูปแบบใดในการส่งออกไฟล์?** บันทึกเป็น XML ด้วย `SaveFileFormat.Xml`.
- **ต้องมีลิขสิทธิ์สำหรับการดำเนินการนี้หรือไม่?** เวอร์ชันทดลองทำงานได้ แต่ลิขสิทธิ์เต็มจะลบลายน้ำออก.
- **สามารถเปลี่ยนวันเริ่มต้นหลังจากสร้างงานได้หรือไม่?** ได้, ให้อัปเดตคุณสมบัติของโครงการก่อนเพิ่มงาน.
- **เข้ากันได้กับเวอร์ชัน Microsoft Project ทั้งหมดหรือไม่?** Aspose.Tasks รองรับ XML, MPP และรูปแบบอื่น ๆ อีกมาก.

## “ตั้งค่าวันเริ่มต้นของโครงการ” คืออะไร?
การตั้งค่าวันเริ่มต้นของโครงการกำหนดปฏิทินพื้นฐานที่ใช้เป็นจุดเริ่มต้นสำหรับการคำนวณการจัดตารางงานทั้งหมด เป็นขั้นตอนแรกในการสร้างตารางโครงการที่เชื่อถือได้โดยอัตโนมัติ

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
Aspose.Tasks ให้ API แบบ pure‑Java ที่ทำงานบนทุกแพลตฟอร์มโดยไม่ต้องติดตั้ง Microsoft Project มันช่วยให้คุณสร้าง, แก้ไขและส่งออกข้อมูลโครงการได้อย่างรวดเร็ว ทำให้เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – เวอร์ชัน JDK ใดก็ได้ที่ทันสมัย
2. **Aspose.Tasks for Java** – ดาวน์โหลดจาก [ที่นี่](https://releases.aspose.com/tasks/java/)
3. **IDE** – IntelliJ IDEA, Eclipse หรือ IDE Java ที่คุณชื่นชอบ

## นำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้าคลาสที่จำเป็น:

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
กำหนดตำแหน่งที่ไฟล์ที่สร้างขึ้นจะถูกจัดเก็บ

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ของ Project
สร้างโครงการใหม่ที่ว่างเปล่า

```java
Project project = new Project();
```

### ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติข้อมูลโครงการ
ที่นี่เราจะ **ตั้งค่าวันเริ่มต้นของโครงการ** และคุณสมบัติการจัดตารางที่เกี่ยวข้อง

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### ขั้นตอนที่ 4: บันทึกเป็น MS Project XML
ส่งออกโครงการที่กำหนดค่าแล้วเป็นไฟล์ XML

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **รูปแบบวันที่ไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่าคุณใช้ `java.util.Calendar` และเรียก `getTime()` ก่อนกำหนดค่า
- **ไฟล์ไม่ถูกบันทึก:** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และสามารถเขียนได้
- **คำเตือนลิขสิทธิ์:** เวอร์ชันทดลองจะเพิ่มลายน้ำ; ให้ใช้ลิขสิทธิ์ที่ถูกต้องเพื่อเอาลายน้ำออก

## คำถามที่พบบ่อย

### Q: สามารถใช้ Aspose.Tasks สำหรับ Java อ่านไฟล์ MS Project ได้หรือไม่?  
**A:** ได้, Aspose.Tasks สำหรับ Java มีฟังก์ชันที่แข็งแกร่งสำหรับการอ่านและเขียนไฟล์ MS Project ทั้งสองอย่าง

### Q: Aspose.Tasks สำหรับ Java เข้ากันได้กับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?  
**A:** แน่นอน, Aspose.Tasks สำหรับ Java รองรับรูปแบบไฟล์ MS Project หลากหลาย ทำให้มีความเข้ากันได้กว้างขวาง

### Q: มีข้อจำกัดใดบ้างในเวอร์ชันทดลองของ Aspose.Tasks สำหรับ Java?  
**A:** เวอร์ชันทดลองให้คุณสำรวจไลบรารีได้ แต่จะเพิ่มลายน้ำลงในไฟล์ผลลัพธ์

### Q: จะขอรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร?  
**A:** คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks [ที่นี่](https://forum.aspose.com/c/tasks/15)

### Q: สามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่?  
**A:** ได้, มีไลเซนส์ชั่วคราวสำหรับการใช้งานระยะสั้น สามารถรับได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

### Q: การบันทึกเป็น XML จะคงฟิลด์ที่กำหนดเองไว้หรือไม่?  
**A:** ค่ะ, เมื่อบันทึกด้วย `SaveFileFormat.Xml` จะรักษาคุณลักษณะและฟิลด์ขยายทั้งหมดไว้

### Q: สามารถเปลี่ยนวันเริ่มต้นหลังจากเพิ่มงานได้หรือไม่?  
**A:** คุณสามารถอัปเดตวันเริ่มต้นได้ตลอดเวลา ก่อนบันทึก; เพียงเรียก `project.set(Prj.START_DATE, …)` อีกครั้ง

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}