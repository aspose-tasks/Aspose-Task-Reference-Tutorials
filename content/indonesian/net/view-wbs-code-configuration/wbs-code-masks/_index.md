---
title: Konfigurasi Kode WBS Langkah demi Langkah di Aspose.Tasks .NET
linktitle: Konfigurasikan Masker Kode WBS di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi konfigurasi Masker Kode WBS langkah demi langkah di proyek .NET menggunakan Aspose.Tasks. Tingkatkan kemampuan manajemen proyek dengan mudah.
type: docs
weight: 14
url: /id/net/view-wbs-code-configuration/wbs-code-masks/
---
## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memberdayakan pengembang untuk memanipulasi data manajemen proyek secara efisien dalam aplikasi .NET. Dalam tutorial ini, kita akan menjelajahi proses mengonfigurasi Masker Kode Work Breakdown Structure (WBS) menggunakan Aspose.Tasks.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Tugas untuk Dokumentasi .NET](https://reference.aspose.com/tasks/net/).
- Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET yang berfungsi.
- Direktori Dokumen: Pilih direktori di sistem Anda untuk menyimpan file proyek.
## Impor Namespace
Dalam proyek .NET Anda, sertakan namespace yang diperlukan untuk bekerja dengan Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Langkah 1: Buat Instans Proyek
Mulailah dengan membuat contoh proyek baru:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Langkah 2: Tentukan Definisi Kode WBS
Siapkan Definisi Kode WBS untuk proyek Anda:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Langkah 3: Tambahkan Masker Kode WBS
Tentukan Masker Kode WBS dan tambahkan ke proyek:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Langkah 4: Buat Tugas
Tambahkan tugas ke proyek:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Langkah 5: Hitung ulang
Hitung ulang proyek untuk memastikan kode WBS diterapkan dengan benar:
```csharp
project.Recalculate();
```
## Langkah 6: Tampilkan Informasi Masker WBS
Keluarkan informasi tentang masker WBS ke konsol:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Langkah 7: Simpan Proyek
Simpan proyek dengan kode WBS yang ditambahkan:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Selamat! Anda telah berhasil mengonfigurasi Masker Kode WBS di proyek Aspose.Tasks Anda.
## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi proses langkah demi langkah mengonfigurasi WBS Code Mask menggunakan Aspose.Tasks untuk .NET. Pustaka yang kuat ini memberi pengembang cara yang mudah untuk meningkatkan kemampuan manajemen proyek dalam aplikasi .NET mereka.

## FAQ
### Bisakah saya menggunakan Aspose.Tasks secara gratis?
 Aspose.Tasks menawarkan uji coba gratis, yang dapat Anda unduh[Di Sini](https://releases.aspose.com/).
### Di mana saya bisa mendapatkan dukungan tambahan?
 mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15)untuk dukungan masyarakat.
### Bagaimana saya bisa mendapatkan lisensi sementara?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah ada dokumentasi terperinci yang tersedia?
 Ya, dokumentasi lengkap tersedia[Di Sini](https://reference.aspose.com/tasks/net/).
### Di mana saya dapat membeli Aspose.Tasks?
 Beli Aspose.Tugas[Di Sini](https://purchase.aspose.com/buy).