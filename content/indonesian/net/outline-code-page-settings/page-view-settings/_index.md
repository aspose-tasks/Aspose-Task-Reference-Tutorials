---
title: Sesuaikan Pengaturan Tampilan Halaman Proyek MS di Aspose.Tasks
linktitle: Konfigurasikan Pengaturan Tampilan Halaman di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi pengaturan tampilan halaman di Aspose.Tasks untuk .NET untuk menyesuaikan format pencetakan dokumen Microsoft Project Anda.
type: docs
weight: 21
url: /id/net/outline-code-page-settings/page-view-settings/
---
## Perkenalan
Microsoft Project adalah alat yang ampuh untuk manajemen proyek, namun terkadang Anda perlu menyesuaikan cara proyek Anda dilihat dan dicetak. Dengan Aspose.Tasks untuk .NET, Anda dapat dengan mudah mengonfigurasi pengaturan tampilan halaman untuk memenuhi kebutuhan spesifik Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks for .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.Tasks for .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: Siapkan file Microsoft Project yang ingin Anda konfigurasikan pengaturan tampilan halamannya.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Tasks di proyek .NET Anda.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Langkah 1: Muat File Proyek
 Mulailah dengan memuat file Microsoft Project Anda ke dalam instance`Project` kelas.
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Langkah 2: Tetapkan Jumlah Kolom Pertama
Tentukan jumlah kolom pertama yang akan dicetak pada semua halaman.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Langkah 3: Cetak Catatan
Pilih apakah akan mencetak catatan bersama dengan proyek.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Langkah 4: Sesuaikan Skala Waktu ke Akhir Halaman
Putuskan apakah akan menyesuaikan skala waktu dengan akhir halaman saat mencetak.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Langkah 5: Cetak Semua Kolom Lembar
Tentukan apakah akan mencetak semua kolom lembar tampilan.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Langkah 6: Cetak Halaman Kosong
Pilih apakah akan mencetak halaman kosong dari suatu tampilan.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Langkah 7: Cetak Kolom Pertama di Semua Halaman
Atur apakah akan mencetak sejumlah kolom pertama tertentu pada semua halaman.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Langkah 8: Simpan Proyek dengan Pengaturan yang Dikonfigurasi
Terakhir, simpan proyek dengan pengaturan tampilan halaman yang dikonfigurasi, tentukan format keluaran, seperti PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Kesimpulan
Mengonfigurasi pengaturan tampilan halaman Proyek Microsoft di Aspose.Tasks untuk .NET sangatlah mudah dan memungkinkan Anda menyesuaikan format pencetakan dengan kebutuhan Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat memastikan bahwa dokumen proyek Anda disajikan persis seperti yang diperlukan.
## FAQ
### T: Bisakah saya mengonfigurasi pengaturan tampilan halaman untuk format file lain selain PDF?
J: Ya, Aspose.Tasks mendukung berbagai format file untuk menyimpan proyek, termasuk XLSX, MPP, dan HTML.
### Q: Apakah ada batasan jumlah kolom yang dapat saya cetak?
A: Aspose.Tasks memungkinkan Anda menyesuaikan jumlah kolom yang akan dicetak berdasarkan kebutuhan Anda.
### T: Bisakah saya menerapkan pengaturan tampilan halaman berbeda untuk proyek berbeda?
J: Ya, Anda dapat menyesuaikan pengaturan tampilan halaman secara independen untuk setiap file proyek yang Anda kerjakan.
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks menawarkan kompatibilitas dengan Microsoft Project 2003 dan versi yang lebih baru.
### T: Di mana saya dapat menemukan bantuan atau dukungan lebih lanjut untuk Aspose.Tasks?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15)untuk pertanyaan atau masalah apa pun yang Anda temui selama penggunaan.