---
title: Mengelola Kumpulan Tugas di Aspose.Tasks
linktitle: Mengelola Kumpulan Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi manajemen pengumpulan tugas yang efisien di Aspose.Tasks untuk .NET. Dari pembuatan hingga pengeditan, kuasai manajemen proyek dengan mudah.
type: docs
weight: 18
url: /id/net/task-table-management/task-collection/
---
## Perkenalan
Jika Anda mempelajari dunia manajemen proyek menggunakan .NET, Aspose.Tasks adalah solusi tepat Anda untuk penanganan kumpulan tugas yang lancar. Tutorial ini akan memandu Anda melalui proses pengelolaan kumpulan tugas secara efisien, memastikan Anda memanfaatkan perpustakaan canggih ini secara maksimal.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar bahasa pemrograman C#.
- Visual Studio diinstal pada mesin Anda.
- Aspose.Tasks untuk perpustakaan .NET diunduh dan direferensikan dalam proyek Anda.
## Impor Namespace
Untuk memulai, mari impor namespace yang diperlukan dalam proyek C# Anda:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Namespace ini menyediakan akses ke kelas dan metode penting yang diperlukan untuk manajemen tugas yang efektif.
Sekarang, mari kita bagi tutorial menjadi serangkaian langkah, memastikan kejelasan dan kesederhanaan.
## Langkah 1: Membuat Instance Proyek
```csharp
var project = new Project();
```
 Buat instance proyek baru menggunakan`Project` kelas.
## Langkah 2: Memeriksa Kesiapan Pengumpulan Tugas
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
Verifikasi apakah kumpulan tugas bersifat baca-saja.
## Langkah 3: Membuat Tugas
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// Tetapkan properti tugas tambahan seperti mulai, durasi, dan selesai
// Langkah serupa untuk Tugas 2 dan Tugas 3
```
Buat tugas dalam proyek dan atur propertinya.
## Langkah 4: Mencetak Tugas Proyek
```csharp
foreach (var child in project.RootTask.Children)
{
    // Cetak detail tugas
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
Cetak detail setiap tugas dalam proyek.
## Langkah 5: Mengedit Tugas
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
Edit tugas menggunakan ID atau UID-nya.
## Langkah 6: Menambahkan Tugas Berulang
```csharp
var parameters = new RecurringTaskParameters
{
    // Tetapkan parameter tugas berulang
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
Tambahkan tugas berulang ke proyek.
## Langkah 7: Mengubah Koleksi menjadi Daftar
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
Ubah kumpulan tugas menjadi daftar dan lakukan operasi pada setiap tugas.
## Kesimpulan
Mengelola kumpulan tugas di Aspose.Tasks untuk .NET sangatlah mudah dengan panduan langkah demi langkah ini. Baik Anda membuat, mengedit, atau menghapus tugas, Aspose.Tasks memberdayakan Anda untuk menangani manajemen proyek dengan lancar.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks kompatibel dengan .NET Core?
Ya, Aspose.Tasks mendukung .NET Core, memungkinkan Anda menggunakannya dalam aplikasi lintas platform.
### Bisakah saya mengekspor tugas proyek ke format file berbeda?
Sangat! Aspose.Tasks menyediakan opsi ekspor serbaguna, termasuk PDF, XLSX, dan MPP.
### Bagaimana cara menangani ketergantungan antar tugas?
 Anda dapat mengatur dependensi tugas menggunakan`TaskLink` kelas yang disediakan oleh Aspose.Tasks.
### Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 Ya, Anda dapat menemukan dukungan dan terlibat dengan komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### Bisakah saya mendapatkan lisensi sementara untuk Aspose.Tasks?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).