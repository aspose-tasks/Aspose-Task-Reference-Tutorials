---
date: 2025-12-25
description: สำรวจบทเรียน Aspose Tasks Java นี้เพื่อเรียนรู้วิธีกำหนดเวอร์ชันของไฟล์
  MS Project. คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'บทเรียน Aspose Tasks Java: กำหนดเวอร์ชันของ MS Project'
url: /th/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java Tutorial: Determine MS Project Version

## บทนำ
ใน **aspose tasks java tutorial** นี้ คุณจะได้เรียนรู้วิธีการค้นหาเวอร์ชันของไฟล์ Microsoft Project อย่างอัตโนมัติโดยใช้ไลบรารี Aspose.Tasks สำหรับ Java การรู้เวอร์ชันของไฟล์ช่วยให้คุณจัดการปัญหาความเข้ากันได้ บังคับใช้นโยบายการย้ายข้อมูล หรือเพียงแค่บันทึกว่าเวอร์ชันของ Project ใดที่สร้างไฟล์นี้ เราจะอธิบายขั้นตอนทั้งหมด—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการพิมพ์เวอร์ชันและวันที่บันทึกล่าสุด—เพื่อให้คุณสามารถผสานการตรวจสอบนี้เข้าไปในแอปพลิเคชัน Java ใดก็ได้อย่างมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **บทแนะนำนี้ครอบคลุมอะไรบ้าง?** การกำหนดเวอร์ชันของไฟล์ MS Project ด้วย Aspose.Tasks สำหรับ Java.  
- **ต้องติดตั้ง Microsoft Project หรือไม่?** ไม่จำเป็น Aspose.Tasks ทำงานได้โดยอิสระ.  
- **ไฟล์ฟอร์แมตใดที่รองรับ?** ไฟล์ Project ที่ใช้ XML (เช่น MPP, XML ฯลฯ).  
- **ใช้เวลานานเท่าไหร่ในการทำ?** ประมาณ 5‑10 นาทีสำหรับการตรวจสอบพื้นฐาน.  
- **ต้องการใบอนุญาตหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง.

## Aspose Tasks Java Tutorial คืออะไร?
**aspose tasks java tutorial** ให้คำแนะนำเชิงปฏิบัติเกี่ยวกับการใช้ Aspose.Tasks API ในโครงการ Java มันแสดงวิธีการอ่าน, แก้ไข, และวิเคราะห์ข้อมูล Microsoft Project โดยไม่ต้องใช้ Microsoft Project เอง.

