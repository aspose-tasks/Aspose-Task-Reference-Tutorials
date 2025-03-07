---
title: อ่านข้อมูลโครงการจากฐานข้อมูล MS Access ใน Aspose.Tasks
linktitle: อ่านข้อมูลโครงการจากฐานข้อมูล Microsoft Access ด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านข้อมูล MS Project จากฐานข้อมูล Microsoft Access โดยใช้ Aspose.Tasks สำหรับ Java ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 11
url: /th/java/project-data-reading/read-access-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านข้อมูลโครงการจากฐานข้อมูล MS Access ใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks for Java เป็น API อันทรงประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ในแอปพลิเคชัน Java ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเน้นที่การอ่านข้อมูล MS Project จากฐานข้อมูล Microsoft Access โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### ติดตั้ง Java Development Kit (JDK) แล้ว
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดได้จากเว็บไซต์ Oracle
### Aspose.Tasks สำหรับไลบรารี Java
 ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ของคุณ คุณสามารถรับได้จากเว็บไซต์ Aspose ติดตาม[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/) เพื่อรับห้องสมุด

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks
```java
import com.aspose.tasks.MpdSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

มาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ Project XML
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: กำหนด MpdSettings
เตรียมใช้งานวัตถุ MpdSettings ด้วยสตริงการเชื่อมต่อกับฐานข้อมูล Microsoft Access และตัวระบุโครงการ
```java
MpdSettings settings = new MpdSettings(getConnectionString(), 1);
```
## ขั้นตอนที่ 3: โหลดโครงการจากฐานข้อมูล
สร้างวัตถุโครงการใหม่โดยผ่านอินสแตนซ์ MpdSettings
```java
Project project = new Project(settings);
```
## ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ
บันทึกข้อมูลโครงการลงในไฟล์ XML
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูล MS Project จากฐานข้อมูล Microsoft Access โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับระบบฐานข้อมูลอื่นนอกเหนือจาก Microsoft Access ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับระบบฐานข้อมูลที่หลากหลาย เช่น SQL Server, MySQL และ Oracle
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะได้รับการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถรับการสนับสนุนทางเทคนิคได้จาก[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Tasks สำหรับ Java หรือไม่
 ตอบ: คุณอาจต้องมีใบอนุญาตชั่วคราวสำหรับคุณสมบัติขั้นสูงบางอย่าง รับมันจาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถซื้อ Aspose.Tasks สำหรับ Java ได้จาก[ลิงค์นี้](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
