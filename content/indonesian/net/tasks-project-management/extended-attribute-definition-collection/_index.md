---
title: Kuasai Proyek MS Definisi Atribut yang Diperluas di Aspose.Tasks
linktitle: Kumpulan Definisi Atribut yang Diperluas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola definisi atribut yang diperluas di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Sesuaikan dan tingkatkan data proyek Anda dengan mudah.
type: docs
weight: 14
url: /id/net/tasks-project-management/extended-attribute-definition-collection/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara bekerja dengan definisi atribut yang diperluas di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Atribut yang diperluas menawarkan cara yang fleksibel untuk menyesuaikan dan menyempurnakan data proyek, memungkinkan pengguna menambahkan kolom tambahan di luar kolom standar yang disediakan secara default. Dengan Aspose.Tasks, Anda dapat dengan mudah mengelola atribut tambahan ini untuk menyesuaikan kebutuhan manajemen proyek Anda.
## Prasyarat
Sebelum melanjutkan, pastikan Anda telah menginstal prasyarat berikut:
- [.NET Kerangka](https://dotnet.microsoft.com/download)
-  Aspose.Tugas untuk perpustakaan .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk mengakses kelas dan metode Aspose.Tasks di proyek .NET Anda. Ikuti langkah ini:
## Langkah 1: Buka proyek .NET Anda
Buka proyek .NET Anda di IDE pilihan Anda, seperti Visual Studio.
## Langkah 2: Tambahkan namespace Aspose.Tasks
Tambahkan baris berikut di awal file kode Anda untuk mengimpor namespace Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Sekarang, mari kita bagi contoh kode yang diberikan menjadi beberapa langkah untuk pemahaman yang komprehensif:
## Langkah 1: Muat file proyek
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Langkah 2: Hapus definisi atribut tambahan yang ada (opsional)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Langkah 3: Buat dan tambahkan definisi atribut yang diperluas untuk suatu tugas
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Langkah 4: Ulangi atribut tugas yang diperluas
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Langkah 5: Buat dan tambahkan definisi atribut yang diperluas untuk sumber daya
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Langkah 6: Masukkan definisi atribut yang diperluas sumber daya
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Langkah 7: Hapus atribut yang diperluas berdasarkan indeks
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Kesimpulan
Dalam tutorial ini, kami telah membahas dasar-dasar bekerja dengan definisi atribut yang diperluas di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola dan menyesuaikan atribut tambahan secara efisien agar sesuai dengan kebutuhan manajemen proyek Anda.
## FAQ
### T: Bisakah saya mengubah definisi atribut tambahan yang sudah ada?
J: Ya, Anda dapat mengubah definisi atribut yang diperluas yang ada atau membuat yang baru sesuai kebutuhan Anda.
### T: Apakah atribut yang diperluas didukung di semua versi Microsoft Project?
J: Ya, atribut yang diperluas didukung di sebagian besar versi Microsoft Project, termasuk versi terbaru.
### T: Dapatkah saya menggunakan atribut yang diperluas untuk menghitung kolom khusus?
J: Tentu saja, atribut yang diperluas dapat digunakan untuk menghitung kolom khusus berdasarkan kriteria spesifik yang Anda tentukan.
### T: Apakah Aspose.Tasks kompatibel dengan kerangka .NET lainnya?
J: Aspose.Tasks kompatibel dengan berbagai kerangka .NET, memastikan fleksibilitas dan kemudahan integrasi.
### T: Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan untuk Aspose.Tasks?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan menjelajahi dokumentasi[Di Sini](https://reference.aspose.com/tasks/net/).