---
date: 2026-04-24
description: เรียนรู้วิธีอ่านข้อมูลโครงการ รวมถึงกำหนดการตั้งแต่เริ่มต้นโดยใช้ Aspose.Tasks
  สำหรับ Java ค้นพบวิธีดึงคุณสมบัติโครงการใน Java อย่างรวดเร็ว.
keywords:
- how to read project
- Aspose.Tasks Java
- read project properties
linktitle: อ่านข้อมูลโครงการด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
title: วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านข้อมูลโครงการจาก Microsoft Project ด้วย Aspose.Tasks for Java

## คำนำ
หากคุณต้องการ **วิธีอ่านโครงการ** รายละเอียดเช่น วันที่เริ่มต้น วันที่สิ้นสุด หรือการตั้งค่าปฏิทินโดยตรงจากไฟล์ Microsoft Project, Aspose.Tasks for Java จะมอบวิธีการแบบโค้ด‑ไฟร์สท์ที่สะอาด ในบทแนะนำนี้คุณจะได้เห็น **วิธีอ่านโครงการ** เมตาดาต้าอย่างชัดเจน เข้าใจ **กำหนดการโครงการจากการเริ่มต้น** และเรียนรู้การดึงคุณสมบัติสำคัญอื่น ๆ — ทั้งหมดในไม่กี่บรรทัดของโค้ด Java

## คำตอบสั้น
- **Aspose.Tasks for Java ทำอะไร?** ให้การเข้าถึงไฟล์ Microsoft Project (MPP, XML ฯลฯ) แบบโปรแกรมเมติกโดยไม่ต้องติดตั้ง Microsoft Project  
- **คุณสมบัติใดบอกว่ากำหนดการอิงจากการเริ่มต้น?** `Prj.SCHEDULE_FROM_START` – true หมายถึงกำหนดการจากการเริ่มต้น, false หมายถึงจากการสิ้นสุด  
- **ฉันสามารถดึงคุณสมบัติโครงการใน Java ได้หรือไม่?** ได้, คุณสามารถอ่านวันที่เริ่มต้น, วันที่สิ้นสุด, วันที่ปัจจุบัน, วันที่สถานะ, และชื่อปฏิทินได้  
- **ต้องใช้ไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวฟรีใช้สำหรับการประเมิน; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือสูงกว่า พร้อมกับไฟล์ JAR ของ Aspose.Tasks บน classpath  
- **มีวิธีโหลดไฟล์ในโหมดอ่าน‑อย่างเดียวหรือไม่?** มี — ใช้ `new Project(filePath, new LoadOptions())` แล้วตั้งค่า `ReadOnly` เป็น true เพื่อลดการใช้หน่วยความจำ

