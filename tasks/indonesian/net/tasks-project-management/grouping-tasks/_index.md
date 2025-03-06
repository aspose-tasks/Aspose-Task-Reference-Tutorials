---
title: Pengelompokan Tugas Proyek MS yang Efisien dengan Aspose.Tasks
linktitle: Mengelompokkan Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelompokkan tugas Microsoft Project secara efektif menggunakan Aspose.Tasks untuk .NET.
type: docs
weight: 25
url: /id/net/tasks-project-management/grouping-tasks/
---
## Perkenalan
Mengelola tugas di Microsoft Project terkadang menjadi tantangan, terutama ketika harus mengaturnya secara efisien. Aspose.Tasks untuk .NET menawarkan solusi komprehensif untuk ini dengan menyediakan fungsionalitas untuk mengelompokkan tugas secara efektif. Dalam tutorial ini, kita akan mempelajari cara mengelompokkan tugas MS Project menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda untuk menggunakan fungsionalitas Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Langkah 1: Muat File Proyek MS
Mulailah dengan memuat file MS Project Anda menggunakan kode berikut:
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Langkah 2: Akses Grup Tugas
Selanjutnya, mari akses grup tugas dalam proyek:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Langkah 3: Ambil Informasi Grup
Sekarang, ambil informasi tentang grup tugas:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Langkah 4: Akses Kriteria Grup
Akses kriteria yang ditetapkan untuk grup tugas:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Langkah 5: Ambil Informasi Kriteria
Ambil informasi rinci tentang setiap kriteria:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat mengelompokkan tugas MS Project secara efektif menggunakan Aspose.Tasks untuk .NET, sehingga meningkatkan organisasi dan pengelolaan data proyek Anda.

## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET memberikan kemampuan yang kuat untuk mengelompokkan tugas-tugas MS Project, memungkinkan pengorganisasian dan pengelolaan data proyek yang lebih baik. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat memanfaatkan fitur-fitur ini secara efisien di aplikasi .NET Anda.
## FAQ
### Bisakah saya mengelompokkan tugas berdasarkan kriteria khusus?
Ya, Anda dapat menentukan kriteria khusus untuk mengelompokkan tugas sesuai dengan kebutuhan spesifik Anda menggunakan Aspose.Tasks untuk .NET.
### Apakah Aspose.Tasks mendukung versi file MS Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai versi file MS Project, memastikan kompatibilitas dan integrasi yang lancar.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 Ya, Anda bisa mendapatkan versi uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).
### Bisakah saya menyesuaikan tampilan tugas yang dikelompokkan?
Tentu saja, Aspose.Tasks menyediakan opsi untuk menyesuaikan tampilan tugas yang dikelompokkan, termasuk warna sel, font, dan gaya.
### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk .NET?
 Anda dapat menemukan dukungan dan bantuan untuk Aspose.Tasks untuk .NET di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).