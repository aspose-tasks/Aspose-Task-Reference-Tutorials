---
title: Mengonfigurasi Tampilan Penggunaan Sumber Daya Proyek MS di Aspose.Tasks
linktitle: Mengonfigurasi Tampilan Penggunaan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi tampilan penggunaan sumber daya MS Project menggunakan Aspose.Tasks untuk .NET. Panduan langkah demi langkah dengan contoh kode disertakan.
type: docs
weight: 15
url: /id/net/resource-risk-analysis/resource-usage-views/
---
## Perkenalan
Microsoft Project (MS Project) adalah alat yang ampuh untuk manajemen proyek, memungkinkan pengguna merencanakan, melaksanakan, dan melacak proyek mereka secara efisien. Aspose.Tasks untuk .NET menyediakan integrasi yang lancar dengan file MS Project, memungkinkan pengembang memanipulasi data proyek secara terprogram. Dalam tutorial ini, kita akan mempelajari cara mengonfigurasi tampilan penggunaan sumber daya MS Project menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: Memiliki file Microsoft Project (`.mpp`) berisi data proyek yang ingin Anda kerjakan.

## Impor Namespace
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Langkah 1: Muat File Proyek
Pertama, muat file MS Project menggunakan Aspose.Tasks:
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## Langkah 2: Tentukan Opsi Simpan
Tentukan opsi penyimpanan yang menentukan pengaturan skala waktu dan format presentasi yang diperlukan:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## Langkah 3: Simpan Proyek dengan Tampilan Penggunaan Sumber Daya
Simpan proyek dengan tampilan penggunaan sumber daya yang dikonfigurasi ke file PDF:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengonfigurasi tampilan penggunaan sumber daya MS Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, pengembang dapat mengintegrasikan Aspose.Tasks dengan lancar ke dalam aplikasi .NET mereka untuk memanipulasi data proyek secara efisien.

## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk .mpp, .mpt, .xml, dan .mpx.
### T: Dapatkah saya menyesuaikan pengaturan skala waktu dan format presentasi lebih lanjut?
J: Tentu saja, Aspose.Tasks memberikan fleksibilitas untuk menyesuaikan pengaturan skala waktu dan format presentasi sesuai dengan kebutuhan Anda.
### T: Apakah Aspose.Tasks mendukung format keluaran lain selain PDF?
J: Ya, Aspose.Tasks mendukung berbagai format output termasuk XLSX, MPP, XML, HTML, dan banyak lagi.
### T: Apakah ada komunitas atau forum untuk dukungan Aspose.Tasks?
 A: Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk pertanyaan, diskusi, atau kebutuhan dukungan apa pun.
### T: Dapatkah saya mencoba Aspose.Tasks sebelum membeli?
 J: Tentu saja, Anda dapat menjelajahi Aspose.Tasks dengan tersedia uji coba gratis[Di Sini](https://releases.aspose.com/).