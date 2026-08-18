---
date: 2026-02-18
description: เรียนรู้วิธีบันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project
  ด้วย Aspose.Tasks for Java รวมถึงการเชื่อมต่อกับ Project Server แปลงโครงการเป็น
  HTML และส่งออกโครงการเป็น XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: บันทึกโครงการเป็น PDF และอ่านฐานข้อมูลโครงการด้วย Aspose.Tasks สำหรับ Java
url: /th/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกโครงการเป็น PDF และอ่านฐานข้อมูล Microsoft Project ด้วย Aspose.Tasks สำหรับ Java

## บทนำ
ในบทเรียนนี้คุณจะได้ค้นพบวิธี **อ่านฐานข้อมูล Microsoft Project** โดยตรงจาก Microsoft Project Server แล้ว **บันทึกโครงการเป็น PDF** ด้วย Aspose.Tasks Java API ไม่ว่าคุณจะต้องการสร้างรายงาน, ย้ายข้อมูล, หรือรวมข้อมูลโครงการเข้ากับแอปพลิเคชันของคุณเอง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน — ตั้งค่าการเชื่อมต่อฐานข้อมูลจนถึงการส่งออกโครงการเป็น PDF, XML หรือ HTML. เมื่อเสร็จสิ้น คุณจะมีโซลูชันที่พร้อมใช้งานในระดับการผลิตซึ่งทำงานได้โดยไม่ต้องติดตั้ง Microsoft Project บนเครื่องโฮสต์.

## คำตอบด่วน
- **Aspose.Tasks ทำอะไร?** มันให้ API แบบ pure‑Java เพื่ออ่าน, เขียน, และจัดการไฟล์และฐานข้อมูล Microsoft Project.  
- **ต้องติดตั้ง Microsoft Project หรือไม่?** ไม่, Aspose.Tasks ทำงานโดยอิสระจาก Microsoft Project.  
- **ประเภทฐานข้อมูลที่รองรับคืออะไร?** Microsoft SQL Server (ฐานข้อมูลเบื้องหลังของ Project Server).  
- **ฉันสามารถส่งออกเป็นรูปแบบอื่นได้หรือไม่?** ใช่, นอกจาก PDF คุณสามารถบันทึกเป็น XML, HTML, CSV, และอื่น ๆ.  
- **ข้อกำหนดเบื้องต้นหลักคืออะไร?** JDK, ไลบรารี Aspose.Tasks สำหรับ Java, ไดรเวอร์ JDBC ของ SQL Server, และข้อมูลรับรองเพื่อ **เชื่อมต่อกับ Project Server**.

## อะไรคือ “อ่านฐานข้อมูล Microsoft Project”?
การอ่านฐานข้อมูล Microsoft Project หมายถึงการเชื่อมต่อไปยังคลังข้อมูล SQL Server ของ Project Server, ดึงข้อมูลโครงการที่จัดเก็บไว้, และโหลดเข้าไปในอ็อบเจกต์ `Project` ที่ Aspose.Tasks สามารถจัดการได้ วิธีนี้เหมาะสำหรับการสร้างรายงานอัตโนมัติ, การย้ายข้อมูล, หรือการวิเคราะห์แบบกำหนดเอง.

## ทำไมต้องใช้ Aspose.Tasks สำหรับ Java?
- **ไม่มีการพึ่งพา Microsoft Project** – ทำงานบนเซิร์ฟเวอร์หรือสภาพแวดล้อม CI ใดก็ได้.  
- **โมเดลอ็อบเจกต์ที่ครบถ้วน** – เข้าถึงงาน, ทรัพยากร, การมอบหมาย, ปฏิทิน, และฟิลด์กำหนดเองโดยโปรแกรม.  
- **ตัวเลือกการส่งออกหลายรูปแบบ** – PDF, XML, HTML, PNG ฯลฯ ด้วยการเรียก API เพียงครั้งเดียว.  
- **ประสิทธิภาพสูง** – ปรับให้เหมาะกับโครงการระดับองค์กรขนาดใหญ่.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, โปรดตรวจสอบว่าคุณมี:

