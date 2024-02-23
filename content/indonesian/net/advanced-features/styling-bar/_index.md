---
title: Styling Bar di Aspose.Tugas
linktitle: Styling Bar di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara menata gaya bar di Aspose.Tasks untuk .NET untuk meningkatkan visualisasi proyek.
type: docs
weight: 19
url: /id/net/advanced-features/styling-bar/
---
## Perkenalan

Styling bar di Aspose.Tasks adalah aspek penting dalam membuat rencana proyek yang menarik secara visual. Dengan fleksibilitas yang ditawarkan oleh Aspose.Tasks API, pengembang dapat menyesuaikan berbagai aspek bilah, seperti warna, bentuk, dan gaya teks, untuk meningkatkan visualisasi proyek. Dalam tutorial ini, kita akan menjelajahi cara menata gaya bar menggunakan Aspose.Tasks untuk .NET, mengelompokkan setiap contoh menjadi langkah-langkah yang dapat dikelola.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Unduh Halaman](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan dukungan kerangka .NET.
3. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk mengakses kelas dan metode Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Langkah 1: Muat Proyek

Untuk memulai, muat file proyek menggunakan Aspose.Tasks API:

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Langkah 2: Konfigurasikan Opsi Penyimpanan

Tentukan opsi penyimpanan, tentukan gaya bilah yang akan diterapkan:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Langkah 3: Tentukan Gaya Batang

Buat gaya bar baru dan sesuaikan propertinya:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Tetapkan jenis item bilah
style.BarColor = Color.Green; // Atur warna batang
style.BarShape = BarShape.HalfHeight; //Atur bentuk batang
style.StartShape = Shape.LeftBracket; // Tetapkan bentuk di awal bar
style.StartShapeColor = Color.Aqua; // Tetapkan warna bentuk awal
style.EndShape = Shape.RightBracket; // Tetapkan bentuk di ujung bilah
style.EndShapeColor = Color.Aquamarine; // Atur warna bentuk akhir
style.TextStyle = new TextStyle(); // Atur gaya teks
style.TextStyle.BackgroundColor = Color.Black; // Atur warna latar belakang untuk teks
```

## Langkah 4: Sesuaikan Konverter Teks

Secara opsional, sesuaikan konverter teks untuk mengubah rendering teks:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Langkah 5: Tambahkan Gaya Batang ke Opsi

Tambahkan gaya bilah yang dikonfigurasi ke opsi penyimpanan:

```csharp
options.BarStyles.Add(style);
```

## Langkah 6: Simpan Proyek

Terakhir, simpan proyek dengan gaya bilah yang diterapkan:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Kesimpulan

Menyesuaikan gaya bilah di Aspose.Tasks untuk .NET memberi pengembang kemampuan untuk membuat rencana proyek yang menarik secara visual. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menata gaya bar secara efisien untuk memenuhi persyaratan visualisasi proyek tertentu.

## FAQ

### Q1: Bisakah saya menerapkan beberapa gaya batang ke satu proyek?

A1: Ya, Anda dapat menentukan dan menerapkan beberapa gaya batang ke berbagai jenis tugas dalam proyek yang sama.
   
### Q2: Apakah mungkin mengubah gaya bilah secara dinamis selama runtime?

A2: Ya, Anda dapat mengubah gaya bilah secara dinamis berdasarkan kondisi atau preferensi pengguna tertentu dalam aplikasi Anda.
   
### Q3: Apakah Aspose.Tasks mendukung ekspor proyek dengan bilah gaya ke format file berbeda?

A3: Ya, Aspose.Tasks mendukung ekspor proyek dengan bilah gaya ke berbagai format seperti PDF, XLSX, dan HTML.
   
### Q4: Apakah ada gaya bilah standar yang tersedia di Aspose.Tasks?

A4: Meskipun Aspose.Tasks menyediakan gaya bilah default, pengembang juga dapat membuat gaya bilah kustom yang disesuaikan dengan kebutuhan proyek mereka.
   
### Q5: Bisakah saya mengambil dan memodifikasi gaya batang yang ada dalam proyek menggunakan API?

A5: Ya, Anda dapat mengambil dan memodifikasi gaya batang yang ada secara terprogram menggunakan Aspose.Tasks untuk .NET API.