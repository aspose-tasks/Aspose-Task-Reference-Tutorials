---
title: Menguasai Tampilan Penggunaan Tugas di Aspose.Tasks untuk .NET
linktitle: Mengonfigurasi Tampilan Penggunaan Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi Aspose.Tasks untuk .NET dan pelajari cara mengonfigurasi tampilan penggunaan tugas. Sesuaikan pengaturan skala waktu dan tingkatkan visual manajemen proyek Anda.
weight: 24
url: /id/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Tampilan Penggunaan Tugas di Aspose.Tasks untuk .NET

## Perkenalan
Dalam bidang manajemen proyek, memvisualisasikan penggunaan tugas sangat penting untuk perencanaan dan pelaksanaan yang efektif. Aspose.Tasks untuk .NET memberikan solusi tangguh untuk merender tampilan penggunaan tugas, memungkinkan Anda menyesuaikan pengaturan skala waktu dan format presentasi. Dalam tutorial ini, kita akan memandu langkah-langkah untuk mengonfigurasi tampilan penggunaan tugas menggunakan Aspose.Tasks.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Tasks yang terintegrasi ke dalam proyek .NET Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan .NET: Siapkan lingkungan .NET yang berfungsi di mesin Anda.
## Impor Namespace
Di proyek .NET Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks. Tambahkan baris berikut ke kode Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Langkah 1: Tetapkan Jalur Direktori Dokumen
 Sebelum bekerja dengan fungsi Aspose.Tasks, atur jalur ke direktori dokumen Anda. Mengganti`"Your Document Directory"` dengan jalur sebenarnya.
```csharp
String DataDir = "Your Document Directory";
```
## Langkah 2: Muat Proyek
 Inisialisasi Aspose.Tasks`Project` objek dengan memuat file proyek Anda (misalnya, TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Langkah 3: Tentukan SaveOptions
 Membuat`SaveOptions`objek untuk menentukan opsi rendering. Atur skala waktu ke 'Hari' dan format presentasi ke 'Penggunaan Tugas'.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Langkah 4: Simpan dengan Skala Waktu Hari
Simpan proyek dengan pengaturan skala waktu 'Hari' yang telah ditentukan sebelumnya.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Langkah 5: Simpan dengan Skala Waktu ThirdsOfMonths
Ubah pengaturan skala waktu menjadi 'ThirdsOfMonths' dan simpan proyek.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Langkah 6: Simpan dengan Skala Waktu Bulan
Tetapkan skala waktu ke 'Bulan' dan simpan proyek dengan pengaturan yang diperbarui.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Kesimpulan
Mengonfigurasi tampilan penggunaan tugas dengan Aspose.Tasks untuk .NET adalah proses yang mudah. Dengan menyesuaikan pengaturan skala waktu, Anda dapat menyesuaikan visualisasi tugas proyek sesuai dengan kebutuhan spesifik Anda.
 Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsi di[dokumentasi](https://reference.aspose.com/tasks/net/).
## Pertanyaan yang Sering Diajukan
### Bisakah saya menyesuaikan skala waktu di luar pengaturan yang telah ditentukan sebelumnya?
Ya, Anda dapat mengatur skala waktu khusus dengan menentukan interval dan satuannya.
### Apakah ada format presentasi lain yang tersedia?
Aspose.Tasks mendukung berbagai format presentasi, termasuk GanttChart, ResourceUsage, dan banyak lagi.
### Apakah Aspose.Tasks kompatibel dengan format file proyek yang berbeda?
Ya, Aspose.Tasks mendukung format file proyek populer seperti MPP, XML, dan CSV.
### Bisakah saya menerapkan pengaturan skala waktu yang berbeda untuk tugas tertentu?
Tentu saja, Anda dapat menyesuaikan pengaturan skala waktu untuk masing-masing tugas dalam proyek Anda.
### Bagaimana saya bisa mendapatkan dukungan atau mencari bantuan untuk Aspose.Tasks?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan bimbingan masyarakat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