1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
2. ไลบรารี Aspose.Tasks สำหรับ Java ที่เพิ่มลงใน classpath ของโปรเจคของคุณ.  
3. ข้อมูลรับรองการเข้าถึงฐานข้อมูล SQL ของ Project Server (ชื่อเซิร์ฟเวอร์, พอร์ต, ชื่อฐานข้อมูล, ชื่อผู้ใช้, รหัสผ่าน) **เพื่อเชื่อมต่อกับ Project Server**.  
4. ไดรเวอร์ Microsoft JDBC สำหรับ SQL Server (เช่น `sqljdbc4.jar`).  

## นำเข้าแพ็กเกจ
ก่อนอื่นให้ทำการนำเข้าคลาสที่คุณต้องการใช้ รายการนี้รวมถึงคลาสหลักของ Aspose.Tasks และยูทิลิตี้มาตรฐานของ Java.

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
การสร้างการเชื่อมต่อที่เชื่อถือได้เป็นพื้นฐานสำคัญสำหรับการอ่านข้อมูลโครงการ ตรวจสอบให้แน่ใจว่าอินสแตนซ์ SQL Server สามารถเข้าถึงได้จากโฮสต์ Java ของคุณและว่าบัญชีผู้ใช้ที่ใช้มีสิทธิ **SELECT** บนสคีมาของ Project Server.

## ขั้นตอนที่ 1: ตั้งค่าการเชื่อมต่อฐานข้อมูล
สร้างอินสแตนซ์ `MspDbSettings` ที่เก็บสตริงการเชื่อมต่อ JDBC. แทนค่าตัวแปรตำแหน่งเก็บด้วยรายละเอียดเซิร์ฟเวอร์จริงของคุณ.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **เคล็ดลับมืออาชีพ:** เก็บสตริงการเชื่อมต่อในไฟล์การกำหนดค่าที่ปลอดภัยหรือในตัวแปรสภาพแวดล้อม แทนการเขียนข้อมูลรับรองแบบฮาร์ดโค้ด.

## ขั้นตอนที่ 2: เพิ่มไดรเวอร์ JDBC
โหลดไดรเวอร์ Microsoft SQL Server JDBC ในระหว่างการทำงานเพื่อให้ JVM สามารถสื่อสารกับฐานข้อมูลได้.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **คำเตือน:** ตรวจสอบให้แน่ใจว่าเวอร์ชันของไดรเวอร์ตรงกับเวอร์ชันของ SQL Server ของคุณ การใช้ไดรเวอร์ที่ไม่เข้ากันอาจทำให้การเชื่อมต่อล้มเหลว.

## ขั้นตอนที่ 3: อ่านข้อมูลโครงการ
สร้างอ็อบเจกต์ `Project` โดยส่งผ่าน `MspDbSettings`. Aspose.Tasks จะดึงข้อมูลโครงการจากฐานข้อมูลโดยอัตโนมัติ.

```java
Project project = new Project(settings);
```

ในขั้นตอนนี้คุณสามารถสำรวจอ็อบเจกต์ `project` — รายการงาน, ทรัพยากร, หรือแก้ไขฟิลด์ตามที่ต้องการ.

## ขั้นตอนที่ 4: บันทึกโครงการเป็น PDF
ส่งออกโครงการที่โหลดแล้วไปยังรูปแบบไฟล์ที่คุณเลือก ตัวอย่างด้านล่างบันทึกโครงการเป็น **PDF**, ซึ่งเหมาะสำหรับรายงานที่ต้องพิมพ์ คุณยังสามารถ **ส่งออกโครงการเป็น XML** หรือ **แปลงโครงการเป็น HTML** ได้โดยการเปลี่ยนค่า enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

หากคุณต้องการ XML เพียงแทนที่ `SaveFileFormat.Pdf` ด้วย `SaveFileFormat.Xml`. สำหรับผลลัพธ์เป็น HTML ให้ใช้ `SaveFileFormat.Html`.

