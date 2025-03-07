---
title: จัดการคุณสมบัติเพิ่มเติมในโครงการ Aspose.Tasks
linktitle: จัดการคุณสมบัติเพิ่มเติมในโครงการ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการแอตทริบิวต์เพิ่มเติมในโปรเจ็กต์ Aspose.Tasks โดยใช้ Java อย่างมีประสิทธิภาพ คำแนะนำทีละขั้นตอนเพื่อการจัดการโครงการที่มีประสิทธิภาพ
weight: 13
url: /th/java/project-management/extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการคุณสมบัติเพิ่มเติมในโครงการ Aspose.Tasks

## การแนะนำ
การจัดการคุณลักษณะเพิ่มเติมในการจัดการโครงการถือเป็นสิ่งสำคัญสำหรับการปรับแต่งและปรับปรุงข้อมูลโครงการ Aspose.Tasks for Java มีเครื่องมือที่มีประสิทธิภาพในการจัดการคุณลักษณะเพิ่มเติมในไฟล์ MS Project ได้อย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้แน่ใจว่าคุณจะเข้าใจแต่ละแนวคิดอย่างละเอียด
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
2. ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
3. Aspose.Tasks สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่าในโปรเจ็กต์ Java ของคุณ
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นกันก่อน:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีข้อมูลของโครงการของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 บรรทัดนี้โหลดไฟล์โครงการชื่อ`"project5.mpp"`.
## ขั้นตอนที่ 3: เข้าถึงคำจำกัดความแอตทริบิวต์เพิ่มเติม
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
ที่นี่ เราดึงชุดคำจำกัดความคุณลักษณะเพิ่มเติมจากโครงการ
## ขั้นตอนที่ 4: สร้างคำจำกัดความแอตทริบิวต์เพิ่มเติม
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 ส่วนของรหัสนี้สร้างข้อกำหนดคุณลักษณะเพิ่มเติมสำหรับงาน โดยระบุประเภทฟิลด์ที่กำหนดเองเป็น`Start` และชื่อแอตทริบิวต์เป็น`"Start 7"`.
## ขั้นตอนที่ 5: เพิ่มคำจำกัดความให้กับโครงการ
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
เราเพิ่มข้อกำหนดคุณลักษณะเพิ่มเติมที่สร้างขึ้นใหม่ให้กับทั้งโครงการและคอลเลกชันของข้อกำหนดคุณลักษณะ
## ขั้นตอนที่ 6: เข้าถึงงานและคุณสมบัติเพิ่มเติม
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
ที่นี่ เราดึงข้อมูลงานจากโครงการและคุณลักษณะเพิ่มเติมที่เกี่ยวข้อง
## ขั้นตอนที่ 7: สร้างอินสแตนซ์แอตทริบิวต์เพิ่มเติม
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
ขั้นตอนนี้สร้างอินสแตนซ์ของแอตทริบิวต์เพิ่มเติมตามข้อกำหนดแอตทริบิวต์ที่กำหนดไว้ก่อนหน้านี้
## ขั้นตอนที่ 8: ตั้งค่าแอตทริบิวต์
```java
Date date = new Date();
ea.setDateValue(date);
```
เราตั้งค่าของแอตทริบิวต์เพิ่มเติม ในกรณีนี้คือค่าวันที่
## ขั้นตอนที่ 9: เพิ่มคุณสมบัติให้กับงาน
```java
eas.add(ea);
```
ในที่สุด เราก็เพิ่มแอตทริบิวต์เพิ่มเติมให้กับงาน
## ขั้นตอนที่ 10: บันทึกโครงการ
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
บรรทัดนี้จะบันทึกโปรเจ็กต์ที่แก้ไขพร้อมกับแอตทริบิวต์เพิ่มเติมที่เพิ่มลงในไฟล์ XML
## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีจัดการแอตทริบิวต์เพิ่มเติมในโปรเจ็กต์ Aspose.Tasks โดยใช้ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการข้อมูลโปรเจ็กต์แบบกำหนดเองได้อย่างมีประสิทธิภาพ และเพิ่มขีดความสามารถในการจัดการโปรเจ็กต์ของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง Java, .NET และ C++.
### ถาม: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จากเว็บไซต์ Aspose.Tasks
### ถาม: ฉันสามารถปรับแต่งประเภทแอตทริบิวต์เพิ่มเติมได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ช่วยให้คุณสามารถกำหนดประเภทแอตทริบิวต์เพิ่มเติมที่กำหนดเองซึ่งปรับให้เหมาะกับความต้องการของโปรเจ็กต์ของคุณได้
### ถาม: ฉันจะเข้าถึงเอกสารประกอบของ Aspose.Tasks ได้อย่างไร
 ตอบ: คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมได้บนเว็บไซต์ Aspose.Tasks[เอกสารประกอบ](https://reference.aspose.com/tasks/java/).
### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึงการสนับสนุนด้านเทคนิคผ่านทางฟอรัม Aspose.Tasks[เว็บไซต์](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
