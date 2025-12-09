---
date: 2025-12-04
description: เรียนรู้วิธีอ่านคุณสมบัติสกุลเงินจากไฟล์ MS Project ด้วย Aspose.Tasks
  for Java. ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อดึงรหัสสกุลเงิน, สัญลักษณ์, จำนวนทศนิยมและตำแหน่งของสกุลเงินโดยอัตโนมัติ.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: อ่านคุณสมบัติสกุลเงิน Java ด้วยโครงการ Aspose.Tasks
url: /th/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านคุณสมบัติสกุลเงิน Java ด้วย Aspose.Tasks Projects

## คำแนะนำ
ในบทแนะนำนี้คุณจะ **อ่านคุณสมบัติสกุลเงิน Java** จากไฟล์ Microsoft Project โดยใช้ Aspose.Tasks for Java API Aspose.Tasks ช่วยให้คุณทำงานกับไฟล์ .mpp ได้โดยไม่ต้องติดตั้ง Microsoft Project ทำให้เหมาะสำหรับการสร้างรายงานอัตโนมัติ การย้ายข้อมูล หรือการรวมเข้ากับแอปพลิเคชันระดับองค์กรที่พัฒนาโดย Java เมื่อคุณอ่านคู่มือนี้จนจบแล้ว คุณจะสามารถดึงรหัสสกุลเงิน สัญลักษณ์ จำนวนตำแหน่งทศนิยม และตำแหน่งของสัญลักษณ์ได้โดยตรงจากไฟล์โปรเจกต์

## คำตอบอย่างรวดเร็ว
- **“read currency properties java” หมายถึงอะไร?** หมายถึงการดึงข้อมูลเมตาดาต้าที่เกี่ยวกับสกุลเงิน (รหัส, สัญลักษณ์, จำนวนตำแหน่งทศนิยม, ตำแหน่งสัญลักษณ์) จากไฟล์ MS Project ด้วยโค้ด Java  
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** มีรุ่นทดลองฟรีของ Aspose.Tasks ให้ใช้ได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **ต้องใช้ JDK เวอร์ชันใด?** Java 8 หรือใหม่กว่า  
- **สามารถแก้ไขการตั้งค่าสกุลเงินหลังจากอ่านได้หรือไม่?** ได้, Aspose.Tasks รองรับการอ่านและเขียนคุณสมบัติสกุลเงิน  
- **รองรับไฟล์ .mpp ทุกเวอร์ชันหรือไม่?** API รองรับไฟล์ที่สร้างด้วย Microsoft Project 2003‑2021  

## read currency properties java คืออะไร?
การอ่านคุณสมบัติสกุลเงินใน Java หมายถึงการเข้าถึงการตั้งค่าระดับโปรเจกต์ที่กำหนดวิธีการแสดงค่าเงินในไฟล์ Microsoft Project การตั้งค่าเหล่านี้รวมถึงรหัสสกุลเงินตามมาตรฐาน ISO (เช่น **USD**), สัญลักษณ์ (**$**), จำนวนตำแหน่งทศนิยม, และว่าตำแหน่งสัญลักษณ์จะอยู่ก่อนหรือหลังจำนวน

