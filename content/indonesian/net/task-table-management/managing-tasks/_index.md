---
title: Mengelola Tugas di Aspose.Tasks
linktitle: Mengelola Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi panduan komprehensif tentang mengelola tugas dengan Aspose.Tasks untuk .NET. Pelajari cara menambah, menampilkan bagian yang terpisah, memindahkan, mendapatkan/mengatur properti, dan banyak lagi.
type: docs
weight: 15
url: /id/net/task-table-management/managing-tasks/
---
## Perkenalan
Jika Anda seorang pengembang .NET yang ingin mengelola tugas dalam proyek Anda secara efisien, Aspose.Tasks untuk .NET memberikan solusi yang kuat. Tutorial ini akan memandu Anda melalui berbagai aspek pengelolaan tugas menggunakan Aspose.Tasks, menawarkan petunjuk langkah demi langkah dan contoh kode. Baik Anda menambahkan tugas, menampilkan bagian yang terpisah, memindahkan tugas di bawah induk yang sama, mendapatkan/mengatur properti tugas, mengulangi penetapan tugas, membaca garis dasar tugas, atau menghapus tugas, panduan ini siap membantu Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Tasks untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
2. Direktori Dokumen: Siapkan direktori tempat dokumen proyek Anda akan disimpan.
## Impor Namespace
Dalam proyek .NET Anda, sertakan namespace yang diperlukan untuk bekerja dengan Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Menambahkan Tugas ke Proyek
```csharp
// Buat proyek baru
var project = new Project();
// Tambahkan tugas
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Simpan proyek
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Menampilkan Bagian Tugas yang Terpisah
```csharp
// Muat proyek dengan tugas terpisah
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Akses tugas
var task = project.RootTask.Children.GetById(4);
// Tampilkan bagian yang terpisah
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Memindahkan Tugas ke Induk yang Sama
```csharp
try
{
    // Muat proyek
    var project = new Project(DataDir + "MoveTask.mpp");
    // Pindahkan tugas dengan id 5 sebelum tugas dengan id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Simpan proyek yang dimodifikasi
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Mendapatkan/Mengatur Properti Tugas
```csharp
// Buat proyek baru
var project = new Project();
// Tambahkan tugas dan atur properti
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Kumpulkan dan tampilkan properti tugas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Mengulangi Penugasan Tugas
```csharp
// Muat proyek dengan tugas
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Kumpulkan dan tampilkan tugas tugas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Membaca Dasar Tugas
```csharp
// Buat proyek baru
var project = new Project();
// Tambahkan tugas dan tetapkan garis dasar
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Tampilkan durasi dasar tugas
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Menghapus Tugas
```csharp
// Buat proyek baru
var project = new Project();
// Tambahkan tugas
var task = project.RootTask.Children.Add("Task");
// Menampilkan jumlah tugas sebelum dan sesudah penghapusan
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Hapus tugas
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Kesimpulan
Mengelola tugas di Aspose.Tasks untuk .NET adalah proses yang lancar dengan contoh yang diberikan. Baik Anda seorang pengembang berpengalaman atau baru memulai, menggabungkan teknik-teknik ini akan meningkatkan kemampuan manajemen proyek Anda.
## Pertanyaan yang Sering Diajukan
### T: Apakah Aspose.Tasks kompatibel dengan semua kerangka .NET?
J: Ya, Aspose.Tasks mendukung berbagai kerangka .NET, memastikan kompatibilitas dengan lingkungan pengembangan Anda.
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 A: Anda bisa mendapatkan lisensi sementara selama 30 hari dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Apakah ada batasan saat bekerja dengan tugas terpisah di Aspose.Tasks?
 J: Tugas terpisah adalah fitur canggih, dan dokumentasi terperinci dapat ditemukan[Di Sini](https://reference.aspose.com/tasks/net/).
### T: Dapatkah saya mengkustomisasi properti tugas melebihi apa yang ditunjukkan dalam contoh?
J: Tentu saja! Aspose.Tasks menyediakan opsi penyesuaian yang luas untuk properti tugas. Periksa dokumentasi untuk lebih jelasnya.
### T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.