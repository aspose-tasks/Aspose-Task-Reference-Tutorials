---
title: Menguasai Masker Garis Besar Proyek Microsoft di Aspose.Tasks
linktitle: Bekerja dengan Outline Mask di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara bekerja dengan file Microsoft Project secara terprogram menggunakan Aspose.Tasks untuk .NET. Kuasai masker garis besar secara efisien.
type: docs
weight: 14
url: /id/net/outline-code-page-settings/outline-masks/
---
## Perkenalan
Di bidang manajemen proyek dan pelacakan tugas, Microsoft Project berdiri sebagai alat landasan. Namun, ketika memanipulasi dan mengelola file proyek secara terprogram, Aspose.Tasks untuk .NET muncul sebagai solusi yang ampuh. Tutorial ini akan mempelajari satu aspek spesifik dalam bekerja dengan file MS Project menggunakan Aspose.Tasks untuk .NET: menangani masker garis besar.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:
- Pemahaman dasar bahasa pemrograman C#.
- Menginstal Visual Studio dengan kerangka .NET.
- Keakraban dengan format file Microsoft Project.
-  Mengunduh dan menginstal Aspose.Tasks untuk perpustakaan .NET. Jika tidak, Anda bisa mendapatkannya[Di Sini](https://releases.aspose.com/tasks/net/).
- Pemahaman dasar tentang konsep manajemen proyek.
## Impor Namespace
Sebelum melanjutkan tutorial, impor namespace yang diperlukan di file C# Anda:
```csharp
    
```
## Langkah 1: Muat File Proyek
Langkah pertama adalah memuat file Microsoft Project menggunakan perpustakaan Aspose.Tasks.
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Langkah 2: Tentukan Kode Garis Besar
Selanjutnya, tentukan definisi kode kerangka untuk proyek tersebut.
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
project.OutlineCodes.Add(outline);
```
## Langkah 3: Tentukan Outline Mask
Sekarang, buat outline mask untuk kode outline.
```csharp
var mask = new OutlineMask();
// Atur jenis topeng
mask.Type = MaskType.Characters;
// Tetapkan pemisah nilai kode
mask.Separator = "/";
// Atur level topeng
mask.Level = 1;
// Tetapkan panjang maksimum (dalam karakter) dari nilai kode kerangka. 0 jika panjangnya tidak ditentukan.
mask.Length = 2;
// Tambahkan topeng ke definisi
outline.Masks.Add(mask);
```
## Langkah 4: Tentukan Nilai Garis Besar
Tentukan nilai outline untuk kode outline.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
Panduan langkah demi langkah ini mencakup proses bekerja dengan masker kerangka di Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif mengelola masker kerangka di file Microsoft Project Anda secara terprogram.

## Kesimpulan
Menguasai manipulasi file Microsoft Project secara terprogram membuka banyak kemungkinan dalam otomatisasi manajemen proyek. Dengan Aspose.Tasks untuk .NET, penanganan masker garis besar menjadi efisien dan efisien, memberdayakan pengembang untuk menciptakan solusi yang disesuaikan untuk pelacakan dan manajemen proyek.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks untuk .NET dengan alat manajemen proyek lainnya?
J: Tentu saja! Meskipun Aspose.Tasks terutama berfokus pada file Microsoft Project, Aspose.Tasks menyediakan interoperabilitas dengan berbagai format manajemen proyek.
### T: Apakah Aspose.Tasks mendukung pembacaan dan penulisan file Microsoft Project?
J: Ya, Aspose.Tasks memungkinkan pengembang membaca dan menulis ke file Microsoft Project, sehingga memungkinkan manipulasi komprehensif.
### T: Apakah ada forum komunitas untuk Aspose.Tasks tempat saya dapat mencari bantuan?
A: Memang benar, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bertanya, berbagi ide, dan berinteraksi dengan pengguna lain.
### T: Dapatkah saya mencoba Aspose.Tasks untuk .NET sebelum membeli?
 J: Tentu saja! Anda dapat mengakses uji coba gratis Aspose.Tasks[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks?
 J: Jika Anda memerlukan lisensi sementara untuk tujuan evaluasi atau pengujian, Anda bisa mendapatkannya[Di Sini](https://purchase.aspose.com/temporary-license/).