## ทำไมต้องอ่านคุณสมบัติสกุลเงิน java ด้วย Aspose.Tasks?
- **ไม่ต้องติดตั้ง Microsoft Project** – API ทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ Java  
- **การสกัดข้อมูลที่เร็วและทำในกระบวนการเดียว** – เหมาะสำหรับการประมวลผลเป็นชุดของไฟล์โปรเจกต์จำนวนมาก  
- **การควบคุมเต็มรูปแบบ** – สามารถนำค่าที่ดึงมาใช้ร่วมกับการสร้างรายงานแบบกำหนดเองหรือรวมเข้ากับระบบ ERP  
- **รองรับหลายเวอร์ชัน** – ทำงานกับไฟล์ .mpp ตั้งแต่ Project 2003 จนถึงรุ่นล่าสุด 2021  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – ติดตั้ง Java 8 หรือใหม่กว่าและกำหนดค่าใน `PATH` ของคุณ  
2. **Aspose.Tasks for Java JAR** – ดาวน์โหลดไลบรารีล่าสุดจาก [here](https://releases.aspose.com/tasks/java/) แล้วเพิ่มเข้าไปใน classpath ของโปรเจกต์  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้า namespace ของ Aspose.Tasks ที่จำเป็นสำหรับการจัดการโปรเจกต์:

```java
import com.aspose.tasks.*;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโปรเจกต์ของคุณ
กำหนดโฟลเดอร์ที่เก็บไฟล์ `.mpp` ที่ต้องการวิเคราะห์ การเก็บเส้นทางไว้ในตัวแปรทำให้โค้ดสามารถนำกลับมาใช้ใหม่ได้:

```java
String dataDir = "Your Data Directory";
```

*แทนที่ `"Your Data Directory"` ด้วยเส้นทางแบบเต็มหรือแบบสัมพันธ์ไปยังโฟลเดอร์ที่มีไฟล์ `project.mpp` อยู่*

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ Project Reader
โหลดไฟล์ Microsoft Project เข้าไปในอ็อบเจ็กต์ `Project` ซึ่งอ็อบเจ็กต์นี้ให้การเข้าถึงคุณสมบัติของโปรเจกต์ทั้งหมดรวมถึงการตั้งค่าสกุลเงิน:

```java
Project project = new Project(dataDir + "project.mpp");
```

*หากไฟล์ของคุณมีชื่อแตกต่างกัน ให้เปลี่ยน `"project.mpp"` ให้ตรงกับชื่อไฟล์นั้น*  

## ขั้นตอนที่ 3: แสดงคุณสมบัติสกุลเงิน
ตอนนี้ให้ดึงค่าแต่ละคุณสมบัติของสกุลเงินโดยใช้ enumeration `Prj` แล้วพิมพ์ผลลัพธ์ลงคอนโซล API จะคืนค่าเป็นอ็อบเจ็กต์ที่สามารถแปลงเป็นสตริงเพื่อแสดงผลได้:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**สิ่งที่คุณจะเห็น:**  
- **Currency Code** – รหัส ISO‑4217 เช่น `USD`, `EUR`, `JPY`  
- **Currency Digits** – ปกติเป็น `2` สำหรับสกุลเงินส่วนใหญ่, `0` สำหรับเยนญี่ปุ่น  
- **Currency Symbol** – ตัวอักษรที่แสดงในรายงาน (`$`, `€`, `¥`)  
- **Currency Symbol Position** – `0` หมายถึง **ก่อน** จำนวน, `1` หมายถึง **หลัง** จำนวน  

## ขั้นตอนที่ 4: สิ้นสุดการประมวลผล
แสดงข้อความสั้น ๆ เพื่อบ่งบอกว่าการสกัดข้อมูลเสร็จสมบูรณ์แล้ว ข้อความนี้มีประโยชน์เมื่อโค้ดทำงานเป็นส่วนหนึ่งของงานประมวลผลชุดใหญ่:

```java
System.out.println("Process completed Successfully");
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------||
| **FileNotFoundException** | เส้นทาง `dataDir` ไม่ถูกต้องหรือชื่อไฟล์สะกดผิด | ตรวจสอบสตริงของไดเรกทอรีและยืนยันว่าไฟล์ `.mpp` มีอยู่ในตำแหน่งที่ระบุ |
| **NullPointerException on `project.get(...)`** | ไฟล์โปรเจกต์ไม่มีข้อมูลสกุลเงิน (เป็นไปได้น้อย) หรือคีย์ของคุณสมบัติไม่ถูกต้อง | ใช้ `project.contains(Prj.CURRENCY_CODE)` เพื่อตรวจสอบการมีอยู่ก่อนอ่านค่า |
| **LicenseException** | รันโดยไม่มีลิขสิทธิ์ Aspose.Tasks ที่ถูกต้องในสภาพแวดล้อมการผลิต | ใส่ไฟล์ลิขสิทธิ์ด้วย `License license = new License(); license.setLicense("Aspose.Tasks.lic");` ก่อนสร้างอ็อบเจ็กต์ `Project` |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks รองรับทุกเวอร์ชันของ Microsoft Project หรือไม่?**  
**A:** Aspose.Tasks รองรับไฟล์ .mpp ที่สร้างโดย Microsoft Project 2003‑2021 ครอบคลุมทั้งรูปแบบเก่าและรูปแบบล่าสุด  

**Q: สามารถแก้ไขคุณสมบัติสกุลเงินด้วย Aspose.Tasks ได้หรือไม่?**  
**A:** ได้, คุณสามารถอ่านและเขียนการตั้งค่าสกุลเงินได้ ใช้ `project.set(Prj.CURRENCY_CODE, "EUR");` แล้วบันทึกโปรเจกต์  

**Q: Aspose.Tasks เหมาะสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
**A:** แน่นอน, เป็นไลบรารีเชิงพาณิชย์ คุณสามารถซื้อใบอนุญาตได้จาก [here](https://purchase.aspose.com/buy)  

**Q: Aspose.Tasks มีรุ่นทดลองฟรีหรือไม่?**  
**A:** มี, รุ่นทดลองเต็มรูปแบบพร้อมใช้งานจาก [here](https://releases.aspose.com/)  

**Q: จะหาความช่วยเหลือหรือสนับสนุนสำหรับ Aspose.Tasks ได้จากที่ไหน?**  
**A:** ฟอรั่มอย่างเป็นทางการของ Aspose.Tasks เป็นแหล่งที่ดีที่สุดสำหรับการขอความช่วยเหลือ – เยี่ยมชมได้ที่ [here](https://forum.aspose.com/c/tasks/15)  

## สรุป
คุณได้เรียนรู้วิธี **อ่านคุณสมบัติสกุลเงิน Java** จากไฟล์ MS Project ด้วย Aspose.Tasks for Java ความสามารถนี้ช่วยให้คุณนำข้อมูลเมตาดาต้าสกุลเงินไปใช้ในรายงานแบบกำหนดเอง การวิเคราะห์ทางการเงิน หรือการรวมข้อมูลในสายงานโดยไม่ต้องพึ่งพา Microsoft Project เอง อย่าลังเลที่จะทดลองแก้ไขคุณสมบัติเหล่านี้หรือผสานข้อมูลนี้กับแอตทริบิวต์อื่นของโปรเจกต์เพื่อสร้างโซลูชันที่สมบูรณ์ยิ่งขึ้น  

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}