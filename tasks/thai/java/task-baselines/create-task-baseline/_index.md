---
title: สร้างงานพื้นฐานโครงการ MS ใน Aspose.Tasks
linktitle: การสร้างงานพื้นฐานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีสร้างงานพื้นฐาน Microsoft Project ใน Java โดยใช้ Aspose.Tasks ซึ่งเป็นไลบรารีที่มีประสิทธิภาพสำหรับการจัดการข้อมูลโครงการได้อย่างง่ายดาย
weight: 11
url: /th/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างงานพื้นฐานโครงการ MS ใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการสร้างงานพื้นฐาน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project ด้วย Aspose.Tasks คุณสามารถจัดการข้อมูลโครงการ รวมถึงงาน ทรัพยากร และปฏิทิน ได้อย่างง่ายดาย เพื่อปรับปรุงงานการจัดการโครงการ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): Aspose.Tasks สำหรับ Java จำเป็นต้องติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จากเว็บไซต์ Oracle
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดไลบรารี Aspose.Tasks สำหรับ Java จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/) ที่ให้ไว้.

## แพ็คเกจนำเข้า
หากต้องการเริ่มทำงานกับ Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## ขั้นตอนที่ 1: สร้างวัตถุโครงการ
```java
Project project = new Project();
```
 ขั้นแรกให้สร้างใหม่`Project` วัตถุ. ออบเจ็กต์นี้แสดงถึงไฟล์ Microsoft Project ที่คุณจะใช้งาน
## ขั้นตอนที่ 2: เพิ่มงานในโครงการ
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 ใช้`getRootTask()` ให้เข้าถึงงานรูทของโปรเจ็กต์ จากนั้นเพิ่มงานใหม่โดยใช้`add()` วิธี. ระบุชื่องานภายในวงเล็บ
## ขั้นตอนที่ 3: ตั้งค่าพื้นฐานสำหรับงานที่ระบุ
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
หากต้องการกำหนดพื้นฐานสำหรับงานเฉพาะ ให้สร้างรายการงาน (`myList` ในกรณีนี้) และเติมงานที่คุณต้องการตั้งค่าพื้นฐาน จากนั้นใช้`setBaseline()` วิธีการระบุประเภทพื้นฐานและรายการงาน
## ขั้นตอนที่ 4: กำหนดพื้นฐานสำหรับโครงการทั้งหมด
```java
project.setBaseline(BaselineType.Baseline);
```
 หรือคุณสามารถกำหนดพื้นฐานสำหรับทั้งโครงการได้โดยเพียงแค่โทรไปที่`setBaseline()` วิธีการที่มีการระบุประเภทพื้นฐาน

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีสร้างงานพื้นฐาน Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพและปรับปรุงงานการจัดการโครงการได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java โดยไม่ต้องติดตั้ง Microsoft Project ได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java ช่วยให้คุณสามารถทำงานกับไฟล์ Microsoft Project ได้โดยไม่ต้องติดตั้ง Microsoft Project บนระบบของคุณ
### Aspose.Tasks สำหรับ Java เข้ากันได้กับ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks สำหรับ Java รองรับ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ฉันสามารถจัดการทรัพยากรโปรเจ็กต์โดยใช้ Aspose.Tasks สำหรับ Java ได้หรือไม่
แน่นอนว่า Aspose.Tasks for Java นำเสนอฟีเจอร์ที่มีประสิทธิภาพสำหรับการจัดการทรัพยากรของโปรเจ็กต์ รวมถึงการเพิ่ม อัปเดต และลบทรัพยากรตามความจำเป็น
### Aspose.Tasks for Java รองรับการตั้งค่าการขึ้นต่อกันของงานหรือไม่
ใช่ คุณสามารถตั้งค่าการขึ้นต่อกันของงานได้อย่างง่ายดายโดยใช้ Aspose.Tasks สำหรับ Java ซึ่งช่วยให้คุณสร้างลำดับของงานภายในโปรเจ็กต์ของคุณได้
### มีการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการสนับสนุนด้านเทคนิคสำหรับ Aspose.Tasks สำหรับ Java ผ่านทาง[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/tasks/15)ซึ่งคุณสามารถถามคำถามและขอความช่วยเหลือจากชุมชนและเจ้าหน้าที่สนับสนุน Aspose
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
