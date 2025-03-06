---
title: Bekerja dengan Koleksi Baseline di Aspose.Tasks
linktitle: Bekerja dengan Koleksi Baseline di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola garis dasar di Aspose.Tasks untuk .NET secara efisien. Ikuti tutorial komprehensif kami untuk panduan langkah demi langkah.
weight: 20
url: /id/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bekerja dengan Koleksi Baseline di Aspose.Tasks

## Perkenalan

Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project di aplikasi .NET mereka dengan lancar. Di antara banyak fiturnya, ini memberikan dukungan kuat untuk mengelola baseline dalam proyek. Garis dasar sangat penting untuk manajemen proyek karena memungkinkan Anda membandingkan rencana proyek awal dengan status saat ini, sehingga memungkinkan pelacakan dan analisis kemajuan proyek yang lebih baik.

## Prasyarat

Sebelum kita mulai bekerja dengan koleksi dasar di Aspose.Tasks, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Instal Visual Studio IDE di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar C#: Biasakan diri Anda dengan bahasa pemrograman C#.
4. File Microsoft Project: Siapkan file Microsoft Project (.mpp) untuk tujuan pengujian.

## Impor Namespace

Untuk mulai bekerja dengan koleksi dasar di Aspose.Tasks, Anda perlu mengimpor namespace berikut:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:

## Langkah 1: Muat File Proyek

Pertama, muat file Microsoft Project menggunakan Aspose.Tasks:

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Langkah 2: Dapatkan Sumber Daya

Selanjutnya, ambil sumber daya yang diinginkan dari proyek:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Langkah 3: Tampilkan Informasi Dasar

Sekarang, tampilkan informasi tentang garis dasar yang terkait dengan sumber daya:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Langkah 4: Ulangi Melalui Garis Dasar

Ulangi setiap garis dasar yang terkait dengan sumber daya dan cetak informasi yang relevan:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Langkah 5: Hapus Garis Dasar

Hapus semua garis dasar yang terkait dengan sumber daya:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara bekerja dengan koleksi dasar di Aspose.Tasks untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengelola garis dasar dalam aplikasi .NET Anda, sehingga memungkinkan pelacakan dan analisis proyek yang efektif.

## FAQ

### Q1: Bisakah Aspose.Tasks menangani file proyek besar?

A1: Ya, Aspose.Tasks dioptimalkan untuk menangani file proyek besar secara efisien, memastikan kinerja lancar.

### Q2: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?

A2: Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### Q3: Dapatkah saya menyesuaikan garis dasar di Aspose.Tasks?

A3: Ya, Anda dapat menyesuaikan garis dasar sesuai dengan kebutuhan proyek Anda menggunakan Aspose.Tasks untuk .NET.

### Q4: Apakah Aspose.Tasks menawarkan dukungan untuk platform cloud?

A4: Ya, Aspose.Tasks memberikan dukungan untuk integrasi dengan platform cloud populer, menawarkan fleksibilitas dalam penerapan.

### Q5: Apakah ada forum komunitas bagi pengguna Aspose.Tasks untuk mencari bantuan dan berbagi pengetahuan?

 A5: Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk terlibat dengan masyarakat dan mendapatkan bantuan dari para ahli.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
