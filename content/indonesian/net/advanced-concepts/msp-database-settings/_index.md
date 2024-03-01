---
title: Pengaturan untuk Microsoft Project Database di Aspose.Tasks
linktitle: Pengaturan untuk Microsoft Project Database di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi pengaturan database Microsoft Project menggunakan Aspose.Tasks untuk integrasi yang lancar ke dalam aplikasi .NET.
type: docs
weight: 19
url: /id/net/advanced-concepts/msp-database-settings/
---
## Perkenalan

Jika Anda bekerja dengan database Microsoft Project di aplikasi .NET menggunakan Aspose.Tasks, Anda harus mengonfigurasi pengaturan yang diperlukan untuk mengimpor data proyek dengan lancar. Tutorial ini akan memandu Anda melalui proses langkah demi langkah.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Akses ke Database Microsoft Project: Anda harus memiliki akses ke database Microsoft Project untuk mengimpor data.

## Impor Namespace

Pertama, pastikan Anda mengimpor namespace yang diperlukan ke proyek Anda:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Langkah 1: Buat String Koneksi

Buat string koneksi ke database Microsoft Project Anda. Berikut ini contohnya:

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

Pastikan untuk mengganti nilai placeholder dengan kredensial database Anda yang sebenarnya.

## Langkah 2: Konfigurasikan MspDbSettings

 Buat sebuah contoh dari`MspDbSettings` dan tentukan string koneksi bersama dengan GUID proyek:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Langkah 3: Muat Data Proyek

 Buat contoh a`Project` objek menggunakan pengaturan yang dikonfigurasi:

```csharp
var project = new Project(settings);
```

## Langkah 4: Simpan Data Proyek

Simpan data proyek yang dimuat ke file:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengonfigurasi pengaturan untuk mengakses database Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat mengimpor data proyek ke aplikasi Anda dengan lancar, sehingga memfasilitasi manajemen proyek yang efisien.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Tasks dengan versi database Microsoft Project yang berbeda?

A1: Ya, Aspose.Tasks mendukung berbagai versi database Microsoft Project, memungkinkan fleksibilitas dalam integrasi.

### Q2: Bagaimana cara memecahkan masalah koneksi dengan database?

 A2: Pastikan string koneksi Anda dikonfigurasi dengan benar dengan kredensial dan detail database yang sesuai. Anda juga dapat merujuk ke dokumentasi atau mencari dukungan dari[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

### Q3: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?

 A3: Ya, Anda dapat mengakses versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Q4: Dapatkah saya menyesuaikan skema untuk interaksi database?

 A4: Ya, Anda dapat menentukan skema untuk`MspDbSettings` objek sesuai dengan struktur database Anda.

### Q5: Di mana saya dapat menemukan dokumentasi lebih rinci tentang penggunaan Aspose.Tasks?

 A5: Anda dapat menjelajahi dokumentasi yang komprehensif[Di Sini](https://reference.aspose.com/tasks/net/) untuk wawasan mendetail tentang fungsi Aspose.Tasks.