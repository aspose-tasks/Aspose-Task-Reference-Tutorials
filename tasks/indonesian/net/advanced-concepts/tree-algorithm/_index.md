---
title: Menggunakan Algoritma Pohon di Aspose.Tasks
linktitle: Menggunakan Algoritma Pohon di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanipulasi hierarki tugas secara efektif di proyek .NET Anda menggunakan Algoritma Pohon Aspose.Tasks.
weight: 13
url: /id/net/advanced-concepts/tree-algorithm/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menggunakan Algoritma Pohon di Aspose.Tasks

## Perkenalan

Aspose.Tasks untuk .NET menyediakan fungsionalitas canggih untuk bekerja dengan tugas, sumber daya, dan jadwal manajemen proyek. Salah satu fitur tersebut adalah Algoritma Pohon, yang memungkinkan pengguna memanipulasi hierarki tugas secara efisien. Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Algoritma Pohon di Aspose.Tasks untuk .NET guna mengumpulkan pekerjaan umum dan memperbarui nilai pekerjaan dalam sebuah proyek.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk mengikuti contoh.

## Impor Namespace

Dalam proyek C# Anda, impor namespace yang diperlukan agar berfungsi dengan fungsi Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:

## Langkah 1: Muat File Proyek

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Muat file proyek ke dalam memori menggunakan`Project` kelas.

## Langkah 2: Tentukan Hierarki Tugas

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Tentukan hierarki tugas dengan menambahkan tugas induk dan anak.

## Langkah 3: Tetapkan Properti Tugas

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Tetapkan properti seperti tanggal mulai, durasi, dan tanggal selesai untuk tugas.

## Langkah 4: Tambahkan Sumber Daya

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Tambahkan sumber daya ke proyek dan tetapkan sumber daya tersebut ke tugas sesuai kebutuhan.

## Langkah 5: Terapkan Algoritma Pohon

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inisialisasi`WorkAccumulator` kelas dan terapkan Algoritma Pohon untuk mengumpulkan pekerjaan umum.

## Langkah 6: Perbarui Pekerjaan Tugas

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Perbarui nilai pekerjaan untuk tugas berdasarkan informasi yang dikumpulkan.

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara memanfaatkan Algoritma Pohon di Aspose.Tasks untuk .NET untuk memanipulasi hierarki tugas secara efektif. Dengan mengikuti panduan langkah demi langkah, Anda dapat mengelola tugas dan sumber daya dalam proyek Anda secara efisien.

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

A1: Aspose.Tasks untuk .NET adalah API canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram menggunakan C#.

### Q2: Dapatkah saya mengunduh uji coba gratis Aspose.Tasks untuk .NET?

 A2: Ya, Anda dapat mengunduh uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?

 A3: Anda dapat menemukan dokumentasi Aspose.Tasks untuk .NET[Di Sini](https://reference.aspose.com/tasks/net/).

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

 A4: Untuk dukungan terkait Aspose.Tasks untuk .NET, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

### Q5: Apakah ada lisensi sementara yang tersedia untuk tujuan pengujian?

 A5: Ya, Anda bisa mendapatkan lisensi sementara untuk tujuan pengujian dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
