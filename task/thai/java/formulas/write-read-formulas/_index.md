---
title: การเขียนและการอ่านสูตร MS Project ใน Aspose.Tasks
linktitle: เขียนและอ่านสูตรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้การเขียนและอ่านสูตร MS Project อย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java พัฒนาทักษะการจัดการโครงการของคุณ
type: docs
weight: 12
url: /th/java/formulas/write-read-formulas/
---
## การแนะนำ
ในขอบเขตของการจัดการโครงการ การจัดการข้อมูลอย่างมีประสิทธิผลเป็นสิ่งสำคัญยิ่ง Aspose.Tasks สำหรับ Java เป็นโซลูชันที่มีประสิทธิภาพซึ่งอำนวยความสะดวกในการจัดการและแยกข้อมูลจากไฟล์ Microsoft Project คุณสมบัติอันทรงพลังอย่างหนึ่งที่มีให้คือความสามารถในการเขียนและอ่านสูตร MS Project บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ประโยชน์จากฟังก์ชันการทำงานนี้เพื่อปรับปรุงงานการจัดการโครงการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java

## การนำเข้าแพ็คเกจ
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
```
ในขั้นตอนนี้ ให้กำหนดไดเร็กทอรีที่มีไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "project.mpp");
```
ที่นี่ โหลดไฟล์ MS Project ลงในไฟล์`Project` วัตถุสำหรับการจัดการ
## ขั้นตอนที่ 3: กำหนดสูตรที่กำหนดเอง
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
ขั้นตอนนี้เกี่ยวข้องกับการสร้างฟิลด์แบบกำหนดเองด้วยสูตรที่เพิ่มต้นทุนงานเป็นสองเท่า
## ขั้นตอนที่ 4: เพิ่มงานและกำหนดต้นทุน
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
ที่นี่ มีการเพิ่มงานใหม่ และตั้งต้นทุนไว้ที่ 100
## ขั้นตอนที่ 5: บันทึกไฟล์โครงการ
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
สุดท้าย ให้บันทึกไฟล์โปรเจ็กต์ที่แก้ไข

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการเขียนและอ่านสูตร MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการข้อมูลโครงการให้ตรงตามความต้องการเฉพาะของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ MS Project ทุกเวอร์ชันหรือไม่
Aspose.Tasks นำเสนอความเข้ากันได้กับ MS Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความยืดหยุ่นสำหรับผู้ใช้
### ฉันสามารถรวม Aspose.Tasks เข้ากับโปรเจ็กต์ Java ที่มีอยู่ของฉันได้หรือไม่
อย่างแน่นอน! Aspose.Tasks มอบการบูรณาการอย่างราบรื่นกับโปรเจ็กต์ Java ผ่านการใช้งาน API แบบธรรมดา
### มีข้อจำกัดใดๆ กับประเภทของสูตรที่ฉันสามารถสร้างได้หรือไม่
ด้วย Aspose.Tasks คุณจะมีความยืดหยุ่นอย่างมากในการสร้างสูตรแบบกำหนดเองที่เหมาะกับความต้องการของโครงการของคุณ
### Aspose.Tasks รองรับการใช้งานหลายแพลตฟอร์มหรือไม่
ใช่ Aspose.Tasks รองรับการปรับใช้งานบนหลายแพลตฟอร์ม ซึ่งเพิ่มความคล่องตัว
### ฉันจะรับการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks ได้อย่างไร
 สำหรับความช่วยเหลือด้านเทคนิคและการสนับสนุนชุมชน โปรดไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).