## ทำไมต้องใช้ Aspose.Tasks for Java เพื่ออ่านข้อมูลโครงการ?
การอ่านข้อมูลโครงการโดยตรงจากไฟล์ MPP ช่วยให้คุณอัตโนมัติการรายงาน, ป้อนข้อมูลแดชบอร์ด, หรือรวมกำหนดการโครงการเข้ากับตรรกะธุรกิจที่กำหนดเองโดยไม่ต้องทำขั้นตอนการส่งออกด้วยมือ Aspose.Tasks รองรับทุกเวอร์ชันของ Microsoft Project, ทำให้คุณได้โซลูชันที่เชื่อถือได้และไม่ขึ้นกับเวอร์ชัน ซึ่งทำงานบนแพลตฟอร์มใด ๆ ที่สนับสนุน Java

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือใหม่กว่า ติดตั้งและกำหนดค่าเรียบร้อย  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีล่าสุดจาก [website](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
เพื่อทำงานกับไฟล์โครงการ, นำเข้า namespace หลักของ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
ตั้งค่าโฟลเดอร์ที่บรรจุไฟล์ `.mpp` ของคุณ แทนที่ตัวแปรตำแหน่งที่เก็บด้วยพาธจริงบนเครื่องของคุณ

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: โหลดไฟล์โครงการ
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ Microsoft Project ที่คุณต้องการตรวจสอบ

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### ขั้นตอนที่ 3: กำหนดฐานการคำนวณกำหนดการโครงการ
ตรวจสอบว่ากำหนดการคำนวณจากวันที่เริ่มต้นของโครงการหรือจากวันที่สิ้นสุด นี่คือหัวใจของ **วิธีอ่านโครงการ** ข้อมูลกำหนดการ

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **เคล็ดลับ:** `Prj.SCHEDULE_FROM_START` คืนค่า Boolean; `true` หมายถึง *กำหนดการโครงการจากการเริ่มต้น*

### ขั้นตอนที่ 4: ดึงข้อมูลกำหนดการโครงการเพิ่มเติม
นอกจากวันที่เริ่ม/สิ้นสุด, คุณมักต้องการวันที่ปัจจุบัน, วันที่สถานะ, และปฏิทินที่เชื่อมโยงกับโครงการ นี่เป็นการสาธิต **read project properties java** ในการทำงาน

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## ปัญหาทั่วไป & วิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` ที่ `project.get(Prj.CALENDAR)` | ไฟล์โครงการไม่มีปฏิทินเริ่มต้น | ตรวจสอบให้ไฟล์ MPP กำหนดปฏิทินหรือทำการตรวจสอบค่า `null` |
| วันที่แสดงเป็น `null` | ไฟล์โครงการเสียหายหรือไม่มีฟิลด์วันที่ | ตรวจสอบไฟล์ต้นฉบับใน Microsoft Project ก่อนประมวลผล |
| ข้อผิดพลาดการคอมไพล์: `cannot find symbol Prj` | ไฟล์ JAR ของ Aspose.Tasks ไม่อยู่ใน classpath | เพิ่ม `aspose-tasks-xx.jar` ไปยังเส้นทางการสร้างของโปรเจกต์ |

## คำถามที่พบบ่อย

### Q: Aspose.Tasks for Java รองรับไฟล์ Microsoft Project เวอร์ชันใดบ้าง?
**A:** รองรับหลายเวอร์ชันของไฟล์ Microsoft Project รวมถึงรูปแบบ MPP และ XML

### Q: Aspose.Tasks for Java เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ทุกประเภทหรือไม่?
**A:** เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ส่วนใหญ่, ให้ความยืดหยุ่นในการผสานรวม

### Q: Aspose.Tasks for Java มีฟังก์ชันการจัดการข้อมูลโครงการนอกเหนือจากการอ่านข้อมูลหรือไม่?
**A:** มี, Aspose.Tasks for Java มีฟังก์ชันการแก้ไข, บันทึก, และส่งออกข้อมูลโครงการอย่างครอบคลุม

### Q: ฉันสามารถอัตโนมัติการสกัดข้อมูลโครงการด้วย Aspose.Tasks for Java ได้หรือไม่?
**A:** ได้, Aspose.Tasks for Java รองรับการอัตโนมัติผ่าน API ที่ครบถ้วน, ช่วยให้กระบวนการสกัดและวิเคราะห์ข้อมูลเป็นไปอย่างราบรื่น

### Q: มีฟอรั่มชุมชนหรือช่องทางสนับสนุนสำหรับผู้ใช้ Aspose.Tasks for Java หรือไม่?
**A:** มี, คุณสามารถค้นหาทรัพยากรและเข้าร่วมชุมชนได้ที่ [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

### Q: ฉันจะอ่านคุณสมบัติโครงการใน Java โดยไม่โหลดต้นไม้งานทั้งหมดได้อย่างไร?
**A:** ใช้เมธอด `Project.get` พร้อมค่าการนับ `Prj` ที่ต้องการ; วิธีนี้จะดึงเมตาดาต้าเท่านั้น, ลดการใช้หน่วยความจำ

### Q: วิธีที่ดีที่สุดในการจัดการไฟล์ MPP ขนาดใหญ่เมื่อสกัดคุณสมบัติคืออะไร?
**A:** โหลดโครงการในโหมด *อ่าน‑อย่างเดียว* (`new Project(filePath, LoadOptions)`) แล้วคิวรีเฉพาะคุณสมบัติที่ต้องการเพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง

## สรุป
โดยทำตามคู่มือนี้คุณจะรู้ **วิธีอ่านโครงการ** เช่น แหล่งกำเนิดกำหนดการ, วันที่, และรายละเอียดปฏิทินโดยใช้ Aspose.Tasks for Java การนำสคริปต์เหล่านี้ไปใช้ในแอปพลิเคชันของคุณจะทำให้การรายงานอัตโนมัติ, แดชบอร์ดแบบกำหนดเอง, และการตัดสินใจที่ชาญฉลาดเป็นไปได้โดยไม่ต้องโต้ตอบกับ Microsoft Project ด้วยตนเอง

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}