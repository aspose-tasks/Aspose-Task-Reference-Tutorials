---
title: Koleksi Proyek MS Kode Garis Besar di Aspose.Tasks
linktitle: Kumpulan Kode Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengumpulkan kode kerangka Microsoft Project menggunakan Aspose.Tasks untuk .NET. Tutorial komprehensif ini memberikan petunjuk langkah demi langkah.
type: docs
weight: 11
url: /id/net/outline-code-page-settings/outline-code-collection/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengumpulkan kode kerangka Microsoft Project menggunakan Aspose.Tasks untuk .NET. Kami akan membagi prosesnya menjadi petunjuk langkah demi langkah untuk memastikan kejelasan dan pemahaman.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Visual Studio: Instal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar pemrograman C#: Keakraban dengan C# akan bermanfaat.

## Impor Namespace
Pertama, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks di proyek C# Anda.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Langkah 1: Muat File Proyek
 Mulailah dengan memuat file Microsoft Project menggunakan`Project` kelas.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Langkah 2: Kumpulkan Kode Garis Besar
Buat kolektor untuk mengumpulkan kode kerangka dari tugas proyek.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Langkah 3: Ulangi Tugas dan Kode Garis Besar
Ulangi tugas yang dikumpulkan dan kode kerangka, cetak detailnya.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Langkah 4: Tambahkan Definisi Kode Kerangka Kustom
Tambahkan definisi kode kerangka khusus ke proyek.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Langkah 5: Buat dan Sisipkan Kode Garis Besar
Buat kode kerangka dan masukkan ke dalam tugas.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Langkah 6: Memanipulasi Kode Garis Besar
Memanipulasi kode outline sesuai kebutuhan, seperti menyisipkan, menghapus, atau menghapus.
```csharp
// Contoh manipulasi
// ...
// Masukkan kode dengan angka 2 pada posisi yang benar
task.OutlineCodes.Insert(2, code2);
// Periksa apakah kode telah dimasukkan
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengumpulkan kode kerangka Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif mengelola kode garis besar dalam proyek Anda, meningkatkan pengorganisasian dan kejelasan.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks for .NET terutama menargetkan platform .NET, namun juga menyediakan dukungan untuk bahasa pemrograman lain melalui Aspose.Tasks for Cloud.
### T: Apakah ada batasan ukuran file Proyek yang dapat ditangani Aspose.Tasks untuk .NET?
J: Aspose.Tasks untuk .NET dapat menangani file Proyek besar secara efisien, namun performanya mungkin bervariasi bergantung pada kompleksitas dan ukuran file.
### T: Apakah Aspose.Tasks untuk .NET kompatibel dengan versi terbaru Microsoft Project?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi Microsoft Project, termasuk yang terbaru.
### T: Bisakah saya menyesuaikan format output saat bekerja dengan Aspose.Tasks untuk .NET?
J: Tentu saja, Aspose.Tasks untuk .NET menyediakan opsi luas untuk menyesuaikan format output sesuai kebutuhan Anda.
### T: Di mana saya dapat menemukan dukungan atau sumber daya tambahan untuk Aspose.Tasks untuk .NET?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun mengenai Aspose.Tasks untuk .NET.