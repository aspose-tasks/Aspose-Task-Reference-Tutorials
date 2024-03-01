---
title: สูตร MS Project พร้อม Aspose.Tasks สำหรับ Java
linktitle: ทำงานกับสูตรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการไฟล์ MS Project ใน Java โดยใช้ไลบรารี Aspose.Tasks สร้าง แก้ไข และคำนวณแอตทริบิวต์ได้อย่างง่ายดาย
type: docs
weight: 11
url: /th/java/formulas/work-with-formulas/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการทำงานกับ MS Project Formulas โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถจัดการไฟล์ Microsoft Project โดยทางโปรแกรม ด้วยคุณสมบัติที่หลากหลาย คุณสามารถสร้าง อ่าน แก้ไข และแปลงไฟล์โปรเจ็กต์ในแอปพลิเคชัน Java ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### สภาพแวดล้อมการพัฒนาจาวา
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ล่าสุดได้จากเว็บไซต์ Oracle
### Aspose.Tasks ไลบรารี
คุณต้องเพิ่มไลบรารี Aspose.Tasks ให้กับโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[หน้าดาวน์โหลด Aspose.Tasks สำหรับ Java](https://releases.aspose.com/tasks/java/) และรวมไว้ในการอ้างอิงของโครงการของคุณ

## แพ็คเกจนำเข้า
ก่อนที่จะเจาะลึกตัวอย่าง ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโค้ด Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

เรามาแยกย่อยตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างโครงการทดสอบด้วยฟิลด์ที่กำหนดเอง
```java
Project project = CreateTestProjectWithCustomField();
```
 ขั้นแรก สร้างโปรเจ็กต์ทดสอบด้วยฟิลด์ที่กำหนดเองโดยใช้`CreateTestProjectWithCustomField()` วิธี. วิธีนี้จะส่งคืนวัตถุโครงการที่แสดงถึงโครงการที่สร้างขึ้นใหม่
## ขั้นตอนที่ 2: กำหนดคำจำกัดความแอตทริบิวต์เพิ่มเติม
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
ดึงคำนิยามแอตทริบิวต์เพิ่มเติมจากโปรเจ็กต์และตั้งค่านามแฝงและสูตร ในตัวอย่างนี้ เรากำลังกำหนดแอตทริบิวต์เพื่อคำนวณจำนวนวันนับจากวันที่เสร็จสิ้นจนถึงกำหนดเวลา
## ขั้นตอนที่ 3: กำหนดกำหนดเวลาสำหรับงาน
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
สร้างวัตถุปฏิทินและกำหนดวันครบกำหนด จากนั้นรับงานจากโปรเจ็กต์และกำหนดกำหนดเวลาโดยใช้ออบเจ็กต์ปฏิทิน
## ขั้นตอนที่ 4: บันทึกโครงการ
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
สุดท้าย ให้บันทึกโปรเจ็กต์ลงในไฟล์ตามชื่อและรูปแบบที่ระบุ ในกรณีนี้ เรากำลังบันทึกเป็นไฟล์ MPP

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีทำงานกับ MS Project Formulas โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการไฟล์โปรเจ็กต์ได้อย่างมีประสิทธิภาพโดยทางโปรแกรม เพิ่มฟิลด์ที่กำหนดเอง และคำนวณแอททริบิวต์ตามสูตร

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับภาษาการเขียนโปรแกรมที่หลากหลาย รวมถึง Java, .NET และอื่นๆ อีกมากมาย
### ถาม: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถค้นหาเอกสารสำหรับ Aspose.Tasks ได้[ที่นี่](https://reference.aspose.com/tasks/java/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้อย่างไร
 ตอบ: หากต้องการความช่วยเหลือ คุณสามารถไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Tasks หรือไม่
ตอบ: หากคุณต้องการคุณสมบัติเพิ่มเติม คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).