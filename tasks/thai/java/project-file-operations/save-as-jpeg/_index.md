---
title: แปลงโครงการ MS เป็น JPEG ใน Aspose.Tasks
linktitle: บันทึกโครงการเป็น JPEG ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีแปลงไฟล์ Microsoft Project เป็นภาพ JPEG ได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java เพิ่มผลผลิตของคุณ
weight: 20
url: /th/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงโครงการ MS เป็น JPEG ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกไฟล์ Microsoft Project เป็นรูปภาพ JPEG โดยใช้ Aspose.Tasks สำหรับ Java สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับการแบ่งปันการแสดงภาพโครงการหรือการบูรณาการข้อมูลโครงการลงในรายงานหรือการนำเสนอ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดได้จาก[เว็บไซต์จาวา](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและตั้งค่า Aspose.Tasks สำหรับ Java โดยทำตามคำแนะนำที่ให้ไว้ใน[เอกสารประกอบ](https://reference.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นไปยังไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณซึ่งมีไฟล์ MS Project อยู่
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ MS
โหลดไฟล์ MS Project โดยใช้ Aspose.Tasks
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## ขั้นตอนที่ 3: กำหนดค่าคุณภาพ JPEG (ไม่บังคับ)
 หากคุณต้องการปรับคุณภาพ JPEG คุณสามารถตั้งค่าได้โดยใช้`ImageSaveOptions` ระดับ. คุณภาพมีตั้งแต่ 0 ถึง 100
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // ตั้งค่าคุณภาพ JPEG เป็น 50
```
## ขั้นตอนที่ 4: บันทึกโครงการเป็น JPEG
บันทึกไฟล์ MS Project เป็นรูปภาพ JPEG
```java
project.save(dataDir + "image_out.jpeg", options);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกไฟล์ Microsoft Project เป็นรูปภาพ JPEG โดยใช้ Aspose.Tasks สำหรับ Java คุณสมบัตินี้ช่วยให้สามารถแบ่งปันและรวมข้อมูลโครงการลงในเอกสารและการนำเสนอต่างๆ ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับคุณภาพของภาพ JPEG ได้หรือไม่
 ตอบ: ได้ คุณสามารถปรับคุณภาพได้โดยใช้`setJpegQuality()` วิธีที่มีช่วงตั้งแต่ 0 ถึง 100
### ถาม: จะเกิดอะไรขึ้นหากฉันไม่ระบุคุณภาพ JPEG
ตอบ: หากคุณไม่ระบุคุณภาพ ระบบจะใช้คุณภาพเริ่มต้น
### ถาม: Aspose.Tasks สำหรับ Java ใช้งานได้ฟรีหรือไม่
 ตอบ: Aspose.Tasks for Java เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถสำรวจคุณสมบัติต่างๆ ได้ด้วยการทดลองใช้ฟรี เยี่ยมชม[หน้าทดลองใช้ฟรี](https://releases.aspose.com/) สำหรับข้อมูลเพิ่มเติม.
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้ที่ไหน
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Tasks ได้หรือไม่
 ตอบ: ได้ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
