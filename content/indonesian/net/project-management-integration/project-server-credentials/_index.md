---
title: Mengelola Kredensial MS Project Server di Aspose.Tasks
linktitle: Mengelola Kredensial Server Proyek di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola kredensial MS Project Server secara lancar dengan Aspose.Tasks untuk .NET. Meningkatkan efisiensi manajemen proyek.
type: docs
weight: 22
url: /id/net/project-management-integration/project-server-credentials/
---
## Perkenalan
Dalam bidang manajemen proyek, koordinasi yang efektif dan komunikasi yang lancar sangat penting untuk keberhasilan pelaksanaan proyek. Aspose.Tasks untuk .NET memberikan solusi komprehensif untuk mengelola kredensial Microsoft Project Server, memungkinkan pengguna mengakses dan memanipulasi data proyek dengan aman. Tutorial ini mempelajari proses pengelolaan kredensial MS Project Server menggunakan Aspose.Tasks untuk .NET, memandu pengguna melalui setiap langkah untuk memastikan pengalaman yang lancar.
## Prasyarat
Sebelum memulai perjalanan mengelola kredensial MS Project Server dengan Aspose.Tasks untuk .NET, pastikan prasyarat berikut terpenuhi:
### 1. Menginstal Aspose.Tasks untuk .NET
 Untuk memulai, unduh dan instal Aspose.Tasks untuk .NET dari yang disediakan[tautan unduhan](https://releases.aspose.com/tasks/net/). Ikuti petunjuk instalasi untuk mengintegrasikan perpustakaan ke dalam lingkungan .NET Anda dengan lancar.
### 2. Akses Kredensial
Kumpulkan kredensial yang diperlukan untuk mengakses MS Project Server. Ini termasuk alamat domain SharePoint, nama pengguna, dan kata sandi yang terkait dengan Project Server.

## Impor Namespace
Dalam proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsi yang disediakan oleh Aspose.Tasks untuk .NET secara efisien.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Langkah 1: Tentukan Jalur Direktori Dokumen
```csharp
String DataDir = "Your Document Directory";
```
## Langkah 2: Tetapkan Alamat Domain SharePoint, Nama Pengguna, dan Kata Sandi
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Langkah 3: Buat Kredensial Server Proyek
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Langkah 4: Muat File Proyek
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Langkah 5: Inisialisasi Manajer Server Proyek
```csharp
var manager = new ProjectServerManager(credentials);
```
## Langkah 6: Buat Proyek Baru
```csharp
manager.CreateNewProject(newProject);
```
## Langkah 7: Ambil Daftar Proyek
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Langkah 8: Ulangi Daftar Proyek
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Kesimpulan
Mengelola kredensial MS Project Server secara efektif adalah hal terpenting untuk manajemen proyek yang efisien. Aspose.Tasks untuk .NET menyederhanakan proses ini dengan menyediakan serangkaian fungsi yang kuat. Dengan mengikuti panduan langkah demi langkah yang diuraikan dalam tutorial ini, pengguna dapat mengintegrasikan Aspose.Tasks untuk .NET ke dalam proyek mereka dengan lancar, memastikan akses yang aman dan manipulasi data proyek.
## FAQ
### T: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi Microsoft Project Server?
J: Aspose.Tasks untuk .NET dirancang agar kompatibel dengan berbagai versi Microsoft Project Server, memastikan keserbagunaan dan fleksibilitas bagi pengguna.
### T: Dapatkah saya mengintegrasikan Aspose.Tasks untuk .NET ke dalam proyek .NET saya yang sudah ada?
J: Ya, Aspose.Tasks untuk .NET dapat diintegrasikan dengan mulus ke dalam proyek .NET yang ada, sehingga memfasilitasi kemampuan manajemen proyek yang efisien.
### T: Apakah Aspose.Tasks untuk .NET menyediakan dukungan untuk mengakses sumber daya proyek?
J: Tentu saja, Aspose.Tasks untuk .NET menawarkan dukungan komprehensif untuk mengakses dan memanipulasi sumber daya proyek, meningkatkan efisiensi manajemen proyek.
### T: Apakah ada opsi lisensi yang tersedia untuk Aspose.Tasks untuk .NET?
J: Ya, Aspose.Tasks untuk .NET menawarkan opsi lisensi yang fleksibel, termasuk lisensi sementara untuk tujuan uji coba dan lisensi penuh untuk penggunaan komersial.
### T: Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.Tasks untuk .NET?
 J: Untuk pertanyaan atau bantuan apa pun mengenai Aspose.Tasks untuk .NET, Anda dapat mengunjungi forum dukungan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).## Kode Sumber Lengkap