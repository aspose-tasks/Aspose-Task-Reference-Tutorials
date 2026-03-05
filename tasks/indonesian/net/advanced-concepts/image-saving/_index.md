---
date: 2026-03-05
description: Pelajari cara menyimpan gambar, menghasilkan HTML dengan gambar, dan
  menyesuaikan ekspor gambar menggunakan Aspose.Tasks untuk .NET. Panduan langkah
  demi langkah untuk menyimpan proyek sebagai HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cara Menyimpan Gambar dengan Aspose.Tasks untuk .NET
url: /id/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menyimpan Gambar dengan Aspose.Tasks untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan menemukan **cara menyimpan gambar** dari file Microsoft Project menggunakan API Aspose.Tasks untuk .NET. Apakah Anda perlu menyematkan diagram dalam laporan, menghasilkan halaman HTML yang berisi visual proyek, atau sekadar mengekspor sumber daya diagram, langkah‑langkah di bawah ini akan memandu Anda melalui seluruh proses—dari menyiapkan objek proyek hingga menyesuaikan callback ekspor gambar.

## Jawaban Cepat
- **Apa arti “cara menyimpan gambar” dalam Aspose.Tasks?**  
  Ini merujuk pada penggunaan antarmuka `IImageSavingCallback` untuk mengontrol dimana dan bagaimana sumber daya visual ditulis ke disk.
- **Apakah saya dapat menyimpan proyek sebagai HTML dengan gambar tersemat?**  
  Ya, dengan menggunakan `HtmlSaveOptions` bersama dengan callback penyimpanan gambar Anda dapat **menyimpan proyek sebagai HTML** yang mencakup semua gambar yang dihasilkan.
- **Apakah saya memerlukan lisensi untuk ekspor gambar?**  
  Lisensi evaluasi sementara berfungsi untuk pengujian; lisensi penuh diperlukan untuk penggunaan produksi.
- **Versi .NET mana yang didukung?**  
  Aspose.Tasks untuk .NET mendukung .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.
- **Apakah memungkinkan untuk menyesuaikan ekspor gambar (format, folder, penamaan)?**  
  Tentu – callback memberikan Anda kontrol penuh atas nama file, format, dan tujuan.

## Apa itu “cara menyimpan gambar” dalam konteks Aspose.Tasks?

Menyimpan gambar berarti mengekstrak elemen visual (diagram, batang Gantt, grafik sumber daya) dari file Project dan menuliskannya ke file gambar (PNG, JPEG, dll.). Aspose.Tasks menyediakan mekanisme callback yang fleksibel yang memungkinkan Anda menentukan lokasi tepat, konvensi penamaan, bahkan format gambar.

## Mengapa menggunakan Aspose.Tasks untuk menyimpan gambar?

- **Kontrol programatik penuh** – tidak memerlukan interaksi UI manual.  
- **Cross‑platform** – berfungsi di Windows, Linux, dan macOS melalui .NET Core.  
- **Rendering fidelity tinggi** – gambar mempertahankan kualitas yang sama dengan tampilan Project asli.  
- **Generasi HTML mudah** – gabungkan `HtmlSaveOptions` dengan callback gambar untuk **menghasilkan HTML dengan gambar** secara otomatis.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. Visual Studio terpasang pada mesin pengembangan Anda.  
2. Aspose.Tasks untuk .NET diunduh dari [here](https://releases.aspose.com/tasks/net/).  
3. Familiaritas dasar dengan C# dan struktur proyek .NET.

## Impor Namespace

Pertama, bawa namespace yang diperlukan ke dalam file sumber Anda:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Langkah 1: Buat Objek Project

Muat file Microsoft Project yang ingin Anda kerjakan:

```csharp
var project = new Project("Project1.mpp");
```

## Langkah 2: Tentukan Opsi Penyimpanan

Buat opsi penyimpanan HTML yang juga akan menampung callback penyimpanan gambar kami:

```csharp
var options = GetSaveOptions(1);
```

## Langkah 3: Simpan Project sebagai HTML (save project as html)

Sekarang ekspor proyek ke file HTML. Gambar‑gambar yang dirujuk dalam HTML akan dihasilkan oleh callback yang akan kami definisikan selanjutnya:

```csharp
project.Save("document_out.html", options);
```

## Langkah 4: Implementasikan Callback Penyimpanan Gambar (customize image export)

Implementasikan antarmuka `IImageSavingCallback`. Di sinilah Anda **menyesuaikan perilaku ekspor gambar**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Langkah 5: Simpan Gambar ke Direktori yang Ditentukan

Di dalam metode `ImageSaving`, tentukan dimana setiap gambar harus disimpan. Contoh di bawah membedakan sumber daya PNG dari format lain:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Langkah 6: Tentukan Opsi Penyimpanan (including callbacks)

Hubungkan callback untuk font, CSS, dan gambar. Ini memastikan setiap elemen visual ditangani secara konsisten:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Gambar tidak muncul di HTML yang dihasilkan | Callback tidak menetapkan jalur file yang valid | Pastikan `args.Path` mengarah ke folder yang dapat ditulisi dan set `args.ImageStream` dengan benar. |
| File PNG disimpan dengan ekstensi yang salah | Logika kondisional hanya memeriksa akhiran “png” | Gunakan `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` untuk deteksi yang lebih kuat. |
| Referensi HTML rusak setelah memindahkan file | Path relatif berubah setelah memindahkan folder output | Simpan folder HTML dan gambar bersama-sama atau perbarui `options.ImageFolder` sesuai. |

## Kesimpulan

Dengan mengikuti langkah‑langkah ini Anda kini tahu **cara menyimpan gambar** dari file Project, **menyimpan proyek sebagai HTML**, dan **menyesuaikan ekspor gambar** agar sesuai dengan struktur folder aplikasi Anda. Pendekatan ini memungkinkan Anda **menghasilkan HTML dengan gambar** yang dapat disematkan dalam laporan, portal dokumentasi, atau dasbor web secara mulus.

## Pertanyaan yang Sering Diajukan

**Q1: Apakah saya dapat menggunakan Aspose.Tasks untuk memanipulasi file proyek dalam format lain selain HTML?**  
A1: Ya, Aspose.Tasks mendukung berbagai format seperti PDF, XLSX, dan MPP.

**Q2: Apakah Aspose.Tasks menyediakan dukungan untuk integrasi penyimpanan cloud?**  
A2: Ya, Aspose.Tasks menawarkan API untuk bekerja dengan layanan penyimpanan cloud populer seperti Amazon S3 dan Google Drive.

**Q3: Apakah Aspose.Tasks kompatibel dengan .NET Core?**  
A3: Ya, Aspose.Tasks kompatibel dengan .NET Core, memungkinkan Anda mengembangkan aplikasi lintas‑platform.

**Q4: Apakah saya dapat menyesuaikan tampilan gambar yang disimpan?**  
A4: Ya, Anda dapat menyesuaikan tampilan gambar yang disimpan dengan memodifikasi logika penyimpanan gambar dalam metode callback.

**Q5: Apakah Aspose.Tasks menawarkan versi percobaan untuk tujuan evaluasi?**  
A5: Ya, Anda dapat memperoleh percobaan gratis Aspose.Tasks dari [here](https://releases.aspose.com/).

**Terakhir Diperbarui:** 2026-03-05  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}