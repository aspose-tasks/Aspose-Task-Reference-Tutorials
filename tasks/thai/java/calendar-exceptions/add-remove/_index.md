---
title: จัดการข้อยกเว้นของปฏิทินใน Aspose.Tasks
linktitle: เพิ่มและลบข้อยกเว้นปฏิทินใน Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีเพิ่มและลบข้อยกเว้นปฏิทินใน Aspose.Tasks สำหรับ Java อย่างมีประสิทธิภาพ ปรับปรุงเวิร์กโฟลว์การจัดการโครงการได้อย่างง่ายดาย
weight: 10
url: /th/java/calendar-exceptions/add-remove/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการข้อยกเว้นของปฏิทินใน Aspose.Tasks


## การแนะนำ
ในการจัดการโครงการ การจัดการข้อยกเว้นภายในปฏิทินถือเป็นสิ่งสำคัญสำหรับการจัดกำหนดการงานและการจัดการทรัพยากรอย่างถูกต้อง Aspose.Tasks for Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการเพิ่มและลบข้อยกเว้นของปฏิทินได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
#### ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Tasks สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่าในโปรเจ็กต์ของคุณ
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java และแนวคิดการจัดการโครงการ

## แพ็คเกจนำเข้า
ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็นในคลาส Java ของคุณเพื่อใช้ฟังก์ชัน Aspose.Tasks อย่างมีประสิทธิภาพ
```java
import com.aspose.tasks.*;
```
## ขั้นตอนที่ 1: โหลดโครงการและเข้าถึงปฏิทิน
เริ่มต้นด้วยการโหลดไฟล์โครงการของคุณและเข้าถึงปฏิทินที่คุณต้องการเพิ่มหรือลบข้อยกเว้น
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## ขั้นตอนที่ 2: ลบข้อยกเว้น
หากต้องการลบข้อยกเว้นที่มีอยู่ออกจากปฏิทิน ให้ตรวจสอบว่ามีข้อยกเว้นอยู่หรือไม่ จากนั้นจึงลบข้อยกเว้นที่ต้องการออก
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## ขั้นตอนที่ 3: เพิ่มข้อยกเว้น
 หากต้องการเพิ่มข้อยกเว้นใหม่ให้กับปฏิทิน ให้สร้าง`CalendarException` วัตถุและกำหนดวันที่เริ่มต้นและสิ้นสุด
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## ขั้นตอนที่ 4: แสดงข้อยกเว้น
สุดท้าย คุณสามารถแสดงข้อยกเว้นเพิ่มเติมสำหรับการตรวจสอบหรือการประมวลผลเพิ่มเติมได้
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## บทสรุป
การจัดการข้อยกเว้นของปฏิทินถือเป็นสิ่งสำคัญสำหรับการจัดกำหนดการโครงการและการจัดสรรทรัพยากรที่แม่นยำ ด้วย Aspose.Tasks สำหรับ Java คุณสามารถเพิ่มและลบข้อยกเว้นได้อย่างง่ายดายเพื่อให้แน่ใจว่าไทม์ไลน์ของโปรเจ็กต์ของคุณได้รับการดูแลอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถเพิ่มข้อยกเว้นหลายรายการให้กับปฏิทินโดยใช้ Aspose.Tasks for Java ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มข้อยกเว้นได้หลายรายการในปฏิทินโดยวนซ้ำรายการข้อยกเว้นและเพิ่มแต่ละรายการทีละรายการ

### ถาม: Aspose.Tasks สำหรับ Java เข้ากันได้กับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่

ตอบ: Aspose.Tasks for Java ให้ความเข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจว่าสามารถผสานรวมกับเวิร์กโฟลว์การจัดการโครงการของคุณได้อย่างราบรื่น

### ถาม: ฉันจะจัดการกับข้อยกเว้นที่เกิดซ้ำในปฏิทินโครงการได้อย่างไร

ตอบ: Aspose.Tasks for Java นำเสนอคุณสมบัติที่มีประสิทธิภาพในการจัดการข้อยกเว้นที่เกิดซ้ำในปฏิทินโปรเจ็กต์ ช่วยให้คุณสามารถกำหนดรูปแบบการเกิดซ้ำที่ซับซ้อนได้อย่างง่ายดาย

### ถาม: Aspose.Tasks สำหรับ Java มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ: ได้ คุณสามารถเข้าถึง Aspose.Tasks for Java เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ

### ถาม: ฉันจะขอรับการสนับสนุนสำหรับปัญหาหรือการสอบถามที่เกี่ยวข้องกับ Aspose.Tasks for Java ได้ที่ไหน

 ตอบ: คุณสามารถเยี่ยมชมฟอรัม Aspose.Tasks สำหรับ Java ได้บน[เว็บไซต์](https://reference.aspose.com/tasks/java/) เพื่อขอความช่วยเหลือจากชุมชนหรือติดต่อทีมสนับสนุนโดยตรงเพื่อขอความช่วยเหลือส่วนบุคคล

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
