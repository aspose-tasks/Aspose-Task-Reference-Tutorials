---
title: กำหนดค่าฐานข้อมูล MS Project Primavera ใน Aspose.Tasks
linktitle: การกำหนดการตั้งค่าฐานข้อมูล Primavera ใน Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: เรียนรู้วิธีกำหนดการตั้งค่าฐานข้อมูล MS Project Primavera ใน Aspose.Tasks สำหรับ .NET ได้อย่างง่ายดาย ปรับปรุงงานการจัดการโครงการของคุณ
type: docs
weight: 11
url: /th/net/project-management-integration/primavera-database-settings/
---
## การแนะนำ
คุณพร้อมที่จะควบคุมพลังของ Aspose.Tasks สำหรับ .NET เพื่อกำหนดการตั้งค่าฐานข้อมูล MS Project Primavera ได้อย่างราบรื่นแล้วหรือยัง? ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน แต่ก่อนที่เราจะดำน้ำ มาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการก่อน
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง Aspose.Tasks สำหรับ .NET
 มุ่งหน้าไปที่[ดาวน์โหลด Aspose.Tasks สำหรับ .NET](https://releases.aspose.com/tasks/net/)และคว้าไลบรารี่ Aspose.Tasks เวอร์ชันล่าสุด ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้มาเพื่อตั้งค่าในสภาพแวดล้อม .NET ของคุณ
### 2. เข้าถึงฐานข้อมูล MS Project Primavera
ตรวจสอบให้แน่ใจว่าคุณมีสิทธิ์เข้าถึงฐานข้อมูล MS Project Primavera คุณจะต้องมีข้อมูลประจำตัวที่จำเป็นและรายละเอียดการเชื่อมต่อเพื่อดำเนินการต่อ
### 3. ความรู้พื้นฐานเกี่ยวกับ C# และ .NET Framework
บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และ .NET Framework

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

```
 บรรทัดนี้นำเข้าไฟล์`System.Data.SqlClient` เนมสเปซซึ่งมีคลาสสำหรับการทำงานกับฐานข้อมูล SQL Server ในแอปพลิเคชัน .NET

ตอนนี้คุณได้ตั้งค่าข้อกำหนดเบื้องต้นและนำเข้าเนมสเปซที่จำเป็นแล้ว เรามาแจกแจงโค้ดตัวอย่างที่ให้ไว้สำหรับการกำหนดการตั้งค่าฐานข้อมูล MS Project Primavera โดยใช้ Aspose.Tasks สำหรับ .NET กัน
## ขั้นตอนที่ 1: สร้างวัตถุ SqlConnectionStringBuilder
```csharp
var sb = new SqlConnectionStringBuilder();
sb.DataSource = "192.168.56.3,1433";
sb.Encrypt = true;
sb.TrustServerCertificate = true;
sb.InitialCatalog = "PrimaveraEDB";
sb.NetworkLibrary = "DBMSSOCN";
sb.UserID = "privuser";
sb.Password = "***";
sb.ConnectTimeout = 2; // ข้าม
```
 รหัสนี้จะสร้าง`SqlConnectionStringBuilder`object และกำหนดคุณสมบัติต่างๆ เช่น`DataSource`, `Encrypt`, `InitialCatalog`, `UserID`, `Password`ฯลฯ เพื่อกำหนดค่าสตริงการเชื่อมต่อสำหรับฐานข้อมูล Primavera
## ขั้นตอนที่ 2: เริ่มต้นวัตถุ PrimaveraDbSettings
```csharp
var settings = new PrimaveraDbSettings(sb.ConnectionString, 4502);
```
 ที่นี่เราเริ่มต้นอินสแตนซ์ใหม่ของ`PrimaveraDbSettings` คลาสโดยส่งสตริงการเชื่อมต่อและรหัสโปรเจ็กต์ (ในกรณีนี้`4502`) เป็นพารามิเตอร์
## ขั้นตอนที่ 3: อ่านโครงการจากฐานข้อมูล
```csharp
var project = new Project(settings);
```
 บรรทัดนี้สร้างใหม่`Project` คัดค้านโดยผ่าน`settings` วัตถุที่เราสร้างไว้ก่อนหน้านี้ สร้างการเชื่อมต่อกับฐานข้อมูล Primavera และอ่านโครงการด้วย UID ที่ระบุ (`4502`).
## ขั้นตอนที่ 4: แสดง UID ของโครงการ
```csharp
Console.WriteLine("Project UID to read: " + settings.ProjectId);
```
สุดท้ายนี้ รหัสนี้จะพิมพ์ UID ของโครงการที่กำลังอ่านไปยังคอนโซล

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีกำหนดการตั้งค่าฐานข้อมูล MS Project Primavera โดยใช้ Aspose.Tasks สำหรับ .NET ด้วยความรู้นี้ คุณสามารถรวม Aspose.Tasks เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ และปรับปรุงงานการจัดการโครงการ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Tasks สำหรับ .NET กับซอฟต์แวร์การจัดการโครงการอื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET รองรับการทำงานร่วมกับซอฟต์แวร์การจัดการโครงการต่างๆ รวมถึง MS Project, Primavera และอื่นๆ อีกมากมาย
### ถาม: Aspose.Tasks สำหรับ .NET เข้ากันได้กับ .NET Core เวอร์ชันล่าสุดหรือไม่
ตอบ: ใช่ Aspose.Tasks สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม .NET Core และ .NET Framework
### ถาม: Aspose.Tasks for .NET ให้การสนับสนุนโซลูชันการจัดการโครงการบนระบบคลาวด์หรือไม่
ตอบ: Aspose.Tasks สำหรับ .NET มุ่งเน้นไปที่โซลูชันการจัดการโครงการในองค์กรเป็นหลัก แต่สามารถปรับให้เข้ากับสภาพแวดล้อมคลาวด์บางประเภทได้ด้วยการกำหนดค่าที่เหมาะสม
### ถาม: ฉันสามารถจัดการข้อมูลโปรเจ็กต์โดยทางโปรแกรมโดยใช้ Aspose.Tasks สำหรับ .NET ได้หรือไม่
ตอบ: แน่นอน! Aspose.Tasks สำหรับ .NET มีชุด API มากมายสำหรับการอ่าน เขียน และจัดการข้อมูลโครงการในรูปแบบต่างๆ
### ถาม: มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับผู้ใช้ Aspose.Tasks สำหรับผู้ใช้ .NET หรือไม่
 ตอบ: ได้ คุณสามารถเยี่ยมชมได้[ฟอรั่ม Aspose.Tasks](https://forum.aspose.com/c/tasks/15)สำหรับการสนับสนุนและความช่วยเหลือจากชุมชนในประเด็นหรือข้อสงสัยใด ๆ ที่คุณอาจมี ## ซอร์สโค้ดที่สมบูรณ์