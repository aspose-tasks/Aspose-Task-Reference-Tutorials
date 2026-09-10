---
date: 2026-09-09
description: เรียนรู้วิธีเปลี่ยน currency symbol ในโครงการ Aspose.Tasks Java, ตั้งค่า
  currency codes, ปรับสัญลักษณ์, และใช้ custom formats สำหรับไฟล์ Microsoft Project
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: ตั้งค่า Currency Properties ในโครงการ Aspose.Tasks
og_description: วิธีเปลี่ยน currency symbol ใน Aspose.Tasks ด้วย Java. ค้นพบคำแนะนำขั้นตอนต่อขั้นตอน,
  ข้อกำหนดเบื้องต้น, และเคล็ดลับในการปรับแต่ง project cost formatting
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: วิธีเปลี่ยน currency symbol ใน Aspose.Tasks – คู่มือ Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: วิธีเปลี่ยน currency symbol ในโครงการ Aspose.Tasks – คู่มือ Java
url: /th/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเปลี่ยนสัญลักษณ์สกุลเงินใน Aspose.Tasks – คู่มือ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเปลี่ยนสัญลักษณ์สกุลเงิน** สำหรับไฟล์ Microsoft Project โดยใช้ Aspose.Tasks Java API ไม่ว่าคุณจะกำลังเตรียมรายงานสำหรับลูกค้าต่างประเทศ, รวมงบประมาณจากหลายภูมิภาค, หรือเพียงต้องการให้สอดคล้องกับมาตรฐานการบัญชีของบริษัท การปรับสัญลักษณ์สกุลเงินจะทำให้ทุกฟิลด์ที่เกี่ยวกับค่าใช้จ่ายแสดงสัญลักษณ์เงินที่ถูกต้อง คู่มือนี้จะอธิบายขั้นตอนทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมการพัฒนาไปจนถึงการบันทึกการเปลี่ยนแปลงในไฟล์โครงการใหม่หรือที่มีอยู่

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Tasks for Java.  
- **ฉันสามารถเปลี่ยนสัญลักษณ์สกุลเงินได้หรือไม่?** ใช่ – ตั้งค่า `Prj.CURRENCY_SYMBOL` และเลือก `CurrencySymbolPositionType`.  
- **รูปแบบไฟล์ใดที่รองรับ?** XML, MPP, และอื่น ๆ อีกหลายรูปแบบผ่าน `SaveFileFormat`.  
- **ฉันต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้ทดสอบได้; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานจริง.  
- **ใช้เวลานานเท่าไหร่ในการดำเนินการ?** ประมาณ 5‑10 นาทีสำหรับการตั้งค่าเบื้องต้น.

## วิธีเปลี่ยนสัญลักษณ์สกุลเงินใน Aspose.Tasks ด้วย Java
โหลดโครงการเป้าหมาย (หรือสร้างใหม่) ตั้งค่าคุณสมบัติสกุลเงินที่ต้องการ แล้วบันทึกไฟล์ การดำเนินการทั้งหมดประกอบด้วยการเรียก API สามครั้ง: สร้างหรือโหลดอ็อบเจ็กต์ `Project`, กำหนดรหัสสกุลเงิน, สัญลักษณ์และตำแหน่ง, จากนั้นเรียก `project.save`. วิธีนี้ทำงานได้ทั้งโครงการใหม่และไฟล์ที่มีอยู่โดยไม่ต้องติดตั้ง Microsoft Project

