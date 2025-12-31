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

## Introduction
หากคุณต้องการ **วิธีอ่านข้อมูลโครงการ** รายละเอียดเช่น วันที่เริ่มต้น วันที่สิ้นสุด หรือการตั้งค่าปฏิทินโดยตรงจากไฟล์ Microsoft Project, Aspose.Tasks for Java ให้วิธีการที่สะอาดและเน้นโค้ดเป็นหลัก ในบทเรียนนี้คุณจะเห็นอย่างชัดเจน **วิธีอ่านข้อมูลโครงการ** เมตาดาต้า เข้าใจ **กำหนดการโครงการจากการเริ่มต้น** และเรียนรู้การดึงคุณสมบัติสำคัญอื่น ๆ — ทั้งหมดนี้ในไม่กี่บรรทัดของโค้ด Java

## Quick Answers
- **Aspose.Tasks for Java ทำอะไร?** มันให้การเข้าถึงไฟล์ Microsoft Project (MPP, XML ฯลฯ) ผ่านโปรแกรมโดยไม่ต้องติดตั้ง Microsoft Project.  
- **คุณสมบัติใดบอกว่ากำหนดการอิงจากการเริ่มต้น?** `Prj.SCHEDULE_FROM_START` – true หมายถึงกำหนดการจากการเริ่มต้น, false หมายถึงจากการสิ้นสุด.  
- **ฉันสามารถดึงคุณสมบัติโครงการใน Java ได้หรือไม่?** ได้, คุณสามารถอ่านวันที่เริ่มต้น, วันที่สิ้นสุด, วันที่ปัจจุบัน, วันที่สถานะ, และชื่อปฏิทิน.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวฟรีใช้ได้สำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า พร้อมกับไฟล์ JAR ของ Aspose.Tasks อยู่ใน classpath.

## Prerequisites
ก่อนที่คุณจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. **Java Development Environment** – JDK 8 หรือใหม่กว่า ติดตั้งและกำหนดค่าเรียบร้อยแล้ว.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีล่าสุดจาก [website](https://releases.aspose.com/tasks/java/).  

## Import Packages
เพื่อโต้ตอบกับไฟล์โครงการ, ให้นำเข้า namespace หลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
กำหนดโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ของคุณ. แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ Microsoft Project ที่คุณต้องการตรวจสอบ.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### Step 3: Determine the Project Schedule Basis
ตรวจสอบว่ากำหนดการคำนวณจากวันที่เริ่มต้นของโครงการหรือจากวันที่สิ้นสุด นี่คือหัวใจของ **วิธีอ่านข้อมูลโครงการ** เกี่ยวกับข้อมูลกำหนดการ.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **เคล็ดลับ:** `Prj.SCHEDULE_FROM_START` คืนค่า Boolean; `true` หมายถึง *กำหนดการโครงการจากการเริ่มต้น*.

### Step 4: Retrieve Additional Project Schedule Information
นอกเหนือจากวันที่เริ่มต้น/สิ้นสุด, คุณมักต้องการวันที่ปัจจุบัน, วันที่สถานะ, และปฏิทินที่เชื่อมโยงกับโครงการ นี่แสดงตัวอย่าง **อ่านคุณสมบัติโครงการ java** ในการทำงาน.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## Common Issues & Solutions
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` on `project.get(Prj.CALENDAR)` | ไฟล์โครงการไม่มีปฏิทินเริ่มต้น. | ตรวจสอบให้ไฟล์ MPP กำหนดปฏิทินหรือทำการตรวจสอบ `null`. |
| Dates printed as `null` | ไฟล์โครงการเสียหายหรือขาดฟิลด์วันที่. | ตรวจสอบไฟล์ต้นทางใน Microsoft Project ก่อนประมวลผล. |
| Compilation error: `cannot find symbol Prj` | Aspose.Tasks JAR ไม่อยู่ใน classpath. | เพิ่ม `aspose-tasks-xx.jar` ไปยังเส้นทางการสร้างของโปรเจกต์. |

## Frequently Asked Questions

### Q: ฉันสามารถใช้ Aspose.Tasks for Java กับไฟล์ Microsoft Project เวอร์ชันใดก็ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java รองรับไฟล์ Microsoft Project หลายเวอร์ชัน รวมถึงรูปแบบ MPP และ XML.

### Q: Aspose.Tasks for Java เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ส่วนใหญ่หรือไม่?
A: Aspose.Tasks for Java เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ส่วนใหญ่, ทำให้การรวมเป็นไปอย่างยืดหยุ่น.

### Q: Aspose.Tasks for Java มีการสนับสนุนการจัดการข้อมูลโครงการนอกเหนือจากการอ่านข้อมูลหรือไม่?
A: แน่นอน, Aspose.Tasks for Java มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการจัดการข้อมูลโครงการ, รวมถึงการแก้ไข, การบันทึก, และการส่งออก.

### Q: ฉันสามารถอัตโนมัติการสกัดข้อมูลโครงการโดยใช้ Aspose.Tasks for Java ได้หรือไม่?
A: ใช่, Aspose.Tasks for Java อนุญาตให้ทำการอัตโนมัติผ่าน API ที่ครบถ้วน, ทำให้กระบวนการสกัดข้อมูลและวิเคราะห์เป็นไปอย่างราบรื่น.

### Q: มีฟอรั่มชุมชนหรือช่องทางสนับสนุนสำหรับผู้ใช้ Aspose.Tasks for Java หรือไม่?
A: มี, คุณสามารถค้นหาทรัพยากรที่เป็นประโยชน์และเข้าร่วมชุมชนได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q: ฉันจะอ่านคุณสมบัติโครงการใน Java โดยไม่โหลดต้นไม้งานทั้งหมดได้อย่างไร?
A: ใช้เมธอด `Project.get` พร้อมค่าการนับ `Prj` ที่ต้องการ; วิธีนี้จะดึงเมตาดาต้าเท่านั้น, ทำให้การใช้หน่วยความจำน้อยลง.

### Q: วิธีที่ดีที่สุดในการจัดการไฟล์ MPP ขนาดใหญ่เมื่อสกัดคุณสมบัติคืออะไร?
A: โหลดโครงการในโหมด *อ่าน‑อย่างเดียว* (`new Project(filePath, LoadOptions)`) และสอบถามเฉพาะคุณสมบัติที่ต้องการเพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง.

## Conclusion
โดยทำตามคู่มือนี้คุณจะรู้ **วิธีอ่านข้อมูลโครงการ** เช่น แหล่งกำเนิดของกำหนดการ, วันที่, และรายละเอียดปฏิทินโดยใช้ Aspose.Tasks for Java การนำสคริปต์เหล่านี้เข้าไปในแอปพลิเคชันของคุณทำให้สามารถสร้างรายงานอัตโนมัติ, แดชบอร์ดแบบกำหนดเอง, และการตัดสินใจที่ชาญฉลาดโดยไม่ต้องโต้ตอบด้วยมือกับ Microsoft Project.

---

**อัปเดตล่าสุด:** 2025-12-31  
**ทดสอบกับ:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}