---
title: Konfigurasikan Pengaturan Halaman Proyek MS dengan Aspose.Tasks
linktitle: Mengonfigurasi Pengaturan Halaman di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi pengaturan halaman MS Project menggunakan Aspose.Tasks untuk .NET. Sesuaikan orientasi, ukuran, dan lainnya dengan langkah sederhana.
weight: 20
url: /id/net/outline-code-page-settings/page-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasikan Pengaturan Halaman Proyek MS dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan memandu proses mengonfigurasi pengaturan halaman Microsoft Project menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks adalah API canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan Visual Studio atau IDE pilihan lainnya untuk pengembangan .NET.

## Mengimpor Namespace
Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Namespace ini menyediakan akses ke kelas Aspose.Tasks dan metode yang diperlukan untuk memanipulasi file MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Langkah 1: Muat File Proyek
Pertama, Anda perlu memuat file MS Project yang ingin Anda konfigurasikan pengaturan halamannya.
```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Langkah 2: Akses Pengaturan Halaman
Selanjutnya, Anda akan mengakses pengaturan halaman file proyek.
```csharp
// Dapatkan pengaturannya
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Langkah 3: Konfigurasikan Pengaturan Halaman
Sekarang, mari konfigurasikan berbagai properti pengaturan halaman sesuai kebutuhan Anda.
```csharp
// Atur orientasi halaman ke potret
settings.IsPortrait = true;
// Tetapkan jumlah lebar halaman yang akan dicetak
settings.PagesInWidth = 5;
// Tetapkan jumlah halaman tinggi yang akan dicetak
settings.PagesInHeight = 7;
// Atur persentase ukuran normal untuk menyesuaikan pencetakan
settings.PercentOfNormalSize = 200;
// Atur ukuran kertas
settings.PaperSize = PrinterPaperSize.PaperB4;
// Tetapkan nomor halaman pertama untuk dicetak
settings.FirstPageNumber = 3;
```
## Langkah 4: Simpan File Proyek
Terakhir, simpan file proyek dengan pengaturan halaman yang diperbarui.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengonfigurasi pengaturan halaman Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menyesuaikan orientasi halaman, ukuran, dan opsi pencetakan lainnya sesuai kebutuhan Anda.

## FAQ
### T: Bisakah saya mengonfigurasi pengaturan halaman untuk beberapa file MS Project secara bersamaan?
J: Ya, Anda dapat mengulang beberapa file proyek dan menerapkan pengaturan halaman yang sama ke masing-masing file.
### T: Apakah mungkin untuk mengembalikan pengaturan halaman ke default?
J: Tentu saja, Anda cukup menghilangkan langkah-langkah konfigurasi atau mengatur ulang pengaturan ke nilai defaultnya.
### T: Apakah ada batasan ukuran kertas yang didukung?
J: Aspose.Tasks mendukung berbagai ukuran kertas, termasuk ukuran standar dan khusus.
### T: Dapatkah saya mengotomatiskan proses konfigurasi pengaturan halaman?
J: Tentu saja, Anda dapat mengintegrasikan fungsi ini ke dalam alur kerja aplikasi Anda untuk mengotomatisasi konfigurasi pengaturan halaman.
### T: Apakah Aspose.Tasks menawarkan dukungan untuk format file lain selain .mpp?
J: Ya, Aspose.Tasks mendukung berbagai format file seperti XML, MPT, HTML, dan lain-lain.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
