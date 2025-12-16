---
date: 2025-12-13
description: เรียนรู้วิธีอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks สำหรับ
  Java คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ดและแนวปฏิบัติที่ดีที่สุด
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: อ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **อ่านฐานข้อมูล Microsoft Project** โดยตรงจาก Microsoft Project Server ด้วย Aspose.Tasks Java API ไม่ว่าคุณจะต้องการสร้างรายงาน, ย้ายข้อมูล, หรือบูรณาการข้อมูลโครงการเข้ากับแอปพลิเคชันของคุณเอง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การตั้งค่าการเชื่อมต่อฐานข้อมูลจนถึงการส่งออกโครงการเป็น XML เมื่อเสร็จสิ้นคุณจะมีโซลูชันที่พร้อมใช้งานในระดับผลิตที่ทำงานได้โดยไม่ต้องติดตั้ง Microsoft Project บนเครื่องโฮสต์

##ำตอบสั้น
- **Aspose.Tasks ทำอะไร?** ให้ API แบบ pure‑Java สำหรับอ่าน, เขียน, และจัดการไฟล์และฐานข้อมูล Microsoft Project  
- **ต้องติดตั้ง Microsoft Project ไหม?** ไม่จำเป็น Aspose.Tasks ทำงานอิสระจาก Microsoft Project  
- **รองรับประเภทฐานข้อมูลใด?** Microsoft SQL Server (แบ็กเอนด์ของ Project Server)  
- **สามารถส่งออกเป็นรูปแบบอื่นได้ไหม?** ได้ นอกจาก XML ยังสามารถบันทึกเป็น PDF, HTML, CSV และอื่น ๆ  
- **ข้อกำหนดเบื้องต้นคืออะไร?** JDK, ไลบรารี Aspose.Tasks สำหรับ Java, และไดรเวอร์ JDBC ของ SQL Server

## “อ่านฐานข้อมูล Microsoft Project” คืออะไร?
การอ่านฐานข้อมูล Microsoft Project หมายถึงการเชื่อมต่อกับคลังข้อมูล SQL Server ของ Project Server, ดึงข้อมูลโครงการที่จัดเก็บไว้, และโหลดเข้าสู่วัตถุ `Project` ที่ Aspose.Tasks สามารถจัดการได้ วิธีนี้เหมาะสำหรับการสร้างรายงานอัตโนมัติ, การย้ายข้อมูล, หรือการวิเคราะห์แบบกำหนดเอง

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
- **ไม่มีการพึ่งพา Microsoft Project** – สามารถรันบนเซิร์ฟเวอร์หรือสภาพแวดล้อม CI ใดก็ได้  
- **โมเดลออบเจ็กต์ที่ครอบคลุม** – เข้าถึงงาน, ทรัพยากร, การมอบหมาย, ปฏิทิน, และฟิลด์กำหนดเองโดยโปรแกรม  
- **ตัวเลือกการส่งออกหลายรูปแบบ** – XML, PDF, HTML, PNG ฯลฯ ด้วยการเรียก API เพียงครั้งเดียว  
- **ประสิทธิภาพสูง** – ปรับให้ทำงานได้ดีสำหรับโครงการระดับองค์กรขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้ตรวจสอบว่าคุณมี:

1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า)  
2. ไลบรารี Aspose.Tasks สำหรับ Java ที่เพิ่มเข้าไปใน classpath ของโปรเจกต์  
3. ข้อมูลรับรองการเข้าถึงฐานข้อมูล SQL ของ Project Server (ชื่อเซิร์ฟเวอร์, พอร์ต, ชื่อฐานข้อมูล, ชื่อผู้ใช้, รหัสผ่าน)  
4. ไดรเวอร์ Microsoft JDBC สำหรับ SQL Server (เช่น `sqljdbc4.jar`)

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น รายการนี้รวมคลาสหลักของ Aspose.Tasks และยูทิลิตี้มาตรฐานของ Java

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## ขั้นตอนที่ 1: ตั้งค่าการเชื่อมต่อฐานข้อมูล
สร้างอินสแตนซ์ `MspDbSettings` ที่เก็บสตริงการเชื่อมต่อ JDBC แทนค่าตัวแปรตำแหน่งที่เก็บด้วยข้อมูลเซิร์ฟเวอร์ของคุณจริง

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **เคล็ดลับ:** เก็บสตริงการเชื่อมต่อในไฟล์กำหนดค่าที่ปลอดภัยหรือในตัวแปรสภาพแวดล้อม แทนการฝังข้อมูลรับรองโดยตรงในโค้ด

## ขั้นตอนที่ 2: เพิ่มไดรเวอร์ JDBC
โหลดไดรเวอร์ Microsoft SQL Server JDBC ในขณะรันไทม์เพื่อให้ JVM สามารถสื่อสารกับฐานข้อมูลได้

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **คำเตือน:** ตรวจสอบให้แน่ใจว่าเวอร์ชันของไดรเวอร์ตรงกับเวอร์ชันของ SQL Server ของคุณ การใช้ไดรเวอร์ที่ไม่เข้ากันอาจทำให้การเชื่อมต่อล้มเหลว

