---
title: Pengaturan Basis Data di Aspose.Tasks
linktitle: Pengaturan Basis Data di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengimpor proyek dari database Primavera menggunakan Aspose.Tasks untuk .NET. Dapatkan panduan langkah demi langkah dalam tutorial komprehensif ini.
weight: 29
url: /id/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengaturan Basis Data di Aspose.Tasks

## Perkenalan

Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project di aplikasi .NET mereka. Dalam tutorial ini, kami akan fokus mengimpor proyek dari database Primavera menggunakan Aspose.Tasks.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Visual Studio diinstal pada sistem Anda.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
- Akses ke database Primavera, beserta izin yang diperlukan.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Namespace ini menyediakan akses ke kelas dan metode yang diperlukan untuk bekerja dengan Aspose.Tasks untuk .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Sekarang, mari kita uraikan kode contoh yang diberikan menjadi beberapa langkah:

## Langkah 1: Tentukan String Koneksi

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Pada langkah ini, kami menentukan string koneksi untuk terhubung ke database Primavera. Pastikan Anda menggantinya`DataDir` dengan direktori tempat file database Anda berada.

## Langkah 2: Buat Pengaturan Basis Data

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Di sini, kita membuat sebuah instance dari`PrimaveraDbSettings` kelas, meneruskan string koneksi dan ID proyek sebagai parameter. Sesuaikan ID proyek sesuai kebutuhan Anda.

## Langkah 3: Tetapkan Nama Invarian Penyedia

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Tentukan nama invarian penyedia. Dalam contoh ini, kami menggunakan SQLite, namun Anda dapat mengubahnya berdasarkan penyedia database Anda.

## Langkah 4: Muat Proyek

```csharp
var project = new Project(settings);
```

 Buat yang baru`Project` objek, meneruskan pengaturan database sebagai parameter.

## Langkah 5: Simpan Proyek

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Terakhir, simpan proyek ke lokasi yang diinginkan dengan format file yang ditentukan.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengimpor proyek dari database Primavera menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengintegrasikan fungsionalitas impor proyek dengan lancar ke dalam aplikasi .NET Anda.

## FAQ

### Q1: Bisakah saya mengimpor proyek dari penyedia database berbeda menggunakan Aspose.Tasks untuk .NET?

A1: Ya, Anda dapat mengimpor proyek dari berbagai penyedia database dengan menyesuaikan string koneksi dan nama invarian penyedia.

### Q2: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?

 A2: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?

 A3: Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

 A4: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).

### Q5: Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.Tasks untuk .NET?

 A5: Jika Anda ingin mengevaluasi fungsionalitas penuh perpustakaan, Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
