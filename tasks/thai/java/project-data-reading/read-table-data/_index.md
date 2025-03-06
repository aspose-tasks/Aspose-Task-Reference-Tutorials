---
title: อ่านข้อมูลตารางจากไฟล์ใน Aspose.Tasks
linktitle: อ่านข้อมูลตารางจากไฟล์ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: ปลดล็อกพลังของ Aspose.Tasks สำหรับ Java เรียนรู้วิธีแยกข้อมูลตารางออกจากไฟล์ในบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 17
url: /th/java/project-data-reading/read-table-data/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการอ่านข้อมูลตารางจากไฟล์โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้งได้จากเว็บไซต์ Oracle
2.  Aspose.Tasks สำหรับไฟล์ Java JAR: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/) และรวมไว้ในโปรเจ็กต์ Java ของคุณ

## แพ็คเกจนำเข้า
นำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์โครงการของคุณ:
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีข้อมูลของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการโดยใช้ Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Project2003.mpp"` ด้วยชื่อไฟล์โครงการของคุณ
## ขั้นตอนที่ 3: ดึงข้อมูลตาราง
รับตารางจากโปรเจ็กต์และวนซ้ำตามฟิลด์:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
ข้อมูลโค้ดนี้จะดึงข้อมูลเกี่ยวกับเขตข้อมูลของตาราง เช่น ความกว้าง ชื่อ และการจัดตำแหน่ง

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูลตารางจากไฟล์โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแยกและจัดการข้อมูลจากเอกสาร Microsoft Project ในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ รวมถึง Project 2003, 2007, 2010, 2013 และ 2016
### ถาม: ฉันสามารถแก้ไขข้อมูลตารางและบันทึกกลับไปยังไฟล์โปรเจ็กต์ได้หรือไม่
ตอบ: ได้ คุณสามารถใช้ Aspose.Tasks เพื่อแก้ไขข้อมูลตารางโดยทางโปรแกรมและบันทึกการเปลี่ยนแปลงลงในไฟล์โปรเจ็กต์ต้นฉบับได้
### ถาม: Aspose.Tasks จำเป็นต้องมีใบอนุญาตแยกต่างหากสำหรับการใช้งานเชิงพาณิชย์หรือไม่
 ตอบ: ใช่ คุณต้องซื้อใบอนุญาตสำหรับ Aspose.Tasks หากคุณต้องการใช้ในสภาพแวดล้อมเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).
### ถาม: Aspose.Tasks มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลด Aspose.Tasks เวอร์ชันทดลองใช้ฟรีได้จาก[หน้าเผยแพร่](https://releases.aspose.com/).
### ถาม: ฉันจะขอความช่วยเหลือและสนับสนุน Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)เพื่อขอความช่วยเหลือและการสนับสนุนจากชุมชนและทีมงาน Aspose