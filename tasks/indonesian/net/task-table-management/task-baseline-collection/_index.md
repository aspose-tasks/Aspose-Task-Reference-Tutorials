---
title: Kumpulan Garis Dasar Tugas di Aspose.Tasks
linktitle: Kumpulan Garis Dasar Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi garis dasar tugas dengan mudah menggunakan Aspose.Tasks untuk .NET. Manajemen proyek yang efisien menjadi sederhana. Unduh sekarang! #Aspose.Tugas #Proyek MS
type: docs
weight: 17
url: /id/net/task-table-management/task-baseline-collection/
---
## Perkenalan
Selamat datang di dunia Aspose.Tasks untuk .NET, perpustakaan canggih yang memfasilitasi manipulasi dan pengelolaan tugas proyek dengan lancar. Dalam tutorial ini, kita akan mempelajari bidang dasar tugas yang menarik—aspek penting dalam perencanaan dan pelacakan proyek. Di akhir panduan ini, Anda akan menguasai seni bekerja dengan kumpulan dasar tugas, memungkinkan Anda meningkatkan kemampuan manajemen proyek Anda.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan dari[halaman rilis](https://releases.aspose.com/tasks/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET pilihan Anda.
- Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# bermanfaat.
Sekarang kita sudah siap, mari masuk ke dunia Aspose.Tasks untuk .NET yang menarik.
## Impor Namespace
Di proyek C# Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Siapkan Proyek dan Tugas
Mulailah dengan membuat proyek baru dan menambahkan tugas ke dalamnya:
```csharp
var project = new Project();
var task = project.RootTask.Children.Add("Task");
```
## 2. Buat Garis Dasar Proyek
Sekarang, mari buat garis dasar proyek untuk tugas tersebut:
```csharp
project.SetBaseline(BaselineType.Baseline);
```
## 3. Cetak Garis Dasar Tugas
Cetak informasi tentang garis dasar tugas:
```csharp
Console.WriteLine("Count of task baselines: " + task.Baselines.Count);
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration: {0}", baseline.Duration);
    Console.WriteLine("Baseline start: {0}", baseline.Start);
    Console.WriteLine("Baseline finish: {0}", baseline.Finish);
}
```
## 4. Hapus Semua Garis Dasar
Jika diperlukan, Anda dapat menghapus semua garis dasar yang terkait dengan tugas tersebut:
```csharp
List<TaskBaseline> baselines = task.Baselines.ToList();
for (var i = 0; i < baselines.Count; i++)
{
    task.Baselines.Remove(baselines[i]);
}
```
Selamat! Anda telah berhasil menavigasi proses bekerja dengan garis dasar tugas menggunakan Aspose.Tasks untuk .NET.
## Kesimpulan
Kesimpulannya, menguasai dasar tugas dengan Aspose.Tasks untuk .NET membuka banyak kemungkinan untuk manajemen proyek yang efisien. Panduan ini telah membekali Anda dengan pengetahuan dan keterampilan untuk memanfaatkan fitur ini secara efektif.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya membuat beberapa garis dasar untuk satu tugas?
J: Ya, Aspose.Tasks untuk .NET memungkinkan Anda mengatur dan mengelola beberapa garis dasar untuk suatu tugas.
### T: Bagaimana cara menangani pengecualian saat bekerja dengan dasar tugas?
J: Anda dapat menggunakan blok try-catch untuk menangani pengecualian dengan baik dan memastikan kelancaran eksekusi kode Anda.
### T: Apakah ada batasan jumlah tugas yang dapat saya sertakan dalam sebuah proyek?
J: Aspose.Tasks untuk .NET tidak menerapkan batasan ketat pada jumlah tugas, sehingga memberikan fleksibilitas untuk beragam ukuran proyek.
### T: Dapatkah saya menyesuaikan format informasi dasar yang dicetak?
J: Tentu saja! Anda memiliki kendali penuh atas pemformatan saat mencetak detail dasar, memungkinkan Anda menyesuaikannya dengan kebutuhan spesifik Anda.
### T: Di mana saya dapat mencari bantuan jika saya mengalami masalah atau memiliki pertanyaan tambahan?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan khusus dan bantuan komunitas.