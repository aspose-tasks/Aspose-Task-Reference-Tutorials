---
title: Mengonfigurasi Tingkat Skala Waktu Gantt Chart di Aspose.Tasks
linktitle: Mengonfigurasi Tingkat Skala Waktu di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi Aspose.Tasks untuk .NET untuk mengonfigurasi tingkat skala waktu dalam tampilan Gantt Chart Anda untuk visualisasi garis waktu proyek yang tepat. #Aspose.Tugas #Proyek MS
weight: 16
url: /id/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonfigurasi Tingkat Skala Waktu Gantt Chart di Aspose.Tasks

## Perkenalan
Dalam lanskap dinamis manajemen proyek, visualisasi yang efektif sangat penting untuk memahami jadwal dan tenggat waktu. Aspose.Tasks untuk .NET menyediakan seperangkat alat yang canggih, dan dalam tutorial ini, kita akan mempelajari cara mengonfigurasi tingkat skala waktu untuk representasi optimal dalam tampilan Gantt Chart. Ikuti petunjuk langkah demi langkah ini untuk meningkatkan visualisasi proyek Anda.
## Prasyarat
Sebelum mendalami tutorial, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang C# dan .NET.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Lingkungan pengembangan yang disiapkan untuk pengembangan aplikasi .NET.
## Impor Namespace
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Sekarang, mari kita uraikan setiap langkah dari contoh yang diberikan.
## Langkah 1: Inisialisasi Proyek dan Tambahkan Tautan Tugas
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Di sini, kami membuat proyek dan membuat tautan tugas antara "Tugas 1" dan "Tugas 2".
## Langkah 2: Konfigurasikan Tampilan Gantt Chart
```csharp
var view = (GanttChartView)project.DefaultView;
```
Akses tampilan Gantt Chart untuk penyesuaian.
## Langkah 3: Sesuaikan Tingkat Skala Waktu Tengah
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Sesuaikan tingkat skala waktu menengah untuk menampilkan minggu dengan label dan perataan tertentu.
## Langkah 4: Tambahkan Tingkat Skala Waktu Teratas
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Tambahkan tingkat skala waktu teratas untuk mewakili bulan.
## Langkah 5: Sesuaikan Tanggal Tingkat Tengah
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personalisasikan label bulan untuk visualisasi yang lebih baik.
## Langkah 6: Tetapkan Skala Waktu Proyek
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Tentukan skala waktu proyek untuk mengontrol garis waktu keseluruhan.
## Langkah 7: Simpan Proyek dengan Skala Waktu yang Disesuaikan
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Simpan proyek dengan pengaturan skala waktu yang ditentukan.
## Kesimpulan
Kesimpulannya, mengonfigurasi tingkat skala waktu di Aspose.Tasks untuk .NET memungkinkan representasi jadwal proyek yang lebih disesuaikan dan menarik secara visual. Langkah-langkah ini memberdayakan Anda untuk membuat tampilan Gantt Chart yang secara tepat memenuhi kebutuhan manajemen proyek Anda.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks dengan perpustakaan .NET lainnya?
Ya, Aspose.Tasks terintegrasi secara mulus dengan pustaka .NET lainnya, menawarkan fleksibilitas dalam tumpukan pengembangan Anda.
### Apakah lisensi sementara tersedia untuk tujuan pengujian?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk evaluasi.
### Apakah ada opsi penyesuaian tambahan untuk tampilan Gantt Chart?
Tentu saja, Aspose.Tasks menyediakan opsi penyesuaian yang luas untuk tampilan Gantt Chart agar sesuai dengan beragam kebutuhan proyek.
### Bisakah saya merender rentang waktu dalam format berbeda?
Tentu saja, Anda dapat menjelajahi berbagai format dan gaya untuk representasi skala waktu agar paling sesuai dengan konteks proyek Anda.
### Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 Ya, kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
