---
title: Kumpulkan Proyek MS Bagian Terpisah di Aspose.Tasks
linktitle: Kumpulan Bagian Terpisah di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengumpulkan bagian terpisah di MS Project menggunakan Aspose.Tasks untuk .NET. Tutorial komprehensif ini memandu Anda melalui proses langkah demi langkah.
type: docs
weight: 19
url: /id/net/rate-recurring-tasks/split-part-collection/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengumpulkan bagian-bagian yang terpisah di MS Project menggunakan Aspose.Tasks untuk .NET. Membagi tugas menjadi beberapa bagian dapat menjadi aspek penting dalam manajemen proyek, dan Aspose.Tasks menyediakan metode mudah untuk menangani hal ini secara efisien.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Pemasangan Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat karena kita akan menulis cuplikan kode dalam C#.

## Impor Namespace
Dalam proyek C# Anda, sertakan namespace yang diperlukan:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Langkah 1: Siapkan Proyek Anda
Pertama, buat proyek baru di IDE pilihan Anda dan pastikan Aspose.Tasks untuk .NET direferensikan dengan benar.
## Langkah 2: Inisialisasi Objek Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inisialisasi objek Proyek baru dengan jalur ke file MS Project Anda.
## Langkah 3: Ambil Tugas dan Ulangi Bagian yang Terpisah
```csharp
var task = project.RootTask.Children.GetById(1);
// Ulangi bagian yang terpisah
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Ambil tugas dari proyek dan ulangi bagian-bagiannya yang terpisah, cetak tanggal mulai dan selesainya.
## Langkah 4: Dapatkan Pisahkan Bagian berdasarkan Indeks
```csharp
// Dapatkan bagian berdasarkan indeks
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Ambil bagian terpisah tertentu berdasarkan indeks dan cetak tanggal mulainya.

## Kesimpulan
Mengelola bagian yang terpisah dalam file MS Project dapat meningkatkan efisiensi manajemen proyek secara signifikan. Aspose.Tasks untuk .NET menyederhanakan proses ini dengan menyediakan API intuitif untuk menangani tugas terpisah dengan lancar.
## FAQ
### T: Dapatkah saya membagi tugas secara dinamis selama runtime?
J: Ya, Anda dapat membagi tugas secara terprogram menggunakan Aspose.Tasks untuk .NET.
### T: Apakah Aspose.Tasks mendukung semua versi file MS Project?
J: Aspose.Tasks mendukung berbagai versi file MS Project, memastikan kompatibilitas di berbagai platform.
### T: Apakah ada versi uji coba yang tersedia untuk tujuan pengujian?
 J: Ya, Anda bisa mendapatkan versi uji coba gratis dari[Di Sini](https://releases.aspose.com/) untuk evaluasi.
### T: Bagaimana cara mendapatkan lisensi sementara untuk proyek saya?
 J: Lisensi sementara dapat diperoleh dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk penggunaan jangka pendek.
### T: Di mana saya dapat mencari bantuan atau dukungan mengenai Aspose.Tasks?
 J: Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk mencari bantuan dari komunitas atau tim dukungan Aspose.