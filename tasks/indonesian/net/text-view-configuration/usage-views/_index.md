---
title: Mengonfigurasi Tampilan Penggunaan di Aspose.Tasks
linktitle: Mengonfigurasi Tampilan Penggunaan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi tampilan penggunaan tugas di Aspose.Tasks untuk .NET. Tingkatkan visualisasi proyek dengan langkah-langkah mendetail. Unduh perpustakaannya sekarang!
weight: 17
url: /id/net/text-view-configuration/usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonfigurasi Tampilan Penggunaan di Aspose.Tasks

## Perkenalan
Jika Anda seorang pengembang .NET yang ingin meningkatkan kemampuan manajemen proyek Anda, Aspose.Tasks adalah alat canggih yang memungkinkan Anda memanipulasi file Microsoft Project dengan mudah. Dalam tutorial ini, kami akan fokus pada mengonfigurasi tampilan penggunaan menggunakan Aspose.Tasks untuk .NET. Ikuti terus untuk mendapatkan wawasan tentang rendering tampilan penggunaan tugas dengan detail untuk visualisasi proyek yang lebih baik.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Perpustakaan Aspose.Tasks: Pastikan Anda memiliki perpustakaan Aspose.Tasks yang terintegrasi ke dalam proyek .NET Anda. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/tasks/net/) dan ikuti petunjuk instalasi.
- Direktori Dokumen: Siapkan direktori tempat dokumen proyek Anda disimpan. Ganti "Direktori Dokumen Anda" di cuplikan kode dengan jalur sebenarnya ke direktori dokumen Anda.
## Impor Namespace
Dalam cuplikan kode yang disediakan, Anda akan melihat penggunaan namespace tertentu. Pastikan untuk menyertakan ini dalam proyek Anda untuk integrasi yang lancar:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## Langkah 1: Render Tampilan Penggunaan Tugas dengan Detail
Mari kita mulai dengan merender tampilan penggunaan tugas dengan detailnya. Ikuti langkah ini:
## Langkah 1.1: Muat Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Langkah 1.2: Dapatkan Tampilannya
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Langkah 1.3: Sesuaikan Pengaturan Tampilan
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Langkah 1.4: Simpan Proyek sebagai PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Langkah 2: Tampilkan Kolom Header Detail
Pada langkah ini, kita akan mengubah pengaturan tampilan untuk menampilkan kolom header detail dan menyimpan proyek sebagai PDF:
## Langkah 2.1: Tampilkan Kolom Header Detail
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Langkah 2.2: Ulangi Header Detail di Semua Baris
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Langkah 2.3: Simpan Proyek sebagai PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## Kesimpulan
Selamat! Anda telah berhasil mengonfigurasi tampilan penggunaan di Aspose.Tasks. Tutorial ini memberikan landasan untuk manajemen dan visualisasi proyek yang efisien menggunakan pustaka Aspose.Tasks.

### FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks?
 Dokumentasi komprehensif tersedia[Di Sini](https://reference.aspose.com/tasks/net/).
### T: Bagaimana cara mengunduh Aspose.Tasks untuk .NET?
 Unduh perpustakaan[Di Sini](https://releases.aspose.com/tasks/net/).
### T: Di mana saya dapat membeli Aspose.Tasks?
 Anda dapat membeli Aspose.Tasks[Di Sini](https://purchase.aspose.com/buy).
### T: Apakah tersedia uji coba gratis?
 Ya, jelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Butuh dukungan atau ada pertanyaan?
 Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
