---
title: Menguasai Urutan WBS dengan Aspose.Tasks untuk .NET
linktitle: Mendefinisikan Urutan WBS di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Berdayakan manajemen proyek Anda dengan Aspose.Tasks untuk .NET – tentukan urutan WBS dengan lancar dan tingkatkan efisiensi dengan mudah. #Aspose #Tugas #MS Project
type: docs
weight: 16
url: /id/net/view-wbs-code-configuration/wbs-sequences/
---
## Perkenalan
Apakah Anda sedang mengerjakan aplikasi manajemen proyek dan memerlukan alat yang tangguh untuk menangani rangkaian Struktur Perincian Kerja (WBS)? Kunjungi Aspose.Tasks untuk .NET, perpustakaan canggih yang menyederhanakan tugas manajemen proyek. Dalam tutorial ini, kami akan memandu Anda melalui proses mendefinisikan urutan WBS langkah demi langkah.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- [Unduh dan instal Aspose.Tasks untuk .NET](https://releases.aspose.com/tasks/net/)
- Pengetahuan dasar tentang pemrograman C#
- Lingkungan pengembangan yang disiapkan untuk proyek .NET
## Impor Namespace
Dalam kode C# Anda, pastikan untuk menyertakan namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Tasks. Tambahkan yang berikut ini di awal skrip Anda:
```csharp
    
    using Aspose.Tasks.Saving;
```
## Mendefinisikan Urutan WBS - Panduan Langkah demi Langkah
## Langkah 1: Siapkan Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project();
```
## Langkah 2: Konfigurasikan Definisi Kode WBS
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Langkah 3: Tentukan Masker Kode WBS
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
## Langkah 4: Tambahkan Tugas ke Proyek
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
```
## Langkah 5: Hitung Ulang Data Proyek
```csharp
project.Recalculate();
```
## Langkah 6: Simpan Proyek
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Selamat! Anda telah berhasil menentukan urutan WBS dalam proyek Anda menggunakan Aspose.Tasks untuk .NET.
## Kesimpulan
Mengelola urutan WBS sangat penting untuk manajemen proyek yang efektif, dan Aspose.Tasks untuk .NET menjadikan tugas ini lancar. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat meningkatkan fungsionalitas WBS dalam aplikasi manajemen proyek Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks kompatibel dengan .NET Core?
Ya, Aspose.Tasks mendukung .NET Core, memungkinkan Anda membangun aplikasi lintas platform.
### Bisakah saya menyesuaikan format kode WBS lebih lanjut?
Sangat! Aspose.Tasks memberikan fleksibilitas dalam menentukan kode WBS sesuai dengan kebutuhan proyek Anda.
### Apakah ada versi uji coba yang tersedia?
 Ya kamu bisa[unduh uji coba gratis](https://releases.aspose.com/) untuk menjelajahi fitur sebelum melakukan pembelian.
### Bagaimana saya bisa mendapatkan dukungan komunitas untuk Aspose.Tasks?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk berhubungan dengan masyarakat dan mencari bantuan.
### Apakah lisensi sementara tersedia?
 Ya, Anda bisa mendapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.