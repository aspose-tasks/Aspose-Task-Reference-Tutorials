---
date: 2026-03-19
description: Pelajari cara menambahkan sumber daya ke proyek, menghitung durasi tugas
  menggunakan Algoritma Pohon Aspose.Tasks, dan menetapkan sumber daya ke tugas dalam
  .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tambahkan Sumber Daya ke Proyek dengan Algoritma Pohon di Aspose.Tasks
url: /id/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Sumber Daya ke Proyek dengan Algoritma Pohon di Aspose.Tasks

## Introduction

Dalam tutorial ini Anda akan menemukan **cara menambahkan sumber daya ke proyek** dengan memanfaatkan Algoritma Pohon yang kuat yang disediakan oleh Aspose.Tasks untuk .NET. Kami akan memandu Anda melalui pembuatan hierarki tugas, menghitung durasi tugas, dan menetapkan sumber daya ke tugas—semuanya dalam cara yang jelas, langkah demi langkah, yang dapat Anda salin ke dalam solusi Anda sendiri.

## Quick Answers
- **What does the Tree Algorithm do?** Algoritma ini menelusuri hierarki tugas untuk mengakumulasi nilai kerja secara efisien.  
- **Which primary operation does this guide cover?** Menambahkan sumber daya ke proyek dan memperbarui total kerja.  
- **Do I need a license?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Can I use this with .NET Core?** Ya, Aspose.Tasks mendukung .NET Framework dan .NET Core.  
- **How long does implementation take?** Sekitar 10‑15 menit untuk file proyek dasar.

## What is “add resource to project” in Aspose.Tasks?

Menambahkan sumber daya ke proyek berarti membuat objek `Resource`, menentukan tipenya (misalnya work), dan menautkannya ke satu atau lebih tugas melalui `ResourceAssignments`. Ini memungkinkan penjadwal menghitung upaya, biaya, dan durasi keseluruhan proyek.

## Why use the Tree Algorithm for resource work calculations?

Algoritma Pohon menelusuri pohon tugas sekali, mengakumulasi kerja dari tugas daun hingga tugas rangkuman mereka. Pendekatan ini jauh lebih efisien dibandingkan mengiterasi setiap tugas secara individual, terutama pada proyek besar dengan hierarki yang dalam. Algoritma ini juga menjamin nilai kerja rangkuman tetap sinkron dengan anak‑anaknya.

## Prerequisites

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Visual Studio** – edisi terbaru apa pun (2019, 2022, atau lebih baru).  
2. **Aspose.Tasks for .NET** – unduh dari [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – Anda harus nyaman dengan kelas, objek, dan LINQ sederhana.

## Import Namespaces

Di proyek C# Anda, impor namespace yang diperlukan untuk bekerja dengan fungsionalitas Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Now, let's break down each example into multiple steps:

## Step 1: Load Project File

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Muat file proyek ke memori menggunakan kelas `Project`.

## Step 2: Define Task Hierarchy

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definisikan hierarki tugas dengan menambahkan tugas induk dan anak.

## Step 3: Set Task Properties (including **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Di sini kami **calculate task duration** dengan mengonversi jam kerja menjadi objek `Duration` dan kemudian menentukan tanggal selesai.

## Step 4: Add Resource (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Potongan kode ini **adds a resource to the project** dan **assigns resources to tasks** sehingga penjadwal mengetahui siapa yang bertanggung jawab atas pekerjaan tersebut.

## Step 5: Apply Tree Algorithm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inisialisasi kelas `WorkAccumulator` dan terapkan Algoritma Pohon untuk mengumpulkan kerja umum di seluruh hierarki.

## Step 6: Update Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Perbarui nilai kerja untuk tugas berdasarkan informasi yang dikumpulkan.

## Common Issues & Tips

- **Missing calendar settings:** Jika tanggal selesai tampak tidak tepat, pastikan kalender proyek dikonfigurasi dengan benar sebelum memanggil `GetFinishDateByStartAndWork`.  
- **Resource type mismatch:** Selalu set `Rsc.Type` ke `ResourceType.Work` untuk sumber daya berbasis upaya; jika tidak, akumulasi kerja dapat menghasilkan nol.  
- **Pro tip:** Setelah memperbarui kerja, panggil `project.Save("UpdatedProject.mpp")` untuk menyimpan perubahan.

## Conclusion

Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **add resource to project**, **calculate task duration**, dan **assign resources to tasks** menggunakan Algoritma Pohon Aspose.Tasks. Metode ini menyederhanakan manajemen hierarki dan menjaga nilai kerja rangkuman tetap akurat dengan kode yang minimal.

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A1: Aspose.Tasks for .NET adalah API yang kuat yang memungkinkan pengembang memanipulasi file Microsoft Project secara programatis menggunakan C#.

### Q2: Can I download a free trial of Aspose.Tasks for .NET?

A2: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks untuk .NET dari [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.Tasks for .NET?

A3: Anda dapat menemukan dokumentasi untuk Aspose.Tasks for .NET [here](https://reference.aspose.com/tasks/net/).

### Q4: How can I get support for Aspose.Tasks for .NET?

A4: Untuk dukungan terkait Aspose.Tasks for .NET, Anda dapat mengunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Is there a temporary license available for testing purposes?

A5: Ya, Anda dapat memperoleh lisensi sementara untuk tujuan pengujian dari [here](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Can I use this approach with an existing large project file?**  
A: Tentu saja. Algoritma Pohon bekerja pada instance `Project` apa pun, terlepas dari ukuran.

**Q: Does the algorithm also update cost values?**  
A: Contoh ini fokus pada kerja, tetapi Anda dapat memperluasnya ke biaya dengan mengakumulasi `Tsk.Cost` dengan cara serupa.

**Q: What .NET versions are supported?**  
A: Aspose.Tasks mendukung .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, dan .NET 6+.

**Q: How do I handle multiple resources per task?**  
A: Tambahkan setiap sumber daya dengan `project.ResourceAssignments.Add(task, resource)`; akumulator akan menjumlahkan kerja mereka secara otomatis.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}