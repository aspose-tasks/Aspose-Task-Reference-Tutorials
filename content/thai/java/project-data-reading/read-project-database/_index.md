---
title: อ่านข้อมูลโครงการจากฐานข้อมูลโครงการ MS ใน Aspose.Tasks
linktitle: อ่านข้อมูลโครงการจากฐานข้อมูลโครงการ Microsoft ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอ่านข้อมูลโปรเจ็กต์จาก Microsoft Project Database โดยใช้ Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 12
url: /th/java/project-data-reading/read-project-database/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีอ่านข้อมูลโปรเจ็กต์จาก Microsoft Project Database โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็น Java API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการเอกสาร Microsoft Project ได้โดยไม่จำเป็นต้องติดตั้ง Microsoft Project ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณจะได้เรียนรู้วิธีดึงข้อมูลโปรเจ็กต์จากฐานข้อมูลอย่างมีประสิทธิภาพและบันทึกในรูปแบบที่ต้องการ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
2. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
3. Aspose.Tasks สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่าในโปรเจ็กต์ของคุณ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## ขั้นตอนที่ 1: ตั้งค่าการเชื่อมต่อฐานข้อมูล
ขั้นแรก คุณต้องตั้งค่าการเชื่อมต่อกับฐานข้อมูลโครงการ Microsoft ซึ่งรวมถึงการระบุ URL ของฐานข้อมูล ชื่อเซิร์ฟเวอร์ หมายเลขพอร์ต ชื่อฐานข้อมูล ชื่อผู้ใช้ และรหัสผ่าน
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## ขั้นตอนที่ 2: เพิ่มไดรเวอร์ JDBC
ถัดไป คุณต้องเพิ่มไดรเวอร์ JDBC ให้กับโปรเจ็กต์ของคุณ ไดรเวอร์นี้อำนวยความสะดวกในการสื่อสารระหว่างแอปพลิเคชัน Java และฐานข้อมูล Microsoft SQL Server
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## ขั้นตอนที่ 3: อ่านข้อมูลโครงการ
 ตอนนี้สร้าง`Project` วัตถุและโหลดข้อมูลโครงการจากฐานข้อมูลโดยใช้การตั้งค่าที่กำหนดไว้ก่อนหน้านี้
```java
Project project = new Project(settings);
```
## ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ
สุดท้าย ให้บันทึกข้อมูลโครงการเป็นรูปแบบที่ต้องการ ในตัวอย่างนี้ เราบันทึกเป็นไฟล์ XML
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
ยินดีด้วย! คุณได้อ่านข้อมูลโครงการจากฐานข้อมูลโครงการ Microsoft โดยใช้ Aspose.Tasks สำหรับ Java เรียบร้อยแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการอ่านข้อมูลโปรเจ็กต์จาก Microsoft Project Database โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถดึงข้อมูลโครงการได้อย่างราบรื่นและจัดการตามความต้องการของคุณ Aspose.Tasks ทำให้การจัดการเอกสาร Microsoft Project ง่ายขึ้น ทำให้สามารถแยกและจัดการข้อมูลได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สามารถใช้อ่านข้อมูลโปรเจ็กต์จากฐานข้อมูลอื่นนอกเหนือจาก Microsoft Project ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับการอ่านข้อมูลโปรเจ็กต์จากแหล่งต่างๆ รวมถึงไฟล์ XML, Primavera และฐานข้อมูล Microsoft Project
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks ได้รับการออกแบบมาเพื่อทำงานร่วมกับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และการผสานรวมที่ราบรื่น
### ถาม: ฉันสามารถจัดการข้อมูลโปรเจ็กต์ก่อนที่จะบันทึกได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks มีคุณสมบัติที่หลากหลายสำหรับการจัดการข้อมูลโปรเจ็กต์ เช่น การเพิ่มงาน การอัปเดตทรัพยากร และการตั้งค่าคุณสมบัติของโปรเจ็กต์
### ถาม: Aspose.Tasks รองรับรูปแบบเอาต์พุตหลายรูปแบบหรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง XML, PDF, HTML และรูปแบบรูปภาพ เช่น PNG และ JPEG
### ถาม: ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Tasks ได้ที่ไหน
 ตอบ: สำหรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติม คุณสามารถไปที่ฟอรัม Aspose.Tasks หรือสำรวจเอกสารที่มีอยู่บนเว็บไซต์[ที่นี่](https://forum.aspose.com/c/tasks/15).