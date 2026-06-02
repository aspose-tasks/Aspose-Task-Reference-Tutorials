---
date: 2026-01-18
description: เรียนรู้วิธีสร้างรายการงานด้วย Java และเพิ่มงานลงใน Microsoft Project
  ตั้งค่า baseline โดยไม่ใช้ MS Project ด้วย Aspose.Tasks
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: สร้างรายการงาน Java – Baseline ของ MS Project ด้วย Aspose.Tasks
url: /th/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรายการงาน Java – เบสไลน์ของ MS Project ด้วย Aspose.Tasks

## การแนะนำ
ในบทแนะนำนี้เพิ่มเติม **สร้างรายการงาน Java** โดยการรักษาเบสไลน์ของงานใน Microsoft Project ด้วย Aspose.Tasks for Java Aspose.Tasks ช่วยให้สามารถทำงานกับไฟล์ Project สำหรับติดตั้ง Microsoft Project, ดังนั้น **เพิ่มงานใน Microsoft Project**, จัดการทรัพยากร, และพื้นที่ ** การตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project**— ทั้งหมดจากโค้ด Java ธรรมดา

## คำตอบด่วน
- **Aspose.Tasks ทำอะไร?** ให้ API สำหรับ Java สร้าง อ่าน และแก้ไขไฟล์ Microsoft Project โดยไม่ต้องใช้ MS Project
- **ต้องติดตั้ง Microsoft Project ไหม?** ไม่จำเป็น, Aspose.Tasks อย่างเป็นทางการ.
- **ต้องใช้ Java เซิร์ฟเวอร์ใดๆ?** JDK8 หรืออื่นๆ
- **สามารถตั้งค่าพื้นฐานให้กับงานเดียวได้ไหม?** ได้หรือไม่, ใช้ `setBaseline` พร้อมรายการงาน.
- **ต้องมีลิขสิทธิ์เหตุผลที่จริงหรือไม่?** ต้องมีลิขสิทธิ์เป็นหลักจะลบความเสียหายของรุ่นประเมิน.

## อะไรคือพื้นฐานงาน?
เบสไลน์ของงานบันทึกค่าจุดเริ่มต้น, สิ้นสุด, และต้องใช้เวลาวางแผนไว้เดิมของงานหนึ่ง. มันสรุปจุดอ้างอิงเพื่ออธิบายความจริงกับแผนเดิม

## เหตุใดจึงต้องใช้ Aspose.Tasks เพื่อสร้างรายการงาน Java
- **ไม่จำเป็นต้องมี MS Project** – ฟังก์ชั่นการทำงานอัตโนมัติบนเซิร์ฟเวอร์.
- **ควบคุมโครงสร้าง** งาน, ทรัพยากร, และปฏิทินผ่านโค้ด Java.
- ** จะต้องจดจำการต่อสู้** กับไฟล์ Project 2007‑2024.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK)** – ติดตั้ง JDK8 หรือใหม่กว่า.
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/tasks/java/)

## แพคเกจนำเข้า
เพื่อเริ่มทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ, ให้นำเข้าแพ็กเกจที่จำเป็น:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## ขั้นตอนที่ 1: สร้างออบเจ็กต์โครงการ
```java
Project project = new Project();
```
ที่นี่เราสร้างอ็อบเจกต์ `Project` ใหม่ – ซึ่งเป็นไฟล์ MS Project ที่จะบรรจุรายการงานของเรา.

## ขั้นตอนที่ 2: เพิ่มงานลงในโครงการ
```java
Task task = project.getRootTask().getChildren().add("Task");
```
โดยใช้ `getRootTask()` เราเข้าถึงรากของโครงสร้างโปรเจ็กต์และ **เพิ่มงานใน Microsoft Project**. สตริง `"Task"` คือชื่อของงาน; คุณสามารถเปลี่ยนเป็นคำอธิบายใดก็ได้ที่ต้องการ.

## ขั้นตอนที่ 3: กำหนดเส้นฐานสำหรับงานที่ระบุ
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
เพื่อ **ตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project**, สร้างรายการของงานที่ต้องการตั้งเบสไลน์ (ที่นี่คือ `myList`) แล้วส่งให้ `setBaseline`. เติม `myList` ด้วยงานที่คุณเพิ่มไว้หากต้องการตั้งค่าเบสไลน์แบบเลือกเฉพาะ.

