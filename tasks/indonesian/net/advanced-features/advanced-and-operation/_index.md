---
title: Lanjutan DAN Operasi di Aspose.Tugas
linktitle: Lanjutan DAN Operasi di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara melakukan operasi AND tingkat lanjut di Aspose.Tasks untuk .NET untuk memfilter tugas proyek secara efisien berdasarkan beberapa kriteria.
type: docs
weight: 10
url: /id/net/advanced-features/advanced-and-operation/
---
## Perkenalan

 Dalam tutorial ini, kita akan mempelajari operasi AND tingkat lanjut di Aspose.Tasks untuk .NET, alat yang ampuh untuk mengelola tugas dan proyek. Kami akan mempelajari cara memfilter tugas proyek berdasarkan beberapa kondisi menggunakan`Util.And` kelas.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Pengetahuan dasar bahasa pemrograman C#.
2.  Menginstal Aspose.Tasks untuk .NET. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan ke proyek C# kita:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Langkah 1: Inisialisasi Proyek dan Kumpulkan Tugas

Mulailah dengan menginisialisasi proyek Aspose.Tasks baru dan mengumpulkan semua tugas di dalamnya:

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Langkah 2: Tentukan Kondisi Filter

Selanjutnya, tentukan kondisi filter. Untuk contoh ini, kita akan membuat dua kondisi: satu untuk memfilter tugas ringkasan dan satu lagi untuk memfilter tugas non-null:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Langkah 3: Gabungkan Kondisi dengan Operasi AND

 Sekarang, gabungkan kondisinya menggunakan`Util.And` kelas untuk membuat kondisi gabungan:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Langkah 4: Terapkan Tugas Kondisi dan Filter

Terapkan kondisi gabungan ke tugas yang dikumpulkan dan filter sesuai kebutuhan:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Langkah 5: Keluaran Tugas yang Difilter

Terakhir, keluarkan tugas yang difilter:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Pemrosesan tambahan dapat dilakukan di sini
}
```

## Kesimpulan

 Dalam tutorial ini, kita mempelajari cara melakukan operasi AND tingkat lanjut di Aspose.Tasks untuk .NET. Dengan menggabungkan kondisi menggunakan`Util.And`kelas, kita dapat memfilter tugas secara efisien berdasarkan beberapa kriteria.

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

J: Aspose.Tasks untuk .NET adalah API tangguh yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram dalam aplikasi .NET.

### Q2: Bisakah saya menerapkan lebih dari dua ketentuan menggunakan Util.And?

J: Ya, Util.And dapat digunakan untuk menggabungkan sejumlah kondisi untuk membuat kriteria pemfilteran yang kompleks.

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?

 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?

 A: Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).

### Q5: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).