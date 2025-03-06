---
title: ตรวจสอบค่าล่วงเวลา ต้นทุนคงเหลือ และทำงานใน Aspose.Tasks
linktitle: ตรวจสอบค่าล่วงเวลา ต้นทุนคงเหลือ และทำงานใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีตรวจสอบค่าล่วงเวลา ต้นทุนที่เหลืออยู่ และทำงานในโครงการ Java โดยใช้ Aspose.Tasks ขั้นตอนง่ายๆ เพื่อการจัดการโครงการอย่างมีประสิทธิภาพ
weight: 18
url: /th/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบค่าล่วงเวลา ต้นทุนคงเหลือ และทำงานใน Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อตรวจสอบการทำงานล่วงเวลา ต้นทุนที่เหลือ และงานในโปรเจ็กต์ สิ่งนี้สามารถประเมินค่ามิได้สำหรับผู้จัดการโครงการและหัวหน้าทีมเพื่อให้แน่ใจว่าโครงการดำเนินไปตามแผนและอยู่ในงบประมาณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): Aspose.Tasks สำหรับ Java ต้องใช้ Java SE 6 หรือใหม่กว่า
2.  Aspose.Tasks สำหรับ Java Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[ที่นี่](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): Java IDE ใดๆ เช่น Eclipse, IntelliJ IDEA หรือ NetBeans

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในไฟล์ Java ของคุณ:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
กำหนดไดเร็กทอรีที่มีไฟล์โครงการของคุณ:
```java
String dataDir = "Your Data Directory";
```
 แทนที่`"Your Data Directory"` พร้อมเส้นทางไปยังไฟล์โครงการของคุณ
## ขั้นตอนที่ 2: โหลดโครงการ
 ยกตัวอย่าง`Project` วัตถุและโหลดไฟล์โครงการ:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 แทนที่`"ResourceAssignmentOvertimes.mpp"` พร้อมชื่อไฟล์โครงการของคุณ
## ขั้นตอนที่ 3: ทำซ้ำผ่านการกำหนดทรัพยากร
วนซ้ำการมอบหมายทรัพยากรแต่ละรายการในโครงการ:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## ขั้นตอนที่ 4: พิมพ์ค่าล่วงเวลาและงาน
ดึงและพิมพ์ค่าล่วงเวลาและงานสำหรับการมอบหมายทรัพยากรแต่ละรายการ:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## ขั้นตอนที่ 5: พิมพ์ต้นทุนที่เหลือและงาน
เรียกดูและพิมพ์ต้นทุนที่เหลือและงานสำหรับการมอบหมายทรัพยากรแต่ละรายการ:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## ขั้นตอนที่ 6: พิมพ์ค่าล่วงเวลาและงานที่เหลืออยู่
เรียกดูและพิมพ์ค่าล่วงเวลาที่เหลือและงานสำหรับการมอบหมายทรัพยากรแต่ละรายการ:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## บทสรุป
การตรวจสอบค่าล่วงเวลา ต้นทุนที่เหลืออยู่ และงานในโครงการเป็นสิ่งสำคัญสำหรับการจัดการโครงการที่ประสบความสำเร็จ ด้วย Aspose.Tasks สำหรับ Java คุณสามารถเข้าถึงและติดตามข้อมูลนี้ได้อย่างง่ายดาย ทำให้มั่นใจได้ว่าโครงการของคุณจะเป็นไปตามกำหนดเวลาและอยู่ภายในงบประมาณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่
ใช่ Aspose.Tasks สำหรับ Java เข้ากันได้กับไลบรารีและเฟรมเวิร์ก Java อื่นๆ
### Aspose.Tasks รองรับรูปแบบไฟล์โปรเจ็กต์ที่แตกต่างกันหรือไม่
ใช่ Aspose.Tasks รองรับไฟล์โปรเจ็กต์หลากหลายรูปแบบ รวมถึง MPP, XML และอื่นๆ
### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอความช่วยเหลือได้ที่ไหนหากฉันประสบปัญหา
 คุณสามารถเยี่ยมชมฟอรัม Aspose.Tasks[ที่นี่](https://forum.aspose.com/c/tasks/15) สำหรับการสนับสนุน
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Tasks ได้อย่างไร
 คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
