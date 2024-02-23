---
title: Ubah Opsi MSP ke XPS dengan Aspose.Tasks
linktitle: Opsi XPS untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonversi file Microsoft Project ke format XPS menggunakan Aspose.Tasks untuk .NET. Integrasi yang mudah, fungsionalitas yang kuat.
type: docs
weight: 21
url: /id/net/saving-options/xps-options/
---
## Perkenalan
Microsoft Project (MSP) adalah alat yang banyak digunakan untuk manajemen proyek, memfasilitasi perencanaan, pelacakan, dan pelaporan aktivitas proyek. Aspose.Tasks untuk .NET menawarkan fungsionalitas yang kuat untuk memanipulasi file MSP secara terprogram, memberdayakan pengembang untuk mengotomatiskan berbagai tugas yang terkait dengan manajemen proyek. Dalam tutorial ini, kita akan mempelajari pemanfaatan Aspose.Tasks untuk .NET untuk menghasilkan file XPS dari dokumen MSP, menjelajahi langkah-langkah dan pertimbangan yang diperlukan.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
2. Dokumen Proyek Microsoft: Siapkan dokumen Microsoft Project (.mpp) yang ingin Anda konversi ke format XPS.

## Impor Namespace
Untuk memulai proses, impor namespace yang diperlukan di proyek .NET Anda:
```csharp

using Aspose.Tasks.Saving;
```

## Langkah 1: Tetapkan Jalur Direktori Dokumen
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
```
 mengganti`"Your Document Directory"` dengan jalur di mana dokumen MSP Anda berada.
## Langkah 2: Muat Dokumen MSP
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 Di sini, kami menginisialisasi yang baru`Project` objek dengan melewati jalur dokumen MSP.
## Langkah 3: Buat Opsi Penyimpanan XPS
```csharp
// Buat opsi penyimpanan XPS dan sesuaikan parameternya
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 Pada langkah ini, kami memberi contoh`XpsOptions`dan konfigurasikan parameter. Pengaturan`RenderMetafileAsBitmap` ke`true` memastikan rendering metafile yang tepat.
## Langkah 4: Simpan Dokumen sebagai XPS
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 Akhirnya, kami menelepon`Save` metode pada`Project` objek, menentukan jalur file keluaran dan yang dikonfigurasi sebelumnya`XpsOptions`.

## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET menyederhanakan proses konversi dokumen Microsoft Project ke format XPS secara terprogram. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, pengembang dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi .NET mereka, sehingga meningkatkan alur kerja manajemen proyek dengan mudah.
## FAQ
### T: Dapatkah Aspose.Tasks untuk .NET menangani file MSP yang kompleks?
J: Ya, Aspose.Tasks untuk .NET dapat secara efisien menangani file Microsoft Project yang kompleks, memastikan konversi yang akurat ke berbagai format.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda bisa mendapatkan versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Apakah Aspose.Tasks untuk .NET mendukung format output lain selain XPS?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai format keluaran seperti PDF, HTML, PNG, dan JPEG, antara lain.
### T: Dapatkah saya menyesuaikan opsi rendering untuk file keluaran?
J: Tentu saja, Aspose.Tasks untuk .NET menyediakan opsi luas untuk menyesuaikan parameter rendering sesuai dengan kebutuhan Anda.
### T: Di mana saya dapat menemukan dukungan atau bantuan tambahan untuk Aspose.Tasks untuk .NET?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk pertanyaan atau bantuan apa pun mengenai Aspose.Tasks untuk .NET.