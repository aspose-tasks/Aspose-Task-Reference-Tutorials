---
title: Bekerja dengan Periode Ketersediaan di Aspose.Tasks
linktitle: Bekerja dengan Periode Ketersediaan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola periode ketersediaan sumber daya secara efisien menggunakan Aspose.Tasks untuk .NET. Tutorial ini memberikan panduan langkah demi langkah untuk bekerja dengan periode ketersediaan di proyek .NET Anda.
type: docs
weight: 17
url: /id/net/advanced-features/working-with-availability-periods/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara bekerja dengan periode ketersediaan di Aspose.Tasks untuk .NET. Periode ketersediaan sangat penting untuk mengelola sumber daya secara efisien dalam skenario manajemen proyek. Kami akan memandu Anda melalui proses langkah demi langkah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Instal Visual Studio atau IDE pilihan lainnya untuk pengembangan .NET.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar pemrograman C#: Keakraban dengan dasar-dasar bahasa pemrograman C# akan sangat membantu.

## Impor Namespace

Sebelum mendalami kode, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Mari kita pecahkan kode contoh menjadi beberapa langkah:

## Langkah 1: Buat instance Proyek baru

```csharp
var project = new Project();
```

Baris ini menginisialisasi instance baru dari kelas Project, yang mewakili proyek di Aspose.Tasks.

## Langkah 2: Tambahkan Sumber Daya

```csharp
var resource = project.Resources.Add("Work Resource");
```

Di sini, kami menambahkan sumber daya baru ke proyek dengan nama "Sumber Daya Kerja".

## Langkah 3: Tentukan Periode Ketersediaan

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Kami memanggil`GetPeriods()` metode untuk mengambil kumpulan periode ketersediaan.

## Langkah 4: Tambahkan Periode Ketersediaan ke Sumber Daya

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Kami mengulangi kumpulan periode ketersediaan yang diperoleh pada langkah sebelumnya dan menambahkannya ke sumber daya.

## Langkah 5: Tampilkan Detail Periode Ketersediaan

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Terakhir, kami menelusuri periode ketersediaan yang terkait dengan sumber daya dan mencetak detailnya, termasuk tanggal mulai, tanggal akhir, dan unit yang tersedia.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara bekerja dengan periode ketersediaan di Aspose.Tasks untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat mengelola ketersediaan sumber daya secara efisien dalam aplikasi manajemen proyek Anda.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Tasks untuk .NET dalam proyek komersial?

 A1: Ya, Aspose.Tasks untuk .NET dapat digunakan dalam proyek komersial. Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).

### Q2: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?

 A2: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?

 A3: Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

 A4: Anda bisa mendapatkan dukungan dari forum komunitas.[Di Sini](https://forum.aspose.com/c/tasks/15).

### Q5: Apakah Anda menawarkan lisensi sementara untuk Aspose.Tasks untuk .NET?

 A5: Ya, lisensi sementara tersedia[Di Sini](https://purchase.aspose.com/temporary-license/).