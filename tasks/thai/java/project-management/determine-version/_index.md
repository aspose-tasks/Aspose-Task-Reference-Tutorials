---
title: กำหนดเวอร์ชันของโครงการ MS ด้วย Aspose.Tasks
linktitle: กำหนดเวอร์ชันของโปรเจ็กต์ด้วย Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีระบุเวอร์ชันของไฟล์ MS Project โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 12
url: /th/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดเวอร์ชันของโครงการ MS ด้วย Aspose.Tasks

## การแนะนำ
บทช่วยสอนนี้จะแนะนำคุณตลอดการใช้ Aspose.Tasks สำหรับ Java เพื่อระบุเวอร์ชันของไฟล์ MS Project ทีละขั้นตอน Aspose.Tasks เป็น Java API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยไม่ต้องติดตั้ง Microsoft Project
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับไฟล์ Java JAR: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[เว็บไซต์](https://releases.aspose.com/tasks/java/) และเพิ่มลงในโปรเจ็กต์ Java ของคุณ
3. ไฟล์ MS Project: เตรียมไฟล์ MS Project (รูปแบบ XML) สำหรับการทดสอบ

## แพ็คเกจนำเข้า
ก่อนที่จะเจาะลึกโค้ด เรามานำเข้าแพ็คเกจที่จำเป็นกันก่อน:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 2: โหลดโครงการ
```java
Project project = new Project(dataDir + "input.xml");
```
 แทนที่`"input.xml"` ด้วยชื่อไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 3: กำหนดเวอร์ชันของโครงการ
```java
//แสดงคุณสมบัติรุ่นโครงการ
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
ข้อมูลโค้ดนี้จะดึงและพิมพ์เวอร์ชันและวันที่บันทึกล่าสุดของไฟล์ MS Project
## ขั้นตอนที่ 4: แสดงผล
```java
//แสดงผลการแปลง
System.out.println("Process completed Successfully");
```
บรรทัดนี้แสดงถึงความสมบูรณ์ของกระบวนการ

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีระบุเวอร์ชันของไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถทำงานกับไฟล์ MS Project ในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพโดยไม่ต้องยุ่งยาก

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ: ใช่ Aspose.Tasks รองรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง .NET, Java และ C++.
### ถาม: Aspose.Tasks เหมาะสำหรับโครงการขนาดใหญ่หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อจัดการโปรเจ็กต์ทุกขนาดได้อย่างง่ายดาย
### ถาม: ฉันสามารถปรับแต่งข้อมูลโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
ตอบ: ได้ คุณสามารถจัดการข้อมูลโปรเจ็กต์ ปรับเปลี่ยนงาน ทรัพยากร และอื่นๆ อีกมากมายได้โดยใช้ Aspose.Tasks
### ถาม: Aspose.Tasks จำเป็นต้องติดตั้ง Microsoft Project หรือไม่
ตอบ: ไม่ Aspose.Tasks ทำงานแยกกันและไม่จำเป็นต้องติดตั้ง Microsoft Project
### ถาม: Aspose.Tasks มีการสนับสนุนด้านเทคนิคหรือไม่
 ตอบ: ได้ คุณสามารถรับการสนับสนุนทางเทคนิคได้จากฟอรัม Aspose.Tasks ได้ที่[ที่นี่](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
