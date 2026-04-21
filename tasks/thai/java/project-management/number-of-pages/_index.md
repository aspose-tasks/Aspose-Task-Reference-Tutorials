---
date: 2025-12-31
description: เรียนรู้วิธีการรับจำนวนหน้าใน Java ด้วย Aspose.Tasks รวมถึงวิธีการเริ่มต้นโปรเจกต์ใน
  Java และดึงจำนวนหน้าจากไฟล์ Microsoft Project.
linktitle: Get Page Count Java with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: รับจำนวนหน้าด้วย Java และ Aspose.Tasks
url: /th/java/project-management/number-of-pages/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับจำนวนหน้าด้วย Java และ Aspose.Tasks

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **get page count java** ด้วยการใช้ไลบรารี Aspose.Tasks ไม่ว่าคุณจะต้องการสร้างรายงาน, แบ่งหน้าโครงการขนาดใหญ่, หรือเพียงแค่ดึงข้อมูลเมตา การรู้จำนวนหน้าที่แน่นอนในไฟล์ Microsoft Project เป็นสิ่งสำคัญ เราจะเดินผ่านกระบวนการทั้งหมดตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเรียก API ที่คืนค่าจำนวนหน้า

## คำตอบอย่างรวดเร็ว
- **“get page count java” ทำอะไร?** คืนค่าจำนวนหน้าที่สามารถพิมพ์ได้ทั้งหมดในไฟล์ Project  
- **คลาสใดให้จำนวนหน้า?** `Project.getPageCount()` (หรือ overload ของมัน)  
- **ต้องมีลิขสิทธิ์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **สามารถกำหนด timescale ได้หรือไม่?** ได้, overload รองรับ `Timescale.Months` หรือ `Timescale.ThirdsOfMonths`  
- **รูปแบบ Project ที่รองรับ?** MPP, MPT, XML และรูปแบบอื่นที่ Aspose.Tasks รองรับ  

## ข้อกำหนดเบื้องต้น
ก่อนจะลงมือเขียนโค้ด ให้ตรวจสอบว่าคุณมีส่วนประกอบต่อไปนี้พร้อมใช้งานแล้ว:

### การติดตั้ง Java Development Kit (JDK)
1. ดาวน์โหลด JDK: เยี่ยมชม [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) เพื่อดาวน์โหลดเวอร์ชันล่าสุดของ JDK ที่เข้ากันกับระบบปฏิบัติการของคุณ  
2. การติดตั้ง: ปฏิบัติตามคำแนะนำการติดตั้งที่ Oracle ให้มาเพื่อทำการติดตั้ง JDK บนเครื่องของคุณ  

