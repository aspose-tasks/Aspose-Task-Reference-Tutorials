---
date: 2025-12-31
description: เรียนรู้วิธีอ่านข้อมูลโครงการ รวมถึงกำหนดการตั้งแต่เริ่มต้นโดยใช้ Aspose.Tasks
  สำหรับ Java ค้นพบวิธีดึงคุณสมบัติโครงการใน Java อย่างรวดเร็ว
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks for Java

## การแนะนำ
**วิธีอ่านข้อมูลโครงการ** รายละเอียดเช่นวันที่เริ่มต้นวันที่สิ้นสุดหรือในช่วงปฏิทินในไฟล์ Microsoft Project, Aspose.Tasks สำหรับ Java ให้อ่านที่สะอาดและเน้นโค้ดเป็นหลักในการตอบสนองนี้คุณจะเห็นได้ใน **วิธีอ่านข้อมูลโครงการ** เมตาดาต้าเข้าใจ ** การตั้งค่าโครงการจากการเปิดใช้งาน** และเรียนรู้การดึงคุณสมบัติสำคัญอื่นๆ — ทั้งหมดที่นี่ในมัลติบรรทัดของโค้ด Java

## คำตอบด่วน
- **Aspose.Tasks for Javaทำอะไร?** ต้องให้ไฟล์ Microsoft Project (MPP, XML และอื่นๆ) ผ่านโปรแกรมที่ติดตั้ง Microsoft Project
- ** คุณสมบัติใดๆ บอกว่ามาจากการเยี่ยมชม?** `Prj.SCHEDULE_FROM_START` – true ฟังก์ชั่นกำหนดการจากระยะไกล, false ต่อเนื่องไปจนถึงสิ้นสุด
- **พบคุณสมบัติโครงการใน Java ได้หรือไม่**, อ่านวันที่เริ่มต้น, วันที่สิ้นสุด, วันที่ปัจจุบัน, วันที่สถานะ, และชื่อปฏิทิน
- ** ยืนยันไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวใช้ได้สำหรับการวิจัย; ไลเซนส์เต็มความจำเป็นจริง.
- **ต้องการเซิร์ฟเวอร์ Java ใด ๆ?** Java8 หรือตามความต้องการไฟล์ JAR ของ Aspose.Tasks อยู่ใน classpath

## ข้อกำหนดเบื้องต้น
ประวัติเริ่ม, ขอให้คุณเชื่อในคุณ:

