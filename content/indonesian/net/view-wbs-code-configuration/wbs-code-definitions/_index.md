---
title: Mendefinisikan Definisi Kode WBS di Aspose.Tasks
linktitle: Mendefinisikan Definisi Kode WBS di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Aspose.Tasks untuk .NET memberdayakan manajemen proyek yang efisien. Kuasai kode WBS dengan mudah menggunakan tutorial komprehensif kami. Sederhanakan alur kerja hari ini!
type: docs
weight: 13
url: /id/net/view-wbs-code-configuration/wbs-code-definitions/
---
## Perkenalan
Seiring berkembangnya manajemen proyek, kebutuhan akan alat canggih yang menyederhanakan proses juga meningkat. Di bidang pengembangan .NET, Aspose.Tasks menonjol sebagai perpustakaan yang kuat untuk menangani tugas-tugas manajemen proyek. Dalam tutorial ini, kita akan mempelajari proses mendefinisikan kode Work Breakdown Structure (WBS) menggunakan Aspose.Tasks untuk .NET. Kode WBS menertibkan hierarki proyek, memungkinkan pelacakan dan pengorganisasian yang efisien.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan kerja tentang pengembangan .NET.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Editor kode (disarankan Visual Studio).
## Impor Namespace
Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
    
    using Aspose.Tasks.Saving;
```
Sekarang, mari kita uraikan proses pendefinisian kode WBS menjadi langkah-langkah yang dapat dikelola.

## Langkah 1: Atur Direktori Dokumen
```csharp
String DataDir = "Your Document Directory";
```
Ganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.
## Langkah 2: Inisialisasi Proyek
```csharp
var project = new Project();
```
Buat instans proyek baru menggunakan Aspose.Tasks.
## Langkah 3: Konfigurasikan Definisi Kode WBS
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
Siapkan parameter definisi kode WBS, seperti pembuatan kode, verifikasi keunikan, dan awalan kode.
## Langkah 4: Tentukan Masker Kode WBS
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
Tentukan masker kode WBS untuk menyusun kode berdasarkan panjang, pemisah, dan urutan.
## Langkah 5: Buat Tugas dan Hitung Ulang
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
project.Recalculate();
```
Tambahkan tugas ke hierarki proyek dan hitung ulang untuk memperbarui kode WBS.
## Langkah 6: Simpan Proyek
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Simpan proyek dengan kode WBS yang baru ditentukan.
## Kesimpulan
Dalam tutorial ini, kita menjelajahi kekuatan Aspose.Tasks untuk .NET dalam mendefinisikan kode WBS. Dengan mengikuti langkah-langkah ini, Anda dapat meningkatkan kemampuan manajemen proyek, menghadirkan struktur dan efisiensi pada alur kerja Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks kompatibel dengan semua versi .NET?
Ya, Aspose.Tasks mendukung berbagai versi .NET, memastikan kompatibilitas dengan berbagai lingkungan pengembangan.
### Bisakah saya menyesuaikan format kode WBS lebih lanjut?
Sangat. Aspose.Tasks memberikan fleksibilitas yang luas, memungkinkan Anda menyesuaikan kode WBS untuk memenuhi persyaratan proyek tertentu.
### Apakah ada batasan jumlah kode WBS yang dapat saya tentukan?
Aspose.Tasks menawarkan skalabilitas, dan Anda dapat menentukan sejumlah besar kode WBS berdasarkan kompleksitas proyek Anda.
### Bagaimana cara memecahkan masalah terkait kode WBS di proyek saya?
 Forum Aspose.Tasks (tautan ke[mendukung](https://forum.aspose.com/c/tasks/15)) adalah sumber daya yang berharga untuk mencari bantuan dan memecahkan pertanyaan.
### Apakah ada versi uji coba yang tersedia sebelum membeli Aspose.Tasks?
 Ya, Anda dapat menjelajahi fitur dan kemampuan Aspose.Tasks dengan mengakses[uji coba gratis](https://releases.aspose.com/) Versi: kapan.