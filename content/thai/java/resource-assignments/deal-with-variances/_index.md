---
title: การจัดการความแปรปรวนของโครงการอย่างมีประสิทธิภาพด้วย Aspose.Tasks
linktitle: จัดการกับความแปรปรวนใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการกับความแปรปรวนของโปรเจ็กต์อย่างมีประสิทธิภาพด้วย Aspose.Tasks สำหรับ Java จัดการงาน ต้นทุน เริ่มต้น และสิ้นสุดผลต่างได้อย่างง่ายดาย
type: docs
weight: 15
url: /th/java/resource-assignments/deal-with-variances/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการกับความแปรปรวนใน Aspose.Tasks สำหรับ Java ผลต่างคือการเบี่ยงเบนไปจากมูลค่าที่วางแผนไว้ เช่น งาน ต้นทุน วันที่เริ่มต้น หรือสิ้นสุด ในการจัดการโครงการ Aspose.Tasks มอบวิธีการที่มีประสิทธิภาพในการดึงข้อมูลและจัดการความแปรปรวนเหล่านี้ ช่วยให้นักพัฒนาวิเคราะห์และปรับกำหนดการของโครงการได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```
## ขั้นตอนที่ 1: ทำซ้ำผ่านการกำหนดทรัพยากร
เพื่อจัดการกับความแปรปรวน เราจำเป็นต้องวนซ้ำผ่านการมอบหมายทรัพยากรในโครงการ สามารถทำได้โดยใช้การวนซ้ำอย่างง่าย:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // ดำเนินการในการมอบหมายทรัพยากรแต่ละครั้ง
}
```
## ขั้นตอนที่ 2: ดึงข้อมูลผลต่างของงาน
ผลต่างของงานแสดงถึงค่าเบี่ยงเบนระหว่างงานที่วางแผนไว้และงานจริงที่ดำเนินการโดยทรัพยากร หากต้องการดึงข้อมูลผลต่างของงานสำหรับการกำหนดทรัพยากรแต่ละรายการ ให้ใช้ข้อมูลโค้ดต่อไปนี้:
```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```
## ขั้นตอนที่ 3: ดึงข้อมูลผลต่างต้นทุน
ผลต่างต้นทุนบ่งชี้ความแตกต่างระหว่างต้นทุนที่วางแผนไว้และต้นทุนจริงที่เกิดขึ้นสำหรับการกำหนดทรัพยากร เมื่อต้องการรับผลต่างต้นทุน ใช้รหัสต่อไปนี้:
```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```
## ขั้นตอนที่ 4: ดึงข้อมูลความแปรปรวนเริ่มต้น
ผลต่างเริ่มต้นหมายถึงผลต่างระหว่างวันที่วางแผนและวันที่เริ่มต้นจริงสำหรับงาน หากต้องการดึงข้อมูลผลต่างเริ่มต้น ให้ใช้รหัสต่อไปนี้:
```java
System.out.println(ra.get(Asn.START_VARIANCE));
```
## ขั้นตอนที่ 5: ดึงข้อมูลผลต่างเสร็จสิ้น
ผลต่างการเสร็จสิ้นแสดงถึงความแตกต่างระหว่างวันที่วางแผนไว้และวันที่เสร็จสิ้นจริงสำหรับงาน หากต้องการรับผลต่างเสร็จสิ้น ให้ใช้รหัสต่อไปนี้:
```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```
## บทสรุป
การจัดการกับความแปรปรวนเป็นสิ่งสำคัญในการจัดการโครงการเพื่อประเมินประสิทธิภาพของโครงการและทำการปรับเปลี่ยนที่จำเป็น ด้วย Aspose.Tasks สำหรับ Java นักพัฒนาสามารถจัดการความแปรปรวนได้อย่างมีประสิทธิภาพและรับประกันความสำเร็จของโครงการ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถผสานรวม Aspose.Tasks เข้ากับไลบรารี Java อื่นๆ ได้หรือไม่
ตอบ: ได้ Aspose.Tasks สามารถรวมเข้ากับไลบรารี Java อื่นๆ ได้อย่างราบรื่นเพื่อเพิ่มความสามารถในการจัดการโปรเจ็กต์
### ถาม: Aspose.Tasks เหมาะสำหรับโครงการขนาดใหญ่หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks ได้รับการออกแบบมาเพื่อรองรับโปรเจ็กต์ทุกขนาด โดยให้ประสิทธิภาพที่แข็งแกร่งและความน่าเชื่อถือ
### ถาม: ฉันสามารถปรับแต่งรายงานตามการวิเคราะห์ผลต่างได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Tasks มีฟีเจอร์มากมายในการปรับแต่งรายงานตามข้อกำหนดการวิเคราะห์ความแปรปรวน
### ถาม: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.Tasks หรือไม่
 ตอบ: ได้ ผู้ใช้สามารถเข้าถึงการสนับสนุนทางเทคนิคผ่านทาง[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ
### ถาม: ฉันสามารถลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.Tasks ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติก่อนตัดสินใจซื้อ