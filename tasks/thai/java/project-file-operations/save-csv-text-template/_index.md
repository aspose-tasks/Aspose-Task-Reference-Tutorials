---
title: บันทึกเป็น CSV ข้อความ และเทมเพลตใน Aspose.Tasks
linktitle: บันทึกเป็น CSV ข้อความ และเทมเพลตใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีบันทึกไฟล์ Microsoft Project ในรูปแบบ CSV ข้อความ และเทมเพลตโดยใช้ Aspose.Tasks สำหรับ Java
weight: 16
url: /th/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกเป็น CSV ข้อความ และเทมเพลตใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกไฟล์โปรเจ็กต์ในรูปแบบต่างๆ เช่น CSV ข้อความ และเทมเพลตโดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่าในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นในไฟล์ Java ของคุณ:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## บันทึกโครงการเป็น CSV
เรามาดูรายละเอียดขั้นตอนในการบันทึกโปรเจ็กต์เป็น CSV กัน:
### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ขั้นตอนที่ 2: บันทึกเป็น CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## บันทึกโครงการเป็นข้อความ
ต่อไปนี้คือวิธีที่คุณสามารถบันทึกโปรเจ็กต์เป็นข้อความ:
### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ขั้นตอนที่ 2: บันทึกเป็นข้อความ
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## บันทึกโครงการเป็นเทมเพลต
การบันทึกโปรเจ็กต์เป็นเทมเพลตเกี่ยวข้องกับขั้นตอนต่อไปนี้:
### ขั้นตอนที่ 1: โหลดโครงการ
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกเทมเพลต
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### ขั้นตอนที่ 3: บันทึกเป็นเทมเพลต
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกไฟล์ Microsoft Project เป็น CSV ข้อความ และเทมเพลตโดยใช้ Aspose.Tasks สำหรับ Java ด้วยขั้นตอนง่ายๆ เหล่านี้ คุณสามารถจัดการไฟล์โปรเจ็กต์ของคุณในรูปแบบต่างๆ ได้อย่างมีประสิทธิภาพ ซึ่งช่วยเพิ่มประสิทธิภาพการทำงานของคุณในฐานะนักพัฒนา Java
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการไฟล์โปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks สำหรับ Java สามารถจัดการโปรเจ็กต์ที่มีความซับซ้อนหลากหลายได้อย่างง่ายดาย โดยให้การสนับสนุนรูปแบบไฟล์ Microsoft Project อย่างครอบคลุม
### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.Tasks for Java ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยเกี่ยวกับ Aspose.Tasks สำหรับ Java
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/)ทำให้คุณสามารถประเมินศักยภาพของห้องสมุดได้อย่างเต็มที่
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับระบบปฏิบัติการที่แตกต่างกันหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับระบบปฏิบัติการต่างๆ รวมถึง Windows, macOS และ Linux
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
