---
title: อัปเดตไฟล์ MPP ใน Aspose.Tasks
linktitle: อัปเดตไฟล์ MPP ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีอัปเดตไฟล์ MPP ได้อย่างราบรื่นโดยใช้ Aspose.Tasks สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการไฟล์โปรเจ็กต์ที่มีประสิทธิภาพ
weight: 19
url: /th/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อัปเดตไฟล์ MPP ใน Aspose.Tasks

## การแนะนำ
ในขอบเขตของการจัดการโครงการ การจัดการและการอัปเดตไฟล์โครงการถือเป็นงานที่สำคัญ Aspose.Tasks for Java มอบโซลูชันอันทรงพลังสำหรับนักพัฒนา Java เพื่อจัดการไฟล์ Microsoft Project ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกการอัปเดตไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/).
3. ความรู้พื้นฐานของ Java: ความคุ้นเคยกับภาษาการเขียนโปรแกรม Java จำเป็นต้องปฏิบัติตามพร้อมกับตัวอย่าง

## แพ็คเกจนำเข้า
ประการแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks อย่างมีประสิทธิภาพ

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
บรรทัดโค้ดนี้จะนำเข้าคลาสและวิธีการที่จำเป็นทั้งหมดจากไลบรารี Aspose.Tasks ทำให้คุณทำงานกับไฟล์ Microsoft Project ได้อย่างง่ายดาย

ตอนนี้ เรามาแจกแจงขั้นตอนการอัพเดตไฟล์ MPP โดยใช้ Aspose.Tasks for Java ให้เป็นขั้นตอนที่สามารถจัดการได้
## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` ด้วยเส้นทางจริงที่มีไฟล์ MPP ของคุณอยู่
## ขั้นตอนที่ 3: อ่านโครงการที่มีอยู่
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 รหัสนี้อ่านชื่อไฟล์โครงการ MPP ที่มีอยู่`SampleMSP2010.mpp` จากไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 4: สร้างงานใหม่
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
ที่นี่ เราเพิ่มงานใหม่ชื่อ "Task1" ให้กับงานรากของโครงการ
## ขั้นตอนที่ 5: กำหนดวันที่เริ่มต้นและสิ้นสุด
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
บรรทัดโค้ดเหล่านี้กำหนดวันที่เริ่มต้นและวันที่สิ้นสุดสำหรับงานที่สร้างขึ้นใหม่
## ขั้นตอนที่ 6: บันทึกโครงการ
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 สุดท้าย ขั้นตอนนี้จะบันทึกโปรเจ็กต์ที่อัปเดตพร้อมกับงานที่เพิ่มใหม่ลงในไฟล์ MPP ใหม่ที่มีชื่อว่า`AfterLinking.mpp`.

## บทสรุป
ในบทช่วยสอนนี้ เราได้ศึกษาวิธีอัปเดตไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถจัดการไฟล์ Microsoft Project ภายในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java สามารถจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java มีคุณสมบัติที่มีประสิทธิภาพในการจัดการโครงสร้างโปรเจ็กต์ที่ซับซ้อนได้อย่างมีประสิทธิภาพ
### ถาม: Aspose.Tasks สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
### ถาม: Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: แน่นอน Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ รวมถึงรูปแบบ MPP, MPT และ XML
### ถาม: ฉันสามารถรับสิทธิ์การใช้งานชั่วคราวสำหรับ Aspose.Tasks สำหรับ Java ได้หรือไม่
 ตอบ: ใช่ ใบอนุญาตชั่วคราวมีไว้เพื่อการทดสอบ คุณสามารถรับได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเกี่ยวกับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
