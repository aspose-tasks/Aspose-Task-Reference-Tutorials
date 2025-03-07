---
title: จัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการมอบหมายใน Aspose.Tasks
linktitle: จัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการกำหนดทรัพยากรใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีจัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการมอบหมายทรัพยากรใน Aspose.Tasks สำหรับ Java ปรับปรุงการทำงานร่วมกันและการเข้าถึงในการจัดการโครงการ
weight: 16
url: /th/java/resource-assignments/hyperlink-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการมอบหมายใน Aspose.Tasks

## การแนะนำ
Aspose.Tasks สำหรับ Java นำเสนอฟีเจอร์อันทรงพลังสำหรับการจัดการงานและทรัพยากรของโปรเจ็กต์ ในบทช่วยสอนนี้ เราจะเน้นไปที่วิธีจัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการกำหนดทรัพยากรโดยใช้ Aspose.Tasks เมื่อทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะสามารถจัดการไฮเปอร์ลิงก์ที่เกี่ยวข้องกับการกำหนดทรัพยากรของโครงการของคุณได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) แล้ว
- เข้าถึง Aspose.Tasks สำหรับไลบรารี Java
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Tasks ในโปรเจ็กต์ Java ของคุณ
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์โปรเจ็กต์
เริ่มต้นด้วยการสร้างอินสแตนซ์โปรเจ็กต์ใหม่โดยใช้ Aspose.Tasks
```java
Project prj = new Project();
```
## ขั้นตอนที่ 2: เพิ่มงานในโครงการ
ตอนนี้ เพิ่มงานในโครงการซึ่งจะเชื่อมโยงกับไฮเปอร์ลิงก์
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## ขั้นตอนที่ 3: เพิ่มทรัพยากร
ถัดไป เพิ่มทรัพยากรให้กับโปรเจ็กต์
```java
Resource resource = prj.getResources().add("Resource 1");
```
## ขั้นตอนที่ 4: สร้างการมอบหมายทรัพยากร
สร้างการมอบหมายทรัพยากรและเชื่อมโยงกับงานและทรัพยากร
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติไฮเปอร์ลิงก์
ตั้งค่าคุณสมบัติไฮเปอร์ลิงก์สำหรับการกำหนดทรัพยากร
```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```
## ขั้นตอนที่ 6: พิมพ์คุณสมบัติไฮเปอร์ลิงก์
พิมพ์คุณสมบัติไฮเปอร์ลิงก์เพื่อตรวจสอบการตั้งค่า
```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```
## ขั้นตอนที่ 7: กระบวนการเสร็จสิ้น
สุดท้าย แสดงข้อความระบุว่ากระบวนการเสร็จสมบูรณ์
```java
System.out.println("Process completed Successfully");
```

## บทสรุป
โดยสรุป การจัดการคุณสมบัติไฮเปอร์ลิงก์สำหรับการกำหนดทรัพยากรใน Aspose.Tasks สำหรับ Java นั้นตรงไปตรงมาและมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมไฮเปอร์ลิงก์เข้ากับงานและทรัพยากรของโปรเจ็กต์ของคุณได้อย่างง่ายดาย เพิ่มประสิทธิภาพการทำงานร่วมกันและการเข้าถึงข้อมูล
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถเพิ่มไฮเปอร์ลิงก์หลายรายการในการมอบหมายทรัพยากรเดียวได้หรือไม่
ตอบ: ได้ คุณสามารถเพิ่มไฮเปอร์ลิงก์หลายรายการในการมอบหมายทรัพยากรได้โดยทำซ้ำขั้นตอนที่แสดงในบทช่วยสอนนี้สำหรับไฮเปอร์ลิงก์แต่ละรายการ
### ถาม: เป็นไปได้หรือไม่ที่จะปรับแต่งรูปลักษณ์ของไฮเปอร์ลิงก์ใน Aspose.Tasks
ตอบ: Aspose.Tasks มุ่งเน้นไปที่การจัดการข้อมูลและคุณสมบัติของโปรเจ็กต์เป็นหลัก รวมถึงไฮเปอร์ลิงก์ สำหรับการปรับแต่งรูปลักษณ์ไฮเปอร์ลิงก์ขั้นสูง คุณอาจต้องสำรวจไลบรารีหรือเครื่องมือเพิ่มเติม
### ถาม: มีข้อจำกัดเกี่ยวกับความยาวของไฮเปอร์ลิงก์ใน Aspose.Tasks หรือไม่
ตอบ: Aspose.Tasks ไม่ได้กำหนดข้อจำกัดที่เข้มงวดเกี่ยวกับความยาวของไฮเปอร์ลิงก์ อย่างไรก็ตาม ขอแนะนำให้ทำไฮเปอร์ลิงก์ให้กระชับและเกี่ยวข้องเพื่อให้อ่านและใช้งานได้สะดวกยิ่งขึ้น
### ถาม: ฉันสามารถลบไฮเปอร์ลิงก์ออกจากการกำหนดทรัพยากรโดยทางโปรแกรมได้หรือไม่
ตอบ: ได้ คุณสามารถลบไฮเปอร์ลิงก์ออกจากการกำหนดทรัพยากรได้โดยการตั้งค่าคุณสมบัติไฮเปอร์ลิงก์ให้เป็นสตริงว่างหรือสตริงว่าง
### ถาม: Aspose.Tasks รองรับการตรวจสอบไฮเปอร์ลิงก์หรือไม่
ตอบ: Aspose.Tasks มุ่งเน้นไปที่การจัดการคุณสมบัติไฮเปอร์ลิงก์มากกว่าการตรวจสอบไฮเปอร์ลิงก์ อย่างไรก็ตาม คุณสามารถใช้ตรรกะการตรวจสอบแบบกำหนดเองภายในแอปพลิเคชัน Java ของคุณเพื่อให้แน่ใจว่าไฮเปอร์ลิงก์มีความสมบูรณ์
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
