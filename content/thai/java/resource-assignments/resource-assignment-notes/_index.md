---
title: จัดการบันทึกย่อสำหรับการกำหนดทรัพยากรใน Aspose.Tasks
linktitle: จัดการบันทึกย่อสำหรับการกำหนดทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการบันทึกย่อสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java บทช่วยสอนทีละขั้นตอนเพื่อการผสานรวมที่ราบรื่น
type: docs
weight: 21
url: /th/java/resource-assignments/resource-assignment-notes/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการจัดการบันทึกย่อสำหรับการมอบหมายทรัพยากรโดยใช้ Aspose.Tasks สำหรับ Java Aspose.Tasks เป็นไลบรารี Java ที่แข็งแกร่งซึ่งออกแบบมาเพื่อจัดการงานการจัดการโครงการอย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน ซึ่งช่วยให้คุณสามารถผสานรวมการจัดการบันทึกย่อเข้ากับเวิร์กโฟลว์โปรเจ็กต์ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[เว็บไซต์](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดเส้นทางไปยังไดเร็กทอรีข้อมูลของคุณซึ่งเป็นที่เก็บไฟล์โปรเจ็กต์ของคุณ
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: โหลดไฟล์โครงการ
โหลดไฟล์โครงการลงในแอปพลิเคชัน Java ของคุณ
```java
Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");
```
## ขั้นตอนที่ 3: รับงานและทรัพยากร
ดึงข้อมูลงานและทรัพยากรที่คุณต้องการเพิ่มบันทึกย่อ
```java
Task task = prj.getRootTask().getChildren().getById(1);
Resource rsc = prj.getResources().getById(1);
```
## ขั้นตอนที่ 4: สร้างการมอบหมายทรัพยากร
สร้างการมอบหมายทรัพยากรสำหรับงานและทรัพยากร
```java
ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);
```
## ขั้นตอนที่ 5: ตั้งค่าบันทึกย่อ
ตั้งค่าบันทึกย่อสำหรับการมอบหมายทรัพยากร
```java
assn.set(Asn.NOTES_TEXT, "Newly added assignment");
```
## ขั้นตอนที่ 6: แสดงบันทึกย่อ
แสดงข้อความบันทึกย่อและรูปแบบ RTF
```java
System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));
```
## ขั้นตอนที่ 7: กระบวนการเสร็จสิ้น
พิมพ์ข้อความแสดงความสำเร็จที่ระบุถึงความสมบูรณ์ของกระบวนการ
```java
System.out.println("Process completed Successfully");
```

## บทสรุป
โดยสรุป การจัดการบันทึกสำหรับการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java นั้นตรงไปตรงมากับ API ที่ให้มา เมื่อทำตามบทช่วยสอนนี้ คุณจะสามารถรวมฟังก์ชันการจัดการบันทึกย่อเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการจัดการโครงการ
## คำถามที่พบบ่อย
### Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ทั้งหมดหรือไม่
Aspose.Tasks สำหรับ Java เข้ากันได้กับ Java IDE ใดๆ รวมถึง IntelliJ IDEA, Eclipse และ NetBeans
### ฉันสามารถลองใช้ Aspose.Tasks สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Tasks for Java รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Tasks สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15).
### ฉันต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Tasks สำหรับ Java ในช่วงทดลองใช้งานหรือไม่
ไม่ ไม่จำเป็นต้องมีใบอนุญาตชั่วคราวในช่วงทดลองใช้งาน คุณสามารถใช้เวอร์ชันทดลองได้โดยไม่ต้องมีใบอนุญาตใดๆ
### ฉันจะซื้อ Aspose.Tasks สำหรับ Java ได้ที่ไหน
คุณสามารถซื้อ Aspose.Tasks สำหรับ Java ได้จากหน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy).