---
date: 2026-03-19
description: Pelajari cara mengatur baseline proyek dan mengelola baseline penugasan
  secara efisien dengan Aspose.Tasks untuk .NET, memastikan pelacakan kemajuan proyek
  yang akurat.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tetapkan Baseline Proyek – Mengelola Baseline Penugasan di Aspose.Tasks
url: /id/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Project Baseline – Mengelola Assignment Baseline di Aspose.Tasks

## Introduction

Saat bekerja pada tugas manajemen proyek, **menetapkan baseline proyek** sangat penting untuk mengukur kemajuan aktual dibandingkan rencana awal. Aspose.Tasks untuk .NET tidak hanya memungkinkan Anda **menetapkan baseline proyek** tetapi juga memberikan kontrol penuh atas assignment baseline, memungkinkan pelacakan kinerja yang tepat. Dalam tutorial ini kami akan membahas seluruh proses—memuat proyek, menetapkan baseline, membaca data assignment baseline, dan membandingkan baseline—sehingga Anda dapat memantau proyek dengan percaya diri.

## Quick Answers
- **What does “set project baseline” mean?** Ini merekam jadwal dan data biaya asli untuk perbandingan nanti dengan kinerja aktual.  
- **Which API method sets a baseline?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Do assignment baselines require a separate call?** Tidak, mereka disimpan secara otomatis saat Anda menetapkan baseline proyek.  
- **What formats are supported?** MPP, XML, MPX dan lebih banyak lagi melalui Aspose.Tasks.  
- **Is a license required for production?** Ya, lisensi komersial diperlukan untuk penggunaan non‑trial.

## Prerequisites

Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang pemrograman C#.  
- Visual Studio (versi terbaru apa pun).  
- Perpustakaan Aspose.Tasks untuk .NET ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/net/).  
- Akses ke file proyek dalam format MPP (misalnya `AssignmentBaseline2007.mpp`).

## Import Namespaces

Tambahkan namespace yang diperlukan di bagian atas file C# Anda sehingga compiler mengetahui di mana menemukan kelas Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

Pertama, muat file MPP yang ada dan kemudian panggil `SetBaseline` untuk **menetapkan baseline proyek** untuk seluruh proyek.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

Setelah baseline ditetapkan, setiap penugasan sumber daya berisi catatan baseline masing-masing. Loop di bawah ini mengekstrak dan mencetak detail tersebut, termasuk tanggal mulai/selesai, biaya, pekerjaan, dan data time‑phased apa pun.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Step 3: Compare Assignment Baselines

Anda dapat membandingkan baseline dari penugasan yang berbeda menggunakan operator kesetaraan dan perbandingan bawaan. Ini berguna ketika Anda perlu mendeteksi pergeseran jadwal atau pembengkakan biaya antar tugas.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Common Issues and Solutions

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Data baseline muncul kosong** | File proyek dibuka dalam mode read‑only atau baseline tidak pernah ditetapkan. | Panggil `project.SetBaseline(BaselineType.Baseline)` sebelum membaca assignment baseline. |
| **`NullReferenceException` pada `TimephasedData`** | Tidak semua baseline berisi entri time‑phased. | Selalu periksa `baseline.TimephasedData != null` (seperti yang ditunjukkan dalam kode). |
| **Pengambilan UID yang Salah** | Nilai UID berbeda antar versi file. | Gunakan `ResourceAssignments.GetByUid` dengan UID yang benar atau iterasi untuk menemukan penugasan yang Anda butuhkan. |

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle multiple baselines for a single assignment?**  
A: Ya, Aspose.Tasks mendukung multiple baseline untuk setiap assignment, memungkinkan pelacakan komprehensif kemajuan proyek dari waktu ke waktu.

**Q: Is Aspose.Tasks compatible with various project file formats other than MPP?**  
A: Ya, Aspose.Tasks mendukung berbagai format file proyek, termasuk XML, MPX, dan MPP, memastikan kompatibilitas dengan berbagai alat manajemen proyek.

**Q: Can I modify baseline information programmatically using Aspose.Tasks?**  
A: Tentu saja, Aspose.Tasks menyediakan API yang luas untuk memodifikasi informasi baseline secara dinamis sesuai kebutuhan proyek, menawarkan fleksibilitas dan kontrol atas proses manajemen proyek.

**Q: Does Aspose.Tasks offer documentation and support resources for developers?**  
A: Ya, pengembang dapat mengakses dokumentasi lengkap, tutorial, dan forum di situs web Aspose.Tasks, memfasilitasi integrasi yang lancar dan pemecahan masalah.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Ya, pengembang dapat memperoleh versi trial gratis Aspose.Tasks untuk .NET dari [here](https://releases.aspose.com/), memungkinkan mereka mengevaluasi fitur dan kemampuan sebelum membuat keputusan pembelian.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose