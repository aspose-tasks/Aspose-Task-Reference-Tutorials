---
date: 2025-12-11
description: เรียนรู้วิธีใช้ Java อ่านฐานข้อมูล Access และแปลง Access เป็น XML ด้วย
  Aspose.Tasks for Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อส่งออก MS Project
  XML.
linktitle: Reading Project Data from Microsoft Access Database with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'java อ่านฐานข้อมูล Access: อ่านข้อมูลโครงการด้วย Aspose.Tasks'
url: /th/java/project-data-reading/read-access-database/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java read access database: การอ่านข้อมูลโครงการด้วย Aspose.Tasks

## บทนำ
Aspose.Tasks for Java เป็น API ที่ทรงพลังที่ช่วยให้คุณ **java read access database** ข้อมูลและแปลงเป็นรูปแบบ Microsoft Project ในบทแนะนำนี้ เราจะอธิบายขั้นตอนที่จำเป็นในการอ่านข้อมูล MS Project ที่เก็บไว้ในฐานข้อมูล Microsoft Access, แปลงข้อมูลเป็น XML, และสุดท้ายส่งออกโครงการเป็นไฟล์ XML ที่สามารถใช้โดยเครื่องมืออื่นได้.

## คำตอบสั้น
- **What does the tutorial cover?** การอ่านข้อมูล MS Project จากฐานข้อมูล Access และส่งออกเป็น XML ด้วย Aspose.Tasks.  
- **Which library is required?** Aspose.Tasks for Java (เวอร์ชันล่าสุด).  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **Can I convert Access to XML?** ใช่ – คลาส `MpdSettings` จะจัดการการแปลงโดยอัตโนมัติ.  
- **Is Java 8+ supported?** แน่นอน, JDK 8 หรือใหม่กว่าจะทำงานได้.

## java read access database คืออะไร?
การอ่านข้อมูลจากฐานข้อมูล Access ด้วย Java หมายถึงการตั้งค่า connection string, ดึงข้อมูลโครงการ, แล้วใช้ Aspose.Tasks เพื่อจัดการข้อมูลนั้น วิธีนี้เหมาะอย่างยิ่งเมื่อคุณมีข้อมูลโครงการแบบเก่าที่เก็บไว้ใน Access และต้องการย้ายไปยังเครื่องมือการจัดการโครงการสมัยใหม่.

## ทำไมต้องใช้ Aspose.Tasks สำหรับงานนี้?
- **No COM interop** – คุณไม่จำเป็นต้องติดตั้ง Microsoft Project บนเซิร์ฟเวอร์.  
- **Direct DB access** – `MpdSettings` อ่านไฟล์ Access โดยไม่ต้องผ่านขั้นตอนกลาง.  
- **Built‑in conversion** – แปลง **access to xml** และ **export ms project xml** โดยอัตโนมัติ.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วยโค้ดเดียวกัน.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** – ตรวจสอบให้แน่ใจว่าได้ติดตั้ง JDK 8 หรือใหม่กว่า.  
- **Aspose.Tasks for Java Library** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ. ตาม [download link](https://releases.aspose.com/tasks/java/) เพื่อรับไลบรารีและเพิ่มลงใน classpath ของโปรเจกต์ของคุณ.

## นำเข้าแพ็กเกจ
ก่อนอื่น ให้นำเข้าคลาสที่จำเป็นสำหรับการจัดการโครงการและการเชื่อมต่อฐานข้อมูล.

```java
import com.aspose.tasks.MpdSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## วิธี java read access database ด้วย Aspose.Tasks?
ต่อไปนี้เป็นขั้นตอนแบบละเอียด แต่ละขั้นจะอธิบายเป็น เพื่อให้คุณเข้าใจว่ากำลังเกิดอะไรขึ้น.

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีข้อมูล
กำหนดโฟลเดอร์ที่ไฟล์ XML ที่สร้างขึ้นจะถูกบันทึก. แทนที่ตัวแสดงตำแหน่งด้วยเส้นทางจริงของคุณ.

```java
String dataDir = "Your Data Directory";
```

### ขั้นตอนที่ 2: กำหนด MpdSettings
สร้างอินสแตนซ์ `MpdSettings` ที่มี connection string ไปยังฐานข้อมูล Access ของคุณและตัวระบุของโครงการที่ต้องการอ่าน (ที่นี่ `1` หมายถึงบันทึกโครงการแรก).

```java
MpdSettings settings = new MpdSettings(getConnectionString(), 1);
```

> **Pro tip:** หากคุณต้องการ **read ms project access** ข้อมูลสำหรับหลายโครงการ ให้วนลูปผ่าน ID และสร้าง `MpdSettings` ใหม่สำหรับแต่ละรอบ.

### ขั้นตอนที่ 3: โหลดโครงการจากฐานข้อมูล
ส่งอ็อบเจ็กต์ `MpdSettings` ไปยังคอนสตรัคเตอร์ `Project`. Aspose.Tasks จะดึงข้อมูลโครงการโดยตรงจากไฟล์ Access.

```java
Project project = new Project(settings);
```

### ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ
สุดท้าย ส่งออกโครงการที่โหลดเป็นไฟล์ XML. ขั้นตอนนี้ **export ms project xml** เพื่อให้เครื่องมืออื่นสามารถใช้ได้.

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

## ปัญหาทั่วไปและวิธีแก้
| Issue | Solution |
|-------|----------|
| *ข้อผิดพลาดของ connection string* | ตรวจสอบเส้นทางไฟล์ Access และให้แน่ใจว่าได้ติดตั้ง Jet/ACE OLEDB provider บนเครื่อง. |
| *การปฏิเสธสิทธิ์เมื่อบันทึก* | ตรวจสอบให้แน่ใจว่าโฟลเดอร์ `dataDir` มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |
| *โครงการปรากฏว่าไม่มีข้อมูล* | ยืนยันว่ามีการส่ง Project ID ที่ถูกต้องไปยัง `MpdSettings`. ใช้โปรแกรมดูฐานข้อมูลเพื่อตรวจสอบคอลัมน์ `ProjectID`. |

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.Tasks for Java กับระบบฐานข้อมูลอื่น ๆ นอกจาก Microsoft Access ได้หรือไม่?  
A: ใช่, Aspose.Tasks รองรับระบบฐานข้อมูลหลายประเภท เช่น SQL Server, MySQL, และ Oracle.

### Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Tasks for Java หรือไม่?  
A: ใช่, คุณสามารถรับการทดลองใช้ฟรีจาก [here](https://releases.aspose.com/).

### Q: ฉันจะรับการสนับสนุนทางเทคนิคสำหรับ Aspose.Tasks for Java ได้อย่างไร?  
A: คุณสามารถรับการสนับสนุนทางเทคนิคจาก [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q: ฉันต้องการใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Tasks for Java หรือไม่?  
A: คุณอาจต้องการใบอนุญาตชั่วคราวสำหรับคุณสมบัติบางอย่างที่ขั้นสูง. รับได้จาก [here](https://purchase.aspose.com/temporary-license/).

### Q: ฉันสามารถซื้อ Aspose.Tasks for Java ได้จากที่ไหน?  
A: คุณสามารถซื้อ Aspose.Tasks for Java ได้จาก [this link](https://purchase.aspose.com/buy).

---  
**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบกับ:** Aspose.Tasks for Java (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}