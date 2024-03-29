---
title: การคำนวณเปอร์เซ็นต์ทรัพยากรโครงการ MS ด้วย Aspose.Tasks
linktitle: ดำเนินการคำนวณเปอร์เซ็นต์สำหรับทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีการคำนวณเปอร์เซ็นต์ทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดรวมอยู่ด้วย
type: docs
weight: 14
url: /th/java/resource-management/percentage-calculations/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการคำนวณเปอร์เซ็นต์สำหรับทรัพยากร MS Project โดยใช้ Aspose.Tasks สำหรับ Java ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการใช้ประโยชน์จาก Aspose.Tasks เพื่อจัดการและแยกข้อมูลทรัพยากรจากไฟล์ Microsoft Project อย่างมีประสิทธิภาพ Aspose.Tasks เป็น Java API อันทรงพลังที่ให้คุณสมบัติที่ครอบคลุมสำหรับการทำงานกับเอกสาร Microsoft Project ช่วยให้นักพัฒนาสามารถรวมฟังก์ชันการจัดการโครงการเข้ากับแอปพลิเคชัน Java ของตนได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### สภาพแวดล้อมการพัฒนาจาวา
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK ได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks ไลบรารี
คุณต้องรวมไลบรารี Aspose.Tasks เข้ากับโปรเจ็กต์ Java ของคุณ หากคุณยังไม่ได้ดำเนินการ คุณสามารถดาวน์โหลดไลบรารีได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ[ที่นี่](https://reference.aspose.com/tasks/java/).

## แพ็คเกจนำเข้า
ก่อนที่เราจะเริ่มเขียนโค้ด เรามานำเข้าแพ็คเกจที่จำเป็นสำหรับบทช่วยสอนนี้ก่อน:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไฟล์โครงการ
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไฟล์ Microsoft Project ของคุณ
## ขั้นตอนที่ 2: โหลดโครงการ
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
รหัสนี้จะโหลดไฟล์ Microsoft Project ชื่อ "Software Development.mpp" ซึ่งอยู่ในไดเร็กทอรีข้อมูลที่ระบุ
## ขั้นตอนที่ 3: ทำซ้ำผ่านทรัพยากร
```java
for (Resource res : prj.getResources()) {
```
เราวนซ้ำทรัพยากรแต่ละรายการในโครงการ
## ขั้นตอนที่ 4: ตรวจสอบชื่อทรัพยากรและเปอร์เซ็นต์งานที่เสร็จสมบูรณ์
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
เราตรวจสอบว่าชื่อทรัพยากรไม่เป็นค่าว่างหรือไม่ จากนั้นจึงพิมพ์เปอร์เซ็นต์ของงานที่เสร็จสมบูรณ์สำหรับแต่ละทรัพยากร

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อคำนวณเปอร์เซ็นต์สำหรับทรัพยากร MS Project อย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถรวมฟังก์ชันการจัดการโครงการเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น โดยให้การควบคุมที่ได้รับการปรับปรุงและข้อมูลเชิงลึกเกี่ยวกับการใช้ทรัพยากรของโครงการ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับเฟรมเวิร์ก Java ต่างๆ เช่น Spring, Hibernate และอื่นๆ
### Aspose.Tasks รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่
Aspose.Tasks ให้การสนับสนุนไฟล์ Microsoft Project ทุกเวอร์ชัน รวมถึง MPP, MPT, XML และอื่นๆ
### ฉันสามารถจัดการกำหนดการของโครงการโดยใช้ Aspose.Tasks ได้หรือไม่
แน่นอนว่า Aspose.Tasks นำเสนอคุณสมบัติที่ครอบคลุมสำหรับการจัดการกำหนดการของโครงการ รวมถึงงาน ทรัพยากร ปฏิทิน และอื่นๆ อีกมากมาย
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Tasks หรือไม่
 ใช่ คุณสามารถค้นหาความช่วยเหลือและมีส่วนร่วมกับผู้ใช้รายอื่นได้ในฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks เสนอใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการประเมินหรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับการประเมินได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).