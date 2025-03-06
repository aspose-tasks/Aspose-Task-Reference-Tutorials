---
title: Mengekstrak Informasi Tugas Berulang di Aspose.Tasks
linktitle: Mengekstrak Informasi Tugas Berulang di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengekstrak informasi tugas berulang dari file MS Project menggunakan Aspose.Tasks untuk .NET. Integrasi yang mudah untuk pengembang .NET.
weight: 13
url: /id/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengekstrak Informasi Tugas Berulang di Aspose.Tasks

## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project di aplikasi .NET mereka. Dalam tutorial ini, kita akan mempelajari cara mengekstrak informasi tugas berulang dari file MS Project menggunakan Aspose.Tasks.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Pemahaman dasar bahasa pemrograman C#.
2. Visual Studio diinstal pada sistem Anda.
3.  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
## Impor Namespace
Untuk memulai, impor namespace yang diperlukan dalam kode C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Sekarang, mari kita bagi contoh ini menjadi beberapa langkah:
## Langkah 1: Siapkan jalur file proyek
```csharp
String DataDir = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan path ke file MS Project Anda.
## Langkah 2: Muat file Proyek MS
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Baris ini menginisialisasi yang baru`Project` objek dengan memuat file MS Project yang ditentukan oleh jalur.
## Langkah 3: Baca informasi tugas yang berulang
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Akses dan tampilkan informasi tugas berulang
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Lanjutkan menampilkan informasi tugas berulang lainnya sesuai kebutuhan
}
```
Perulangan ini mengulangi semua tugas dalam proyek dan memeriksa apakah setiap tugas memiliki informasi berulang yang terkait dengannya. Jika ya, ia mengambil dan menampilkan berbagai properti tugas berulang, seperti tanggal mulai, durasi, tanggal akhir, dll.
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengekstrak informasi tugas berulang dari file MS Project menggunakan Aspose.Tasks untuk .NET. Dengan pengetahuan ini, kini Anda dapat mengintegrasikan fungsi ini ke dalam aplikasi .NET Anda untuk bekerja dengan tugas berulang dengan lebih efisien.
## FAQ
### T: Bisakah saya mengubah informasi tugas berulang menggunakan Aspose.Tasks untuk .NET?
J: Ya, Anda dapat mengubah informasi tugas berulang secara terprogram menggunakan API yang disediakan.
### T: Apakah Aspose.Tasks mendukung format file proyek lain selain MS Project?
A: Ya, Aspose.Tasks mendukung berbagai format file proyek seperti MPP, XML, dan CSV.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?
 A: Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).
### T: Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Tasks untuk .NET?
 J: Anda bisa mendapatkan dukungan teknis dari forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
