---
date: 2026-03-14
description: เรียนรู้วิธีกำหนดสคีมาฐานข้อมูลสำหรับฐานข้อมูล Microsoft Project ด้วย
  Aspose.Tasks และวิธีนำเข้าข้อมูลโครงการเข้าสู่แอปพลิเคชัน .NET
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: กำหนดสคีมาฐานข้อมูลสำหรับ Project DB ด้วย Aspose.Tasks
url: /th/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าสำหรับฐานข้อมูล Microsoft Project ใน Aspose.Tasks

## บทนำ

หากคุณกำลังทำงานกับฐานข้อมูล Microsoft Project ในแอปพลิเคชัน .NET ของคุณโดยใช้ Aspose.Tasks คุณจะต้อง **ระบุสคีมาของฐานข้อมูล** และกำหนดค่าการตั้งค่าที่จำเป็นเพื่อ **นำเข้าข้อมูลโครงการ** อย่างราบรื่น บทเรียนนี้จะนำคุณผ่านกระบวนการทีละขั้นตอน แสดงให้คุณเห็น **วิธีกำหนดค่าการเชื่อมต่อ** รายละเอียด, **สร้างสตริงการเชื่อมต่อ .NET**, และสุดท้าย **บันทึกโครงการเป็น MPP**.

## คำตอบด่วน
- **เป้าหมายหลักคืออะไร?** เพื่อระบุสคีมาของฐานข้อมูลและนำเข้าฐานข้อมูล Project ไปยังแอป .NET.  
- **ต้องใช้ไลบรารีใด?** Aspose.Tasks สำหรับ .NET.  
- **ฉันจะเชื่อมต่อกับ Project Server อย่างไร?** โดยสร้างสตริงการเชื่อมต่อ SQL ที่เหมาะสมและใช้ `MspDbSettings`.  
- **รูปแบบไฟล์ที่สร้างคืออะไร?** ไฟล์ MPP ที่บันทึกด้วย `SaveFileFormat.Mpp`.  
- **ฉันสามารถเปลี่ยนชื่อสคีม่าได้หรือไม่?** ได้ โดยตั้งค่าคุณสมบัติ `Schema` บน `MspDbSettings`.

## วิธีระบุสคีมาของฐานข้อมูลสำหรับ Project DB

