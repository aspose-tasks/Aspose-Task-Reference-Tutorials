---
title: รองรับฟังก์ชันการประเมินผลในสูตร Aspose.Tasks
linktitle: รองรับฟังก์ชันการประเมินผลในสูตร Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีสนับสนุนการประเมินฟังก์ชัน MS Project ในสูตร Aspose.Tasks โดยใช้ Java เพิ่มประสิทธิภาพการทำงานของคุณด้วย Aspose.Tasks
type: docs
weight: 10
url: /th/java/formulas/evaluation-functions/
---

## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project โดยทางโปรแกรมได้ หนึ่งในคุณสมบัติที่สำคัญคือความสามารถในการสนับสนุนการประเมินฟังก์ชัน MS Project ภายในสูตร Aspose.Tasks ความสามารถนี้ทำให้ผู้ใช้สามารถคำนวณและวิเคราะห์ที่ซับซ้อนได้โดยตรงภายในแอปพลิเคชัน Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้นการรวมฟังก์ชัน MS Project เข้ากับสูตร Aspose.Tasks ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณพร้อมกับ IDE ที่เข้ากันได้สำหรับการพัฒนา Java เช่น IntelliJ IDEA หรือ Eclipse
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด Aspose.Tasks สำหรับ Java](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในคลาส Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## ขั้นตอนที่ 1: สร้างวัตถุโครงการใหม่
 ขั้นแรกให้สร้างใหม่`Project`วัตถุที่จะทำงานร่วมกับ:
```java
Project project = new Project();
```
นี่เป็นการเริ่มต้นโปรเจ็กต์ว่างใหม่
## ขั้นตอนที่ 2: กำหนดแอตทริบิวต์เพิ่มเติมสำหรับงาน
ถัดไป กำหนดแอตทริบิวต์เพิ่มเติมสำหรับงาน คุณลักษณะนี้จะเก็บข้อมูลที่กำหนดเองที่เกี่ยวข้องกับงาน:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 ที่นี่เราสร้างแอตทริบิวต์เพิ่มเติมของประเภท`Number` ด้วยชื่อ "ไซน์" สำหรับงาน
## ขั้นตอนที่ 3: เพิ่มแอตทริบิวต์เพิ่มเติมให้กับโครงการ
เพิ่มข้อกำหนดคุณลักษณะเพิ่มเติมลงในรายการคุณลักษณะเพิ่มเติมของโครงการ:
```java
project.getExtendedAttributes().add(attr);
```
นี่เป็นการเพิ่มแอตทริบิวต์ที่กำหนดเองให้กับโปรเจ็กต์
## ขั้นตอนที่ 4: สร้างงานใหม่
ตอนนี้ เรามาสร้างงานใหม่ภายในโปรเจ็กต์กันดีกว่า:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
นี่เป็นการเพิ่มงานใหม่ชื่อ "งาน" ให้กับโครงการ
## ขั้นตอนที่ 5: เชื่อมโยงแอตทริบิวต์เพิ่มเติมกับงาน
เชื่อมโยงแอตทริบิวต์เพิ่มเติมที่สร้างขึ้นก่อนหน้านี้กับงาน:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
ซึ่งจะเชื่อมโยงแอตทริบิวต์เพิ่มเติม "Sine" กับงาน

## บทสรุป
โดยสรุป การรวมฟังก์ชัน MS Project เข้ากับสูตร Aspose.Tasks ใน Java นั้นเป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถใช้ความสามารถอันทรงพลังของ Aspose.Tasks สำหรับ Java ได้อย่างมีประสิทธิภาพเพื่อจัดการและวิเคราะห์ไฟล์ Microsoft Project โดยทางโปรแกรม
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการสูตร MS Project ที่ซับซ้อนได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับการประเมินฟังก์ชัน MS Project ที่หลากหลาย ทำให้สามารถคำนวณที่ซับซ้อนภายในแอปพลิเคชัน Java ได้
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks สำหรับ Java ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: Aspose.Tasks for Java มีลิขสิทธิ์ชั่วคราวหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้จากเว็บไซต์ Aspose[ที่นี่](https://purchase.aspose.com/temporary-license/).