## ขั้นตอนที่ 3: อ่านข้อมูลโครงการ
สร้างออบเจ็กต์ `Project` โดยส่ง `MspDbSettings` เข้าไป Aspose.Tasks จะดึงข้อมูลโครงการจากฐานข้อมูลโดยอัตโนมัติ

```java
Project project = new Project(settings);
```

ในขั้นตอนนี้คุณสามารถสำรวจออบเจ็กต์ `project` — รายการงาน, ทรัพยากร, หรือแก้ไขฟิลด์ตามต้องการ

## ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ
ส่งออกโครงการที่โหลดแล้วเป็นไฟล์รูปแบบที่คุณต้องการ ตัวอย่างด้านล่างบันทึกโครงการเป็น XML ซึ่งสามารถนำเข้า Microsoft Project หรือประมวลผลต่อได้

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

คุณสามารถเปลี่ยน `SaveFileFormat.Xml` เป็น `Pdf`, `Html`, `Csv` ฯลฯ ตามความต้องการของการรายงาน

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุทั่วไป | วิธีแก้ |
|-------|--------------|----------|
| **Connection timeout** | เซิร์ฟเวอร์/พอร์ตผิดหรือไฟร์วอลล์บล็อก | ตรวจสอบที่อยู่เซิร์ฟเวอร์, เปิดพอร์ต 1433, และทดสอบการเชื่อมต่อด้วยโปรแกรม JDBC อย่างง่าย |
| **Authentication error** | ชื่อผู้ใช้/รหัสผ่านไม่ถูกต้อง หรือ SQL Server ไม่ได้ตั้งค่าให้รับการตรวจสอบแบบ SQL | ใช้ล็อกอิน SQL ที่ถูกต้องหรือเปิดการตรวจสอบแบบ mixed‑mode บนเซิร์ฟเวอร์ |
| **Driver not found** | ไฟล์ JAR ของ JDBC ไม่อยู่ใน classpath | ตรวจสอบให้ `addJDBCDriver` ชี้ไปที่ไฟล์ `.jar` ที่ถูกต้องและใช้เครื่องหมาย backslash คู่ (`\\`) ในพาธ |
| **Empty project after load** | สิทธิ์ไม่เพียงพอในการอ่านตารางของ Project Server | ให้สิทธิ์ SELECT กับสคีมาฐานข้อมูล Project Server แก่ผู้ใช้ที่ใช้เชื่อมต่อ |

## คำถามที่พบบ่อย

**ถาม: Aspose.Tasks สามารถใช้เพื่ออ่านข้อมูลโครงการจากฐานข้อมูลอื่นนอกจาก Microsoft Project ได้หรือไม่?**  
ตอบ: ได้ Aspose.Tasks รองรับการอ่านข้อมูลโครงการจากแหล่งต่าง ๆ รวมถึงไฟล์ XML, Primavera, และฐานข้อมูล Microsoft Project

**ถาม: Aspose.Tasks รองรับเวอร์ชันของ Microsoft Project ต่าง ๆ หรือไม่?**  
ตอบ: ใช่ Aspose.Tasks ถูกออกแบบให้ทำงานร่วมกับหลายเวอร์ชันของ Microsoft Project เพื่อให้การบูรณาการเป็นไปอย่างราบรื่น

**ถาม: ฉันสามารถแก้ไขข้อมูลโครงการก่อนบันทึกได้หรือไม่?**  
ตอบ: แน่นอน Aspose.Tasks มี API ที่ครอบคลุมสำหรับการเพิ่มงาน, ปรับปรุงทรัพยากร, และตั้งค่าคุณสมบัติโครงการก่อนส่งออก

**ถาม: Aspose.Tasks รองรับรูปแบบผลลัพธ์หลายรูปแบบหรือไม่?**  
ตอบ: ใช่ คุณสามารถบันทึกโครงการเป็น XML, PDF, HTML, CSV, PNG, JPEG และอื่น ๆ อีกมาก

**ถาม: จะหาแหล่งสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Tasks ได้จากที่ไหน?**  
ตอบ: สำหรับความช่วยเหลือเพิ่มเติม ให้เยี่ยมชมฟอรั่ม Aspose.Tasks หรือดูเอกสารที่เว็บไซต์ [ที่นี่](https://forum.aspose.com/c/tasks/15)

## สรุป
โดยทำตามคู่มือขั้นตอน‑โดยขั้นตอนนี้ คุณจะรู้วิธี **อ่านฐานข้อมูล Microsoft Project** ด้วย Aspose.Tasks สำหรับ Java, จัดการข้อมูลโดยโปรแกรม, และส่งออกเป็นรูปแบบที่ต้องการ วิธีนี้ช่วยขจัดการพึ่งพา Microsoft Project, ทำให้การรายงานอัตโนมัติง่ายขึ้น, และเปิดประตูสู่การบูรณาการแบบกำหนดเองที่ทรงพลัง

---

**อัปเดตล่าสุด:** 2025-12-13  
**ทดสอบกับ:** Aspose.Tasks for Java 24.5 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
