---
title: Menguasai Tampilan Gantt Chart di Aspose.Tasks
linktitle: Tampilan Gantt Chart di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengkustomisasi tampilan bagan Gantt di file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Panduan langkah demi langkah untuk manajemen proyek yang efisien.
type: docs
weight: 22
url: /id/net/tasks-project-management/gantt-chart-views/
---
## Perkenalan
Bagan Gantt adalah alat canggih yang digunakan dalam manajemen proyek untuk memvisualisasikan tugas, garis waktu, dan ketergantungan. Aspose.Tasks untuk .NET memberikan kemampuan yang kuat untuk bekerja dengan tampilan bagan Gantt di file Microsoft Project. Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk memanipulasi tampilan bagan Gantt, menyesuaikan tampilannya, dan menyimpannya sebagai file PDF.
## Prasyarat
Sebelum melanjutkan, pastikan Anda memiliki prasyarat berikut:
### 1. Instalasi Aspose.Tasks untuk .NET
 Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/net/)dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi[Di Sini](https://reference.aspose.com/tasks/net/).
### 2. File Proyek Microsoft
Siapkan file Microsoft Project (`Project2.mpp`) yang akan Anda gunakan untuk bekerja dengan tampilan bagan Gantt.
### 3. Pengetahuan Dasar C# dan .NET Framework
Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang bahasa pemrograman C# dan kerangka .NET.
## Impor Namespace
Sebelum Anda mulai bekerja dengan tampilan bagan Gantt di Aspose.Tasks, Anda perlu mengimpor namespace yang diperlukan ke dalam kode C# Anda. Inilah cara Anda melakukannya:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Mari kita pecahkan kode contoh yang diberikan menjadi beberapa langkah dan jelaskan setiap langkah secara detail:
## Langkah 1: Muat File Proyek
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Langkah ini melibatkan memuat file Microsoft Project (`Project2.mpp` ) menjadi sebuah instance dari`Project` kelas.
## Langkah 2: Tetapkan Tanggal Status
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Di sini, kami menetapkan tanggal status proyek ke tanggal mulainya.
## Langkah 3: Akses Tampilan Gantt Chart
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Kami mengakses tampilan bagan Gantt dari proyek. Aspose.Tasks memungkinkan mengakses tampilan seperti Gantt Chart, Diagram Jaringan, dan Penggunaan Tugas.
## Langkah 4: Sesuaikan Tampilan Gantt Chart
Sekarang, mari sesuaikan berbagai aspek tampilan bagan Gantt:
### Atur Pembulatan Bar
```csharp
view.BarRounding = false;
```
Ini menentukan apakah batang pada diagram Gantt akan membulat ke hari terdekat.
### Tetapkan Ukuran Batang
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Ini menentukan ketinggian batang Gantt pada grafik.
### Sembunyikan Rollup Bar
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Menentukan apakah bilah rollup akan disembunyikan saat memperluas tugas ringkasan.
### Atur Warna Waktu Non-Kerja
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Mendefinisikan warna untuk waktu tidak bekerja pada bagan Gantt.
### Gulung Gantt Bar
```csharp
view.RollUpGanttBars = true;
```
Tentukan apakah batang pada bagan Gantt harus digulung.
### Tampilkan Pemisahan Bar
```csharp
view.ShowBarSplits = true;
```
Menentukan apakah pembagian tugas pada bagan Gantt harus ditampilkan.
### menunjukkan gambar
```csharp
view.ShowDrawings = true;
```
Menentukan apakah gambar pada bagan Gantt harus ditampilkan.
### Persentase Ukuran Skala Waktu
```csharp
view.TimescaleSizePercentage = 10;
```
Menetapkan persentase untuk menyesuaikan jarak antar unit pada tingkat skala waktu.
## Langkah 5: Simpan Tampilan Gantt Chart sebagai PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Terakhir, kami menyimpan tampilan bagan Gantt yang disesuaikan sebagai file PDF.
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara bekerja dengan tampilan bagan Gantt di Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat memanipulasi dan menyesuaikan bagan Gantt secara efisien sesuai dengan kebutuhan proyek Anda.
## FAQ
### T: Dapatkah saya menyesuaikan tampilan bilah bagan Gantt lebih lanjut?
J: Ya, Aspose.Tasks menyediakan opsi luas untuk menyesuaikan tampilan bilah bagan Gantt, termasuk warna, bentuk, dan ukuran.
### T: Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### T: Dapatkah saya mengekspor tampilan bagan Gantt ke format selain PDF?
J: Tentu saja, Aspose.Tasks mendukung ekspor tampilan bagan Gantt ke berbagai format, termasuk PNG, JPEG, dan XPS.
### T: Apakah Aspose.Tasks menawarkan dukungan untuk algoritma penjadwalan proyek yang kompleks?
J: Ya, Aspose.Tasks menyediakan algoritma penjadwalan tingkat lanjut untuk menangani jadwal proyek yang kompleks secara efektif.
### T: Apakah ada forum komunitas tempat saya dapat mencari bantuan atau berbagi pengalaman saya dengan Aspose.Tasks?
 A: Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk terlibat dengan pengguna lain, mengajukan pertanyaan, dan menemukan solusi atas pertanyaan Anda.