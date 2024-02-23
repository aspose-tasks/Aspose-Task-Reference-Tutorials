---
title: Menangani Pengecualian Ukuran Tidak Valid untuk Bitmap di Aspose.Tasks
linktitle: Menangani Pengecualian Ukuran Tidak Valid untuk Bitmap di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani BitmapInvalidSizeException di Aspose.Tasks untuk .NET saat menyimpan proyek sebagai gambar. Tutorial komprehensif dengan panduan langkah demi langkah.
type: docs
weight: 22
url: /id/net/advanced-features/bitmap-invalid-size-exception/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari penanganannya`BitmapInvalidSizeException` saat bekerja dengan Aspose.Tasks untuk .NET. Aspose.Tasks adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram, memungkinkan tugas seperti menyimpan proyek sebagai gambar. Namun, terkadang, saat mencoba menyimpan proyek sebagai gambar, kami mungkin menemui masalah`Invalid Size Exception` terkait dengan bitmap. Tutorial ini bertujuan untuk memandu Anda melalui proses menangkap dan menangani pengecualian ini secara efektif.

## Prasyarat

Sebelum melanjutkan tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Pemahaman dasar bahasa pemrograman C#.
2. Menginstal Aspose.Tasks untuk .NET.
3. Keakraban dengan bekerja dengan file Microsoft Project.

## Impor Namespace

Sebelum memulai, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Langkah 1: Inisialisasi Proyek dan Tentukan Tampilan

 Pertama, inisialisasi a`Project` objek dan menentukan tampilan, seperti`GanttChartView`.

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## Langkah 2: Tentukan Opsi Penyimpanan Gambar

Selanjutnya, tentukan opsi untuk menyimpan gambar, termasuk format dan skala waktu.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## Langkah 3: Tetapkan Satuan dan Hitungan Skala Waktu

Sesuaikan unit skala waktu dan hitung sesuai kebutuhan Anda. Dalam contoh ini, kami menetapkan skala waktu menjadi menit.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Langkah 4: Simpan Proyek sebagai Gambar

Cobalah untuk menyimpan proyek sebagai gambar menggunakan opsi yang ditentukan.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Langkah 5: Tangkap dan Tangani Pengecualian

 Terapkan penanganan pengecualian untuk menangkap`BitmapInvalidSizeException` jika itu terjadi selama proses penyimpanan gambar.

```csharp
try
{
    // Cobalah untuk menyimpan proyek sebagai gambar
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Tangani pengecualian tersebut
    Console.WriteLine(ex.Message);
}
```

## Kesimpulan

 Kesimpulannya, penanganannya`BitmapInvalidSizeException` saat menyimpan proyek sebagai gambar di Aspose.Tasks untuk .NET sangat penting untuk memastikan kelancaran pelaksanaan aplikasi Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menangkap dan menangani pengecualian ini secara efektif, sehingga meningkatkan ketahanan solusi manajemen proyek Anda.

## FAQ

### Q1: Apa yang menyebabkan BitmapInvalidSizeException di Aspose.Tasks?

A1: Pengecualian ini terjadi ketika mencoba menyimpan proyek sebagai gambar dengan parameter ukuran bitmap yang tidak valid.

### Q2: Dapatkah saya menyesuaikan skala waktu saat menyimpan proyek sebagai gambar?

A2: Ya, Anda dapat menyesuaikan satuan skala waktu dan menghitung sesuai kebutuhan Anda, seperti yang ditunjukkan dalam tutorial.

### Q3: Di mana saya dapat menemukan lebih banyak sumber daya untuk bekerja dengan Aspose.Tasks untuk .NET?

A3: Anda dapat menjelajahi dokumentasi dan forum dukungan yang disediakan oleh Aspose.Tasks untuk panduan dan bantuan yang komprehensif.

### Q4: Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?

A4: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, memungkinkan interoperabilitas yang lancar.

### Q5: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks?

A5: Anda dapat memperoleh lisensi sementara untuk tujuan evaluasi melalui tautan yang disediakan di artikel.