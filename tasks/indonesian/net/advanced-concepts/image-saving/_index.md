---
title: Menangani Penyimpanan Gambar di Aspose.Tasks
linktitle: Menangani Penyimpanan Gambar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani penyimpanan gambar di Aspose.Tasks untuk .NET menggunakan panduan langkah demi langkah. Integrasikan fungsionalitas penyimpanan gambar dengan mulus ke dalam aplikasi .NET Anda.
weight: 10
url: /id/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menangani Penyimpanan Gambar di Aspose.Tasks

## Perkenalan

Dalam tutorial ini, kita akan mempelajari proses penanganan penyimpanan gambar di Aspose.Tasks untuk .NET. Aspose.Tasks adalah API canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Salah satu tugas umum saat bekerja dengan file proyek adalah kebutuhan untuk menyimpan gambar, yang dapat mencakup bagan, grafik, atau elemen visual lainnya. Kami akan menguraikan prosesnya langkah demi langkah, memastikan kejelasan dan pemahaman secara menyeluruh.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan ke dalam proyek kita:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Langkah 1: Buat Objek Proyek

Mulailah dengan membuat objek Proyek dari file Microsoft Project Anda:

```csharp
var project = new Project("Project1.mpp");
```

## Langkah 2: Tentukan Opsi Simpan

Tentukan opsi penyimpanan untuk proyek Anda, tentukan halaman dan pengaturan lainnya:

```csharp
var options = GetSaveOptions(1);
```

## Langkah 3: Simpan Proyek sebagai HTML

Simpan proyek sebagai HTML dengan opsi yang ditentukan:

```csharp
project.Save("document_out.html", options);
```

## Langkah 4: Terapkan Panggilan Balik Penghematan Gambar

Implementasikan antarmuka ImageSavingCallback untuk menangani penyimpanan gambar:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Logika penyimpanan gambar ada di sini
    }
}
```

## Langkah 5: Simpan Gambar ke Direktori Tertentu

Dalam metode ImageSaving, tentukan logika untuk menyimpan gambar ke direktori yang diinginkan:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Simpan sumber daya yang disarangkan
}
else
{
    // Hemat sumber daya reguler
}
```

## Langkah 6: Tentukan Opsi Simpan

Tentukan opsi penyimpanan, termasuk callback untuk CSS, font, dan gambar:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Tentukan opsi penyimpanan di sini
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Kesimpulan

Kesimpulannya, menangani penyimpanan gambar di Aspose.Tasks untuk .NET melibatkan penentuan opsi penyimpanan dan penerapan callback untuk mengelola proses penyimpanan secara efektif. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan fungsionalitas penyimpanan gambar ke dalam aplikasi .NET Anda.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Tasks untuk memanipulasi file proyek dalam format lain selain HTML?

A1: Ya, Aspose.Tasks mendukung berbagai format seperti PDF, XLSX, dan MPP.

### Q2: Apakah Aspose.Tasks menyediakan dukungan untuk integrasi penyimpanan cloud?

A2: Ya, Aspose.Tasks menawarkan API untuk bekerja dengan layanan penyimpanan cloud populer seperti Amazon S3 dan Google Drive.

### Q3: Apakah Aspose.Tasks kompatibel dengan .NET Core?

A3: Ya, Aspose.Tasks kompatibel dengan .NET Core, memungkinkan Anda mengembangkan aplikasi lintas platform.

### Q4: Dapatkah saya menyesuaikan tampilan gambar yang disimpan?

A4: Ya, Anda dapat menyesuaikan tampilan gambar yang disimpan dengan memodifikasi logika penyimpanan gambar dalam metode panggilan balik.

### Q5: Apakah Aspose.Tasks menawarkan versi uji coba untuk tujuan evaluasi?

 A5: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