การเข้าใจว่าทำไมคุณอาจต้อง **ระบุสคีมของฐานข้อมูล** จึงเป็นสิ่งสำคัญ ในหลายสภาพแวดล้อมองค์กร ฐานข้อมูล Project Server จะอยู่ภายใต้สคีมาที่กำหนดเอง (เช่น `dbo`, `psdata`). โดยการตั้งค่าสคีมาชัดเจน คุณจะทำให้ Aspose.Tasks คิวรีตารางที่ถูกต้อง ป้องกันข้อผิดพลาดขณะทำงานและรับประกันการนำเข้าข้อมูลที่แม่นยำ.

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก [here](https://releases.aspose.com/tasks/net/).  
2. การเข้าถึงฐานข้อมูล Microsoft Project: คุณควรมีการเข้าถึงฐานข้อมูล Microsoft Project เพื่อทำการนำเข้าข้อมูล.

## นำเข้า Namespaces

ก่อนอื่น ให้แน่ใจว่าคุณได้นำเข้า namespaces ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## ขั้นตอนที่ 1: สร้างสตริงการเชื่อมต่อ

สร้างสตริงการเชื่อมต่อไปยังฐานข้อมูล Microsoft Project ของคุณ ที่นี่คุณจะ **สร้างสตริงการเชื่อมต่อ .NET** และกำหนดวิธี **เชื่อมต่อกับ Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **เคล็ดลับ:** ตรวจสอบค่า `DataSource` และ `InitialCatalog` อีกครั้ง; ค่าต้องตรงกับที่อยู่ของเซิร์ฟเวอร์ของคุณและชื่อฐานข้อมูลที่เผยแพร่.

## ขั้นตอนที่ 2: กำหนดค่า MspDbSettings

สร้างอินสแตนซ์ของ `MspDbSettings` ส่งสตริงการเชื่อมต่อและ **ระบุสคีมของฐานข้อมูล** โดยตั้งค่าคุณสมบัติ `Schema` ซึ่งบอก Aspose.Tasks ว่าจะคิวรีสคีม่าใด.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

ที่นี่เรายังให้ค่า GUID ของโครงการที่ระบุโครงการเฉพาะที่คุณต้องการโหลด.

## ขั้นตอนที่ 3: โหลดข้อมูลโครงการ

สร้างอ็อบเจกต์ `Project` ด้วยการตั้งค่าที่กำหนดไว้ ขั้นตอนนี้ทำให้ **การนำเข้าข้อมูลโครงการ** จากฐานข้อมูลสู่วัตถุ .NET เป็นไปได้อย่างมีประสิทธิภาพ.

```csharp
var project = new Project(settings);
```

## ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ

สุดท้าย บันทึกโครงการที่โหลดแล้วลงไฟล์ MPP บนดิสก์ ซึ่งแสดงให้เห็น **การบันทึกโครงการเป็น MPP** ด้วย API ของ Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

หลังจากรันโค้ด คุณจะพบไฟล์ `ImportProjectDataFromDatabase_out.mpp` ในไดเรกทอรีผลลัพธ์ พร้อมเปิดใน Microsoft Project.

## สรุป

ในบทเรียนนี้ คุณได้เรียนรู้วิธี **ระบุสคีมของฐานข้อมูล** สำหรับฐานข้อมูล Microsoft Project, **กำหนดค่าการเชื่อมต่อ**, **นำเข้าข้อมูลโครงการ**, และ **บันทึกโครงการเป็น MPP** ด้วย Aspose.Tasks สำหรับ .NET ขั้นตอนเหล่านี้ทำให้การรวมข้อมูล Project Server เข้ากับแอปพลิเคชันของคุณเป็นไปอย่างราบรื่น ช่วยให้คุณสร้างโซลูชันการจัดการโครงการที่แข็งแกร่งได้

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ Aspose.Tasks กับเวอร์ชันต่าง ๆ ของฐานข้อมูล Microsoft Project ได้หรือไม่?

A1: ได้, Aspose.Tasks รองรับเวอร์ชันต่าง ๆ ของฐานข้อมูล Microsoft Project ทำให้มีความยืดหยุ่นในการรวมระบบ.

### Q2: ฉันจะแก้ไขปัญหาการเชื่อมต่อกับฐานข้อมูลอย่างไร?

A2: ตรวจสอบให้แน่ใจว่าสตริงการเชื่อมต่อของคุณตั้งค่าอย่างถูกต้องพร้อมข้อมูลรับรองและรายละเอียดฐานข้อมูลที่เหมาะสม คุณยังสามารถอ้างอิงเอกสารหรือขอความช่วยเหลือจาก [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: มีเวอร์ชันทดลองสำหรับ Aspose.Tasks หรือไม่?

A3: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีได้จาก [here](https://releases.aspose.com/).

### Q4: ฉันสามารถปรับแต่งสคีมาสำหรับการโต้ตอบกับฐานข้อมูลได้หรือไม่?

A4: ได้, คุณสามารถระบุสคีมาสำหรับอ็อบเจกต์ `MspDbSettings` ตามโครงสร้างฐานข้อมูลของคุณ.

### Q5: ฉันจะหาเอกสารรายละเอียดเพิ่มเติมเกี่ยวกับการใช้ Aspose.Tasks ได้จากที่ไหน?

A5: คุณสามารถสำรวจเอกสารที่ครอบคลุมได้ [here](https://reference.aspose.com/tasks/net/) เพื่อรับข้อมูลเชิงลึกเกี่ยวกับฟังก์ชันของ Aspose.Tasks.

**Q: วิธีนี้ทำงานกับฐานข้อมูล Azure SQL หรือไม่?**  
A: แน่นอน เพียงปรับค่า `DataSource` ให้เป็นชื่อเซิร์ฟเวอร์ Azure ของคุณและตรวจสอบให้เปิดการตั้งค่า TLS/SSL.

**Q: ฉันจะจัดการกับฐานข้อมูล Project ขนาดใหญ่โดยไม่ให้หมดเวลาได้อย่างไร?**  
A: เพิ่มค่า `ConnectTimeout` ในสตริงการเชื่อมต่อและพิจารณาโหลดโครงการเป็นชุดหากจำเป็น.

---

**อัปเดตล่าสุด:** 2026-03-14  
**ทดสอบด้วย:** Aspose.Tasks 24.12 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}