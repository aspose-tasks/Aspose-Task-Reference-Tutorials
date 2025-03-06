---
title: การตั้งค่าสำหรับฐานข้อมูลโครงการ Microsoft ใน Aspose.Tasks
linktitle: การตั้งค่าสำหรับฐานข้อมูลโครงการ Microsoft ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดการตั้งค่าฐานข้อมูล Microsoft Project โดยใช้ Aspose.Tasks เพื่อการผสานรวมเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น
weight: 19
url: /th/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าสำหรับฐานข้อมูลโครงการ Microsoft ใน Aspose.Tasks

## การแนะนำ

หากคุณกำลังทำงานกับฐานข้อมูล Microsoft Project ในแอปพลิเคชัน .NET ของคุณโดยใช้ Aspose.Tasks คุณจะต้องกำหนดการตั้งค่าที่จำเป็นเพื่อนำเข้าข้อมูลโครงการได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  Aspose.Tasks สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Tasks จาก[ที่นี่](https://releases.aspose.com/tasks/net/).
2. การเข้าถึงฐานข้อมูลโครงการ Microsoft: คุณควรมีสิทธิ์เข้าถึงฐานข้อมูลโครงการ Microsoft เพื่อนำเข้าข้อมูล

## นำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ของคุณ:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## ขั้นตอนที่ 1: สร้างสตริงการเชื่อมต่อ

สร้างสตริงการเชื่อมต่อกับฐานข้อมูล Microsoft Project ของคุณ นี่คือตัวอย่าง:

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

ตรวจสอบให้แน่ใจว่าได้แทนที่ค่าตัวยึดตำแหน่งด้วยข้อมูลรับรองฐานข้อมูลจริงของคุณ

## ขั้นตอนที่ 2: กำหนดค่า MspDbSettings

 สร้างอินสแตนซ์ของ`MspDbSettings` และระบุสตริงการเชื่อมต่อพร้อมกับ GUID ของโครงการ:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## ขั้นตอนที่ 3: โหลดข้อมูลโครงการ

 ยกตัวอย่าง`Project` วัตถุโดยใช้การตั้งค่าที่กำหนดไว้:

```csharp
var project = new Project(settings);
```

## ขั้นตอนที่ 4: บันทึกข้อมูลโครงการ

บันทึกข้อมูลโครงการที่โหลดลงในไฟล์:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีกำหนดการตั้งค่าสำหรับการเข้าถึงฐานข้อมูล Microsoft Project โดยใช้ Aspose.Tasks สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถนำเข้าข้อมูลโครงการไปยังแอปพลิเคชันของคุณได้อย่างราบรื่น ซึ่งช่วยอำนวยความสะดวกในการจัดการโครงการที่มีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Tasks กับฐานข้อมูล Microsoft Project เวอร์ชันต่างๆ ได้หรือไม่

ตอบ 1: ใช่ Aspose.Tasks รองรับฐานข้อมูล Microsoft Project เวอร์ชันต่างๆ ทำให้มีความยืดหยุ่นในการบูรณาการ

### คำถามที่ 2: ฉันจะแก้ไขปัญหาการเชื่อมต่อกับฐานข้อมูลได้อย่างไร

 A2: ตรวจสอบให้แน่ใจว่าสายอักขระการเชื่อมต่อของคุณได้รับการกำหนดค่าอย่างถูกต้องด้วยข้อมูลประจำตัวและรายละเอียดฐานข้อมูลที่เหมาะสม คุณยังสามารถดูเอกสารประกอบหรือขอการสนับสนุนจาก[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### คำถามที่ 3: Aspose.Tasks มีเวอร์ชันทดลองใช้งานหรือไม่

 A3: ใช่ คุณสามารถเข้าถึงเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันสามารถปรับแต่งสคีมาสำหรับการโต้ตอบกับฐานข้อมูลได้หรือไม่

 A4: ได้ คุณสามารถระบุสคีมาสำหรับ`MspDbSettings` วัตถุตามโครงสร้างฐานข้อมูลของคุณ

### คำถามที่ 5: ฉันจะหาเอกสารโดยละเอียดเพิ่มเติมเกี่ยวกับการใช้ Aspose.Tasks ได้ที่ไหน

 A5: คุณสามารถสำรวจเอกสารประกอบที่ครอบคลุมได้[ที่นี่](https://reference.aspose.com/tasks/net/) สำหรับข้อมูลเชิงลึกโดยละเอียดเกี่ยวกับฟังก์ชันการทำงานของ Aspose.Tasks
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
