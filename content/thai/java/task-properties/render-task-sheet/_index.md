---
title: เรนเดอร์แผ่นงานใน Aspose.Tasks
linktitle: เรนเดอร์แผ่นงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: ปลดล็อกการจัดการโครงการที่มีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java เรนเดอร์แผ่นงานได้อย่างราบรื่น สำรวจคำแนะนำที่ครอบคลุมทันที!
type: docs
weight: 27
url: /th/java/task-properties/render-task-sheet/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกของ Aspose.Tasks สำหรับ Java ไลบรารีอันทรงพลังที่เสริมศักยภาพให้กับนักพัฒนา Java ด้วยความสามารถในการจัดการโปรเจ็กต์ที่ราบรื่น ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ที่ต้องการพัฒนาทักษะการจัดการโครงการ คู่มือนี้จะแนะนำคุณเกี่ยวกับการเรนเดอร์แผ่นงานโดยใช้ Aspose.Tasks
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ติดตั้ง JDK เวอร์ชันล่าสุดเพื่อรันโปรแกรม Java
2.  Aspose.Tasks สำหรับ Java Library: ดาวน์โหลดและตั้งค่าไลบรารี คุณสามารถหามันได้[ที่นี่](https://releases.aspose.com/tasks/java/).
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ ขั้นตอนนี้มีความสำคัญอย่างยิ่งในการเข้าถึงฟังก์ชัน Aspose.Tasks ในโค้ดของคุณ
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณในโค้ด Java นี่คือที่ที่ไฟล์โครงการของคุณและแผ่นงานที่แสดงผลจะถูกบันทึกไว้
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการของคุณโดยใช้ไลบรารี Aspose.Tasks ในตัวอย่างนี้ เราถือว่าไฟล์โครงการชื่อ "NewProductDev.mpp"
```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```
## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึก
กำหนดค่าตัวเลือกการบันทึก โดยระบุรูปแบบการนำเสนอที่ต้องการ ในกรณีนี้ เราต้องการสร้างแผ่นงานในรูปแบบ PDF
```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```
## ขั้นตอนที่ 4: บันทึกโครงการเป็นแผ่นงาน
บันทึกโครงการด้วยตัวเลือกที่ระบุเพื่อสร้างแผ่นงานในรูปแบบ PDF
```java
project.save(dataDir + "taskSheet.pdf", options);
```
## ขั้นตอนที่ 5: ตรวจสอบผลลัพธ์
ตรวจทานแผ่นงานที่สร้างขึ้นซึ่งแนบอยู่ในไดเร็กทอรีที่ระบุ ขณะนี้แผ่นงานของโครงการของคุณแสดงผลได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Tasks สำหรับ Java
## บทสรุป
Aspose.Tasks สำหรับ Java ช่วยให้การจัดการโครงการง่ายขึ้นโดยมอบคุณสมบัติที่มีประสิทธิภาพสำหรับการเรนเดอร์แผ่นงาน ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณได้ใช้ประโยชน์จากพลังของ Aspose.Tasks เพื่อปรับปรุงความสามารถในการจัดการโครงการของคุณ

## คำถามที่พบบ่อย
### Aspose.Tasks เข้ากันได้กับ Java เวอร์ชันทั้งหมดหรือไม่
 ใช่ Aspose.Tasks เข้ากันได้กับ Java เวอร์ชันต่างๆ มากมาย อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/tasks/java/) สำหรับรายละเอียดเฉพาะ
### ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 อย่างแน่นอน! สำรวจเวอร์ชันทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks ได้ที่ไหน
 เข้าร่วมชุมชน Aspose.Tasks บน[ฟอรั่ม](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุนและการอภิปราย
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร
 รับใบอนุญาตชั่วคราวของคุณ[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
 ซื้อ Aspose.Tasks สำหรับ Java[ที่นี่](https://purchase.aspose.com/buy).