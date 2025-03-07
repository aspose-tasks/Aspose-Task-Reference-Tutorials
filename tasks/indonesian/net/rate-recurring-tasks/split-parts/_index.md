---
title: Menangani Bagian Split Proyek MS di Aspose.Tasks
linktitle: Menangani Bagian Terpisah di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani bagian terpisah MS Project secara efisien dengan Aspose.Tasks untuk .NET. Tingkatkan alur kerja manajemen proyek Anda.
weight: 18
url: /id/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menangani Bagian Split Proyek MS di Aspose.Tasks


## Perkenalan
Mengelola bagian terpisah Proyek MS dapat menjadi aspek penting dalam manajemen proyek saat menggunakan Aspose.Tasks untuk .NET. Dalam tutorial ini, kita akan mengeksplorasi cara efektif menangani bagian yang terbelah menggunakan panduan langkah demi langkah.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
   
2. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace
Dalam kode C# Anda, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Langkah 1: Membuat Instance Proyek
```csharp
var project = new Project();
```
 Buat instance baru dari`Project` kelas.
## Langkah 2: Menetapkan Tanggal Mulai dan Selesai Proyek
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Tetapkan tanggal mulai dan selesai proyek.
## Langkah 3: Menambahkan Tugas
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Tambahkan tugas baru ke proyek.
## Langkah 4: Mengatur Properti Tugas
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Tetapkan properti seperti status manual, tanggal mulai, dan durasi tugas.
## Langkah 5: Menambahkan Penugasan Sumber Daya
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Tambahkan penetapan sumber daya ke tugas.
## Langkah 6: Mengatur Properti Penugasan
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Tetapkan properti seperti tanggal mulai, pekerjaan, dan tanggal selesai untuk tugas.
## Langkah 7: Menghasilkan Data Berfase Waktu
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Hasilkan data fase waktu untuk tugas berdasarkan kalender proyek.
## Langkah 8: Membagi Tugas
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Bagi tugas menjadi beberapa bagian dalam jangka waktu yang ditentukan.
## Langkah 9: Mengulangi Bagian yang Terpisah
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Ulangi bagian tugas yang terpisah dan cetak tanggal mulai dan selesainya.

## Kesimpulan
Menangani bagian terpisah Proyek MS di Aspose.Tasks untuk .NET secara efektif sangat penting untuk efisiensi manajemen proyek. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengelola tugas terpisah dan meningkatkan alur kerja manajemen proyek Anda dengan lancar.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan kerangka .NET lainnya?
J: Ya, Aspose.Tasks untuk .NET kompatibel dengan berbagai kerangka .NET termasuk .NET Core dan .NET Standard.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda bisa mendapatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Apakah Aspose.Tasks untuk .NET mendukung manajemen sumber daya?
J: Ya, Aspose.Tasks untuk .NET memungkinkan Anda mengelola sumber daya proyek secara efisien.
### T: Bisakah saya mengkustomisasi kalender proyek menggunakan Aspose.Tasks untuk .NET?
J: Tentu saja, Anda dapat menyesuaikan kalender proyek sesuai dengan kebutuhan proyek Anda.
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk .NET?
 J: Anda dapat menemukan dukungan dan bantuan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
