---
title: Menguasai Dasar Tugas di Aspose.Tasks untuk .NET
linktitle: Menangani Garis Dasar Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani garis dasar tugas di Aspose.Tasks untuk .NET dengan tutorial komprehensif ini. Tingkatkan keterampilan manajemen proyek Anda hari ini!
type: docs
weight: 16
url: /id/net/task-table-management/task-baselines/
---
## Perkenalan
Dalam dunia manajemen proyek yang dinamis, tetap terorganisir dan mendapat informasi sangatlah penting. Aspose.Tasks untuk .NET memberikan solusi canggih untuk menangani garis dasar tugas, memungkinkan Anda mengakses informasi dasar yang berharga secara efisien. Panduan langkah demi langkah ini akan memandu Anda melalui prosesnya, memastikan Anda memahami setiap konsep dengan jelas.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Pengaturan Lingkungan: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya dari[Dokumentasi Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#, karena tutorial ini mengasumsikan pemahaman dasar.
- Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE pilihan seperti Visual Studio untuk mengikutinya dengan lancar.
## Impor Namespace
Untuk memulai, impor namespace yang diperlukan ke dalam proyek Anda. Ini memastikan Anda memiliki akses ke fungsionalitas Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
```
Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memandu Anda dalam menangani garis dasar tugas di Aspose.Tasks.
## Langkah 1: Buat Proyek
```csharp
var project = new Project();
```
 Mulailah dengan menginisialisasi proyek baru menggunakan`Project` kelas.
## Langkah 2: Buat Tugas dan Tetapkan Dasar
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
 Tambahkan tugas ke proyek dan tetapkan garis dasarnya menggunakan`SetBaseline` metode.
## Langkah 3: Tampilkan Informasi Dasar Tugas
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
Ambil dan tampilkan informasi penting tentang dasar tugas, seperti waktu mulai, durasi, dan waktu selesai.
## Langkah 4: Detail Dasar Tambahan
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
Jelajahi rincian tambahan, termasuk apakah baseline tersebut merupakan Baseline Interim dan biaya tetap yang terkait dengannya.
## Langkah 5: Cetak Data Bertahap Waktu
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
Memahami data fase waktu yang terkait dengan garis besar tugas, memberikan wawasan tentang berbagai lini waktu proyek.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menangani garis dasar tugas di Aspose.Tasks untuk .NET. Pengetahuan ini akan meningkatkan kemampuan manajemen proyek Anda, memastikan pelacakan dan perencanaan yang akurat.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.Tasks dengan kerangka .NET lainnya?
J: Aspose.Tasks kompatibel dengan beberapa kerangka .NET, memberikan fleksibilitas dalam lingkungan pengembangan Anda.
### T: Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 J: Ya, Anda dapat memperoleh dukungan dan terlibat dengan komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 Sebuah kunjungan[Di Sini](https://purchase.aspose.com/temporary-license/)untuk mendapatkan lisensi sementara untuk Aspose.Tasks.
### T: Apakah ada tutorial di luar dasar tugas yang tersedia?
 J: Jelajahi[dokumentasi](https://reference.aspose.com/tasks/net/) untuk berbagai tutorial tentang fitur Aspose.Tasks.
### T: Di mana saya dapat membeli Aspose.Tasks untuk .NET?
 J: Anda dapat dengan mudah membeli Aspose.Tasks[Di Sini](https://purchase.aspose.com/buy).