## ปัญหาที่พบบ่อยและวิธีแก้ไข
| ปัญหา | สาเหตุทั่วไป | วิธีแก้ |
|-------|---------------|-----|
| **Connection timeout** | เซิร์ฟเวอร์/พอร์ตผิดหรือไฟร์วอลล์บล็อก | ตรวจสอบที่อยู่เซิร์ฟเวอร์, เปิดพอร์ต 1433, และทดสอบการเชื่อมต่อด้วยโปรแกรมทดสอบ JDBC อย่างง่าย. |
| **Authentication error** | ชื่อผู้ใช้/รหัสผ่านไม่ถูกต้องหรือ SQL Server ไม่ได้ตั้งค่าให้รองรับการตรวจสอบแบบ SQL | ใช้ล็อกอิน SQL ที่ถูกต้องหรือเปิดใช้งานการตรวจสอบแบบ mixed‑mode บนเซิร์ฟเวอร์. |
| **Driver not found** | ไฟล์ JAR ของ JDBC ไม่อยู่ใน classpath | ตรวจสอบให้แน่ใจว่า `addJDBCDriver` ชี้ไปยังไฟล์ `.jar` ที่ถูกต้องและเส้นทางใช้เครื่องหมายแบ็กสแลชคู่ (`\\`). |
| **Empty project after load** | สิทธิไม่เพียงพอในการอ่านตารางของ Project Server | ให้สิทธิ SELECT กับล็อกอินบนสคีมาของฐานข้อมูล Project Server. |

## คำถามที่พบบ่อย

**Q: Aspose.Tasks สามารถใช้เพื่ออ่านข้อมูลโครงการจากฐานข้อมูลอื่น ๆ นอกจาก Microsoft Project ได้หรือไม่?**  
A: ใช่, Aspose.Tasks รองรับการอ่านข้อมูลโครงการจากแหล่งต่าง ๆ รวมถึงไฟล์ XML, Primavera, และฐานข้อมูล Microsoft Project.

**Q: Aspose.Tasks เข้ากันได้กับเวอร์ชันต่าง ๆ ของ Microsoft Project หรือไม่?**  
A: ใช่, Aspose.Tasks ถูกออกแบบให้ทำงานกับหลายเวอร์ชันของ Microsoft Project, ทำให้การบูรณาการเป็นไปอย่างราบรื่น.

**Q: ฉันสามารถจัดการข้อมูลโครงการก่อนบันทึกได้หรือไม่?**  
A: แน่นอน, Aspose.Tasks มี API ที่ครบถ้วนสำหรับการเพิ่มงาน, ปรับปรุงทรัพยากร, และตั้งค่าคุณสมบัติโครงการก่อนการส่งออก.

**Q: Aspose.Tasks รองรับหลายรูปแบบการส่งออกหรือไม่?**  
A: ใช่, คุณสามารถบันทึกโครงการเป็น PDF, XML, HTML, CSV, PNG, JPEG, และรูปแบบอื่น ๆ อีกมากมาย.

**Q: จะหาแหล่งสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Tasks ได้จากที่ไหน?**  
A: สำหรับความช่วยเหลือเพิ่มเติม, เยี่ยมชมฟอรั่ม Aspose.Tasks หรือสำรวจเอกสารที่มีบนเว็บไซต์ [here](https://forum.aspose.com/c/tasks/15).

## สรุป
โดยทำตามคู่มือขั้นตอน‑โดย‑ขั้นตอนนี้, คุณจะรู้วิธี **อ่านฐานข้อมูล Microsoft Project**, **บันทึกโครงการเป็น PDF**, และส่งออกเป็นรูปแบบอื่น ๆ ด้วย Aspose.Tasks สำหรับ Java วิธีการนี้ขจัดการพึ่งพา Microsoft Project, ทำให้การสร้างรายงานอัตโนมัติเป็นเรื่องง่าย, และเปิดประตูสู่การบูรณาการแบบกำหนดเองที่ทรงพลัง.

---

**อัปเดตล่าสุด:** 2026-02-18  
**ทดสอบกับ:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}