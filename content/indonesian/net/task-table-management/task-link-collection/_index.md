---
title: Menangani Tautan Tugas di Aspose.Tasks
linktitle: Menangani Tautan Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi kekuatan Aspose.Tasks untuk .NET dalam mengelola tautan tugas proyek secara efisien. Ikuti panduan langkah demi langkah kami untuk meningkatkan pengalaman manajemen proyek Anda.
type: docs
weight: 19
url: /id/net/task-table-management/task-link-collection/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah dalam menangani tautan tugas di Aspose.Tasks untuk .NET! Tautan tugas memainkan peran penting dalam manajemen proyek, memungkinkan Anda membangun hubungan antar tugas dan menciptakan ketergantungan. Dalam tutorial ini, kami akan memandu Anda melalui proses bekerja dengan kumpulan tautan tugas menggunakan Aspose.Tasks.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/tasks/net/).
2. Contoh File Proyek: Siapkan contoh file proyek (misalnya, "SampleProject.mpp") untuk mengikuti contohnya.
Sekarang, mari kita mulai!
## Impor Namespace
Di proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Muat Proyek dan Akses Tugas
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
// Muat proyek
var project = new Project(DataDir + "SampleProject.mpp");
// Akses tugas berdasarkan ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Langkah 2: Buat Tautan Tugas
Hubungkan tugas-tugas tersebut untuk membangun ketergantungan:
```csharp
// Tautkan tugas menggunakan ketergantungan FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Langkah 3: Cetak Tautan Tugas
Cetak tautan tugas untuk proyek tersebut:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
// Ulangi melalui tautan tugas
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Langkah 4: Edit Tautan Tugas
Edit tautan tugas berdasarkan akses indeks:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Langkah 5: Hapus Tautan Tugas
Hapus semua tautan tugas dari proyek:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menangani tautan tugas di Aspose.Tasks untuk .NET. Panduan komprehensif ini mencakup memuat proyek, membuat tautan tugas, mencetak tautan, mengedit tautan, dan menghapus tautan tugas.
Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsi yang ditawarkan oleh Aspose.Tasks untuk meningkatkan pengalaman manajemen proyek Anda.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan semua versi .NET?
Ya, Aspose.Tasks dirancang untuk bekerja secara lancar dengan semua versi .NET.
### Bisakah saya membuat jenis tautan tugas khusus menggunakan Aspose.Tasks?
Saat ini, Aspose.Tasks mendukung tipe tautan tugas standar, dan tipe tautan kustom tidak tersedia.
### Bagaimana cara menerapkan batasan pada tugas di Aspose.Tasks?
 Anda dapat menerapkan batasan menggunakan`ConstraintType` properti dari`Task` kelas di Aspose.Tugas.
### Apakah ada batasan ukuran file proyek yang dapat ditangani Aspose.Tasks?
Aspose.Tasks dapat menangani file proyek besar secara efisien dengan dampak kinerja minimal.
### Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 Ya, Anda dapat menemukan dukungan dan terlibat dengan komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).