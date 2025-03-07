---
title: กรองข้อมูลจากไฟล์ MPP ใน Aspose.Tasks
linktitle: กรองข้อมูลจากไฟล์ MPP ใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีกรองข้อมูลจากไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java ปรับปรุงขั้นตอนการจัดการโครงการของคุณได้อย่างง่ายดาย
weight: 14
url: /th/java/project-management/filter-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กรองข้อมูลจากไฟล์ MPP ใน Aspose.Tasks

## การแนะนำ
ในขอบเขตของการพัฒนา Java การจัดการงานโครงการอย่างมีประสิทธิภาพเป็นส่วนสำคัญของการจัดการโครงการที่ประสบความสำเร็จ Aspose.Tasks for Java นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการจัดการงานการจัดการโครงการโดยทางโปรแกรม ช่วยให้นักพัฒนามีเครื่องมือที่จำเป็นในการกรองข้อมูลจากไฟล์ MPP ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการกรองข้อมูลจากไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java โดยแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่ามีความเข้าใจที่ครอบคลุม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Tasks สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Tasks สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการ
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```
 ในขั้นตอนนี้ เราจะเริ่มต้น a`Project` วัตถุโดยระบุเส้นทางไปยังไฟล์ MPP
## ขั้นตอนที่ 2: ดึงตัวกรอง
```java
Filter filter = project.getTaskFilters().toList().get(1);
```
 ที่นี่เราได้รับก`Filter` วัตถุจากโครงการ คุณสามารถระบุดัชนีของตัวกรองที่คุณต้องการดึงข้อมูลได้
## ขั้นตอนที่ 3: เกณฑ์ตัวกรองการเข้าถึง
```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```
ขั้นตอนนี้เกี่ยวข้องกับการเข้าถึงเกณฑ์และการทำงานของตัวกรอง
## ขั้นตอนที่ 4: ดึงข้อมูลรายละเอียดเกณฑ์
```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```
ที่นี่ เราจะดึงรายละเอียดของแถวเกณฑ์แรก
## ขั้นตอนที่ 5: วนซ้ำตามแถวเกณฑ์
```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```
ขั้นตอนนี้เกี่ยวข้องกับการวนซ้ำแถวเกณฑ์และการเข้าถึงรายละเอียด
## ขั้นตอนที่ 6: พิมพ์ข้อมูลเกณฑ์
```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```
ในขั้นตอนสุดท้ายนี้ เราจะพิมพ์ข้อมูลเกี่ยวกับเกณฑ์

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการกรองข้อมูลจากไฟล์ MPP โดยใช้ Aspose.Tasks สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณสามารถจัดการและจัดการข้อมูลโปรเจ็กต์ได้อย่างง่ายดายอย่างมีประสิทธิภาพ ซึ่งช่วยปรับปรุงเวิร์กโฟลว์การพัฒนา Java ของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ Java รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และความยืดหยุ่นในงานการจัดการโครงการ
### ถาม: ฉันสามารถปรับแต่งเกณฑ์ตัวกรองตามความต้องการเฉพาะของโปรเจ็กต์ได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks for Java ช่วยให้คุณสามารถปรับแต่งเกณฑ์การกรองตามความต้องการเฉพาะของโปรเจ็กต์ของคุณ ทำให้สามารถจัดการและวิเคราะห์ข้อมูลที่กำหนดเป้าหมายได้
### ถาม: Aspose.Tasks สำหรับ Java เหมาะสำหรับทั้งโปรเจ็กต์ขนาดเล็กและขนาดใหญ่หรือไม่
ตอบ: ได้ ไม่ว่าคุณจะจัดการโครงการขนาดเล็กหรือจัดการพอร์ตโครงการที่กว้างขวาง Aspose.Tasks for Java มอบความสามารถในการปรับขนาดและประสิทธิภาพที่จำเป็นสำหรับสถานการณ์การจัดการโครงการที่หลากหลาย
### ถาม: Aspose.Tasks for Java มีเอกสารประกอบและทรัพยากรสนับสนุนที่ครอบคลุมหรือไม่
 ตอบ: แน่นอน! คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/tasks/java/) สำหรับคำแนะนำโดยละเอียดและการอ้างอิง API นอกจากนี้ คุณยังสามารถขอความช่วยเหลือจากฟอรัมชุมชน Aspose.Tasks สำหรับข้อสงสัยหรือปัญหาใดๆ ที่คุณพบ
### ถาม: ฉันสามารถสำรวจฟังก์ชันการทำงานของ Aspose.Tasks สำหรับ Java ก่อนตัดสินใจซื้อได้หรือไม่
 ตอบ: แน่นอน! คุณสามารถทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/) เพื่อสัมผัสประสบการณ์คุณสมบัติและความสามารถของ Aspose.Tasks สำหรับ Java โดยตรง
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
