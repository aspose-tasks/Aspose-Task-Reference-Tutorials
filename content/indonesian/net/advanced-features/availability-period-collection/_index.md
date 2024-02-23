---
title: Kumpulan Periode Ketersediaan di Aspose.Tasks
linktitle: Kumpulan Periode Ketersediaan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola periode ketersediaan sumber daya di Aspose.Tasks untuk .NET. Tutorial langkah demi langkah ini memandu Anda dalam menambahkan, memperbarui, dan menghapus periode ketersediaan, memastikan perencanaan sumber daya proyek yang efektif.
type: docs
weight: 18
url: /id/net/advanced-features/availability-period-collection/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara bekerja dengan kumpulan periode ketersediaan sumber daya di Aspose.Tasks untuk .NET. Mengelola periode ketersediaan sangat penting untuk manajemen proyek, memungkinkan kita menentukan kapan sumber daya tersedia untuk tugas-tugas dalam suatu proyek.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman Dasar: Keakraban dengan kerangka C# dan .NET.

## Impor Namespace

Pertama, kita perlu mengimpor namespace yang diperlukan ke proyek kita:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Mari kita pecahkan kode contoh menjadi beberapa langkah dan pahami setiap bagiannya:

## Langkah 1: Inisialisasi Proyek dan Sumber Daya

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Di sini, kami memuat file proyek dan mendapatkan sumber daya tertentu berdasarkan ID-nya.

## Langkah 2: Hapus Periode Ketersediaan yang Ada

```csharp
resource.AvailabilityPeriods.Clear();
```

Kami menghapus semua periode ketersediaan yang terkait dengan sumber daya.

## Langkah 3: Tambahkan Periode Ketersediaan

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Kami mengulangi kumpulan periode ketersediaan dan menambahkannya ke sumber daya.

## Langkah 4: Masukkan Periode Ketersediaan Baru

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Kami membuat periode ketersediaan baru untuk tahun 2013 dan memasukkannya ke dalam koleksi.

## Langkah 5: Tampilkan Periode Ketersediaan

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Kami mencetak jumlah dan rincian setiap periode ketersediaan yang terkait dengan sumber daya.

## Langkah 6: Salin Periode Ketersediaan ke Sumber Daya Lain

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Kami menyalin periode ketersediaan dari satu sumber daya ke sumber daya lainnya.

## Langkah 7: Perbarui dan Hapus Periode Ketersediaan

```csharp
// Perbarui unit yang tersedia untuk periode tertentu
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Hapus periode tertentu
otherResource.AvailabilityPeriods.Remove(period2013);
```

Kami memperbarui unit yang tersedia untuk suatu periode dan menghapus periode tertentu dari koleksi.

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara bekerja dengan koleksi periode ketersediaan di Aspose.Tasks untuk .NET. Mengelola ketersediaan sumber daya sangat penting untuk perencanaan dan pelaksanaan proyek yang efektif.

## FAQ

### Q1: Bisakah saya menambahkan kolom khusus ke periode ketersediaan?

A1: Tidak, periode ketersediaan di Aspose.Tasks untuk .NET tidak mendukung bidang khusus.

### Q2: Apakah periode ketersediaan terkait dengan tugas tertentu?

A2: Tidak, periode ketersediaan dikaitkan dengan sumber daya dan menentukan kapan sumber daya tersebut tersedia untuk tugas secara umum.

### Q3: Dapatkah saya mengimpor periode ketersediaan dari sumber eksternal?

A3: Ya, Anda dapat mengimpor periode ketersediaan dari berbagai sumber data menggunakan Aspose.Tasks untuk .NET API.

### Q4: Bagaimana cara menangani periode ketersediaan yang tumpang tindih?

A4: Aspose.Tasks untuk .NET tidak menyediakan mekanisme bawaan untuk menangani periode yang tumpang tindih. Anda mungkin perlu menerapkan logika khusus untuk mengelola skenario tersebut.

### Q5: Apakah ada batasan jumlah periode ketersediaan yang dimiliki suatu sumber daya?

A5: Tidak ada batasan yang ditentukan sebelumnya mengenai jumlah periode ketersediaan sumber daya, namun kinerja dapat menurun seiring dengan banyaknya periode.