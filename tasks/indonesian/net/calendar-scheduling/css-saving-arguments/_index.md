---
title: Argumen Menyimpan CSS di Aspose.Tasks
linktitle: Argumen Menyimpan CSS di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan argumen CSS di Aspose.Tasks untuk .NET guna menyesuaikan keluaran HTML. Sempurnakan presentasi dengan pengaturan CSS yang disesuaikan.
weight: 20
url: /id/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Argumen Menyimpan CSS di Aspose.Tasks

## Perkenalan

Dalam tutorial ini, kita akan mempelajari proses menyimpan argumen CSS menggunakan Aspose.Tasks untuk .NET. Cascading Style Sheets (CSS) sangat penting untuk mendefinisikan presentasi elemen HTML. Aspose.Tasks memungkinkan kita memanipulasi dan menyimpan atribut CSS ini secara efisien.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  Instalasi: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/tasks/net/).

2. Pengetahuan Dasar: Keakraban dengan lingkungan pengembangan C# dan .NET dianjurkan.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Langkah 1: Tentukan Panggilan Balik Penghematan CSS

Pertama, kita mendefinisikan metode callback penyimpanan CSS untuk menangani penyimpanan file CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Terapkan logika penyimpanan CSS Anda di sini
    }
}
```

## Langkah 2: Terapkan Panggilan Balik Penghematan Font dan Gambar

Selanjutnya, terapkan metode callback penyimpanan font dan gambar dengan cara yang sama:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Terapkan logika penyimpanan font Anda di sini
}

public void ImageSaving(ImageSavingArgs args)
{
    // Terapkan logika penyimpanan gambar Anda di sini
}
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan

Sekarang, konfigurasikan opsi penyimpanan HTML untuk memanfaatkan callback yang diterapkan:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Konfigurasikan opsi penyimpanan HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Langkah 4: Simpan Proyek dengan CSS Khusus

Terakhir, simpan proyek Anda dengan pengaturan CSS yang disesuaikan:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara menyimpan argumen CSS menggunakan Aspose.Tasks untuk .NET. Dengan menentukan callback penyimpanan CSS dan mengonfigurasi opsi penyimpanan HTML, kita dapat memanipulasi atribut CSS secara efisien sesuai dengan kebutuhan kita.

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

A1: Aspose.Tasks untuk .NET adalah .NET API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram.

### Q2: Bisakah saya menyesuaikan atribut CSS saat menyimpan file HTML dengan Aspose.Tasks?

A2: Ya, Anda dapat menentukan callback penyimpanan CSS untuk menyesuaikan atribut CSS sesuai kebutuhan Anda.

### Q3: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi file Microsoft Project?

A3: Aspose.Tasks untuk .NET mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### Q4: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks untuk .NET?

A4: Anda dapat merujuk ke[dokumentasi](https://reference.aspose.com/tasks/net/) untuk informasi rinci dan contoh.

### Q5: Apakah Aspose.Tasks untuk .NET menawarkan dukungan untuk pengembang?

 A5: Ya, Anda bisa mendapatkan dukungan dari komunitas Aspose.Tasks melalui[forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
