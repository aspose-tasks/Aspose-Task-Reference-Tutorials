---
title: Menguasai Tampilan Garis Waktu Proyek di Aspose.Tasks
linktitle: Menyesuaikan Tampilan Garis Waktu di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Kuasai Aspose.Tasks untuk .NET dalam menyesuaikan tampilan garis waktu. Tingkatkan manajemen proyek Anda dengan garis waktu yang menarik secara visual dan disesuaikan dengan kebutuhan proyek Anda.
type: docs
weight: 13
url: /id/net/text-view-configuration/timeline-views/
---
## Perkenalan
Membuat tampilan garis waktu yang menarik secara visual dan informatif sangat penting untuk manajemen proyek yang efektif. Aspose.Tasks untuk .NET memberikan solusi tangguh untuk menyesuaikan tampilan garis waktu, memungkinkan Anda menyesuaikan tampilan tugas sesuai dengan kebutuhan spesifik proyek Anda. Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menggunakan Aspose.Tasks untuk membuat dan menyesuaikan tampilan garis waktu dengan mudah.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang pemrograman C# dan .NET.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Jika tidak, unduh[Di Sini](https://releases.aspose.com/tasks/net/).
- Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.
## Impor Namespace
Pastikan Anda mengimpor namespace yang diperlukan dalam kode C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Langkah 1: Inisialisasi Proyek dan Tampilan Timeline
Mulailah dengan menginisialisasi proyek baru dan tampilan garis waktu:
```csharp
var project = new Project();
var view = new TimelineView();
```
## Langkah 2: Atur Properti Tampilan Garis Waktu
Sesuaikan tampilan garis waktu dengan mengatur berbagai properti:
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## Langkah 3: Tampilkan Detail Tampilan Garis Waktu
Ambil informasi tentang tampilan garis waktu:
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## Langkah 4: Tambahkan Tampilan ke Proyek
Tambahkan tampilan garis waktu yang disesuaikan ke proyek:
```csharp
project.Views.Add(view);
```
## Langkah 5: Tambahkan Data Uji ke Proyek
Isi proyek dengan contoh tugas:
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## Langkah 6: Simpan Proyek sebagai PDF
Simpan proyek dengan tampilan garis waktu yang disesuaikan sebagai file PDF:
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## Kesimpulan
Selamat! Anda telah berhasil mengkustomisasi tampilan garis waktu menggunakan Aspose.Tasks untuk .NET. Pustaka canggih ini menyederhanakan proses pembuatan jadwal proyek yang menarik secara visual, sehingga meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan kerangka .NET lainnya?
Ya, Aspose.Tasks mendukung berbagai kerangka .NET, memastikan kompatibilitas dengan lingkungan pengembangan Anda.
### Bisakah saya menyesuaikan tampilan masing-masing tugas dalam tampilan garis waktu?
Sangat! Aspose.Tasks memberikan fleksibilitas untuk menyesuaikan tampilan setiap tugas dalam tampilan timeline.
### Di mana saya dapat menemukan sumber daya tambahan dan dukungan untuk Aspose.Tasks?
 Mengunjungi[Dokumentasi Aspose.Tasks](https://reference.aspose.com/tasks/net/)untuk panduan komprehensif dan[forum dukungan](https://forum.aspose.com/c/tasks/15) untuk bantuan.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).