1. **Java Development Environment** – JDK8 หรือใหม่กว่าที่จำเป็นและทุกอย่าง
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีล่าสุดจาก [เว็บไซต์](https://releases.aspose.com/tasks/java/)

## แพคเกจนำเข้า
เพื่อโต้ตอบกับไฟล์โครงการ, ให้นำเข้า namespace หลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ของคุณ. แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ Microsoft Project ที่คุณต้องการตรวจสอบ.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### ขั้นตอนที่ 3: กำหนดฐานตารางเวลาโครงการ
ตรวจสอบว่ากำหนดการคำนวณจากวันที่เริ่มต้นของโครงการหรือจากวันที่สิ้นสุด นี่คือหัวใจของ **วิธีอ่านข้อมูลโครงการ** เกี่ยวกับข้อมูลกำหนดการ.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **เคล็ดลับ:** `Prj.SCHEDULE_FROM_START` คืนค่า Boolean; `true` หมายถึง *กำหนดการโครงการจากการเริ่มต้น*.

### ขั้นตอนที่ 4: ดึงข้อมูลตารางเวลาโครงการเพิ่มเติม
นอกเหนือจากวันที่เริ่มต้น/สิ้นสุด, คุณมักต้องการวันที่ปัจจุบัน, วันที่สถานะ, และปฏิทินที่เชื่อมโยงกับโครงการ นี่แสดงตัวอย่าง **อ่านคุณสมบัติโครงการ java** ในการทำงาน.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## ปัญหาและแนวทางแก้ไขทั่วไป
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` บน `project.get(Prj.CALENDAR)` | มีโครงการไม่มีปฏิทินเริ่มต้น. | ถ่ายภาพให้ไฟล์ MPP กำหนดปฏิทินหรือทำการตรวจสอบ `null` |
| วันที่พิมพ์เป็น `null` | จะมีการแจ้งหรือขาดการแจ้งเตือนวันที่. | การตัดไฟล์ต้นทางใน Microsoft Project อย่างเป็นทางการ |
| ข้อผิดพลาดในการรวบรวม: `ไม่พบสัญลักษณ์ Prj` | Aspose.Tasks JAR ไม่อยู่ใน classpath | `aspose-tasks-xx.jar` ยังคงเส้นทางของโปรเจกต์. |

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถใช้ Aspose.Tasks for Java กับไฟล์ Microsoft Project บัลเล่ต์หรือไม่ก็ได้?
ตอบ: ถูกต้อง, Aspose.Tasks สำหรับ Java ที่รองรับไฟล์ Microsoft Project เพื่อตรวจสอบรูปแบบ MPP และ XML

### ถาม: Aspose.Tasks สำหรับ Java สามารถตรวจสอบการพัฒนา Java ได้หรือไม่?
ตอบ: Aspose.Tasks for Java ไม่จำเป็นต้องพูดถึงการพัฒนา Java อีกครั้ง, ส่วนเนื้อหาของภาพยนตร์เรื่องนี้

### ถาม: Aspose.Tasks for Java มีการจัดการข้อมูลโครงการเพื่อตรวจสอบข้อมูลหรือไม่?
ตอบ: แน่นอน, Aspose.Tasks for Java มีฟังก์ชั่นการทำงานสำหรับการจัดการข้อมูลโครงการ, และความเชื่อ, ร้องเรียน, และความเชื่อ

### ถาม: ระบบอัตโนมัติการสกัดข้อมูลโครงการต่างๆ Aspose.Tasks for Java สามารถทำได้หรือไม่?
ตอบ: ถูกต้อง, Aspose.Tasks สำหรับ Java ทำงานอัตโนมัติผ่าน API ที่ครบถ้วน, หากต้องการทราบวิเคราะห์ข้อมูลและวิเคราะห์ความคิดเห็น

### ถาม: มีฟอรั่มชุมชนหรือช่องทางสนับสนุน Aspose.Tasks สำหรับ Java หรือเปล่า?
ตอบ: มีแหล่งที่มาของทรัพยากรและชุมชนเข้าร่วมได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

### ถาม: ฉันอ่านคุณสมบัติโครงการใน Java โดยไม่โหลดต้นไม้งานทั้งหมดได้อย่างไร?
A: ใช้เมธอด `Project.get` พร้อมค่าการนับ `Prj` ต้องการ; วิธีการดึงเมตาดาต้าเท่านั้น โดยที่การใช้น้อยลง

### ถาม: ไม่ว่าไฟล์ MPP ขนาดใหญ่เมื่อสกัดคุณสมบัติคืออะไร?
ตอบ: อ่านโครงการที่เกี่ยวข้อง *อ่าน-อย่างเดียว* (`new Project(filePath, LoadOptions)`) และสอบถามเฉพาะคุณสมบัติที่ต้องการสำหรับการใช้งานสูง

## บทสรุป
โดยทำตามคู่มือนี้คุณจะรู้ **วิธีอ่านข้อมูลโครงการ** เช่น แหล่งกำเนิดของกำหนดการ, วันที่, และรายละเอียดปฏิทินโดยใช้ Aspose.Tasks for Java การนำสคริปต์เหล่านี้เข้าไปในแอปพลิเคชันของคุณทำให้สามารถสร้างรายงานอัตโนมัติ, แดชบอร์ดแบบกำหนดเอง, และการตัดสินใจที่ชาญฉลาดโดยไม่ต้องโต้ตอบด้วยมือกับ Microsoft Project.

---

**อัปเดตล่าสุด:** 2025-12-31  
**ทดสอบกับ:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}