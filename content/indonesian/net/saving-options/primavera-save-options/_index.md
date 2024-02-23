---
title: Simpan MS Project Options Primavera dengan Aspose.Tasks
linktitle: Primavera Simpan Opsi untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Temukan cara menyimpan opsi MS Project untuk Primavera dengan lancar menggunakan Aspose.Tasks untuk .NET. Ikuti tutorial langkah demi langkah kami.
type: docs
weight: 14
url: /id/net/saving-options/primavera-save-options/
---
## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project di aplikasi .NET mereka dengan lancar. Salah satu fungsi utama yang ditawarkannya adalah kemampuan untuk menyimpan opsi MS Project untuk Primavera, perangkat lunak manajemen proyek yang populer. Dalam tutorial ini, kita akan mempelajari cara mencapainya menggunakan Aspose.Tasks.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pemahaman dasar tentang kerangka C# dan .NET.
-  Aspose.Tasks untuk .NET diinstal di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Contoh file MS Project untuk eksperimen.

## Impor Namespace
Pertama, mari impor namespace yang diperlukan ke kode C# kita:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Langkah 1: Muat File Proyek MS
Mulailah dengan memuat file MS Project yang ingin Anda gunakan ke dalam aplikasi C# Anda. Anda dapat melakukan ini menggunakan`Project` kelas yang disediakan oleh Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Langkah 2: Tentukan Opsi Penyimpanan Primavera
Selanjutnya, buat opsi penyimpanan Primavera dan sesuaikan sesuai kebutuhan Anda. Langkah ini melibatkan penentuan parameter seperti awalan ID aktivitas, akhiran, kenaikan, dan apakah akan memberi nomor ulang pada ID aktivitas.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Langkah 3: Simpan Opsi Proyek MS untuk Primavera
 Sekarang Anda telah memuat file proyek dan menentukan opsi penyimpanan Primavera, sekarang saatnya menyimpan opsi untuk Primavera. Menggunakan`Save` metode yang disediakan oleh`Project` kelas, meneruskan jalur file keluaran yang diinginkan dan opsi penyimpanan Primavera.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Kesimpulan
Kesimpulannya, memanfaatkan Aspose.Tasks untuk .NET memungkinkan pengembang memanipulasi file MS Project dengan lancar, termasuk opsi penyimpanan untuk Primavera. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fungsi ini secara efisien ke dalam aplikasi .NET Anda.
## FAQ
### T: Bisakah saya mengkustomisasi parameter lain selain ID aktivitas saat menyimpan opsi MS Project untuk Primavera?
J: Ya, Aspose.Tasks menyediakan berbagai opsi penyesuaian, termasuk alokasi sumber daya dan penjadwalan tugas.
### T: Apakah Aspose.Tasks mendukung perangkat lunak manajemen proyek lain selain Primavera?
J: Ya, Aspose.Tasks mendukung berbagai format yang kompatibel dengan alat manajemen proyek populer seperti Oracle Primavera, Microsoft Project Server, dan banyak lagi.
### T: Apakah Aspose.Tasks cocok untuk proyek skala kecil dan tingkat perusahaan?
J: Tentu saja, Aspose.Tasks dirancang untuk memenuhi kebutuhan pengembang yang mengerjakan proyek dari semua ukuran, menawarkan skalabilitas dan kinerja yang kuat.
### T: Dapatkah saya mencoba Aspose.Tasks secara gratis sebelum melakukan pembelian?
 J: Ya, Anda dapat mengunduh uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/) untuk mengeksplorasi fitur dan kemampuannya.
### T: Di mana saya bisa mendapatkan dukungan jika saya mengalami masalah atau memiliki pertanyaan saat menggunakan Aspose.Tasks?
J: Anda dapat mencari bantuan dari komunitas Aspose.Tasks dan tim dukungan di[forum](https://forum.aspose.com/c/tasks/15).