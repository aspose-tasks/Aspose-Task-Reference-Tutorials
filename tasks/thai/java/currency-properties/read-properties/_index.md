---
title: อ่านคุณสมบัติของสกุลเงินในโครงการ Aspose.Tasks
linktitle: อ่านคุณสมบัติของสกุลเงินในโครงการ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแยกข้อมูลสกุลเงินจากไฟล์ MS Project โดยใช้ Aspose.Tasks สำหรับ Java มีคำแนะนำทีละขั้นตอน
weight: 10
url: /th/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านคุณสมบัติของสกุลเงินในโครงการ Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่ออ่านคุณสมบัติสกุลเงินจากไฟล์ Microsoft Project Aspose.Tasks เป็น Java API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการเอกสาร Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project เมื่อทำตามขั้นตอนด้านล่างนี้ คุณจะสามารถดึงข้อมูลที่เกี่ยวข้องกับสกุลเงินได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java JAR: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/tasks/java/) และรวมไว้ในโปรเจ็กต์ Java ของคุณ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นลงในคลาส Java ของคุณ:
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก ให้ตั้งค่าไดเรกทอรีโครงการของคุณซึ่งมีไฟล์ Microsoft Project ของคุณอยู่ คุณสามารถกำหนดเส้นทางไดเร็กทอรีนี้ได้ดังนี้:
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ตัวอ่านโปรเจ็กต์
 ยกตัวอย่าง`Project` วัตถุโดยระบุเส้นทางไปยังไฟล์ Microsoft Project ของคุณ:
```java
Project project = new Project(dataDir + "project.mpp");
```
 ให้แน่ใจว่าจะเปลี่ยน`"project.mpp"` ด้วยชื่อไฟล์ MS Project ของคุณ
## ขั้นตอนที่ 3: แสดงคุณสมบัติสกุลเงิน
ดึงข้อมูลและแสดงคุณสมบัติสกุลเงินจากไฟล์โครงการ:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
ส่วนโค้ดนี้จะดึงข้อมูล เช่น รหัสสกุลเงิน ตัวเลข สัญลักษณ์ และตำแหน่งสัญลักษณ์จากไฟล์ MS Project และพิมพ์ลงในคอนโซล
## ขั้นตอนที่ 4: กระบวนการเสร็จสิ้น
สุดท้าย ให้พิมพ์ข้อความระบุว่ากระบวนการนี้เสร็จสมบูรณ์:
```java
System.out.println("Process completed Successfully");
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการอ่านคุณสมบัติของสกุลเงินจากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถดึงข้อมูลที่เกี่ยวข้องกับสกุลเงินออกจากไฟล์โปรเจ็กต์ของคุณได้อย่างง่ายดายโดยทางโปรแกรม ช่วยให้สามารถผสานรวมเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks เข้ากันได้กับ Microsoft Project ทุกเวอร์ชันหรือไม่
ตอบ: Aspose.Tasks รองรับ Microsoft Project เวอร์ชันต่างๆ รวมถึงไฟล์ MPP ที่สร้างโดย MS Project 2003-2021
### ถาม: ฉันสามารถแก้ไขคุณสมบัติสกุลเงินโดยใช้ Aspose.Tasks ได้หรือไม่
ตอบ: ได้ Aspose.Tasks อนุญาตให้คุณอ่านและแก้ไขคุณสมบัติสกุลเงินในไฟล์ MS Project โดยทางโปรแกรม
### ถาม: Aspose.Tasks เหมาะสำหรับการใช้งานเชิงพาณิชย์หรือไม่
 ตอบ: ใช่ Aspose.Tasks เป็นไลบรารีเชิงพาณิชย์ที่ออกแบบมาสำหรับการใช้งานระดับมืออาชีพ คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: Aspose.Tasks ให้ทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.Tasks ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอความช่วยเหลือหรือสนับสนุน Aspose.Tasks ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมฟอรัม Aspose.Tasks ได้[ที่นี่](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