### การติดตั้ง Aspose.Tasks
1. ดาวน์โหลด Aspose.Tasks for Java: ไปที่ [download page](https://releases.aspose.com/tasks/java/) บนเว็บไซต์ Aspose  
2. รับลิขสิทธิ์: หากคุณต้องการใช้ Aspose.Tasks ในสภาพแวดล้อมการผลิต ให้ซื้อใบอนุญาตจาก [purchase page](https://purchase.aspose.com/buy)  

## นำเข้าแพ็กเกจ
เพื่อเริ่มใช้ Aspose.Tasks ในโครงการ Java ของคุณ คุณต้องนำเข้าแพ็กเกจที่จำเป็น ต่อไปนี้คือขั้นตอนแบบละเอียด:

## ขั้นตอนที่ 1: เพิ่มการพึ่งพา Aspose.Tasks
ตรวจสอบว่าคุณได้เพิ่ม Aspose.Tasks เป็น dependency ในโครงการ Java ของคุณแล้ว ใส่ dependency ของ Maven ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>xx.xx</version> <!-- Replace xx.xx with the latest version -->
</dependency>
```

## ขั้นตอนที่ 2: นำเข้าคลาส Aspose.Tasks
ในโค้ด Java ของคุณ ให้นำเข้าคลาส Aspose.Tasks ที่จำเป็น:

```java
import com.aspose.tasks.*;
```

## วิธีการเริ่มต้น Project ด้วย Java และ Aspose.Tasks
ขั้นตอนแรกที่ทำได้คือการสร้างอ็อบเจกต์ `Project` ที่แทนไฟล์ Microsoft Project ของคุณ

### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจกต์ Project
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir);
```
แทนที่ `"Your Data Directory"` ด้วยพาธเต็มไปยังไฟล์ `.mpp` หรือ `.xml` ที่คุณต้องการวิเคราะห์ ขั้นตอน **initialize project java** นี้จะทำให้คุณได้โมเดลโปรเจกต์ที่โหลดเต็มที่พร้อมสำหรับการดำเนินการต่อ

### ขั้นตอนที่ 2: รับจำนวนหน้า
ดึงจำนวนหน้าทั้งหมดโดยใช้ overload อย่างง่ายของ `getPageCount()`:

```java
int iPages = project.getPageCount();
```
ตอนนี้ตัวแปร `iPages` จะเก็บจำนวนหน้าที่สามารถพิมพ์ได้สำหรับ timescale เริ่มต้น

### ขั้นตอนที่ 3: รับจำนวนหน้าโดยกำหนด Timescale
หากต้องการจำนวนหน้าสำหรับ timescale เฉพาะ (เช่น เดือนหรือหนึ่งในสามของเดือน) ให้ใช้เมธอด overload:

```java
// Get number of pages with Timescale.Months
iPages = project.getPageCount(0, Timescale.Months);
// Get number of pages with Timescale.ThirdsOfMonths
iPages = project.getPageCount(0, Timescale.ThirdsOfMonths);
```
 overload เหล่านี้ช่วยให้คุณปรับการแบ่งหน้าให้ตรงกับวิธีที่คุณต้องการแสดงตารางเวลา

## ปัญหาทั่วไปและวิธีแก้
- **NullPointerException เมื่อโหลดไฟล์:** ตรวจสอบให้แน่ใจว่า `dataDir` ชี้ไปยังไฟล์ Project ที่ถูกต้องและไฟล์ไม่เสียหาย  
- **จำนวนหน้าผิดพลาด:** ตรวจสอบว่าคุณใช้ overload ของ timescale ที่ตรงกับมุมมองที่ต้องการพิมพ์  
- **ไม่พบลิขสิทธิ์:** วางไฟล์ `Aspose.Tasks.lic` ไว้ที่โฟลเดอร์รากของโครงการหรือกำหนดลิขสิทธิ์แบบโปรแกรมก่อนสร้างอ็อบเจกต์ `Project`  

## คำถามที่พบบ่อย

**Q: Aspose.Tasks รองรับไฟล์ Microsoft Project ทุกเวอร์ชันหรือไม่?**  
A: Aspose.Tasks รองรับรูปแบบไฟล์ Microsoft Project หลากหลายรวมถึง MPP, MPT, และ XML  

**Q: สามารถใช้ Aspose.Tasks ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, คุณสามารถใช้ Aspose.Tasks ในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์ได้หลังจากได้ลิขสิทธิ์ที่เหมาะสม  

**Q: Aspose.Tasks มีการสนับสนุนการรวมกับไลบรารี Java อื่นหรือไม่?**  
A: Aspose.Tasks มีเอกสารและการสนับสนุนที่ครบถ้วน ทำให้สามารถทำงานร่วมกับไลบรารีและเฟรมเวิร์ก Java ต่าง ๆ ได้  

**Q: มีฟอรั่มชุมชนที่สามารถขอความช่วยเหลือเกี่ยวกับ Aspose.Tasks ได้หรือไม่?**  
A: มี, คุณสามารถเยี่ยมชม [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) เพื่อโต้ตอบกับชุมชนและขอความช่วยเหลือเกี่ยวกับปัญหาต่าง ๆ  

**Q: สามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: แน่นอน, คุณสามารถสำรวจคุณลักษณะและฟังก์ชันของ Aspose.Tasks ได้โดยรับเวอร์ชันทดลองฟรีจาก [website](https://releases.aspose.com/)  

## สรุป
ด้วยการเข้าใจขั้นตอน **get page count java** คุณจะสามารถกำหนดจำนวนหน้าที่ตารางเวลา Microsoft Project จะใช้ได้อย่างอัตโนมัติ ปรับตัวเลือกการพิมพ์ และนำตรรกะการแบ่งหน้าไปใช้ในโซลูชันการรายงานที่ใหญ่ขึ้น ใช้ขั้นตอนข้างต้นเพื่อ **initialize project java**, ดึงจำนวนหน้า, และปรับ timescale ตามต้องการ ขอให้สนุกกับการเขียนโค้ด!

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.Tasks 24.12 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}