## ขั้นตอนที่ 4: กำหนดเส้นฐานสำหรับโครงการทั้งหมด
```java
project.setBaseline(BaselineType.Baseline);
```
หากต้องการตั้งค่าเบสไลน์ให้กับโปรเจ็กต์ทั้งหมดในครั้งเดียว, เพียงเรียก `setBaseline` พร้อม `BaselineType` ที่ต้องการ.

## วิธีเพิ่มงานใน Microsoft Project โดยใช้ Aspose.Tasks
มาดูงานอย่างเดียว, ในส่วนงานหลายงาน, งานย่อย, และกำหนดทรัพยากรได้. ทุกการเรียก `add()` จะต้องมีอ็อบเจกต์ `Task` การปรับแต่งต่อได้ (ระยะเวลา, วันที่เริ่มต้น ฯลฯ)

## วิธีตั้งค่าพื้นฐานโดยไม่มี MS Project
Aspose.Tasks หลังจากที่เบสไลน์ทำได้ทั้งหมดผ่านโค้ด ในการตั้งค่าเบสไลน์ตามปกติ (Baseline, Baseline1‑Baseline10) โดยเปลี่ยนค่า enum `BaselineType`, อย่าลืมติดตามหลาย ๆ คนของเบสไลน์และเปิด MS Project.

## ปัญหาทั่วไปและแนวทางแก้ไข
- **Baseline ไม่แสดง:** การควบคุมที่คุณเรียกว่า `project.save("output.mpp")` หลังจากที่ตั้งค่าเบสไลน์ (ขั้นตอนการวิจัยถูกละไว้เพื่อความกระชับ)
- **รายการงานว่าง:** สำหรับข้อมูลเพิ่มเติมเพิ่มเติมงานพาเรนต์ที่ถูกต้อง (`getRootTask()` หรืองานย่อย)
- **การประชุมไม่สอดคล้องกัน:** ใช้ JAR ของ Aspose.Tasks ล่าสุดเพื่อรับรองการเฉลิมฉลองกับฟอร์แมต .mpp ใหม่

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Tasks for Java ได้โดยไม่ต้องติดตั้ง Microsoft Project หรือไม่?**  
A: ใช่, Aspose.Tasks ทำงานได้อย่างอิสระและไม่ต้องการ Microsoft Project บนเครื่องโฮสต์.

**Q: Aspose.Tasks for Java รองรับเวอร์ชันต่างๆ ของ Microsoft Project หรือไม่?**  
A: รองรับแน่นอน. ไลบรารีสนับสนุนไฟล์ Project ตั้งแต่ปี 2007 จนถึงรุ่นล่าสุดของปี 2024.

**Q: สามารถจัดการทรัพยากรของโปรเจ็กต์ด้วย Aspose.Tasks for Java ได้หรือไม่?**  
A: ได้, คุณสามารถเพิ่ม, ปรับปรุง, และลบทรัพยากรผ่านโค้ดได้เช่นเดียวกับงาน.

**Q: Aspose.Tasks for Java รองรับการตั้งค่าความสัมพันธ์ระหว่างงานหรือไม่?**  
A: ใช่, คุณสามารถกำหนดความสัมพันธ์ predecessor‑successor ด้วยคลาส `TaskLink`.

**Q: มีการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks for Java หรือไม่?**  
A: มี, คุณสามารถขอความช่วยเหลือได้ผ่าน [support forum](https://forum.aspose.com/c/tasks/15), โดยทีมงาน Aspose และชุมชนจะตอบคำถามของคุณ.

## บทสรุป
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธี **สร้างรายการงาน Java**, **เพิ่มงานใน Microsoft Project**, และ **ตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project** ด้วย Aspose.Tasks. วิธีนี้ช่วยให้การทำอัตโนมัติโปรเจ็กต์เป็นเรื่องง่าย, ไม่ต้องพึ่งพาการติดตั้ง Project บนเดสก์ท็อป, และให้คุณควบคุมข้อมูลโปรเจ็กต์ได้อย่างเต็มที่ผ่านโค้ด.

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
