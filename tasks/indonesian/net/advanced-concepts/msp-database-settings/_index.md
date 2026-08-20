---
date: 2026-03-14
description: Pelajari cara menentukan skema basis data untuk basis data Microsoft
  Project menggunakan Aspose.Tasks, serta cara mengimpor data proyek ke dalam aplikasi
  .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tentukan skema basis data untuk Project DB dengan Aspose.Tasks
url: /id/net/advanced-concepts/msp-database-settings/
weight: 19
---

-03-14"

**Tested With:** Aspose.Tasks 24.12 for .NET => "**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET"

**Author:** Aspose => "**Penulis:** Aspose"

Then closing shortcodes.

Now produce final content with all translations.

Make sure to keep shortcodes unchanged.

Let's assemble.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengaturan Database Microsoft Project di Aspose.Tasks

## Pendahuluan

Jika Anda bekerja dengan database Microsoft Project dalam aplikasi .NET menggunakan Aspose.Tasks, Anda perlu **menentukan skema database** dan mengonfigurasi pengaturan yang diperlukan untuk **mengimpor proyek** secara mulus. Tutorial ini akan memandu Anda melalui proses langkah demi langkah, menunjukkan **cara mengonfigurasi detail koneksi**, **membuat string koneksi .NET**, dan akhirnya **menyimpan proyek sebagai MPP**.

## Jawaban Cepat
- **Apa tujuan utama?** Menentukan skema database dan mengimpor database Project ke dalam aplikasi .NET.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk .NET.  
- **Bagaimana cara terhubung ke Project Server?** Dengan membuat string koneksi SQL yang tepat dan menggunakan `MspDbSettings`.  
- **Format file apa yang dihasilkan?** File MPP yang disimpan dengan `SaveFileFormat.Mpp`.  
- **Apakah saya dapat mengubah nama skema?** Ya, atur properti `Schema` pada `MspDbSettings`.

## Cara menentukan skema database untuk Project DB

Memahami mengapa Anda mungkin perlu **menentukan skema database** sangat penting. Di banyak lingkungan perusahaan, database Project Server berada di bawah skema khusus (misalnya, `dbo`, `psdata`). Dengan secara eksplisit mengatur skema, Anda memastikan Aspose.Tasks menanyakan tabel yang tepat, mencegah kesalahan runtime dan menjamin impor data yang akurat.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks dari [here](https://releases.aspose.com/tasks/net/).  
2. Akses ke Database Microsoft Project: Anda harus memiliki akses ke database Microsoft Project untuk mengimpor data darinya.  

## Impor Namespace

Pertama, pastikan Anda mengimpor namespace yang diperlukan ke dalam proyek Anda:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Langkah 1: Buat String Koneksi

Bangun string koneksi ke database Microsoft Project Anda. Di sinilah Anda **membuat string koneksi .NET** dan juga menentukan cara **terhubung ke Project Server**.

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

> **Tips Pro:** Periksa kembali nilai `DataSource` dan `InitialCatalog`; nilai tersebut harus sesuai dengan alamat server Anda dan nama database yang dipublikasikan.

## Langkah 2: Konfigurasikan MspDbSettings

Buat sebuah instance `MspDbSettings`, berikan string koneksi, dan **tentukan skema database** dengan mengatur properti `Schema`. Ini memberi tahu Aspose.Tasks skema mana yang harus dipertanyakan.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Di sini kami juga menyediakan GUID proyek yang mengidentifikasi proyek spesifik yang ingin Anda muat.

## Langkah 3: Muat Data Proyek

Instansiasi objek `Project` menggunakan pengaturan yang telah dikonfigurasi. Langkah ini secara efektif **cara mengimpor data proyek** dari database ke dalam objek .NET.

```csharp
var project = new Project(settings);
```

## Langkah 4: Simpan Data Proyek

Akhirnya, simpan proyek yang dimuat ke file MPP di disk. Ini mendemonstrasikan **menyimpan proyek sebagai MPP** menggunakan API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Setelah menjalankan kode, Anda akan menemukan file `ImportProjectDataFromDatabase_out.mpp` di direktori output, siap dibuka di Microsoft Project.

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara **menentukan skema database** untuk database Microsoft Project, **mengonfigurasi koneksi**, **mengimpor data proyek**, dan **menyimpan proyek sebagai MPP** menggunakan Aspose.Tasks untuk .NET. Langkah-langkah ini memungkinkan integrasi data Project Server yang mulus ke dalam aplikasi kustom Anda, membantu Anda membangun solusi manajemen proyek yang kuat.

## Pertanyaan yang Sering Diajukan

### Q1: Apakah saya dapat menggunakan Aspose.Tasks dengan versi berbeda dari database Microsoft Project?
A1: Ya, Aspose.Tasks mendukung berbagai versi database Microsoft Project, memungkinkan fleksibilitas dalam integrasi.

### Q2: Bagaimana saya dapat memecahkan masalah koneksi dengan database?
A2: Pastikan string koneksi Anda dikonfigurasi dengan benar dengan kredensial dan detail database yang tepat. Anda juga dapat merujuk ke dokumentasi atau mencari dukungan di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks?
A3: Ya, Anda dapat mengakses versi percobaan gratis dari [here](https://releases.aspose.com/).

### Q4: Apakah saya dapat menyesuaikan skema untuk interaksi database?
A4: Ya, Anda dapat menentukan skema untuk objek `MspDbSettings` sesuai dengan struktur database Anda.

### Q5: Di mana saya dapat menemukan dokumentasi lebih detail tentang penggunaan Aspose.Tasks?
A5: Anda dapat menjelajahi dokumentasi komprehensif [here](https://reference.aspose.com/tasks/net/) untuk wawasan mendetail tentang fungsionalitas Aspose.Tasks.

**Q: Apakah pendekatan ini bekerja dengan database Azure SQL?**  
**A:** Tentu saja. Cukup sesuaikan `DataSource` ke nama server Azure Anda dan **pastikan pengaturan TLS/SSL diaktifkan**.

**Q: Bagaimana cara menangani database Project yang besar tanpa kehabisan waktu?**  
**A:** Tingkatkan nilai `ConnectTimeout` dalam string koneksi dan pertimbangkan memuat proyek secara **batch** jika diperlukan.

---

**Terakhir Diperbarui:** 2026-03-14  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}