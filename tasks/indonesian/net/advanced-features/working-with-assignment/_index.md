---
title: Bekerja dengan Tugas di Aspose.Tasks
linktitle: Bekerja dengan Tugas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola tugas proyek di .NET menggunakan Aspose.Tasks. Jelajahi kontur berbeda untuk penjadwalan sumber daya.
weight: 13
url: /id/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bekerja dengan Tugas di Aspose.Tasks

## Perkenalan

Dalam tutorial ini, kita akan menjelajahi cara bekerja dengan tugas di Aspose.Tasks untuk .NET. Penugasan sangat penting dalam manajemen proyek karena mereka mengalokasikan sumber daya untuk tugas, membantu dalam penjadwalan dan melacak kemajuan. Kami akan fokus pada menghasilkan data bertahap waktu penetapan sumber daya dengan berbagai kontur menggunakan Aspose.Tasks.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. Pemahaman Dasar C# dan .NET Framework: Keakraban dengan bahasa pemrograman C# dan konsep .NET framework diperlukan untuk diikuti.

## Impor Namespace

Pastikan untuk mengimpor namespace yang diperlukan ke proyek C# Anda:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Langkah 1: Buat Proyek dan Tugas

Mari kita mulai dengan membuat proyek baru dan menambahkan tugas ke dalamnya. Tetapkan tanggal mulai, durasi, dan tanggal selesai tugas:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Langkah 2: Tambahkan Sumber Daya dan Tetapkan ke Tugas

Selanjutnya, tambahkan sumber daya ke proyek dan tetapkan ke tugas yang dibuat sebelumnya:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Langkah 3: Hasilkan Data Berfase Waktu dengan Kontur Berbeda

Sekarang, mari kita buat data bertahap dengan kontur berbeda untuk penetapan sumber daya:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Langkah 4: Ubah Kontur dan Hasilkan Data

Kita dapat mengubah tipe kontur dan menghasilkan data berfase waktu yang sesuai. Berikut beberapa contohnya:

```csharp
// Ubah kontur
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Hasilkan data bertahap dan cetak
// Ulangi langkah ini untuk tipe kontur lainnya
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara bekerja dengan tugas di Aspose.Tasks untuk .NET. Kami mengeksplorasi pembuatan data bertahap waktu penugasan sumber daya dengan berbagai kontur. Pengetahuan ini bisa sangat berguna dalam skenario manajemen proyek.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Tasks untuk menjadwalkan tugas di aplikasi .NET saya?

A1: Ya, Aspose.Tasks menyediakan API komprehensif untuk penjadwalan dan manajemen tugas dalam aplikasi .NET.

### Q2: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?

 A2: Ya, Anda dapat memanfaatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Q3: Apakah ada batasan jumlah tugas atau sumber daya di Aspose.Tasks?

A3: Aspose.Tasks tidak menerapkan batasan apa pun pada jumlah tugas atau sumber daya yang dapat Anda kelola dalam proyek Anda.

### Q4: Dapatkah saya menyesuaikan kontur untuk penetapan sumber daya di Aspose.Tasks?

A4: Ya, seperti yang ditunjukkan dalam tutorial ini, Anda dapat mengatur berbagai kontur seperti turtle, bell, peak, dll., sesuai dengan kebutuhan proyek Anda.

### Q5: Di mana saya dapat menemukan dukungan untuk pertanyaan terkait Aspose.Tasks?

A5: Anda dapat menemukan dukungan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) di mana para ahli dan anggota masyarakat secara aktif terlibat dalam diskusi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
