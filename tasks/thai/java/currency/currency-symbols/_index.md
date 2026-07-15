---
date: 2026-02-10
description: เรียนรู้วิธีดึงและอัปเดตคุณสมบัติโครงการ Java เช่น สัญลักษณ์สกุลเงินโดยใช้
  Aspose.Tasks for Java เปลี่ยนสกุลเงินของโครงการและดึงสัญลักษณ์สกุลเงินได้อย่างง่ายดาย.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: คุณสมบัติโปรเจกต์ Java – ดึงสัญลักษณ์สกุลเงินจากไฟล์ MPP ด้วย Aspose.Tasks
  สำหรับ Java
url: /th/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงสัญลักษณ์สกุลเงินจากไฟล์ mpp ด้วย Aspose.Tasks for Java

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธีทำงานกับ **java project properties**—โดยเฉพาะวิธีดึงสัญลักษณ์สกุลเงินจากไฟล์ Microsoft Project (MPP) และวิธี **change currency symbol java** หรือ **retrieve currency symbol java** ด้วยไลบรารี Aspose.Tasks ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน, ผสานข้อมูล Project เข้ากับระบบการเงิน, หรือเพียงต้องการแสดงสัญลักษณ์สกุลเงินที่ถูกต้องใน UI ของคุณ การทำความเข้าใจงานเล็ก ๆ แต่สำคัญนี้จะทำให้แอปพลิเคชัน Java ของคุณแข็งแรงและเป็นมิตรต่อผู้ใช้มากยิ่งขึ้น

## คำตอบสั้น ๆ
- **“extract currency symbol mpp” หมายถึงอะไร?** หมายถึงการอ่านสัญลักษณ์สกุลเงินที่เก็บไว้ในไฟล์ MPP (Microsoft Project)  
- **ไลบรารีใดรับผิดชอบเรื่องนี้?** Aspose.Tasks for Java มี API ที่ง่ายต่อการใช้งานสำหรับงานนี้  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ใช้เวลานานแค่ไหน?** ด้วยโค้ดด้านล่างคุณสามารถดึงสัญลักษณ์ได้ภายในไม่กี่วินาที  
- **ฉันสามารถเปลี่ยนสัญลักษณ์ได้หรือไม่?** ได้ – คุณสามารถตั้งค่าค่าใหม่โดยใช้ property `Prj.CURRENCY_SYMBOL` เดียวกัน

## “extract currency symbol mpp” คืออะไร?
Microsoft Project เก็บสัญลักษณ์สกุลเงิน (เช่น $, €, £) ไว้ในส่วนหัวของไฟล์โปรเจกต์ การทำ **extract currency symbol mpp** จะอ่านค่าดังกล่าวเพื่อให้คุณสามารถแสดงหรือจัดการได้โดยโปรแกรม

## ทำไมต้องอัปเดตสัญลักษณ์สกุลเงินใน java project properties?
โปรเจกต์มักขยายข้ามหลายภูมิภาค การที่คุณสามารถ **change project currency** หรือ **update currency symbol** ในขณะทำงานได้ จะช่วยให้คุณปรับรายงาน, ใบแจ้งหนี้, หรือแดชบอร์ดให้สอดคล้องกับตลาดท้องถิ่นโดยไม่ต้องสร้างไฟล์โปรเจกต์ใหม่ ความยืดหยุ่นนี้เป็นส่วนสำคัญของการจัดการ java project properties อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ให้ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือสูงกว่า  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR ล่าสุดจาก [หน้าดาวน์โหลด Aspose.Tasks](https://releases.aspose.com/tasks/java/)  
3. ไฟล์ **project.mpp** ที่ถูกต้องและอยู่ในโฟลเดอร์ที่คุณสามารถอ้างอิงจากโค้ดได้

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นสำหรับทำงานกับไฟล์ Project

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
บอกแอปพลิเคชันว่ามีไฟล์ *.mpp* ของคุณอยู่ที่ไหน

```java
String dataDir = "Your Data Directory";
```

> **เคล็ดลับ:** ใช้ `System.getProperty("user.dir")` เพื่อสร้างพาธแบบเต็มที่ทำงานได้บนเครื่องใดก็ได้

## ขั้นตอนที่ 2: โหลดไฟล์ MS Project
สร้างอ็อบเจกต์ `Project` ที่แทนไฟล์ MPP ในหน่วยความจำ

```java
Project project = new Project(dataDir + "project.mpp");
```

## ขั้นตอนที่ 3: ดึง (และอาจเปลี่ยน) สัญลักษณ์สกุลเงิน
ตอนนี้เราจะ **retrieve currency symbol java** โดยอ่าน property `Prj.CURRENCY_SYMBOL` คุณยังสามารถ **change currency symbol java** (หรือ **change project currency**) โดยกำหนดสตริงใหม่ให้กับ property เดียวกัน

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

คำสั่ง `System.out.println` จะพิมพ์สัญลักษณ์ (เช่น `$`) ไปที่คอนโซล เพื่อยืนยันว่าการดึงสำเร็จ

## ปัญหาที่พบบ่อยและวิธีแก้
| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | พาธไฟล์ผิดหรือไฟล์ไม่พบ | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้ `new File(dataDir).exists()` เพื่อตรวจสอบ |
| สัญลักษณ์แสดงผลไม่ถูกต้อง (เช่น `?`) | โปรเจกต์สร้างด้วย locale ที่ไม่มาตรฐาน | ตรวจสอบว่าไฟล์ MPP ต้นทางกำหนดสัญลักษณ์สกุลเงินจริงหรือไม่; คุณสามารถตั้งค่าใหม่ตามตัวอย่างด้านบน |
| เกิดข้อผิดพลาดลิขสิทธิ์ | ใช้รุ่นทดลองโดยไม่มีไฟล์ลิขสิทธิ์ที่ถูกต้อง | โหลดลิขสิทธิ์ของคุณด้วย `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` ก่อนสร้างอ็อบเจกต์ `Project` |

## คำถามที่พบบ่อย

**Q: ฉันสามารถจัดการคุณสมบัติอื่นของโปรเจกต์ได้นอกจากสัญลักษณ์สกุลเงินด้วย Aspose.Tasks หรือไม่?**  
A: ได้, Aspose.Tasks ให้คุณแก้ไขงาน, ทรัพยากร, การมอบหมาย, ปฏิทิน, และคุณสมบัติโปรเจกต์อื่น ๆ อีกมากมาย

**Q: Aspose.Tasks รองรับไฟล์ MS Project เวอร์ชันใดบ้าง?**  
A: รองรับอย่างแน่นอน ทั้ง MPP, MPT, และ XML ตั้งแต่ Project 98 จนถึงเวอร์ชันล่าสุด

**Q: Aspose.Tasks มีเอกสารและการสนับสนุนสำหรับนักพัฒนาหรือไม่?**  
A: มีเอกสาร API ครบถ้วน, ตัวอย่างโค้ด, และฟอรั่มสนับสนุนเฉพาะบนเว็บไซต์ Aspose.Tasks

**Q: ฉันสามารถทดลองใช้ Aspose.Tasks ก่อนซื้อได้หรือไม่?**  
A: ได้ – สามารถดาวน์โหลดรุ่นทดลองที่ทำงานเต็มรูปแบบจาก [เว็บไซต์ Aspose](https://purchase.aspose.com/buy)

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Tasks ได้อย่างไร?**  
A: ลิขสิทธิ์ชั่วคราวมีให้ที่ [หน้าลิขสิทธิ์ชั่วคราวของ Aspose](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล

---

**อัปเดตล่าสุด:** 2026-02-10  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}