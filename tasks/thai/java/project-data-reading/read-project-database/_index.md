---
date: 2026-10-31
description: เรียนรู้วิธีบันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project
  ด้วย Aspose.Tasks for Java รวมถึงการเชื่อมต่อกับ Project Server การแปลงโครงการเป็น
  HTML และการส่งออกโครงการเป็น XML
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: การอ่านข้อมูลโครงการจากฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks
og_description: บันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks
  for Java เรียนรู้การเชื่อมต่อกับ Project Server การส่งออกเป็น HTML, XML, และ CSV
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: บันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: บันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks
  for Java
url: /th/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks for Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **อ่านฐานข้อมูล Microsoft Project** โดยตรงจาก Microsoft Project Server และจากนั้น **บันทึกโครงการเป็น PDF** ด้วย Aspose.Tasks Java API ไม่ว่าคุณจะต้องการสร้างรายงานที่พิมพ์ได้, ย้ายข้อมูลเก่า, หรือฝังข้อมูลโครงการลงในพอร์ทัลที่กำหนดเอง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การกำหนดค่าเชื่อมต่อ JDBC ไปจนถึงการส่งออกโครงการเป็น PDF, XML หรือ HTML. เมื่อเสร็จสิ้น คุณจะมีโซลูชันพร้อมใช้งานที่ทำงานบนเซิร์ฟเวอร์ Java ใดก็ได้โดยไม่ต้องติดตั้ง Microsoft Project.

## คำตอบอย่างรวดเร็ว
- **Aspose.Tasks ทำอะไร?** ให้ API แบบ pure‑Java สำหรับอ่าน, เขียน และจัดการไฟล์และฐานข้อมูล Microsoft Project.  
- **ต้องติดตั้ง Microsoft Project หรือไม่?** No, Aspose.Tasks works independently of Microsoft Project.  
- **ฐานข้อมูลประเภทใดที่รองรับ?** Microsoft SQL Server, the backend of Project Server.  
- **ฉันสามารถส่งออกเป็นรูปแบบอื่นได้หรือไม่?** Yes—PDF, XML, HTML, CSV, PNG, JPEG, and more.  
- **ข้อกำหนดเบื้องต้นหลักคืออะไร?** JDK 8 หรือใหม่กว่า, ไลบรารี Aspose.Tasks for Java, ไดรเวอร์ SQL Server JDBC, และข้อมูลประจำตัว Project Server ที่ถูกต้อง.

## “อ่านฐานข้อมูล Microsoft Project” คืออะไร?
การอ่านฐานข้อมูล Microsoft Project หมายถึงการเชื่อมต่อกับคลังข้อมูล SQL Server ของ Project Server, ดึงข้อมูลโครงการที่จัดเก็บไว้, และโหลดเข้าสู่วัตถุ `Project` ที่ Aspose.Tasks สามารถจัดการได้ วิธีนี้เหมาะสำหรับการรายงานอัตโนมัติ, การย้ายข้อมูล, หรือการวิเคราะห์แบบกำหนดเอง.

## ทำไมต้องใช้ Aspose.Tasks for Java?
Aspose.Tasks for Java ช่วยให้คุณทำงานกับข้อมูล Microsoft Project ได้โดยไม่ต้องใช้แอปพลิเคชันบนเดสก์ท็อป, มอบโซลูชัน pure‑Java ที่ทำงานบนแพลตฟอร์มใดก็ได้. มันให้โมเดลวัตถุที่ครบถ้วนสำหรับงาน, ทรัพยากร, ปฏิทิน, และฟิลด์กำหนดเอง, และสามารถจัดการโครงการระดับองค์กรขนาดใหญ่ได้อย่างมีประสิทธิภาพ ทำให้เหมาะสำหรับการรายงานอัตโนมัติ, การย้ายข้อมูล, และสถานการณ์การบูรณาการ.

- **ไม่มีการพึ่งพา Microsoft Project** – run on any server or CI environment.  
- **Rich object model** – access tasks, resources, assignments, calendars, and custom fields programmatically.  
- **Multiple export options** – Aspose.Tasks supports exporting to **over 20 file formats**, including PDF, XML, HTML, CSV, PNG, and JPEG, with a single API call.  
- **High performance** – the library can process projects containing **up to 10,000 tasks** in under a minute, and it streams data to avoid loading the entire file into memory.

