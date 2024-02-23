---
title: Ketik Perhitungan di Aspose.Tasks
linktitle: Ketik Perhitungan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengkustomisasi perhitungan nilai dalam proyek .NET dengan Jenis Perhitungan di perpustakaan Aspose.Tasks.
type: docs
weight: 30
url: /id/net/advanced-features/calculation-type/
---
## Perkenalan

Dalam tutorial ini, kita akan menjelajahi fitur Jenis Perhitungan di Aspose.Tasks untuk .NET. Aspose.Tasks adalah perpustakaan canggih yang memungkinkan pengembang .NET bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project di sistem mereka. Jenis Perhitungan memungkinkan kita menentukan bagaimana nilai dihitung untuk tugas dan ringkasan tugas dalam suatu proyek.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Pengetahuan dasar tentang kerangka C# dan .NET.
2. Visual Studio diinstal pada sistem Anda.
3.  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
4.  Akses ke dokumentasi Aspose.Tasks untuk .NET untuk referensi, tersedia[Di Sini](https://reference.aspose.com/tasks/net/).

## Impor Namespace

Sebelum mendalami contoh, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;


```

## Langkah 1: Buat Proyek baru

Pertama, mari buat objek proyek baru:

```csharp
var project = new Project();
```

## Langkah 2: Tambahkan Tugas

Sekarang, mari tambahkan tugas ke proyek kita:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Langkah 3: Tentukan Jenis Perhitungan untuk Atribut yang Diperluas

Kita akan membuat definisi atribut yang diperluas dengan Calculation Type yang diatur ke Formula:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Langkah 4: Tentukan Jenis Perhitungan untuk Baris Ringkasan

Selanjutnya, kita akan membuat definisi atribut yang diperluas lainnya di mana nilai untuk tugas ringkasan dihitung menggunakan tipe Rollup rata-rata:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara bekerja dengan Calculation Type di Aspose.Tasks untuk .NET. Dengan menentukan Jenis Perhitungan untuk atribut yang diperluas, kita dapat menyesuaikan cara penghitungan nilai untuk tugas dan ringkasan tugas dalam suatu proyek, memberikan fleksibilitas dan kontrol yang lebih besar.

## FAQ

### Q1: Apa Jenis Perhitungan di Aspose.Tasks?

A1: Jenis Perhitungan di Aspose.Tasks menentukan bagaimana nilai dihitung untuk tugas dan ringkasan tugas dalam suatu proyek, menawarkan opsi seperti Formula dan Rollup.

### Q2: Bagaimana cara mengatur Tipe Perhitungan untuk Atribut yang Diperluas?

A2: Anda dapat mengatur Calculation Type untuk Atribut yang Diperluas dengan mendefinisikan properti CalculationType-nya sesuai dengan itu.

### Q3: Bisakah saya menyesuaikan Jenis Perhitungan untuk baris ringkasan dalam sebuah proyek?

A3: Ya, Aspose.Tasks memungkinkan Anda menentukan Jenis Perhitungan untuk baris ringkasan, memungkinkan Anda menyesuaikan penghitungan nilai berdasarkan kebutuhan Anda.

### Q4: Apakah ada Jenis Rollup berbeda yang tersedia untuk penghitungan tugas ringkasan?

A4: Ya, Aspose.Tasks menyediakan berbagai Jenis Rollup seperti Rata-rata, Jumlah, dan Hitungan untuk menghitung nilai tugas ringkasan.

### Q5: Di mana saya dapat menemukan lebih banyak sumber daya tentang Aspose.Tasks untuk .NET?

 A5: Anda dapat menjelajahi dokumentasi dan forum dukungan komunitas yang tersedia di[Aspose.Tugas untuk .NET](https://reference.aspose.com/tasks/net/) untuk bimbingan dan bantuan komprehensif.