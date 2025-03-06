---
title: จัดการคุณสมบัติของโครงการ MS ใน Aspose.Tasks ได้อย่างมีประสิทธิภาพ
linktitle: จัดการคุณสมบัติโปรเจ็กต์เริ่มต้นใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการคุณสมบัติเริ่มต้นของ MS Project โดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงขั้นตอนการจัดการโครงการของคุณได้อย่างง่ายดาย
weight: 11
url: /th/java/project-management/default-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการคุณสมบัติของโครงการ MS ใน Aspose.Tasks ได้อย่างมีประสิทธิภาพ

## การแนะนำ
คุณกำลังมองหาวิธีปรับปรุงกระบวนการจัดการโครงการของคุณด้วย Aspose.Tasks สำหรับ Java หรือไม่? การจัดการคุณสมบัติเริ่มต้นในไฟล์ Microsoft Project สามารถเพิ่มประสิทธิภาพได้อย่างมาก ในบทช่วยสอนนี้ เราจะอธิบายคำแนะนำทีละขั้นตอนเกี่ยวกับวิธีจัดการคุณสมบัติเริ่มต้นของ MS Project โดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. ชุดพัฒนาจาวา (JDK)
   - ตรวจสอบให้แน่ใจว่าติดตั้ง JDK บนระบบของคุณแล้ว
   -  คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks สำหรับไลบรารี Java
   - ดาวน์โหลดและรวมไลบรารี Aspose.Tasks สำหรับ Java ในโปรเจ็กต์ของคุณ
   -  คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นในไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้:
## ขั้นตอนที่ 1: โหลดไฟล์โครงการ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## ขั้นตอนที่ 2: แสดงคุณสมบัติเริ่มต้น
```java
// แสดงคุณสมบัติเริ่มต้น
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติเริ่มต้น
```java
// ตั้งค่าคุณสมบัติเริ่มต้น
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## ขั้นตอนที่ 4: บันทึกโครงการเป็นรูปแบบ XML
```java
// บันทึกโครงการเป็นรูปแบบ XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## ขั้นตอนที่ 5: แสดงผล
```java
// แสดงผลการแปลง
System.out.println("Process completed Successfully");
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการคุณสมบัติเริ่มต้นของ MS Project ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks for Java
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการคุณสมบัติเริ่มต้นของ MS Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการใช้เทคนิคเหล่านี้ คุณสามารถเพิ่มประสิทธิภาพเวิร์กโฟลว์การจัดการโครงการ เพิ่มประสิทธิภาพการผลิตและองค์กรได้
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ตอบ 1: ใช่ Aspose.Tasks รองรับภาษาการเขียนโปรแกรมที่หลากหลาย เช่น .NET, Python และ Java
### คำถามที่ 2: Aspose.Tasks เหมาะสำหรับการใช้งานส่วนบุคคลและองค์กรหรือไม่
A2: แน่นอน! ไม่ว่าคุณจะจัดการโครงการส่วนตัวขนาดเล็กหรือโครงการริเริ่มขององค์กรขนาดใหญ่ Aspose.Tasks ก็พร้อมรองรับทุกคน
### คำถามที่ 3: Aspose.Tasks ให้การสนับสนุนลูกค้าหรือไม่
A3: ใช่ คุณสามารถค้นหาความช่วยเหลือและการสนับสนุนจากชุมชนได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### คำถามที่ 4: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 A4: แน่นอน! คุณสามารถทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 A5: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบและประเมินผล
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