## ข้อกำหนดเบื้องต้น
1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
2. ไลบรารี Aspose.Tasks for Java เพิ่มเข้าไปใน classpath ของโปรเจกต์ของคุณ.  
3. ข้อมูลประจำตัวการเข้าถึงฐานข้อมูล SQL ของ Project Server (ชื่อเซิร์ฟเวอร์, พอร์ต, ชื่อฐานข้อมูล, ชื่อผู้ใช้, รหัสผ่าน) เพื่อเชื่อมต่อกับ Project Server.  
4. ไดรเวอร์ Microsoft JDBC สำหรับ SQL Server (เช่น `sqljdbc4.jar`).  

## นำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้าคลาสที่คุณต้องการใช้ รายการนี้รวมถึงคลาสหลักของ Aspose.Tasks และยูทิลิตี้มาตรฐานของ Java.

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

## วิธีเชื่อมต่อกับ Project Server
การสร้างการเชื่อมต่อที่เชื่อถือได้เป็นพื้นฐานสำหรับการอ่านข้อมูลโครงการ ตรวจสอบให้แน่ใจว่าอินสแตนซ์ SQL Server สามารถเข้าถึงได้จากโฮสต์ Java ของคุณและบัญชีผู้ใช้ที่ใช้มีสิทธิ์ **SELECT** บนสคีมาของ Project Server คุณควรตรวจสอบความหน่วงของเครือข่ายและกำหนดค่าการตั้งค่า SSL ที่จำเป็นเพื่อให้การสื่อสารปลอดภัย.

## ขั้นตอนที่ 1: ตั้งค่าการเชื่อมต่อฐานข้อมูล
คลาส `MspDbSettings` รวมรายละเอียดการเชื่อมต่อ JDBC ที่จำเป็นสำหรับการเข้าถึงฐานข้อมูล Microsoft Project Server สร้างอินสแตนซ์ `MspDbSettings` ที่เก็บสตริงการเชื่อมต่อ JDBC แล้วแทนค่าตัวแปรตัวอย่างด้วยรายละเอียดเซิร์ฟเวอร์จริงของคุณ.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **เคล็ดลับ:** เก็บสตริงการเชื่อมต่อในไฟล์กำหนดค่าที่ปลอดภัยหรือในตัวแปรสภาพแวดล้อมแทนการเขียนข้อมูลประจำตัวแบบ hard‑coding.

## ขั้นตอนที่ 2: เพิ่มไดรเวอร์ JDBC
โหลดไดรเวอร์ Microsoft SQL Server JDBC ในขณะรันไทม์เพื่อให้ JVM สามารถสื่อสารกับฐานข้อมูลได้.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **คำเตือน:** ตรวจสอบให้แน่ใจว่าเวอร์ชันของไดรเวอร์ตรงกับเวอร์ชันของ SQL Server การใช้ไดรเวอร์ที่ไม่เข้ากันอาจทำให้การเชื่อมต่อล้มเหลว.

## ขั้นตอนที่ 3: อ่านข้อมูลโครงการ
คลาส `Project` แสดงไฟล์ Microsoft Project ที่โหลดเข้าสู่หน่วยความจำ, เปิดเผยงาน, ทรัพยากร, และการมอบหมาย สร้างอ็อบเจกต์ `Project` โดยส่งผ่าน `MspDbSettings` Aspose.Tasks จะดึงข้อมูลโครงการจากฐานข้อมูลโดยอัตโนมัติ.

```java
Project project = new Project(settings);
```

ในขั้นตอนนี้คุณสามารถสำรวจอ็อบเจกต์ `project` — แสดงรายการงาน, ทรัพยากร, หรือแก้ไขฟิลด์ตามต้องการ.

