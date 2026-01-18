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

## Introduction
ในบทแนะนำนี้ คุณจะ **สร้างรายการงาน Java** โดยการสร้างเบสไลน์ของงานใน Microsoft Project ด้วย Aspose.Tasks for Java. Aspose.Tasks ช่วยให้คุณทำงานกับไฟล์ Project ได้โดยไม่ต้องติดตั้ง Microsoft Project, ดังนั้นคุณสามารถ **เพิ่มงานใน Microsoft Project**, จัดการทรัพยากร, และแม้กระทั่ง **ตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project**—ทั้งหมดจากโค้ด Java ธรรมดา.

## Quick Answers
- **Aspose.Tasks ทำอะไร?** ให้ API สำหรับ Java เพื่อสร้าง, อ่าน, และแก้ไขไฟล์ Microsoft Project โดยไม่ต้องใช้ MS Project.  
- **ต้องติดตั้ง Microsoft Project ไหม?** ไม่จำเป็น, Aspose.Tasks ทำงานได้อย่างอิสระ.  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 8 หรือสูงกว่า.  
- **สามารถตั้งค่าเบสไลน์ให้กับงานเดียวได้ไหม?** ได้, ใช้ `setBaseline` พร้อมรายการงาน.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ต้องมี, ลิขสิทธิ์เชิงพาณิชย์จะลบข้อจำกัดของรุ่นประเมิน.

## What is a Task Baseline?
เบสไลน์ของงานบันทึกค่าการเริ่มต้น, สิ้นสุด, และงานที่วางแผนไว้เดิมของงานหนึ่ง. มันทำหน้าที่เป็นจุดอ้างอิงเพื่อเปรียบเทียบความคืบหน้าจริงกับแผนเดิม.

## Why use Aspose.Tasks to create task list Java?
- **ไม่ต้องพึ่งพา MS Project** – เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์.  
- **ควบคุมเต็มรูปแบบ** งาน, ทรัพยากร, และปฏิทินผ่านโค้ด Java.  
- **ความเข้ากันได้ข้ามเวอร์ชัน** กับไฟล์ Project 2007‑2024.

## Prerequisites
1. **Java Development Kit (JDK)** – ติดตั้ง JDK 8 หรือใหม่กว่า.  
2. **Aspose.Tasks for Java** – ดาวน์โหลดไลบรารีจาก [download link](https://releases.aspose.com/tasks/java/).  

## Import Packages
เพื่อเริ่มทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ, ให้นำเข้าแพ็กเกจที่จำเป็น:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Step 1: Create a Project Object
```java
Project project = new Project();
```
ที่นี่เราสร้างอ็อบเจกต์ `Project` ใหม่ – ซึ่งเป็นไฟล์ MS Project ที่จะบรรจุรายการงานของเรา.

## Step 2: Add a Task to the Project
```java
Task task = project.getRootTask().getChildren().add("Task");
```
โดยใช้ `getRootTask()` เราเข้าถึงรากของโครงสร้างโปรเจ็กต์และ **เพิ่มงานใน Microsoft Project**. สตริง `"Task"` คือชื่อของงาน; คุณสามารถเปลี่ยนเป็นคำอธิบายใดก็ได้ที่ต้องการ.

## Step 3: Set Baseline for Specified Tasks
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
เพื่อ **ตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project**, สร้างรายการของงานที่ต้องการตั้งเบสไลน์ (ที่นี่คือ `myList`) แล้วส่งให้ `setBaseline`. เติม `myList` ด้วยงานที่คุณเพิ่มไว้หากต้องการตั้งค่าเบสไลน์แบบเลือกเฉพาะ.

## Step 4: Set Baseline for the Entire Project
```java
project.setBaseline(BaselineType.Baseline);
```
หากต้องการตั้งค่าเบสไลน์ให้กับโปรเจ็กต์ทั้งหมดในครั้งเดียว, เพียงเรียก `setBaseline` พร้อม `BaselineType` ที่ต้องการ.

## How to add task to Microsoft Project using Aspose.Tasks
นอกจากงานเดียวที่แสดงข้างต้น, คุณสามารถเพิ่มหลายงาน, งานย่อย, และกำหนดทรัพยากรได้. ทุกการเรียก `add()` จะคืนค่าอ็อบเจกต์ `Task` ที่คุณสามารถตั้งค่าต่อได้ (ระยะเวลา, วันที่เริ่มต้น ฯลฯ).

## How to set baseline without MS Project
Aspose.Tasks ทำให้การสร้างเบสไลน์ทำได้ทั้งหมดผ่านโค้ด. คุณสามารถตั้งค่าเบสไลน์หลายประเภท (Baseline, Baseline1‑Baseline10) โดยเปลี่ยนค่า enum `BaselineType`, ทำให้คุณติดตามหลายเวอร์ชันของเบสไลน์โดยไม่ต้องเปิด MS Project.

## Common Issues and Solutions
- **Baseline ไม่แสดง:** ตรวจสอบว่าคุณเรียก `project.save("output.mpp")` หลังจากตั้งค่าเบสไลน์ (ขั้นตอนการบันทึกถูกละไว้เพื่อความกระชับ).  
- **รายการงานว่าง:** ยืนยันว่าคุณกำลังเพิ่มงานเข้าไปในพาเรนต์ที่ถูกต้อง (`getRootTask()` หรืองานย่อย).  
- **ข้อผิดพลาดเวอร์ชันไม่ตรงกัน:** ใช้ JAR ของ Aspose.Tasks เวอร์ชันล่าสุดเพื่อรับรองความเข้ากันได้กับฟอร์แมต .mpp ใหม่ๆ.

## Frequently Asked Questions

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

## Conclusion
โดยทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธี **สร้างรายการงาน Java**, **เพิ่มงานใน Microsoft Project**, และ **ตั้งค่าเบสไลน์โดยไม่ต้องใช้ MS Project** ด้วย Aspose.Tasks. วิธีนี้ช่วยให้การทำอัตโนมัติโปรเจ็กต์เป็นเรื่องง่าย, ไม่ต้องพึ่งพาการติดตั้ง Project บนเดสก์ท็อป, และให้คุณควบคุมข้อมูลโปรเจ็กต์ได้อย่างเต็มที่ผ่านโค้ด.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---