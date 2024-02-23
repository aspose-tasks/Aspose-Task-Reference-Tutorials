---
title: Menangani Pola Pengulangan Bulanan di Aspose.Tasks
linktitle: Menangani Pola Pengulangan Bulanan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani pola pengulangan bulanan di Aspose.Tasks untuk .NET dengan tutorial langkah demi langkah ini.
type: docs
weight: 18
url: /id/net/advanced-concepts/monthly-recurrence-patterns/
---
## Perkenalan

Aspose.Tasks untuk .NET adalah API canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Salah satu fungsi penting yang ditawarkannya adalah kemampuan untuk menangani tugas berulang secara efisien. Dalam tutorial ini, kita akan mempelajari cara bekerja dengan pola pengulangan bulanan menggunakan Aspose.Tasks, langkah demi langkah.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menginstal prasyarat berikut:

## Impor Namespace

Pertama, pastikan Anda telah mengimpor namespace yang diperlukan dalam proyek .NET Anda:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Sekarang, mari kita uraikan proses penanganan pola pengulangan bulanan menjadi beberapa langkah:

## Langkah 1: Inisialisasi Proyek

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Langkah 2: Tetapkan Parameter Tugas Berulang

Tentukan parameter untuk tugas berulang, termasuk nama tugas, durasi, dan pola pengulangan:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Langkah 3: Tambahkan Parameter ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

## Langkah 4: Simpan Proyek

Simpan proyek yang dimodifikasi dengan tugas berulang:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Kesimpulan

Menangani pola pengulangan bulanan di Aspose.Tasks untuk .NET sangatlah mudah dan efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah membuat tugas berulang dengan interval bulanan dan rentang pengulangan tertentu.

## FAQ

### Q1: Apakah Aspose.Tasks kompatibel dengan semua versi file Microsoft Project?

A1: Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk MPP, MPT, XML, dan MPX.

### Q2: Dapatkah saya menyesuaikan pola pengulangan lebih lanjut?

A2: Ya, Aspose.Tasks menyediakan opsi luas untuk menyesuaikan pola pengulangan, termasuk harian, mingguan, bulanan, dan tahunan.

### Q3: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?

 A3: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks dari situs web[Di Sini](https://releases.aspose.com/).

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?

 A4: Anda dapat mencari bantuan dan berpartisipasi dalam diskusi mengenai[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

### Q5: Di mana saya dapat membeli lisensi untuk Aspose.Tasks?

 A5: Anda dapat membeli lisensi untuk Aspose.Tasks dari situs web[Di Sini](https://purchase.aspose.com/buy)