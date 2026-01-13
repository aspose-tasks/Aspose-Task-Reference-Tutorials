---
date: 2026-01-13
description: เรียนรู้วิธีการวนซ้ำทรัพยากรที่ไม่ใช่รากในไฟล์ Microsoft Project โดยใช้
  Aspose.Tasks สำหรับ Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: วนซ้ำทรัพยากรที่ไม่ใช่รากด้วย Aspose.Tasks สำหรับ Java
url: /th/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ทำซ้ำทรัพยากรที่ไม่ใช่รากด้วย Aspose.Tasks for Java

## บทนำ
Aspose.Tasks for Java เป็นไลบรารีที่ทรงพลังซึ่งให้วิธีการทำงานกับไฟล์ Microsoft Project แบบเชิงวัตถุ (object‑oriented) ที่สะอาดและเป็นระบบ ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีทำซ้ำทรัพยากรที่ไม่ใช่ราก** เพื่อให้คุณสามารถอ่าน แก้ไข หรือวิเคราะห์ข้อมูลทรัพยากรโดยไม่ต้องจัดการกับตัวแทนราก ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน สคริปต์การย้ายข้อมูล หรือระบบจัดตารางงานแบบกำหนดเอง การเชี่ยวชาญเทคนิคนี้จะทำให้โค้ดของคุณแม่นยำและมีประสิทธิภาพมากขึ้น

## คำตอบด่วน
- **อะไรคือ “non‑root resource”?** ทรัพยากรที่ไม่ใช่ตัวแทน “Project” เริ่มต้น (โหนดราก)  
- **ทำไมต้องกรองเอาตัวแทนรากออก?** ตัวแทนรากไม่มีข้อมูลการจัดตารางที่มีประโยชน์และอาจทำให้รายงานรกเกินไป  
- **คลาสของ Aspose.Tasks ที่ให้คอลเลกชันทรัพยากรคืออะไร?** `Project.getResources()`  
- **ต้องมีลิขสิทธิ์สำหรับโค้ดนี้หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถใช้กับ Java 17 ได้หรือไม่?** ได้ – Aspose.Tasks รองรับ Java 8 ขึ้นไป  

## ข้อกำหนดเบื้องต้น
ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – ติดตั้ง JDK เวอร์ชันล่าสุดจาก [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)  
2. **Aspose.Tasks for Java library** – ดาวน์โหลด JAR ล่าสุดจาก [download page](https://releases.aspose.com/tasks/java/)  

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้นำเข้าคลาส Aspose.Tasks ที่จำเป็น:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีข้อมูล
```java
String dataDir = "Your Data Directory";
```
เปลี่ยน `"Your Data Directory"` ให้เป็นพาธเต็มที่ไฟล์ `.mpp` ของคุณอยู่

## ขั้นตอนที่ 2: โหลดไฟล์โปรเจกต์
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
โค้ดนี้จะสร้างอินสแตนซ์ `Project` โดยโหลด **ResourceCosts.mpp** จากโฟลเดอร์ที่คุณระบุ

## ขั้นตอนที่ 3: ทำซ้ำทรัพยากรที่ไม่ใช่ราก
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
ลูปนี้จะเดินผ่านอ็อบเจ็กต์ `Resource` ทุกตัวในโปรเจกต์ การตรวจสอบ `isRoot()` จะข้ามตัวแทนรากที่สร้างมาโดยอัตโนมัติ และคำสั่ง `System.out.println` จะพิมพ์ชื่อของ **non‑root resource** แต่ละรายการ

## วิธีทำซ้ำทรัพยากรที่ไม่ใช่ราก
ตัวอย่างข้างต้นแสดงรูปแบบหลัก:

1. ดึงคอลเลกชันเต็มด้วย `prj.getResources()`  
2. ใช้ `isRoot()` เพื่อกรองเอาตัวแทนรากออก  
3. เข้าถึงฟิลด์ของทรัพยากรใดก็ได้ (เช่น `Rsc.NAME`, `Rsc.COST`) ตามต้องการ  

คุณสามารถต่อยอดรูปแบบนี้เพื่อสรุปค่าใช้จ่าย ส่งออกเป็น CSV หรือใช้กฎธุรกิจที่กำหนดเองได้

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **Null checks** – บางทรัพยากรอาจมีฟิลด์ที่เป็นออปชัน; ควรตรวจสอบ `null` ก่อนเรียก `get()` เสมอ  
- **Performance** – สำหรับโปรเจกต์ขนาดใหญ่มาก ควรพิจารณาใช้ลูปแบบอิงดัชนีเพื่อหลีกเลี่ยงการสร้างคอลเลกชันกลาง  
- **Licensing** – การรันโค้ดโดยไม่มีลิขสิทธิ์ที่ถูกต้องจะทำให้ไฟล์ที่ส่งออกมีลายน้ำ; ควรเปิดใช้งานลิขสิทธิ์ตั้งแต่ต้นแอปพลิเคชัน  

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้ **วิธีทำซ้ำทรัพยากรที่ไม่ใช่ราก** ด้วย Aspose.Tasks for Java เทคนิคนี้ช่วยให้คุณโฟกัสที่ทรัพยากรของโครงการจริง ทำความสะอาดข้อมูลที่สกัดออกมา และสร้างโซลูชันการจัดการโครงการที่น่าเชื่อถือยิ่งขึ้น

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Tasks for Java เพื่อสร้างไฟล์โปรเจกต์ใหม่ได้หรือไม่?
ได้, Aspose.Tasks มีความสามารถ CRUD (Create, Read, Update, Delete) ครบถ้วนสำหรับรูปแบบไฟล์ MPP, MPT, และ XML  

### Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันทั้งหมดหรือไม่?
แน่นอน. รองรับไฟล์ Project 2003‑2019 รวมถึงสเปค MPP ล่าสุด  

### Aspose.Tasks เข้ากันได้กับเฟรมเวิร์ก Java เช่น Spring หรือไม่?
ได้, คุณสามารถฉีดไลบรารีนี้เข้าไปใน Spring beans หรือใช้ในแอปพลิเคชัน Java มาตรฐานใดก็ได้  

### ฉันสามารถปรับแต่งฟิลด์ข้อมูลของโปรเจกต์โดยใช้ Aspose.Tasks ได้หรือไม่?
ได้เลย. API ให้คุณเพิ่ม, แก้ไข หรือ ลบฟิลด์กำหนดเองบนงาน, ทรัพยากร, และการมอบหมาย  

### Aspose.Tasks มีการสนับสนุนและเอกสารสำหรับนักพัฒนาหรือไม่?
ผลิตภัณฑ์มาพร้อมกับเอกสาร API ครบถ้วน, ตัวอย่างโค้ด, และฟอรั่มสนับสนุนเฉพาะสำหรับการช่วยเหลืออย่างรวดเร็ว  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-13  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12  
**ผู้เขียน:** Aspose