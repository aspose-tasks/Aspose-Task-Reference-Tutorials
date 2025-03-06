---
title: ทำซ้ำทรัพยากรที่ไม่ใช่รูทใน Aspose.Tasks
linktitle: ทำซ้ำทรัพยากรที่ไม่ใช่รูทใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีวนซ้ำทรัพยากรที่ไม่ใช่รูทอย่างมีประสิทธิภาพในไฟล์ Microsoft Project โดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงกระบวนการพัฒนาของคุณ
type: docs
weight: 12
url: /th/java/resource-management/iterate-non-root-resources/
---
## การแนะนำ
Aspose.Tasks for Java เป็นไลบรารีอันทรงพลังที่ให้นักพัฒนามีเครื่องมือที่จำเป็นในการจัดการไฟล์ Microsoft Project ได้อย่างมีประสิทธิภาพ ด้วยอินเทอร์เฟซที่ใช้งานง่ายและฟังก์ชันการทำงานที่ครอบคลุม Aspose.Tasks ทำให้กระบวนการทำงานกับข้อมูลโปรเจ็กต์ง่ายขึ้น ช่วยให้นักพัฒนามุ่งเน้นไปที่การสร้างแอปพลิเคชันที่แข็งแกร่งได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.Tasks สำหรับ Java ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับไลบรารี Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมพาธไปยังไดเร็กทอรีที่เก็บไฟล์โปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
 บรรทัดนี้เริ่มต้นใหม่`Project` วัตถุโดยการโหลดไฟล์โครงการชื่อ`"ResourceCosts.mpp"` จากไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 3: ทำซ้ำทรัพยากรที่ไม่ใช่รูท
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
ลูปนี้จะวนซ้ำทรัพยากรแต่ละรายการในโปรเจ็กต์ (`prj.getResources()`). หากทรัพยากรเป็นทรัพยากรราก จะข้ามไปยังการวนซ้ำครั้งถัดไป มิฉะนั้น จะพิมพ์ชื่อของทรัพยากรที่ไม่ใช่รูท

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการวนซ้ำทรัพยากรที่ไม่ใช่รูทโดยใช้ Aspose.Tasks สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพและปรับปรุงกระบวนการพัฒนาของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java เพื่อสร้างไฟล์โปรเจ็กต์ใหม่ได้หรือไม่
ใช่ Aspose.Tasks มีฟังก์ชันสำหรับสร้าง แก้ไข และบันทึกไฟล์โครงการในรูปแบบต่างๆ
### Aspose.Tasks รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
Aspose.Tasks รองรับรูปแบบไฟล์ Microsoft Project 2003-2019 รวมถึง MPP, MPT และ XML
### Aspose.Tasks เข้ากันได้กับกรอบงาน Java เช่น Spring หรือไม่
ใช่ Aspose.Tasks สามารถผสานรวมเข้ากับเฟรมเวิร์ก Java เช่น Spring สำหรับแอปพลิเคชันระดับองค์กรได้อย่างราบรื่น
### ฉันสามารถปรับแต่งช่องข้อมูลโปรเจ็กต์โดยใช้ Aspose.Tasks ได้หรือไม่
แน่นอนว่า Aspose.Tasks มี API มากมายสำหรับปรับแต่งช่องข้อมูลโปรเจ็กต์ตามความต้องการของคุณ
### Aspose.Tasks ให้การสนับสนุนและเอกสารสำหรับนักพัฒนาหรือไม่
ใช่ Aspose.Tasks นำเสนอเอกสารที่ครอบคลุมและฟอรัมสนับสนุนเฉพาะเพื่อช่วยเหลือนักพัฒนาในการสอบถามหรือปัญหาที่พวกเขาพบ