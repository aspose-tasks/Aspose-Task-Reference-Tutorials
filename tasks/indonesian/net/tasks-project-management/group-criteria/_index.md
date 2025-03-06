---
title: Manipulasi Kriteria Grup Proyek MS di Aspose.Tasks
linktitle: Kriteria Kelompok di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Jelajahi cara memanipulasi file MS Project secara terprogram di .NET menggunakan Aspose.Tasks. Ambil contoh langkah demi langkah informasi kelompok tugas dan kriteria.
weight: 27
url: /id/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulasi Kriteria Grup Proyek MS di Aspose.Tasks

## Perkenalan
Aspose.Tasks untuk .NET adalah API canggih yang memfasilitasi bekerja dengan file Microsoft Project di aplikasi .NET Anda. Baik Anda sedang mengembangkan perangkat lunak manajemen proyek atau perlu memanipulasi data proyek secara terprogram, Aspose.Tasks menawarkan serangkaian fitur lengkap untuk memenuhi kebutuhan Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
### 1. Pengetahuan tentang C# dan .NET Framework
Keakraban dengan bahasa pemrograman C# dan .NET Framework sangat penting untuk memahami dan menerapkan contoh yang diberikan dalam tutorial ini.
### 2. Instalasi Aspose.Tasks untuk .NET
 Pastikan Anda telah menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/net/) dan ikuti petunjuk instalasi yang diberikan.
### 3. Lingkungan Pengembangan Terpadu (IDE)
Miliki IDE seperti Visual Studio yang terinstal di sistem Anda untuk menulis dan mengeksekusi kode C#.

## Impor Namespace
Untuk memulai, impor namespace yang diperlukan dalam kode C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Muat File Proyek Microsoft
Pertama, tentukan jalur ke file Microsoft Project Anda:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Mengganti`"Your Document Directory"` dengan jalur ke file proyek Anda.
## Langkah 2: Ambil Informasi Kelompok Tugas
Selanjutnya, ambil informasi tentang kelompok tugas dalam proyek:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Cuplikan kode ini mencetak jumlah total grup tugas, mengambil grup tugas kedua, namanya, dan jumlah kriteria yang dimilikinya.
## Langkah 3: Ambil Informasi Kriteria Kelompok Tugas
Sekarang, mari kita selidiki rincian kriteria tertentu dalam kelompok tugas:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Segmen ini menampilkan berbagai properti kriteria seperti indeks, bidang, informasi pengelompokan, warna sel, warna font, interval grup, dan titik awal.
## Langkah 4: Ambil Informasi Font Kriteria
Terakhir, dapatkan detail kriteria terkait font:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Langkah ini mencetak nama font, ukuran, gaya, dan apakah kriteria diurutkan dalam urutan menaik atau menurun.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara menggunakan Aspose.Tasks untuk .NET untuk mengambil informasi tentang grup tugas dan kriteria dari file Microsoft Project. Dengan mengikuti panduan langkah demi langkah, Anda dapat bekerja secara efisien dengan data proyek secara terprogram di aplikasi .NET Anda.
## FAQ
### Bisakah Aspose.Tasks menangani file Microsoft Project yang besar?
Aspose.Tasks dioptimalkan untuk menangani file proyek besar secara efisien, memastikan kinerja dan keandalan tinggi.
### Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
Ya, Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai format file.
### Bisakah saya memanipulasi data proyek menggunakan Aspose.Tasks?
Tentu saja, Aspose.Tasks menyediakan fungsionalitas luas untuk memanipulasi data proyek, termasuk tugas, sumber daya, kalender, dan banyak lagi.
### Apakah Aspose.Tasks menawarkan dukungan untuk platform .NET yang berbeda?
Ya, Aspose.Tasks mendukung beberapa platform .NET termasuk .NET Framework, .NET Core, dan .NET Standard.
### Apakah ada forum komunitas untuk Aspose.Tasks di mana saya dapat mencari bantuan?
 Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bertanya, berbagi pengetahuan, dan berkolaborasi dengan pengguna lain.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
