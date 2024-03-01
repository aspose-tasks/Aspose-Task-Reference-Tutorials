---
title: Bekerja dengan Operasi NOT di Aspose.Tasks
linktitle: Bekerja dengan Operasi NOT di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menggunakan operasi NOT di Aspose.Tasks untuk .NET untuk memfilter tugas secara efektif. Tingkatkan kemampuan manajemen proyek Anda sekarang.
type: docs
weight: 20
url: /id/net/advanced-concepts/not-operation/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara memanfaatkan operasi NOT di Aspose.Tasks untuk .NET. Operasi NOT memungkinkan kita membalikkan kondisi filter, memungkinkan kita memilih elemen yang tidak memenuhi kriteria tertentu.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Anda memerlukan instalasi Visual Studio yang berfungsi untuk mengikuti contoh kode.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
3. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan membantu dalam memahami contoh kode.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk kode kita:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Siapkan Proyek dan Tugas

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Kita mulai dengan memuat file proyek bernama "Project2.mpp" menggunakan`Project` kelas yang disediakan oleh Aspose.Tasks. Pastikan file proyek ada di direktori yang ditentukan.

## Langkah 2: Kumpulkan Tugas Proyek

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Di sini, kami membuat a`ChildTasksCollector` objek untuk mengumpulkan semua tugas dalam proyek. Kami kemudian menggunakan`TaskUtils.Apply` metode untuk menelusuri hierarki tugas proyek dan mengumpulkan semua tugas anak.

## Langkah 3: Tentukan Kondisi Filter

```csharp
var filter = new NullCondition();
```

 Kami mendefinisikan kondisi filter menggunakan nama kelas khusus`NullCondition`. Kondisi ini memilih tugas yang memiliki nilai null.

## Langkah 4: Terapkan BUKAN Operasi

```csharp
var condition = new Not<Task>(filter);
```

 Kami menerapkan operasi NOT pada kondisi filter menggunakan`Not<T>`kelas yang disediakan oleh Aspose.Tasks. Ini akan membalikkan kondisi filter, memilih tugas yang tidak memiliki nilai nol.

## Langkah 5: Filter Tugas

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Kami memfilter tugas yang dikumpulkan berdasarkan kondisi yang diterapkan menggunakan kebiasaan`Filter` metode. Metode ini mengambil kumpulan tugas yang dapat dihitung dan kondisi filter sebagai parameter masukan, dan mengembalikan daftar tugas yang memenuhi kondisi tersebut.

## Langkah 6: Proses Tugas yang Difilter

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Bekerja dengan properti lain...
}
```

Terakhir, kami mengulangi tugas yang difilter dan melakukan operasi apa pun yang diinginkan. Dalam contoh ini, kita cukup mencetak nama tugas ke konsol.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara bekerja dengan operasi NOT di Aspose.Tasks untuk .NET. Dengan membalikkan kondisi filter, kami dapat secara selektif memilih elemen yang tidak memenuhi kriteria yang ditentukan, sehingga meningkatkan fleksibilitas kami dalam manipulasi tugas dalam proyek.

## FAQ

### Q1: Dapatkah saya menggunakan Aspose.Tasks dengan kerangka .NET lainnya?

J: Ya, Aspose.Tasks mendukung berbagai kerangka .NET termasuk .NET Core, .NET Standard, dan .NET Framework.

### Q2: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?

 J: Ya, Anda dapat mengunduh uji coba gratis dari[situs web](https://releases.aspose.com/).

### Q3: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?

 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk pertanyaan dukungan atau bantuan teknis apa pun.

### Q4: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks?

 J: Ya, Anda dapat membeli lisensi sementara dari[halaman pembelian](https://purchase.aspose.com/temporary-license/).

### Q5: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks?

 A: Anda dapat mengakses dokumentasi lengkapnya di[Halaman dokumentasi Aspose.Tasks](https://reference.aspose.com/tasks/net/).