## ทำไมต้องใช้ Aspose.Tasks เพื่อเปลี่ยนสกุลเงิน?
Aspose.Tasks ให้ **การครอบคลุม API อย่างเต็มรูปแบบสำหรับคุณสมบัติที่เกี่ยวกับสกุลเงินกว่า 30 รายการ** ทำให้คุณสามารถกำหนดรหัส, สัญลักษณ์, จำนวนตำแหน่งทศนิยม และตำแหน่งการแสดงผลได้ในที่เดียว ไลบรารีสามารถประมวลผลไฟล์ Project หลายร้อยหน้าในเวลาไม่ถึงหนึ่งวินาทีบนเซิร์ฟเวอร์ทั่วไป และทำงานบน Windows, Linux, macOS โดยไม่มีการพึ่งพาเพิ่มเติม

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK) 8 หรือสูงกว่า** – API ต้องการอย่างน้อย JDK 8.  
2. **Aspose.Tasks for Java** – ดาวน์โหลด JAR เวอร์ชันล่าสุดจาก [หน้าดาวน์โหลด Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA หรือโปรแกรมแก้ไขใด ๆ ที่รองรับ Java.  
4. **โฟลเดอร์ที่สามารถเขียนได้** – ที่จะบันทึกไฟล์โครงการที่สร้างขึ้น

## นำเข้าแพ็กเกจ
คลาสต่อไปนี้ให้คุณเข้าถึงคุณสมบัติของโครงการ, การจัดการไฟล์, และการตั้งค่าสกุลเงิน  

`Project` – แสดงไฟล์ Microsoft Project ในหน่วยความจำ.  
`Prj` – มีค่าสำหรับคุณสมบัติระดับโครงการทั้งหมด รวมถึงฟิลด์สกุลเงิน.  
`CurrencySymbolPositionType` – ระบุตำแหน่งที่เป็นไปได้ของสัญลักษณ์สกุลเงิน (ก่อนหรือหลังจำนวน).  

การนำเข้าดังกล่าวจำเป็นก่อนที่โค้ดใด ๆ จะจัดการกับโครงการ

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
เลือกโฟลเดอร์ที่เก็บไฟล์ต้นฉบับและที่ผลลัพธ์จะถูกเขียนออกไป ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และกระบวนการ Java ของคุณมีสิทธิ์เขียน

### ขั้นตอนที่ 2: สร้างอินสแตนซ์โปรเจกต์ใหม่
คลาส `Project` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Tasks ที่แสดงไฟล์ Project หนึ่งไฟล์ในหน่วยความจำ การสร้างอินสแตนซ์จะสร้างโครงการเปล่าพร้อมสำหรับการกำหนดค่า

### ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติสกุลเงิน
ที่นี่คุณกำหนดรหัสสกุลเงิน, จำนวนตำแหน่งทศนิยม, สัญลักษณ์เอง, และตำแหน่งของสัญลักษณ์  

- **รหัสสกุลเงิน** – รหัส ISO 4217 สามตัวอักษร เช่น `AUD` หรือ `USD`.  
- **ตำแหน่งทศนิยม** – ปกติ 2 สำหรับสกุลเงินส่วนใหญ่.  
- **สัญลักษณ์สกุลเงิน** – ตัวอักษรหรือสตริงที่แสดงพร้อมจำนวนเงิน เช่น `$` หรือ `€`.  
- **ตำแหน่งสัญลักษณ์** – `CurrencySymbolPositionType.Before` จะวางสัญลักษณ์หน้าตัวเลข; `After` จะวางหลัง.  

การตั้งค่าเหล่านี้จะมีผลต่อทุกฟิลด์ที่เกี่ยวกับค่าใช้จ่าย (อัตราทรัพยากร, งบประมาณงาน ฯลฯ) ในโครงการ

> **เคล็ดลับ:** หากคุณต้องการเปลี่ยนสกุลเงินสำหรับไฟล์ที่มีอยู่ ให้โหลดไฟล์ด้วย `new Project("file.mpp")` ก่อนที่จะใช้การตั้งค่าข้างต้น.

### ขั้นตอนที่ 4: บันทึกโครงการที่อัปเดต
เขียนโครงการกลับไปยังดิสก์โดยใช้รูปแบบที่ต้องการ รูปแบบ XML สามารถอ่านได้โดยมนุษย์, ส่วน `SaveFileFormat.MPP` จะรักษาความเข้ากันได้เต็มรูปแบบกับ Microsoft Project

### ขั้นตอนที่ 5: ยืนยันความสำเร็จ
พิมพ์ข้อความสั้นหรือบันทึกเพื่อให้คุณทราบว่าการดำเนินการเสร็จสิ้นโดยไม่มีข้อผิดพลาด ซึ่งเป็นประโยชน์อย่างยิ่งในระบบอัตโนมัติ

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`NullPointerException` บน `project.save`** | `dataDir` ไม่ใช่เส้นทางที่ถูกต้องหรือไม่มีสิทธิ์เขียน. | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และกระบวนการ Java ของคุณมีสิทธิ์เขียน. |
| **สัญลักษณ์สกุลเงินไม่แสดง** | ตำแหน่งสัญลักษณ์ตั้งค่าไม่ถูกต้องสำหรับภาษาท้องถิ่นของคุณ. | ใช้ `CurrencySymbolPositionType.Before` หากสัญลักษณ์ควรอยู่หน้าจำนวน. |
| **ไฟล์โครงการไม่เปิดใน MS Project** | บันทึกในรูปแบบเก่าที่มีการตั้งค่าไม่เข้ากัน. | บันทึกโดยใช้ `SaveFileFormat.MPP` เพื่อความเข้ากันได้เต็มรูปแบบกับเวอร์ชันล่าสุดของ MS Project. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถตั้งค่าสกุลเงินหลายรายการในโครงการเดียวโดยใช้ Aspose.Tasks ได้หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถกำหนดการตั้งค่าสกุลเงินที่แตกต่างกันให้กับทรัพยากรหรืองานแต่ละรายการโดยการแก้ไขฟิลด์ค่าใช้จ่ายของพวกเขาหลังจากที่ได้กำหนดสกุลเงินระดับโครงการแล้ว.

**ถาม: Aspose.Tasks รองรับไฟล์ Microsoft Project เวอร์ชันต่าง ๆ หรือไม่?**  
**ตอบ:** แน่นอน. ไลบรารีรองรับไฟล์ MPP ตั้งแต่ Project 2000 จนถึงรุ่นล่าสุด, รวมถึง XML และรูปแบบแลกเปลี่ยนอื่น ๆ.

**ถาม: Aspose.Tasks มีการสนับสนุนรูปแบบสกุลเงินแบบกำหนดเองหรือไม่?**  
**ตอบ:** มี, คุณสามารถกำหนดสัญลักษณ์, จำนวนตำแหน่งทศนิยม, และตำแหน่งการแสดงผลตามความต้องการของแต่ละภูมิภาค, และการตั้งค่าเหล่านี้จะถูกบันทึกในไฟล์ที่บันทึกไว้.

**ถาม: ฉันสามารถรวม Aspose.Tasks กับเฟรมเวิร์ก Java อื่น ๆ ได้หรือไม่?**  
**ตอบ:** ได้เลย. API เป็น Java แท้ ๆ ทำงานร่วมกับ Spring, Hibernate, Maven, Gradle และระบบอื่น ๆ อย่างไร้รอยต่อ.

**ถาม: ฉันจะหาเอกสารหรือแบบอย่างเพิ่มเติมได้จากที่ไหน?**  
**ตอบ:** เยี่ยมชม [ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15) เพื่อรับความช่วยเหลือจากชุมชน, หรือดูเอกสารอย่างเป็นทางการสำหรับอ้างอิง API รายละเอียด.

## สรุป
คุณได้เรียนรู้ **วิธีเปลี่ยนสัญลักษณ์สกุลเงิน** ในโครงการ Aspose.Tasks ด้วย Java แล้ว, ตั้งค่ารหัสสกุลเงิน, ปรับตำแหน่งทศนิยม, และใช้สัญลักษณ์ที่กำหนดเอง ความสามารถเหล่านี้ช่วยให้คุณสร้างรายงานค่าใช้จ่ายตามภูมิภาค, ปรับงบประมาณโครงการให้สอดคล้องกับมาตรฐานการบัญชีของแต่ละพื้นที่, และทำให้ไฟล์ Microsoft Project ของคุณสอดคล้องกันทั่วทีมทั่วโลก

**อัปเดตล่าสุด:** 2026-09-09  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.11  
**ผู้เขียน:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## บทแนะนำที่เกี่ยวข้อง

- [คุณสมบัติโครงการ Java – ดึงสัญลักษณ์สกุลเงินจาก MPP ด้วย Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [อ่านคุณสมบัติสกุลเงิน Java ด้วยโครงการ Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [จัดการรหัสสกุลเงิน Java ด้วย Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}