## ขั้นตอนที่ 4: บันทึกโครงการเป็น PDF
enumeration `SaveFileFormat` กำหนดรูปแบบผลลัพธ์สำหรับเมธอด `Project.save` เช่น PDF, XML หรือ HTML ส่งออกโครงการที่โหลดแล้วเป็นรูปแบบไฟล์ที่คุณเลือก ตัวอย่างด้านล่างบันทึกโครงการเป็น **PDF** ซึ่งเหมาะสำหรับรายงานที่ต้องพิมพ์ คุณยังสามารถ **ส่งออกโครงการเป็น XML** หรือ **แปลงโครงการเป็น HTML** โดยเปลี่ยนค่า enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

หากคุณต้องการ XML เพียงแทนที่ `SaveFileFormat.Pdf` ด้วย `SaveFileFormat.Xml`. สำหรับผลลัพธ์ HTML ให้ใช้ `SaveFileFormat.Html`.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุทั่วไป | วิธีแก้ |
|-------|---------------|-----|
| **Connection timeout** | เซิร์ฟเวอร์/พอร์ตผิดหรือไฟร์วอลล์บล็อก | ตรวจสอบที่อยู่เซิร์ฟเวอร์, เปิดพอร์ต 1433, และทดสอบการเชื่อมต่อด้วยโปรแกรมทดสอบ JDBC อย่างง่าย. |
| **Authentication error** | ชื่อผู้ใช้/รหัสผ่านไม่ถูกต้องหรือ SQL Server ไม่ได้ตั้งค่าให้รองรับการตรวจสอบสิทธิ์แบบ SQL | ใช้การล็อกอิน SQL ที่ถูกต้องหรือเปิดใช้งานการตรวจสอบสิทธิ์แบบ mixed‑mode บนเซิร์ฟเวอร์. |
| **Driver not found** | JDBC jar ไม่อยู่ใน classpath | ตรวจสอบให้แน่ใจว่า `addJDBCDriver` ชี้ไปที่ไฟล์ `.jar` ที่ถูกต้องและเส้นทางใช้ backslashes คู่ (`\\`). |
| **Empty project after load** | สิทธิ์ไม่เพียงพอในการอ่านตารางของ Project Server | ให้สิทธิ์ SELECT กับการล็อกอินบนสคีมาของฐานข้อมูล Project Server. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถใช้เพื่ออ่านข้อมูลโครงการจากฐานข้อมูลอื่นนอกจาก Microsoft Project ได้หรือไม่?**  
A: Yes, Aspose.Tasks supports reading project data from XML files, Primavera databases, and other standard project formats.

**Q: Aspose.Tasks รองรับเวอร์ชันต่าง ๆ ของ Microsoft Project หรือไม่?**  
A: Yes, the library works with Microsoft Project 2007 through the latest 2024 releases, ensuring seamless integration across versions.

**Q: ฉันสามารถจัดการข้อมูลโครงการก่อนบันทึกได้หรือไม่?**  
A: Absolutely, you can add, update, or delete tasks, resources, and custom fields using the rich API before exporting.

**Q: Aspose.Tasks รองรับหลายรูปแบบผลลัพธ์หรือไม่?**  
A: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over 20 formats in total.

**Q: ฉันจะหาแหล่งสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Tasks ได้จากที่ไหน?**  
A: For additional help, visit the Aspose.Tasks forum or explore the documentation available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## สรุป
โดยทำตามคู่มือขั้นตอนนี้ คุณจะรู้วิธี **อ่านฐานข้อมูล Microsoft Project**, **บันทึกโครงการเป็น PDF**, และส่งออกเป็นรูปแบบอื่น ๆ ด้วย Aspose.Tasks for Java วิธีนี้ขจัดการพึ่งพา Microsoft Project, ทำให้การรายงานอัตโนมัติเป็นเรื่องง่าย, และเปิดประตูสู่การบูรณาการแบบกำหนดเองที่ทรงพลัง.

---

**อัปเดตล่าสุด:** 2026-10-31  
**ทดสอบด้วย:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีบันทึกโครงการเป็น PDF ด้วย Aspose.Tasks – คู่มือการส่งออก](/tasks/java/project-file-operations/save-as-pdf/)
- [บันทึกโครงการเป็น PDF – แสดงแผ่นงานงานด้วย Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [ส่งออกโครงการเป็น PDF และลดช่องว่างระหว่างรายการงานกับส่วนท้ายใน Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}