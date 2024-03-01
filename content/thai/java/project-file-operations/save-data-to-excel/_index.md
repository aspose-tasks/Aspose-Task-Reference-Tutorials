---
title: บันทึกข้อมูลโครงการ MS ไปยัง Excel ใน Aspose.Tasks
linktitle: บันทึกข้อมูลลงใน Excel ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีบันทึกข้อมูล Microsoft Project ลงในไฟล์ Excel โดยใช้ Aspose.Tasks สำหรับ Java บูรณาการอย่างง่ายดายสำหรับนักพัฒนา Java
type: docs
weight: 19
url: /th/java/project-file-operations/save-data-to-excel/
---
## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการบันทึกข้อมูลจากไฟล์โปรเจ็กต์ไปยังไฟล์ Excel ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จากเว็บไซต์ Oracle
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/) และรวมไว้ในโปรเจ็กต์ Java ของคุณ

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณเพื่อทำงานกับ Aspose.Tasks
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

มาแบ่งตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"`พร้อมเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณซึ่งมีไฟล์โครงการอยู่
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "project5.mpp");
```
บรรทัดโค้ดนี้จะโหลดไฟล์โครงการชื่อ "project5.mpp" จากไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 3: บันทึกโครงการเป็น XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 นี่.`save` วิธีการใช้เพื่อบันทึกไฟล์โครงการที่โหลดเป็นไฟล์ Excel ที่มีชื่อ "project1.xlsx" ในไดเรกทอรีข้อมูลเดียวกัน เราระบุ`SaveFileFormat.Xlsx` พารามิเตอร์เพื่อบันทึกในรูปแบบ XLSX

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกข้อมูลจากไฟล์ Microsoft Project ไปยังไฟล์ Excel โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อจัดการข้อมูลโปรเจ็กต์โดยทางโปรแกรมได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java มีคุณสมบัติมากมายในการจัดการข้อมูลโปรเจ็กต์ รวมถึงการอ่าน การเขียน และการแก้ไขไฟล์โปรเจ็กต์
### มี Aspose.Tasks สำหรับ Java รุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบสำหรับ Aspose.Tasks สำหรับ Java[ที่นี่](https://reference.aspose.com/tasks/java/).
### ฉันจะรับการสนับสนุนสำหรับปัญหาหรือการสอบถามที่เกี่ยวข้องกับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนได้โดยไปที่ฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).