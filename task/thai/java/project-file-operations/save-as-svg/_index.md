---
title: แปลง MS Project เป็น SVG ใน Java
linktitle: บันทึกเป็น SVG ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีบันทึกไฟล์ Microsoft Project เป็น SVG ใน Java โดยใช้ไลบรารี Aspose.Tasks คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 18
url: /th/java/project-file-operations/save-as-svg/
---
## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีอันทรงพลังสำหรับการทำงานกับไฟล์การจัดการโปรเจ็กต์ ช่วยให้นักพัฒนาจัดการข้อมูลโปรเจ็กต์ ดำเนินการต่างๆ และสร้างรายงานได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกโปรเจ็กต์เป็น SVG โดยใช้ Aspose.Tasks สำหรับ Java SVG (Scalable Vector Graphics) เป็นรูปแบบที่ใช้กันอย่างแพร่หลายในการแสดงกราฟิกแบบเวกเตอร์บนเว็บ ซึ่งให้ความสามารถในการปรับขนาดและการเรนเดอร์คุณภาพสูง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### สภาพแวดล้อมการพัฒนาจาวา
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จากเว็บไซต์ Oracle
### Aspose.Tasks สำหรับไลบรารี Java
 ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จากเว็บไซต์ คุณสามารถดูลิงค์ดาวน์โหลดได้ในเอกสารที่ให้ไว้[ที่นี่](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโปรแกรม Java ของคุณเพื่อทำงานกับฟังก์ชัน Aspose.Tasks

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

ตอนนี้เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"`พร้อมพาธไปยังไดเร็กทอรีที่มีไฟล์โปรเจ็กต์ของคุณอยู่
## ขั้นตอนที่ 3: โหลดไฟล์โครงการ
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
ขั้นตอนนี้จะโหลดไฟล์โครงการชื่อ "HomeMovePlan.mpp" จากไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 4: บันทึกเป็น SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
ขั้นตอนนี้จะบันทึกโปรเจ็กต์ที่โหลดเป็นรูปแบบ SVG โดยใช้ชื่อ "project5.svg" ในไดเร็กทอรีข้อมูลที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกโปรเจ็กต์เป็น SVG โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถแปลงไฟล์โปรเจ็กต์เป็นรูปแบบ SVG ได้อย่างมีประสิทธิภาพ ช่วยให้สามารถผสานรวมกับแอปพลิเคชันบนเว็บหรือเครื่องมือแสดงภาพได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
ใช่ Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอาต์พุต SVG ได้หรือไม่
ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเอาต์พุต SVG ได้โดยการปรับพารามิเตอร์ เช่น แบบอักษร สี และการกำหนดค่าเค้าโครง
### Aspose.Tasks for Java จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่
 ใช่ จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งาน Aspose.Tasks for Java ในเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันสามารถลองใช้ Aspose.Tasks สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถขอทดลองใช้ Aspose.Tasks สำหรับ Java ฟรีได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy) เพื่อประเมินคุณสมบัติและความสามารถของมัน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้โดยไปที่ฟอรัม[ที่นี่](https://forum.aspose.com/c/tasks/15)ซึ่งคุณสามารถถามคำถามและโต้ตอบกับชุมชนได้