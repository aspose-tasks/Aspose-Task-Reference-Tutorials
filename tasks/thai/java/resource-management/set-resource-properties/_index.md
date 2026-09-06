---
date: 2026-08-24
description: เรียนรู้วิธีเพิ่ม resource ms project, ตั้งค่า standard rate และคุณสมบัติ
  resource อื่น ๆ ใน MS Project ด้วย Aspose.Tasks for Java, และจัดการ resource อย่างมีประสิทธิภาพ
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: ตั้งค่า Resource Properties ใน Aspose.Tasks
og_description: เพิ่ม resource ms project และตั้งค่า standard rate ด้วย Aspose.Tasks
  for Java. เรียนรู้ข้อกำหนดเบื้องต้น, โค้ดขั้นตอนต่อขั้นตอน, และการแก้ไขปัญหาในคู่มือสั้นนี้
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: เพิ่ม resource ms project และตั้งค่า rate ด้วย Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: วิธีเพิ่ม resource ms project ด้วย Aspose.Tasks
url: /th/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มทรัพยากร ms project และตั้งอัตราใน Aspose.Tasks

## บทนำ
หากคุณกำลังพัฒนาแอปพลิเคชัน Java ที่ต้องอ่านหรือเขียนไฟล์ Microsoft Project, **การเพิ่มทรัพยากร ms project** และการกำหนดอัตรามาตรฐานเป็นงานที่ทำบ่อยแต่สำคัญ ในคู่มือนี้คุณจะได้เห็นวิธีสร้างอ็อบเจ็กต์ `Project`, เพิ่มทรัพยากร, และตั้งค่าอัตรามาตรฐานและอัตราโอเวอร์ไทม์โดยใช้ Aspose.Tasks สำหรับ Java. เมื่อเสร็จคุณจะสามารถทำการคำนวณต้นทุนอัตโนมัติและทำให้กำหนดการโครงการของคุณเป็นปัจจุบันโดยไม่ต้องติดตั้ง Microsoft Project.

## คำตอบสั้น
- **คลาสใดที่เป็นตัวแทนไฟล์ Project?** `Project`
- **เมธอดใดที่เพิ่มทรัพยากรใหม่?** `project.getResources().add()`
- **จะตั้งค่าอัตรามาตรฐานอย่างไร?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **ต้องมีใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่, คุณต้องโหลดใบอนุญาต Aspose.Tasks ที่ถูกต้อง.
- **เวอร์ชัน Java ใดที่รองรับ?** Java 8 ขึ้นไป (แนะนำ Java 17+).

## “ตั้งอัตรามาตรฐาน” คืออะไร
การดำเนินการ *ตั้งอัตรามาตรฐาน* จะกำหนดค่าใช้จ่ายต่อชั่วโมงเริ่มต้นให้กับทรัพยากร อัตรานี้ถูกใช้โดยผู้จัดการโครงการเพื่อคำนวณค่าแรง, สร้างรายงานต้นทุน, และคาดการณ์งบประมาณ, เพื่อให้การคำนวณต้นทุนสะท้อนราคาที่คาดว่าจะจ่ายสำหรับงานที่ทำโดยแต่ละทรัพยากรตลอดวงจรชีวิตของโครงการ.

## ทำไมต้องตั้งอัตราด้วย Aspose.Tasks?
Aspose.Tasks สามารถประมวลผล **มากกว่า 50 รูปแบบไฟล์เข้าและออก** รวมถึงไฟล์ MPP, MPX, XML, และ Primavera และสามารถจัดการโครงการหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ สิ่งนี้ทำให้สามารถประมวลผลแบบแบตช์ความเร็วสูงบนเซิร์ฟเวอร์ Windows, Linux หรือ macOS, ลดความพยายามในการทำงานด้วยมือได้ถึง 90 % ในสถานการณ์อัตโนมัติทั่วไป.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบให้แน่ใจว่ารายการต่อไปนี้พร้อมใช้งาน:

