---
title: Kumpulan Definisi Kode Garis Besar di Aspose.Tasks .NET
linktitle: Kumpulan Definisi Kode Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanipulasi definisi kode kerangka dalam dokumen Microsoft Project menggunakan Aspose.Tasks untuk .NET. Kategorisasi data proyek Anda dengan mudah.
type: docs
weight: 13
url: /id/net/outline-code-page-settings/outline-code-definition-collection/
---
## Perkenalan
Aspose.Tasks adalah pustaka .NET canggih yang dirancang untuk memanipulasi dokumen Microsoft Project dengan mudah dan efisien. Salah satu fitur utamanya adalah kemampuan untuk bekerja dengan definisi kode garis besar, memungkinkan pengguna untuk mengatur dan mengkategorikan data proyek secara efektif. Dalam tutorial ini, kita akan mempelajari cara bekerja dengan definisi kode kerangka menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal-hal berikut:
1. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.
2. Visual Studio: Instal Visual Studio atau lingkungan pengembangan C# pilihan lainnya.
3.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).

## Impor Namespace
Untuk memulai, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Langkah 1: Muat Dokumen Proyek Microsoft
Pertama, muat dokumen Microsoft Project untuk mulai bekerja dengan definisi kode kerangka:
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Langkah 2: Akses Definisi Kode Garis Besar
Sekarang, mari akses definisi kode garis besar dalam proyek:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Langkah 3: Tambahkan Definisi Kode Kerangka Kustom
Anda dapat menambahkan definisi kode kerangka khusus sebagai berikut:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Langkah 4: Ubah Definisi Kode Garis Besar
Ubah definisi kode kerangka yang ada dengan mudah:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Langkah 5: Hapus Definisi Kode Garis Besar
Hapus definisi kode kerangka ketika tidak lagi diperlukan:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Langkah 6: Simpan Perubahan
Terakhir, simpan perubahan Anda ke dokumen proyek:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET menyediakan fungsionalitas komprehensif untuk mengelola definisi kode kerangka dalam dokumen Microsoft Project. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat memanipulasi definisi kode kerangka secara efisien untuk mengatur dan mengkategorikan data proyek Anda secara efektif.
## FAQ
### T: Dapatkah saya menambahkan beberapa definisi kode kerangka ke satu proyek?
 J: Ya, Anda dapat menambahkan beberapa definisi kode kerangka ke proyek berdasarkan kebutuhan Anda. Cukup gunakan`Add` metode untuk setiap definisi yang ingin Anda sertakan.
### T: Apakah mungkin untuk menghapus semua definisi kode kerangka dari sebuah proyek sekaligus?
 J: Ya, Anda dapat menghapus semua definisi kode kerangka dari sebuah proyek menggunakan`Clear` metode.
### T: Apa yang terjadi jika saya mencoba mengubah definisi kode kerangka hanya-baca?
J: Jika definisi kode outline bersifat baca-saja, Anda tidak akan dapat mengubahnya secara langsung. Anda harus memeriksa status hanya-baca sebelum mencoba modifikasi apa pun.
### T: Apakah ada batasan jumlah definisi kode kerangka yang dapat saya tambahkan ke proyek?
J: Aspose.Tasks untuk .NET tidak menerapkan batasan spesifik apa pun pada jumlah definisi kode kerangka yang dapat Anda tambahkan ke proyek. Namun, pertimbangkan implikasi kinerja ketika bekerja dengan sejumlah besar definisi.
### T: Dapatkah saya menggunakan definisi kode kerangka untuk mengelompokkan tugas berdasarkan kriteria khusus?
J: Ya, definisi kode kerangka memungkinkan Anda mengkategorikan tugas berdasarkan kriteria khusus, memberikan fleksibilitas dalam mengatur data proyek.## Kode Sumber Lengkap