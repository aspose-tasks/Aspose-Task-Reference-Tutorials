---
title: Konfigurasikan Opsi Tampilan Proyek MS di Aspose.Tasks
linktitle: Konfigurasikan Opsi Tampilan Proyek di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi opsi tampilan MS Project secara terprogram menggunakan Aspose.Tasks untuk .NET. Sesuaikan tampilan proyek Anda dengan mudah.
type: docs
weight: 17
url: /id/net/project-management-integration/project-display-options/
---
## Perkenalan
Microsoft Project menawarkan sejumlah besar opsi tampilan untuk menyesuaikan tampilan proyek Anda. Aspose.Tasks untuk .NET menyediakan kerangka kerja yang kuat untuk memanipulasi opsi ini secara terprogram. Dalam tutorial ini, kita akan mempelajari cara mengonfigurasi opsi tampilan MS Project menggunakan Aspose.Tasks.
## Prasyarat
Sebelum mendalami tutorial, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: Siapkan file MS Project (.mpp) yang valid untuk menerapkan opsi tampilan.
3. Pengetahuan Dasar C#: Diperlukan keakraban dengan bahasa pemrograman C#.

## Mengimpor Namespace
Pertama, pastikan untuk mengimpor namespace yang diperlukan ke dalam kode C# Anda:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Langkah 1: Muat File Proyek
 Muat file MS Project menggunakan`Project` kelas yang disediakan oleh Aspose.Tugas:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Langkah 2: Konfigurasikan Opsi Tampilan
Sekarang, mari konfigurasikan berbagai opsi tampilan yang tersedia di MS Project:
### Nonaktifkan Peringatan Jadwal Tugas
Untuk menonaktifkan peringatan konflik penjadwalan dengan tugas yang dijadwalkan secara manual (tersedia untuk Project 2010 dan yang lebih baru):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Tambahkan Spasi Sebelum Label
Atur untuk menambahkan spasi sebelum nilai angka dan singkatan waktu:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Konfigurasikan Tampilan Label untuk Satuan Waktu
Sesuaikan tampilan satuan waktu yang berbeda:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Tampilkan Tugas Ringkasan Proyek
Tampilkan informasi ringkasan tentang keseluruhan proyek dalam satu baris:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Aktifkan Saran Jadwal Tugas
Izinkan menampilkan saran untuk konflik penjadwalan dengan tugas yang dijadwalkan secara manual:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Garis bawahi Hyperlink
Atur untuk menggarisbawahi hyperlink dalam proyek:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Langkah 3: Simpan Proyek
Terakhir, simpan proyek dengan opsi tampilan yang diterapkan:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonfigurasi opsi tampilan MS Project menggunakan Aspose.Tasks untuk .NET. Dengan kemampuan ini, Anda dapat secara efisien menyesuaikan tampilan file proyek Anda secara terprogram.
## FAQ
### T: Dapatkah saya menerapkan opsi tampilan ini hanya untuk tugas tertentu?
J: Ya, Anda dapat secara selektif menerapkan opsi tampilan ke masing-masing tugas menggunakan Aspose.Tasks API.
### T: Apakah opsi tampilan ini memengaruhi data proyek yang mendasarinya?
J: Tidak, opsi ini hanya mengubah representasi visual proyek dan tidak mengubah data yang mendasarinya.
### T: Apakah opsi tampilan ini kompatibel dengan semua versi Microsoft Project?
J: Tidak, beberapa opsi mungkin spesifik untuk versi MS Project tertentu. Lihat dokumentasi untuk detail kompatibilitas.
### T: Dapatkah saya mengembalikan opsi tampilan ke pengaturan default?
J: Ya, Anda dapat mengatur ulang opsi tampilan ke nilai defaultnya menggunakan Aspose.Tasks API.
### T: Apakah ada batasan dalam menyesuaikan opsi tampilan secara terprogram?
J: Meskipun Aspose.Tasks menyediakan kemampuan penyesuaian yang luas, opsi tampilan tertentu mungkin tidak dapat diakses secara terprogram karena keterbatasan dalam format file MS Project.