### การตั้งค่าสภาพแวดล้อมการพัฒนา Java
1. ติดตั้ง JDK 8 หรือใหม่กว่า คุณสามารถดาวน์โหลดได้จาก [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. เลือก IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans และตั้งค่าให้พร้อมสำหรับการพัฒนา Java.

### การติดตั้ง Aspose.Tasks สำหรับ Java
1. ดาวน์โหลดแพคเกจ Aspose.Tasks สำหรับ Java ล่าสุดจาก [download page](https://releases.aspose.com/tasks/java/).  
2. เพิ่มไฟล์ JAR ไปยัง classpath ของโปรเจกต์ของคุณหรือประกาศการพึ่งพา Maven/Gradle ตามที่แสดงในเอกสารผลิตภัณฑ์.

## นำเข้าแพ็กเกจ
นำเข้าคลาสหลักของ Aspose.Tasks ที่คุณต้องการ ขั้นตอนนี้จะให้คุณเข้าถึงประเภท `Project`, `Resource`, และ `Rsc` ที่ใช้ต่อไป.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์โปรเจกต์
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนสุดที่แทนไฟล์ MS Project ทั้งหมดในหน่วยความจำ การสร้างอินสแตนซ์ของมันจะสร้างโปรเจกต์เปล่าที่คุณสามารถเติมด้วยงาน, ทรัพยากร, และข้อมูลอื่น ๆ.

```java
Project project = new Project();
```

## ขั้นตอนที่ 2: เพิ่มทรัพยากร (add resource ms project)
คลาส `Resource` จำลองทรัพยากรโครงการหนึ่งรายการ เช่น บุคคล, อุปกรณ์, หรือวัสดุ การเพิ่มทรัพยากรโดยใช้ `project.getResources().add()` จะคืนค่าอินสแตนซ์ `Resource` ที่ไม่เป็น null พร้อมสำหรับการกำหนดคุณสมบัติ.

```java
Resource rsc = project.getResources().add("Rsc");
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติของทรัพยากร (how to set rates)
enum `Rsc` มีค่าคงที่สำหรับฟิลด์ของทรัพยากร เช่น `STANDARD_RATE` และ `OVERTIME_RATE`.  
คุณตั้งค่าอัตรามาตรฐานและอัตราโอเวอร์ไทม์โดยเรียก `set` บนวัตถุ `Resource` พร้อมค่าของ enum `Rsc` ที่เหมาะสม. อัตราถูกเก็บเป็น `BigDecimal` เพื่อรักษาความแม่นยำของค่าเงิน.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| `NullPointerException` เมื่อเรียก `set` | ทรัพยากรไม่ได้ถูกเพิ่มอย่างถูกต้อง. | ตรวจสอบให้แน่ใจว่า `project.getResources().add()` คืนค่า `Resource` ที่ไม่เป็น null. |
| อัตราปรากฏเป็น 0 ในไฟล์ที่บันทึก | ใช้ `int` แทน `BigDecimal`. | ใช้ `BigDecimal.valueOf()` สำหรับค่าด้านการเงินเสมอ. |
| ไม่พบใบอนุญาต | ไฟล์ใบอนุญาตไม่ได้โหลดก่อนสร้าง `Project`. | โหลดใบอนุญาต (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) ที่จุดเริ่มต้นของโปรแกรม. |

## สรุป
ตอนนี้คุณรู้วิธี **เพิ่มทรัพยากร ms project**, สร้างอ็อบเจ็กต์ `Project`, และ **ตั้งค่าอัตรามาตรฐานและอัตราโอเวอร์ไทม์** ด้วย Aspose.Tasks สำหรับ Java ความสามารถนี้ทำให้คุณสามารถทำการคำนวณต้นทุนอัตโนมัติ, สร้างรายงานแบบกำหนดเอง, และจัดการทรัพยากร MS Project อย่างเต็มรูปแบบจากแอปพลิเคชัน Java ใดก็ได้.

## คำถามที่พบบ่อย
**ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการไฟล์ MS Project ที่ซับซ้อนได้หรือไม่?**  
ตอบ: ใช่, รองรับรูปแบบ Project หลักทั้งหมด รวมถึงไฟล์ขนาดใหญ่ที่มีงานและทรัพยากรหลายพันรายการ, รักษาทุกฟิลด์โดยไม่มีการสูญเสียข้อมูล.

**ถาม: มีการทดลองใช้ฟรีหรือไม่?**  
ตอบ: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Tasks สำหรับ Java ได้จาก [Aspose.Tasks free trial page](https://releases.aspose.com/).

**ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้จากที่ไหน?**  
ตอบ: คุณสามารถขอความช่วยเหลือได้ที่ [support forum](https://forum.aspose.com/c/tasks/15).

**ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับการประเมินได้อย่างไร?**  
ตอบ: มีใบอนุญาตชั่วคราวให้บริการจาก [temporary license page](https://purchase.aspose.com/temporary-license/).

**ถาม: ฉันจะซื้อเวอร์ชันที่มีใบอนุญาตได้จากที่ไหน?**  
ตอบ: ซื้อใบอนุญาตเต็มรูปแบบได้จาก [purchase page](https://purchase.aspose.com/buy).

---

**อัปเดตล่าสุด:** 2026-08-24  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างทรัพยากร – การจัดการทรัพยากรด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/)
- [เพิ่มทรัพยากรลงในโปรเจกต์ด้วย Aspose.Tasks สำหรับ Java](/tasks/java/resource-management/create-resources/)
- [วิธีเพิ่มทรัพยากรลงในโปรเจกต์และจัดการคุณสมบัติการหน่วงเวลา Leveling ใน Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}