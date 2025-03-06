---
title: ตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks
linktitle: ตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks
second_title: Aspose.Tasks Java API
description: เรียนรู้วิธีตั้งค่าคุณสมบัติสกุลเงินในโปรเจ็กต์ Aspose.Tasks โดยใช้ Java จัดการไฟล์ Microsoft Project ได้อย่างง่ายดาย
weight: 11
url: /th/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการตั้งค่าคุณสมบัติสกุลเงินในโปรเจ็กต์ Aspose.Tasks โดยใช้ Java Aspose.Tasks เป็นไลบรารี Java ที่ทรงพลังซึ่งช่วยให้นักพัฒนาจัดการไฟล์ Microsoft Project โดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2.  Aspose.Tasks สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks สำหรับ Java จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/tasks/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการ เช่น Eclipse หรือ IntelliJ IDEA
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Tasks ใน Java กันก่อน
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีข้อมูล
ตั้งค่าไดเร็กทอรีข้อมูลซึ่งมีไฟล์โปรเจ็กต์ของคุณอยู่
```java
String dataDir = "Your Data Directory";
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของโครงการ
สร้างอินสแตนซ์โครงการใหม่โดยใช้ Aspose.Tasks
```java
Project project = new Project();
```
## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติสกุลเงิน
ตอนนี้ มาตั้งค่าคุณสมบัติสกุลเงินสำหรับโครงการกัน
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## ขั้นตอนที่ 4: บันทึกโครงการ
บันทึกโครงการด้วยคุณสมบัติสกุลเงินที่อัพเดต
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## ขั้นตอนที่ 5: แสดงข้อความเสร็จสิ้น
แสดงข้อความแจ้งว่ากระบวนการเสร็จสมบูรณ์แล้ว
```java
System.out.println("Process completed Successfully");
```
ยินดีด้วย! คุณได้ตั้งค่าคุณสมบัติสกุลเงินในโครงการ Aspose.Tasks โดยใช้ Java สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.Tasks สำหรับ Java เพื่อตั้งค่าคุณสมบัติสกุลเงินในไฟล์โปรเจ็กต์ ด้วย Aspose.Tasks นักพัฒนาสามารถจัดการข้อมูลโครงการได้อย่างมีประสิทธิภาพ ทำให้เป็นเครื่องมืออันมีค่าสำหรับแอปพลิเคชันการจัดการโครงการ
## คำถามที่พบบ่อย
### ฉันสามารถตั้งค่าหลายสกุลเงินในโปรเจ็กต์เดียวโดยใช้ Aspose.Tasks ได้หรือไม่
ใช่ Aspose.Tasks ช่วยให้คุณสามารถจัดการหลายสกุลเงินภายในไฟล์โปรเจ็กต์เดียว
### Aspose.Tasks เข้ากันได้กับไฟล์ Microsoft Project เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### Aspose.Tasks ให้การสนับสนุนรูปแบบสกุลเงินที่กำหนดเองหรือไม่
แน่นอนว่า Aspose.Tasks มอบความยืดหยุ่นในการกำหนดรูปแบบสกุลเงินที่กำหนดเองเพื่อให้ตรงตามข้อกำหนดเฉพาะของโครงการ
### ฉันสามารถรวม Aspose.Tasks เข้ากับไลบรารีหรือเฟรมเวิร์ก Java อื่นๆ ได้หรือไม่
ใช่ Aspose.Tasks สามารถผสานรวมกับไลบรารีและเฟรมเวิร์ก Java อื่นๆ ได้อย่างราบรื่น ช่วยเพิ่มฟังก์ชันการทำงานและความอเนกประสงค์
### ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมสำหรับ Aspose.Tasks ได้ที่ไหน
 สำหรับการสนับสนุนเพิ่มเติม คุณสามารถไปที่[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)ซึ่งคุณสามารถค้นหาแหล่งข้อมูลที่เป็นประโยชน์และมีส่วนร่วมกับชุมชนได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
