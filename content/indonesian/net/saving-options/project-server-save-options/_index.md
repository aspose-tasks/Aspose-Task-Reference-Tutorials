---
title: Server Simpan Opsi Proyek MS untuk Aspose.Tasks
linktitle: Opsi Penyimpanan Server Proyek untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan opsi Microsoft Project untuk Aspose.Tasks menggunakan integrasi Project Server. Tingkatkan alur kerja manajemen proyek Anda.
type: docs
weight: 16
url: /id/net/saving-options/project-server-save-options/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menyimpan opsi Microsoft Project untuk Aspose.Tasks menggunakan Project Server. Aspose.Tasks adalah .NET API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram. Dengan memanfaatkan kemampuan Project Server, kami dapat mengintegrasikan Aspose.Tasks dengan lancar ke dalam alur kerja manajemen proyek kami. Tutorial ini akan memandu Anda melalui proses langkah demi langkah.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET: Instal Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
   
2. Akses ke Project Server: Anda memerlukan kredensial akses dan URL instans Project Server Anda. Jika Anda tidak memilikinya, Anda dapat memperoleh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
3. File Microsoft Project: Siapkan file Microsoft Project (.mpp) yang ingin Anda simpan menggunakan Aspose.Tasks.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Langkah 1: Inisialisasi Proyek dan Kredensial
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Pastikan Anda menggantinya`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,Dan`Password` dengan nilai-nilai Anda yang sebenarnya.
## Langkah 2: Buat Manajer Server Proyek
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Langkah 3: Tentukan Opsi Simpan
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Sesuaikan`ProjectGuid`, `ProjectName`, `Timeout` ,Dan`PollingInterval` sesuai dengan kebutuhan Anda.
## Langkah 4: Simpan Proyek ke Server
```csharp
manager.CreateNewProject(project, options);
```
Ini akan menyimpan proyek ke Project Server dengan opsi yang ditentukan.

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyimpan opsi Microsoft Project untuk Aspose.Tasks menggunakan integrasi Project Server. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menggabungkan Aspose.Tasks ke dalam alur kerja manajemen proyek Anda, sehingga meningkatkan efisiensi dan produktivitas.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks dengan versi Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda bisa mendapatkan Aspose.Tasks versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Apakah Aspose.Tasks mendukung multi-threading?
J: Ya, Aspose.Tasks dirancang agar aman untuk thread, memungkinkan akses bersamaan ke data proyek.
### T: Bisakah saya mengkustomisasi opsi penyimpanan saat menggunakan integrasi Project Server?
J: Ya, Anda dapat menyesuaikan opsi penyimpanan seperti nama proyek, batas waktu, dan interval polling agar sesuai dengan kebutuhan Anda.
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?
 J: Anda dapat menemukan dukungan dan bantuan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).