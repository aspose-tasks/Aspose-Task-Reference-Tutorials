---
title: Ekstrak Informasi Proyek MS di Aspose.Tasks
linktitle: Mengekstrak Informasi Proyek di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengekstrak informasi MS Project dengan mudah menggunakan Aspose.Tasks untuk .NET. Selami tutorial komprehensif kami.
type: docs
weight: 20
url: /id/net/project-management-integration/project-information/
---
## Perkenalan
Apakah Anda ingin mengekstrak informasi dari file Microsoft Project secara efisien menggunakan Aspose.Tasks untuk .NET? Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah. Namun sebelum kita mendalami detail penerapannya, pertama-tama pastikan Anda memiliki semua yang Anda perlukan.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
### 1. Aspose.Tugas untuk .NET
 Pastikan Anda telah menginstal perpustakaan Aspose.Tasks untuk .NET. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Aspose.Tugas untuk situs web .NET](https://releases.aspose.com/tasks/net/).
### 2. Kredensial untuk SharePoint
Anda memerlukan kredensial untuk mengakses SharePoint tempat file MS Project Anda disimpan. Pastikan Anda memiliki informasi berikut:
- Alamat Domain SharePoint
- Nama belakang
- Kata sandi
## Mengimpor Namespace
Setelah prasyarat Anda diselesaikan, sekarang saatnya mengimpor namespace yang diperlukan ke dalam proyek Anda.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Sekarang mari kita uraikan proses mengekstraksi informasi MS Project menjadi beberapa langkah.
## Langkah 1: Berikan Kredensial
Pertama, Anda perlu memberikan kredensial SharePoint Anda untuk mengakses Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Langkah 2: Inisialisasi Manajer Server Proyek
 Selanjutnya, inisialisasi a`ProjectServerManager` misalnya dengan kredensial yang diberikan.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Langkah 3: Ambil Daftar Proyek
Sekarang, Anda dapat mengambil daftar proyek dari Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Langkah 4: Cetak Informasi Proyek
Terakhir, ulangi daftar proyek dan cetak informasinya.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengekstrak informasi MS Project menggunakan Aspose.Tasks untuk .NET. Dengan pengetahuan ini, kini Anda dapat mengintegrasikan fungsi ini ke dalam aplikasi .NET Anda dengan lancar.
## FAQ
### Q1: Dapatkah saya menggunakan Aspose.Tasks untuk .NET dengan versi Microsoft Project apa pun?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi Microsoft Project, termasuk 2003, 2007, 2010, 2013, 2016, dan 2019.
### Q2: Apakah Aspose.Tasks untuk .NET kompatibel dengan platform Windows dan Linux?
J: Ya, Aspose.Tasks untuk .NET kompatibel dengan platform Windows dan Linux, sehingga serbaguna untuk lingkungan pengembangan yang berbeda.
### Q3: Bisakah saya mengekstrak dependensi tugas menggunakan Aspose.Tasks untuk .NET?
J: Tentu saja! Aspose.Tasks untuk .NET menyediakan fungsionalitas yang kuat untuk mengekstrak tidak hanya informasi proyek dasar tetapi juga dependensi tugas dan detail rumit lainnya.
### Q4: Apakah Aspose.Tasks untuk .NET menawarkan dukungan teknis?
 J: Ya, Anda bisa mendapatkan dukungan teknis untuk Aspose.Tasks untuk .NET melalui[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15), tempat Anda dapat mengajukan pertanyaan dan mencari bantuan dari para ahli.
### Q5: Bisakah saya mencoba Aspose.Tasks untuk .NET sebelum membelinya?
 J: Tentu saja! Anda dapat memanfaatkan uji coba gratis Aspose.Tasks untuk .NET dari[halaman rilis](https://releases.aspose.com/), memungkinkan Anda menjelajahi fitur-fiturnya sebelum membuat keputusan pembelian.