## ทำไมต้องใช้ Aspose.Tasks เพื่อกำหนดเวอร์ชันของโปรเจกต์?
- **ไม่มีการพึ่งพา Microsoft Project** – เหมาะสำหรับการทำงานอัตโนมัติบนเซิร์ฟเวอร์.  
- **เมตาดาต้าเวอร์ชันที่แม่นยำ** – ดึงข้อมูลฟิลด์ SAVE_VERSION และ LAST_SAVED อย่างตรงไปตรงมา.  
- **ข้ามแพลตฟอร์ม** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java.  
- **ประสิทธิภาพสูง** – การพาร์สที่มีน้ำหนักเบา เหมาะสำหรับการประมวลผลเป็นชุด.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Java Development Kit (JDK)** – JDK รุ่นใหม่ใดก็ได้ (เวอร์ชัน 8 หรือสูงกว่า).  
2. **Aspose.Tasks for Java JAR** – ดาวน์โหลดจาก [website](https://releases.aspose.com/tasks/java/) แล้วเพิ่มไปยัง classpath ของโครงการของคุณ.  
3. **ไฟล์ MS Project** – ไฟล์ Project ที่ใช้ XML (เช่น `input.xml`) ที่คุณต้องการตรวจสอบ.  

> **เคล็ดลับ:** เก็บไฟล์ Project ไว้ในโฟลเดอร์ `data` แยกเฉพาะเพื่อให้ง่ายต่อการจัดการเส้นทาง.

## นำเข้าแพ็กเกจ
ขั้นแรก, นำเข้าคลาส Aspose.Tasks ที่จำเป็น:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีของโปรเจกต์
กำหนดโฟลเดอร์ที่บรรจุไฟล์ Project ของคุณ.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

แทนที่ `"Your Data Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ที่ไฟล์ `input.xml` อยู่.

## ขั้นตอนที่ 2: โหลดโปรเจกต์
สร้างอินสแตนซ์ `Project` โดยโหลดไฟล์ XML.

```java
Project project = new Project(dataDir + "input.xml");
```

หากไฟล์ของคุณมีชื่ออื่น, ปรับ `"input.xml"` ให้สอดคล้อง.

## ขั้นตอนที่ 3: วิธีกำหนดเวอร์ชันของโปรเจกต์
ดึงข้อมูลเวอร์ชันและเวลาที่บันทึกล่าสุด.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

คุณสมบัติ `Prj.SAVE_VERSION` แสดงเวอร์ชันของ Microsoft Project ที่ใช้บันทึกไฟล์ (เช่น 12 สำหรับ Project 2010). `Prj.LAST_SAVED` คืนค่าวันที่/เวลา ของการบันทึกล่าสุด.

## ขั้นตอนที่ 4: แสดงผล
แสดงสัญญาณว่าการตรวจสอบเวอร์ชันสำเร็จ.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | ไฟล์ไม่พบหรือเส้นทางไม่ถูกต้อง | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้เส้นทางแบบ absolute สำหรับการทดสอบ. |
| หมายเลขเวอร์ชันที่ไม่คาดคิด (เช่น 0) | กำลังโหลดไฟล์ XML ที่ไม่ใช่ Project | ตรวจสอบว่าไฟล์เป็นไฟล์ Microsoft Project ที่ถูกต้อง (MPP/XML). |
| License exception | ใช้รุ่นทดลองโดยไม่มีใบอนุญาตที่ถูกต้องในสภาพแวดล้อมการผลิต | ใช้ใบอนุญาต Aspose.Tasks ของคุณ (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถใช้ Aspose.Tasks กับภาษาโปรแกรมอื่นได้หรือไม่?
ตอบ: ใช่, Aspose.Tasks รองรับหลายภาษา รวมถึง .NET, Java, และ C++.

### ถาม: Aspose.Tasks เหมาะกับโครงการขนาดใหญ่หรือไม่?
ตอบ: แน่นอน, Aspose.Tasks ถูกออกแบบให้จัดการโครงการขนาดใดก็ได้อย่างง่ายดาย.

### ถาม: ฉันสามารถปรับแต่งข้อมูลโปรเจกต์โดยใช้ Aspose.Tasks ได้หรือไม่?
ตอบ: ใช่, คุณสามารถจัดการข้อมูลโปรเจกต์, แก้ไขงาน, ทรัพยากร, และอื่น ๆ อีกมากมายโดยใช้ Aspose.Tasks.

### ถาม: Aspose.Tasks ต้องการการติดตั้ง Microsoft Project หรือไม่?
ตอบ: ไม่, Aspose.Tasks ทำงานได้โดยอิสระและไม่ต้องการการติดตั้ง Microsoft Project.

### ถาม: มีการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks หรือไม่?
ตอบ: มี, คุณสามารถรับการสนับสนุนทางเทคนิคจากฟอรั่ม Aspose.Tasks ที่ [here](https://forum.aspose.com/c/tasks/15).

### คำถามเพิ่มเติม

**ถาม: ฉันจะดึงคุณสมบัติโปรเจกต์อื่น ๆ (เช่น ผู้เขียน, บริษัท) อย่างไร?**  
ตอบ: ใช้ `project.get(Prj.AUTHOR)` หรือ `project.get(Prj.COMPANY)` เช่นเดียวกับตัวอย่างเวอร์ชัน.

**ถาม: ฉันสามารถตรวจสอบเวอร์ชันของไฟล์ MPP (รูปแบบไบนารี) ได้หรือไม่?**  
ตอบ: ได้, Aspose.Tasks สามารถโหลดไฟล์ `.mpp` ได้โดยตรง; คุณสมบัติ `Prj.SAVE_VERSION` ทำงานเช่นเดียวกัน.

**ถาม: มีวิธีการอัปเกรดไฟล์โปรเจกต์เก่าเป็นเวอร์ชันใหม่โดยอัตโนมัติหรือไม่?**  
ตอบ: โหลดไฟล์เก่า, แล้วบันทึกโดยใช้ `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks จะเขียนไฟล์ในรูปแบบล่าสุดโดยค่าเริ่มต้น.

## สรุป
คุณได้ทำ **aspose tasks java tutorial** สั้น ๆ ที่แสดง **วิธีกำหนดเวอร์ชันของโปรเจกต์** ของไฟล์ MS Project ด้วย Aspose.Tasks สำหรับ Java เสร็จแล้ว ผสานโค้ดนี้เข้ากับกระบวนการอัตโนมัติที่ใหญ่ขึ้น, เครื่องมือรายงาน, หรือยูทิลิตี้การย้ายข้อมูล เพื่อให้คุณมั่นใจว่า คุณรู้เวอร์ชันของ Project ที่กำลังทำงานอยู่เสมอ.

---

**อัปเดตล่าสุด:** 2025-12-25  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}