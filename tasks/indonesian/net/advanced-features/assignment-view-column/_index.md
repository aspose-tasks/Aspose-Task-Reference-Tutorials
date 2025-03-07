---
title: Kolom Tampilan Tugas Kustom di Aspose.Tasks
linktitle: Kolom Tampilan Tugas Kustom di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menambahkan kolom tampilan penugasan kustom di Aspose.Tasks untuk .NET guna meningkatkan kemampuan manajemen proyek.
weight: 16
url: /id/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kolom Tampilan Tugas Kustom di Aspose.Tasks

## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara menambahkan kolom kustom untuk tampilan tugas menggunakan Aspose.Tasks untuk .NET. Kolom khusus memberikan fleksibilitas dan memungkinkan Anda menampilkan informasi tambahan yang relevan dengan kebutuhan manajemen proyek Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Pengetahuan dasar bahasa pemrograman C#.
2.  Aspose.Tasks untuk perpustakaan .NET diinstal. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/tasks/net/).
3. Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk mengakses kelas dan metode yang diperlukan untuk membuat kolom tampilan tugas khusus:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Langkah 1: Muat Proyek

 Untuk memulai, muat file proyek Anda menggunakan`Project` kelas:

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Langkah 2: Buat Opsi Penyimpanan Spreadsheet

 Selanjutnya, buat sebuah instance dari`Spreadsheet2003SaveOptions` yang memungkinkan kita menyesuaikan kolom tampilan tugas:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Langkah 3: Tentukan Kolom Kustom

 Sekarang, tentukan kolom khusus Anda dengan membuat sebuah instance`AssignmentViewColumn`. Kelas ini memerlukan nama kolom, lebar, dan fungsi delegasi untuk mengubah data tugas menjadi teks kolom:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Langkah 4: Tambahkan Kolom Kustom ke Opsi

Tambahkan kolom kustom ke kumpulan kolom tampilan tugas dari opsi penyimpanan:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Langkah 5: Ulangi Melalui Penugasan

Ulangi setiap penetapan sumber daya dalam proyek dan tampilkan teks kolom khusus:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Langkah 6: Simpan Proyek dengan Kolom Kustom

Terakhir, simpan proyek dengan kolom tampilan tugas khusus:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menambahkan kolom tampilan penugasan kustom menggunakan Aspose.Tasks untuk .NET. Kolom khusus menawarkan fleksibilitas dalam menampilkan informasi tambahan yang disesuaikan dengan kebutuhan proyek Anda, sehingga meningkatkan kemampuan manajemen proyek.

## FAQ

### Q1: Dapatkah saya menambahkan beberapa kolom khusus ke tampilan tugas?

 A1: Ya, Anda dapat menambahkan beberapa kolom khusus dengan membuat instance tambahan`AssignmentViewColumn` dan menambahkannya ke`Columns` koleksi.

### Q2: Apakah ada konverter standar yang tersedia untuk bidang tugas umum?

A2: Ya, Aspose.Tasks menyediakan konverter yang telah ditentukan sebelumnya untuk bidang penugasan umum, sehingga lebih mudah mengekstrak data untuk kolom khusus.

### Q3: Dapatkah saya menyesuaikan tampilan kolom khusus, seperti memformat teks atau menerapkan gaya?

A3: Ya, Anda dapat menyesuaikan tampilan kolom kustom dengan memodifikasi properti seperti lebar, font, dan perataan.

### Q4: Apakah mungkin untuk menghapus kolom default dari tampilan tugas?

 A4: Ya, Anda dapat menghapus kolom default dengan mengecualikannya dari`Columns` mengumpulkan atau mengatur lebarnya ke nol.

### Q5: Apakah Aspose.Tasks mendukung ekspor proyek ke format lain selain spreadsheet dengan kolom khusus?

A5: Ya, Aspose.Tasks mendukung ekspor proyek ke berbagai format seperti PDF, HTML, dan XML, memungkinkan opsi pelaporan proyek serbaguna.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
