---
title: เพิ่มคุณสมบัติเพิ่มเติมให้กับงานใน Aspose.Tasks
linktitle: เพิ่มคุณสมบัติเพิ่มเติมให้กับงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: สำรวจพลังของ Aspose.Tasks Java ในการปรับแต่งไฟล์ Microsoft Project ด้วยคุณสมบัติเพิ่มเติม เพิ่มความสามารถในการจัดการโครงการของคุณได้อย่างง่ายดาย
type: docs
weight: 11
url: /th/java/task-properties/add-extended-attributes/
---
## การแนะนำ
การเพิ่มขีดความสามารถในการจัดการโครงการเป็นสิ่งสำคัญสำหรับการติดตามงานและการจัดการทรัพยากรอย่างมีประสิทธิภาพ Aspose.Tasks for Java มอบโซลูชันอันทรงพลังสำหรับนักพัฒนา Java เพื่อจัดการไฟล์ Microsoft Project ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มแอตทริบิวต์เพิ่มเติมให้กับงานโดยใช้ Aspose.Tasks สำหรับ Java ซึ่งช่วยให้คุณปรับแต่งและจัดระเบียบข้อมูลโปรเจ็กต์ของคุณตามความต้องการเฉพาะของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Tasks สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/java/).
- Java Integrated Development Environment (IDE) ที่ติดตั้งบนระบบของคุณ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## 1. การเพิ่มแอตทริบิวต์ข้อความธรรมดา
1. ตั้งค่าเส้นทางไดเรกทอรีเอกสาร:
```java
String dataDir = "Your Document Directory";
```
2. สร้างโครงการใหม่:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. สร้างคำจำกัดความแอตทริบิวต์เพิ่มเติมของประเภท Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. เพิ่มคำจำกัดความให้กับคอลเลกชัน Extended Attributes ของโปรเจ็กต์:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. เพิ่มงานในโครงการ:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. สร้างแอตทริบิวต์เพิ่มเติมจากคำจำกัดความของแอตทริบิวต์:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. กำหนดค่าให้กับแอตทริบิวต์เพิ่มเติมที่สร้างขึ้น:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. เพิ่มคุณสมบัติเพิ่มเติมให้กับงาน:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. บันทึกโครงการ:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. การเพิ่มแอตทริบิวต์ข้อความพร้อมตัวเลือกการค้นหา
ทำตามขั้นตอนเดียวกันกับข้างต้น แทนที่ Text1 ด้วย Text2 และปรับแต่งค่าการค้นหา
## 3. การเพิ่มแอตทริบิวต์ระยะเวลาพร้อมตัวเลือกการค้นหา
ทำตามขั้นตอนเดียวกันกับด้านบน แทนที่ Text1 ด้วย Duration2 และปรับแต่งค่าการค้นหา
## บทสรุป
ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณได้เรียนรู้วิธีใช้ประโยชน์จาก Aspose.Tasks สำหรับ Java เพื่อเพิ่มแอตทริบิวต์เพิ่มเติมให้กับงานในไฟล์ Microsoft Project ของคุณ การปรับแต่งนี้ช่วยให้คุณปรับแต่งแนวทางการจัดการโครงการ เพิ่มความยืดหยุ่นและประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับไลบรารี Java อื่นๆ ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สำหรับ Java สามารถผสานรวมเข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่น และทำงานได้ดีกับไลบรารี Java อื่นๆ
### ถาม: Aspose.Tasks สำหรับ Java เหมาะสำหรับแอปพลิเคชันการจัดการโครงการขนาดใหญ่หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks สำหรับ Java ได้รับการออกแบบมาเพื่อจัดการกับโปรเจ็กต์ที่มีขนาดแตกต่างกัน รวมถึงแอปพลิเคชันขนาดใหญ่ด้วย
### ถาม: มีข้อควรพิจารณาในการอนุญาตให้ใช้สิทธิ์สำหรับการใช้ Aspose.Tasks สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์หรือไม่
 ตอบ: ได้ ตรวจสอบให้แน่ใจว่าได้ตรวจสอบข้อมูลใบอนุญาตที่ให้ไว้ใน[เว็บไซต์ Aspose.Tasks](https://purchase.aspose.com/buy).
### ถาม: ฉันจะรับการสนับสนุนหรือความช่วยเหลือเกี่ยวกับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks สำหรับ Java ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึงเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).