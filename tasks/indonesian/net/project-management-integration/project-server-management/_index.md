---
title: Mengelola MS Project Server dengan Aspose.Tasks
linktitle: Mengelola Server Proyek dengan Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Buka kunci manajemen MS Project Server yang lancar dengan Aspose.Tasks untuk .NET. Otomatiskan tugas proyek dengan mudah.
weight: 23
url: /id/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengelola MS Project Server dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola MS Project Server menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram, memungkinkan integrasi dan manipulasi data proyek tanpa hambatan.
## Prasyarat
Sebelum kita mendalami pengelolaan MS Project Server dengan Aspose.Tasks, pastikan Anda telah menyiapkan prasyarat berikut:
1. Microsoft Project Server: Anda memerlukan akses ke instans Microsoft Project Server tempat Anda memiliki hak administratif atau setidaknya izin untuk membuat dan mengelola proyek.
2.  Aspose.Tasks untuk .NET Library: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/tasks/net/).
3. Kredensial: Dapatkan kredensial yang diperlukan untuk mengautentikasi dengan instans MS Project Server Anda. Ini biasanya mencakup nama pengguna dan kata sandi.
## Impor Namespace
Sebelum memulai, pastikan Anda telah mengimpor namespace yang diperlukan dalam kode C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Langkah 1: Siapkan Kredensial Otentikasi
Pertama, Anda perlu menyiapkan kredensial autentikasi untuk menyambung ke instans MS Project Server Anda. Ini termasuk alamat domain, nama pengguna, dan kata sandi.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Langkah 2: Muat Proyek
Selanjutnya, muat file MS Project yang ingin Anda kelola menggunakan Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Langkah 3: Buat Manajer Server Proyek
 Buat contoh a`ProjectServerManager` objek menggunakan kredensial yang ditentukan sebelumnya.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Langkah 4: Tentukan Opsi Simpan
Tentukan opsi penyimpanan spesifik untuk proyek Anda. Misalnya, Anda dapat menetapkan batas waktu untuk pengoperasian.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Langkah 5: Buat atau Perbarui Proyek
Terakhir, buat atau perbarui proyek di MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Selamat! Anda telah berhasil mengelola MS Project Server menggunakan Aspose.Tasks untuk .NET.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara mengelola MS Project Server secara terprogram menggunakan Aspose.Tasks untuk .NET. Dengan langkah-langkah yang disediakan, Anda dapat mengintegrasikan Aspose.Tasks dengan lancar ke dalam aplikasi .NET Anda untuk mengotomatiskan tugas manajemen proyek di MS Project Server.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project Server?
J: Aspose.Tasks mendukung integrasi dengan berbagai versi Microsoft Project Server, memastikan kompatibilitas di berbagai lingkungan.
### T: Dapatkah saya melakukan operasi massal pada proyek menggunakan Aspose.Tasks?
J: Ya, Aspose.Tasks memungkinkan Anda melakukan operasi massal seperti membuat, memperbarui, dan menghapus proyek di MS Project Server.
### T: Apakah Aspose.Tasks menyediakan dukungan untuk penjadwalan proyek dan manajemen sumber daya?
J: Tentu saja, Aspose.Tasks menawarkan dukungan komprehensif untuk penjadwalan proyek, alokasi sumber daya, dan fungsi manajemen tugas.
### T: Apakah mungkin untuk mengotomatiskan tugas pelaporan dengan Aspose.Tasks?
J: Ya, Aspose.Tasks memungkinkan Anda mengotomatiskan pembuatan laporan khusus berdasarkan data proyek, memfasilitasi pemantauan dan analisis proyek secara efisien.
### T: Dapatkah saya mencoba Aspose.Tasks sebelum membelinya?
 J: Ya, Anda dapat menjelajahi kemampuan Aspose.Tasks dengan mengakses uji coba gratis dari[situs web](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
