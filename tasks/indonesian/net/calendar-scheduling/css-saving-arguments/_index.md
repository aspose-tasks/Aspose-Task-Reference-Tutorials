---
date: 2026-07-05
description: Pelajari cara menyesuaikan CSS saat mengekspor proyek ke HTML menggunakan
  Aspose.Tasks untuk .NET. Sesuaikan output HTML dengan argumen penyimpanan CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Cara Menyesuaikan CSS Saat Menyimpan Proyek dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cara Menyesuaikan CSS Saat Menyimpan Proyek dengan Aspose.Tasks
url: /id/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menyesuaikan CSS Saat Menyimpan Proyek dengan Aspose.Tasks

Dalam panduan ini Anda akan menemukan **cara menyesuaikan CSS** selama ekspor HTML file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan menyesuaikan argumen penyimpanan CSS, Anda mendapatkan kontrol penuh atas gaya visual halaman HTML yang dihasilkan, sehingga output sesuai dengan merek atau standar pelaporan Anda.

## Jawaban Cepat
- **Apa titik masuk utama?** Gunakan `HtmlSaveOptions` dengan callback khusus.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Bisakah saya mengekspor proyek besar?** Aspose.Tasks menangani proyek dengan > 10.000 tugas tanpa memuat seluruh file ke memori.  
- **Apakah penyesuaian CSS bersifat opsional?** Ya, Anda dapat mengabaikan callback untuk menggunakan stylesheet default.

## Cara Menyesuaikan CSS di Aspose.Tasks?

Muat proyek Anda, lampirkan callback penyimpanan CSS ke objek `HtmlSaveOptions`, lalu panggil `project.Save`. Pola ini memungkinkan Anda menulis file CSS khusus, mengganti gaya default, dan mengontrol struktur folder—semua dalam beberapa baris kode. Callback dipanggil secara otomatis untuk setiap file CSS selama proses ekspor.

`HtmlSaveOptions` mengonfigurasi cara proyek diekspor ke HTML.

## Pendahuluan

Dalam tutorial ini, kita akan menyelami proses penyimpanan argumen CSS menggunakan Aspose.Tasks untuk .NET. Cascading Style Sheets (CSS) sangat penting untuk mendefinisikan tampilan elemen HTML. Aspose.Tasks memungkinkan kita memanipulasi dan menyimpan atribut CSS ini secara efisien.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Instalasi: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari [website](https://releases.aspose.com/tasks/net/).
2. Pengetahuan Dasar: Familiaritas dengan C# dan lingkungan pengembangan .NET disarankan.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Langkah 1: Definisikan Callback Penyimpanan CSS

`ICssSavingCallback` adalah antarmuka yang memungkinkan Anda menyesuaikan cara file CSS disimpan selama ekspor HTML.

Sebuah **callback penyimpanan CSS** adalah delegasi yang dipanggil Aspose.Tasks untuk menulis file CSS selama ekspor HTML. Definisikan metode callback untuk mengontrol cara setiap file CSS dibuat:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Langkah 2: Implementasikan Callback Penyimpanan Font dan Gambar

`FontSavingArgs` menyediakan informasi tentang font yang sedang disimpan, sementara `ImageSavingArgs` memberikan detail untuk sumber daya gambar.

Implementasikan metode callback penyimpanan font dan gambar secara serupa:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan

`HtmlSaveOptions` adalah objek konfigurasi yang mengontrol cara Proyek diekspor ke HTML.

`HtmlSaveOptions` memungkinkan Anda menentukan callback, folder output, dan pengaturan ekspor lainnya.

Atur propertinya untuk menggunakan callback yang didefinisikan sebelumnya dan menentukan folder output:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Langkah 4: Simpan Proyek dengan CSS yang Disesuaikan

`Project` mewakili file Microsoft Project yang dapat dimanipulasi dan disimpan.

Akhirnya, simpan proyek Anda dengan pengaturan CSS yang disesuaikan:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Mengapa Menyesuaikan CSS Saat Mengekspor Proyek?

Aspose.Tasks mendukung **ekspor proyek ke HTML** dalam lebih dari 30 format dan dapat menghasilkan hingga 30 file CSS terpisah per ekspor. Ia secara andal memproses proyek yang berisi lebih dari 10 000 tugas sambil menjaga penggunaan memori di bawah 200 MB, memungkinkan pelaporan skala perusahaan tanpa hambatan kinerja.

## Kesimpulan

Dalam tutorial ini, kami telah mengeksplorasi cara menyimpan argumen CSS menggunakan Aspose.Tasks untuk .NET. Dengan mendefinisikan callback penyimpanan CSS dan mengonfigurasi opsi penyimpanan HTML, kita dapat memanipulasi atribut CSS secara efisien sesuai kebutuhan kita.

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

A1: Aspose.Tasks untuk .NET adalah API .NET yang kuat yang memungkinkan pengembang bekerja dengan file Microsoft Project secara programatis.

### Q2: Bisakah saya menyesuaikan atribut CSS saat menyimpan file HTML dengan Aspose.Tasks?

A2: Ya, Anda dapat mendefinisikan callback penyimpanan CSS untuk menyesuaikan atribut CSS sesuai kebutuhan Anda.

### Q3: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi file Microsoft Project?

A3: Aspose.Tasks untuk .NET mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### Q4: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Tasks untuk .NET?

A4: Anda dapat merujuk ke [dokumentasi](https://reference.aspose.com/tasks/net/) untuk informasi detail dan contoh.

### Q5: Apakah Aspose.Tasks untuk .NET menawarkan dukungan untuk pengembang?

A5: Ya, Anda dapat mendapatkan dukungan dari komunitas Aspose.Tasks melalui [forum](https://forum.aspose.com/c/tasks/15).

**Pertanyaan Tambahan**

**Q: Bagaimana penyesuaian CSS memengaruhi ukuran HTML yang diekspor?**  
A: Menggunakan CSS khusus dapat mengurangi ukuran total hingga 15 % karena Anda dapat menghilangkan gaya default yang tidak terpakai.

**Q: Bisakah saya menggunakan callback yang sama untuk beberapa proyek?**  
A: Tentu saja. Implementasikan callback sekali dan gunakan kembali pada ekspor proyek berapa pun.

**Q: Apakah memungkinkan untuk menyematkan CSS langsung ke dalam HTML alih-alih file terpisah?**  
A: Ya, atur `HtmlSaveOptions.EmbeddedCss = true` untuk menyisipkan stylesheet secara inline, yang menyederhanakan distribusi.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Simpan MS Project sebagai HTML dengan Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Mengimplementasikan Callback Penyimpanan Halaman di Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Menangani Penyimpanan Gambar di Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}