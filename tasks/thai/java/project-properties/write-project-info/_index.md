---
date: 2025-12-31
description: เรียนรู้วิธีตั้งค่าวันเริ่มต้นของโครงการ, เขียนข้อมูลโครงการ, และบันทึกโครงการเป็น
  XML โดยใช้ Aspose.Tasks สำหรับ Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: ตั้งค่าวันเริ่มต้นของโครงการใน MS Project ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าวันเริ่มต้นของโครงการใน MS Project ด้วย Aspose.Tasks for Java

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **ตั้งค่าวันเริ่มต้นของโครงการ** และเขียนข้อมูลเพิ่มเติมของ MS Project ด้วย Aspose.Tasks for Java ไม่ว่าคุณจะต้องการอัตโนมัติการจัดตารางโครงการ, สร้างรายงาน, หรือผสานข้อมูล Project เข้ากับระบบขนาดใหญ่ การควบคุมวันเริ่มต้นผ่านโปรแกรมจะให้คุณควบคุมไทม์ไลน์ได้อย่างแม่นยำ เราจะเดินผ่านแต่ละขั้นตอน—from การตั้งค่าสภาพแวดล้อมจนถึงการบันทึกโครงการที่อัปเดตเป็นไฟล์ XML—เพื่อให้คุณสามารถนำเทคนิคเหล่านี้ไปใช้ได้ทันที

## คำตอบสั้น
- **คลาสหลักสำหรับจัดการโครงการคืออะไร?** `Project` จากไลบรารี Aspose.Tasks  
- **จะตั้งค่าวันเริ่มต้นของโครงการอย่างไร?** ใช้ `project.set(Prj.START_DATE, <date>)`  
- **สามารถตั้งค่าวันสถานะได้ด้วยหรือไม่?** ได้, ด้วย `project.set(Prj.STATUS_DATE, <date>)`  
- **ควรใช้รูปแบบใดในการส่งออกโครงการ?** บันทึกเป็น XML ด้วย `SaveFileFormat.Xml`  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องเพื่อใช้งานเต็มรูปแบบ

## **set project start date** คืออะไร?
การตั้งค่าวันเริ่มต้นของโครงการหมายถึงการกำหนดวันในปฏิทินที่งานทั้งหมดจะเริ่มต้นตามกำหนดเวลา นี่เป็นจุดอ้างอิงสำหรับการคำนวณเช่น ระยะเวลางาน, ความขึ้นต่อกัน, และเส้นทางวิกฤต การตั้งค่าวันนี้ผ่านโปรแกรมช่วยให้คุณรักษาความสอดคล้องระหว่างไฟล์โครงการหลายไฟล์และลดข้อผิดพลาดจากการป้อนข้อมูลด้วยมือ

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่อเขียนข้อมูลโครงการ?
- **ครอบคลุม API ทั้งหมด:** อ่าน, แก้ไข, และเขียนคุณสมบัติโครงการทุกอย่างโดยไม่ต้องติดตั้ง Microsoft Project  
- **ข้ามแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS  
- **พร้อมสำหรับการอัตโนมัติ:** เหมาะสำหรับการประมวลผลเป็นชุด, CI pipelines, หรือบริการแบ็กเอนด์ที่สร้างตารางโครงการแบบไดนามิก  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุด (แนะนำ 8+)  
2. **Aspose.Tasks for Java library** – ดาวน์โหลดจาก [here](https://releases.aspose.com/tasks/java/)  
3. **IDE** – IntelliJ IDEA, Eclipse หรือโปรแกรมแก้ไข Java ที่คุณชื่นชอบ  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
กำหนดไดเรกทอรีที่ไฟล์ข้อมูลโครงการจะถูกจัดเก็บ
```java
String dataDir = "Your Data Directory";
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ Project
เริ่มต้นอินสแตนซ์ของโครงการใหม่
```java
Project project = new Project();
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติข้อมูลโครงการ
ที่นี่เราตั้งค่า **project start date**, schedule from start, และ status date—ครอบคลุมคีย์เวิร์ดหลักและรอง *write project information* และ *how to set status*
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## ขั้นตอนที่ 4: บันทึกโครงการเป็น XML
สุดท้ายบันทึกไฟล์โครงการที่อัปเดตไว้ นี้แสดงคีย์เวิร์ดรอง **save project as xml**
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **วันเริ่มต้นไม่ถูกต้อง** | เดือนใน Calendar เริ่มจากศูนย์ใน Java | ใช้ `Calendar.JULY` (หรือเพิ่ม 1 ให้กับดัชนีเดือน) ตามที่แสดง |
| **ไฟล์ไม่ถูกบันทึก** | `dataDir` ไม่มีอยู่หรือไม่มีสิทธิ์เขียน | สร้างไดเรกทอรีล่วงหน้าหรือเลือกเส้นทางที่สามารถเขียนได้ |
| **คำเตือนลิขสิทธิ์** | รันโดยไม่มีลิขสิทธิ์ทำให้มีลายน้ำ | ใส่ลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องก่อนสร้างอ็อบเจกต์ `Project` |

## คำถามที่พบบ่อย
### ถ: สามารถใช้ Aspose.Tasks for Java อ่านไฟล์ MS Project ได้หรือไม่?
**ตอบ:** ได้, Aspose.Tasks for Java มีฟังก์ชันที่แข็งแกร่งสำหรับการอ่านและเขียนไฟล์ MS Project ทั้งหมด  

### ถ: Aspose.Tasks for Java รองรับเวอร์ชันต่าง ๆ ของ MS Project หรือไม่?
**ตอบ:** แน่นอน, Aspose.Tasks for Java รองรับหลายเวอร์ชันของ MS Project ทำให้เข้ากันได้กับรูปแบบไฟล์ที่หลากหลาย  

### ถ: มีข้อจำกัดอะไรบ้างในเวอร์ชันทดลองของ Aspose.Tasks for Java?
**ตอบ:** เวอร์ชันทดลองให้คุณสำรวจความสามารถของไลบรารี แต่มีข้อจำกัดบางอย่าง เช่น ลายน้ำบนไฟล์ผลลัพธ์  

### ถ: จะขอรับการสนับสนุนสำหรับ Aspose.Tasks for Java ได้อย่างไร?
**ตอบ:** คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.Tasks ได้ที่ [here](https://forum.aspose.com/c/tasks/15)  

### ถ: สามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks for Java ได้หรือไม่?
**ตอบ:** ได้, มีใบอนุญาตชั่วคราวสำหรับการใช้งานระยะสั้น คุณสามารถรับได้จาก [here](https://purchase.aspose.com/temporary-license/)  

## สรุป
คุณได้เรียนรู้วิธี **ตั้งค่าวันเริ่มต้นของโครงการ**, เขียนข้อมูลโครงการที่สำคัญ, และ **บันทึกโครงการเป็น XML** ด้วย Aspose.Tasks for Java แล้ว บล็อกพื้นฐานเหล่านี้จะช่วยให้คุณอัตโนมัติการทำงานด้านการจัดการโครงการ, สร้างตารางเวลาที่สอดคล้อง, และผสานข้อมูล MS Project เข้ากับแอปพลิเคชัน Java ของคุณ

---

**อัปเดตล่าสุด:** 2025-12-31  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}