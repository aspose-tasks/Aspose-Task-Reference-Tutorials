---
title: Sesuaikan Kolom Tampilan Sumber Daya Proyek MS di Aspose.Tasks
linktitle: Menyesuaikan Kolom Tampilan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengkustomisasi kolom tampilan sumber daya MS Project secara efisien menggunakan Aspose.Tasks untuk .NET. Buat tampilan yang disesuaikan untuk manajemen proyek yang lebih baik.
weight: 17
url: /id/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sesuaikan Kolom Tampilan Sumber Daya Proyek MS di Aspose.Tasks

## Perkenalan
Aspose.Tasks untuk .NET adalah API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram. Salah satu tugas umum dalam manajemen proyek adalah menyesuaikan tampilan untuk menampilkan informasi spesifik. Dalam tutorial ini, kita akan mempelajari cara mengkustomisasi kolom tampilan sumber daya MS Project menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks untuk .NET Library: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. File Proyek Microsoft: Miliki contoh file Proyek MS yang berguna untuk pengujian.
3. Lingkungan Pengembangan: Lingkungan pengembangan yang diatur dengan kerangka .NET.
## Impor Namespace
Pertama, mari impor namespace yang diperlukan ke proyek kita:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Langkah 1: Muat File Proyek
Muat file MS Project menggunakan Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Langkah 2: Dapatkan Sumber Daya dan Tentukan Opsi
Selanjutnya, dapatkan sumber daya yang kolom tampilannya ingin Anda sesuaikan dan tentukan opsi penyimpanan PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Langkah 3: Tentukan Kolom Kustom
Sekarang, tentukan kolom khusus untuk tampilan sumber daya. Anda dapat menentukan berbagai bidang dan bahkan menggunakan delegasi untuk penghitungan khusus:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Langkah 4: Ulangi Kolom
Ulangi kolom yang ditentukan dan tampilkan propertinya:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Langkah 5: Simpan Tampilan Khusus
Terakhir, atur tampilan khusus dan simpan sebagai file PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Dengan mengikuti langkah-langkah ini, Anda dapat mengkustomisasi kolom tampilan sumber daya MS Project secara efisien menggunakan Aspose.Tasks untuk .NET.
## Kesimpulan
Menyesuaikan kolom tampilan sumber daya Proyek MS sangat penting untuk menampilkan informasi relevan yang disesuaikan dengan kebutuhan proyek Anda. Dengan Aspose.Tasks untuk .NET, tugas ini menjadi mudah dan efisien, memungkinkan Anda membuat tampilan yang disesuaikan dengan mudah.
## FAQ
### Bisakah saya menyesuaikan tampilan untuk elemen lain selain sumber daya?
Ya, Aspose.Tasks juga memungkinkan penyesuaian untuk tugas, tugas, dan elemen proyek lainnya.
### Apakah Aspose.Tasks mendukung penyimpanan tampilan dalam format selain PDF?
Ya, Anda dapat menyimpan tampilan dalam berbagai format seperti XLSX, HTML, dan gambar.
### Apakah mungkin untuk menerapkan pemformatan ke tampilan khusus?
Tentu saja, Aspose.Tasks menyediakan opsi pemformatan ekstensif untuk menyempurnakan tampilan tampilan kustom Anda.
### Bisakah saya memperbarui tampilan kustom secara dinamis berdasarkan perubahan data proyek?
Ya, Anda dapat memperbarui dan membuat ulang tampilan kustom setiap kali data proyek yang mendasarinya berubah.
### Apakah Aspose.Tasks mendukung pengembangan lintas platform?
Aspose.Tasks untuk .NET terutama menargetkan platform .NET, namun ada juga versi yang tersedia untuk Java dan platform lainnya.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
