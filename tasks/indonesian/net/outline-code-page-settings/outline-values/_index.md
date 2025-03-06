---
title: Menguasai Nilai Garis Besar Proyek MS dengan Aspose.Tasks
linktitle: Mengelola Nilai Garis Besar di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola nilai kerangka Proyek MS secara efisien menggunakan Aspose.Tasks untuk .NET. Sesuaikan garis besar proyek dengan mudah.
weight: 16
url: /id/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Nilai Garis Besar Proyek MS dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola nilai kerangka Microsoft Project menggunakan pustaka Aspose.Tasks untuk .NET. Dengan Aspose.Tasks, Anda dapat dengan mudah memanipulasi kode kerangka, membuat nilai kerangka baru, dan menyesuaikan kerangka proyek sesuai dengan kebutuhan Anda.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan, seperti Visual Studio, dengan kompatibilitas kerangka .NET.
3. Pemahaman Dasar Pemrograman C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#, karena kita akan menggunakan C# untuk bekerja dengan pustaka Aspose.Tasks.

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam kode C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Langkah 1: Muat File Proyek
```csharp
// Jalur ke direktori dokumen.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Langkah ini menginisialisasi objek Proyek baru dan memuat file Microsoft Project dari direktori yang ditentukan.
## Langkah 2: Tentukan Definisi Kode Garis Besar
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Di sini, kita mendefinisikan dua objek OutlineCodeDefinition dan menambahkannya ke koleksi OutlineCodes proyek.
## Langkah 3: Tentukan Outline Mask
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Langkah ini menyiapkan OutlineMask untuk definisi kode kerangka.
## Langkah 4: Buat Nilai Garis Besar
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Pada langkah ini, kita membuat dua objek OutlineValue dan mengatur propertinya seperti nilai, ID nilai, tipe, deskripsi, dan status penciutan.

## Kesimpulan
Mengelola nilai garis besar Proyek MS menggunakan Aspose.Tasks untuk .NET sangatlah mudah dengan fungsionalitas yang disediakan. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien memanipulasi kode dan nilai kerangka untuk menyesuaikan kerangka proyek sesuai dengan kebutuhan Anda.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks dengan kerangka .NET lainnya?
J: Ya, Aspose.Tasks kompatibel dengan berbagai kerangka .NET, memastikan fleksibilitas dalam lingkungan pengembangan Anda.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda dapat mengakses Aspose.Tasks versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 A: Untuk dukungan dan bantuan, Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks?
J: Ya, Anda dapat membeli lisensi sementara untuk Aspose.Tasks dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks?
 J: Anda dapat merujuk pada dokumentasi lengkap yang tersedia[Di Sini](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
