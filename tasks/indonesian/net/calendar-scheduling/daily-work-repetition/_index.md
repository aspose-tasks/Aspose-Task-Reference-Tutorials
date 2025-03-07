---
title: Pengulangan Pekerjaan Harian di Aspose.Tugas
linktitle: Pengulangan Pekerjaan Harian di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara membuat tugas berulang harian di file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Tingkatkan produktivitas dan organisasi dengan mudah.
weight: 26
url: /id/net/calendar-scheduling/daily-work-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengulangan Pekerjaan Harian di Aspose.Tugas

## Perkenalan

Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project dengan mudah. Di antara segudang fiturnya adalah kemampuan untuk menangani tugas berulang secara efisien. Dalam tutorial ini, kita akan mempelajari fungsi Pengulangan Pekerjaan Harian, yang memungkinkan pembuatan tugas yang berulang setiap hari dalam sebuah proyek.

## Prasyarat

Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang kerangka C# dan .NET.
- Visual Studio diinstal pada sistem Anda.
-  Aspose.Tugas untuk perpustakaan .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Keakraban dengan file Microsoft Project (.mpp).

## Impor Namespace

Sebelum kita mulai, pastikan Anda mengimpor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah:

## Langkah 1: Muat File Proyek

Pertama, muat file proyek menggunakan`Project` kelas:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Langkah 2: Tentukan Parameter Tugas Berulang

Tentukan parameter untuk tugas berulang:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Langkah 3: Tetapkan Kalender dan Tanggal Mulai Tugas

Tetapkan kalender dan tanggal mulai tugas:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memanfaatkan Aspose.Tasks untuk .NET untuk membuat tugas berulang dengan pengulangan pekerjaan sehari-hari. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola tugas dalam proyek Anda secara efisien, memastikan kelancaran alur kerja dan pengorganisasian.

## FAQ

### Q1: Dapatkah saya menyesuaikan pola pengulangan lebih lanjut?

A1: Ya, Anda dapat menyesuaikan parameter seperti tanggal mulai, jumlah kejadian, dan interval pengulangan untuk menyesuaikan pola pengulangan sesuai kebutuhan Anda.

### Q2: Apakah Aspose.Tasks kompatibel dengan versi Microsoft Project yang berbeda?

A2: Ya, Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas dan integrasi yang lancar.

### Q3: Bagaimana cara menangani pengecualian atau modifikasi pada tugas berulang?

A3: Aspose.Tasks menyediakan fungsionalitas yang kuat untuk mengelola pengecualian dan modifikasi dalam tugas berulang, memungkinkan fleksibilitas dan penyesuaian.

### Q4: Bisakah saya mengekspor proyek ke format lain?

A4: Tentu saja, Aspose.Tasks menawarkan dukungan untuk mengekspor proyek ke berbagai format termasuk PDF, HTML, XML, dan lainnya, memfasilitasi berbagi dan kolaborasi dengan mudah.

### Q5: Apakah Aspose.Tasks menawarkan dukungan teknis?

A5: Ya, Aspose.Tasks memberikan dukungan teknis komprehensif melalui forumnya, tempat Anda dapat mencari bantuan, berbagi pengalaman, dan berinteraksi dengan sesama pengguna.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
