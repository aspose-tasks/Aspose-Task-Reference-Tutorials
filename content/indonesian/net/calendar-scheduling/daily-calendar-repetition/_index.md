---
title: Pengulangan Kalender Harian di Aspose.Tugas
linktitle: Pengulangan Kalender Harian di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara membuat tugas berulang dengan pengulangan kalender harian di Aspose.Tasks untuk .NET. Tingkatkan efisiensi manajemen proyek dengan mudah.
type: docs
weight: 25
url: /id/net/calendar-scheduling/daily-calendar-repetition/
---
## Perkenalan

 Aspose.Tasks untuk .NET menyediakan seperangkat alat canggih untuk mengelola tugas dan proyek secara terprogram. Salah satu fitur utamanya adalah kemampuan menangani pengulangan kalender harian secara efisien. Dalam tutorial ini, kita akan mengeksplorasi cara memanfaatkan`DailyCalendarRepetition` kelas bersama dengan kelas lain yang relevan untuk membuat tugas berulang dengan pengulangan harian berdasarkan kalender yang ditentukan.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan yang berikut:

1.  Instalasi: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).

2. Pengimporan Namespace: Impor namespace yang diperlukan ke dalam proyek Anda:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Langkah 1: Inisialisasi Proyek

Pertama, kita perlu memuat proyek yang sudah ada atau membuat proyek baru untuk dikerjakan:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Langkah 2: Tentukan Kalender

Selanjutnya, kita membuat kalender dengan durasi 24 jam dan mengaitkannya dengan proyek:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Langkah 3: Tetapkan Parameter Tugas Berulang

Sekarang, mari kita atur parameter untuk tugas berulang kita. Kami menentukan nama, durasi, pola pengulangan, dan jangkauannya:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Langkah 4: Tetapkan Kalender untuk Tugas

Kaitkan kalender yang ditentukan dengan tugas:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Langkah 5: Tambahkan Tugas ke Proyek

Tambahkan tugas dengan parameter yang ditentukan ke proyek:

```csharp
project.RootTask.Children.Add(parameters);
```

## Langkah 6: Simpan Proyek

Terakhir, simpan proyek dengan tugas berulang tambahan:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Sekarang Anda telah berhasil membuat proyek dengan kumpulan tugas berulang yang diulang setiap hari berdasarkan kalender 24 jam menggunakan Aspose.Tasks untuk .NET!

## Kesimpulan

Dalam tutorial ini, kami telah menunjukkan cara memanfaatkan Aspose.Tasks untuk .NET untuk menangani pengulangan kalender harian secara efisien. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan tugas berulang ke dalam proyek Anda, sehingga meningkatkan produktivitas dan pengorganisasian.

## FAQ

### Q1: Dapatkah saya menyesuaikan durasi setiap pengulangan?

A1: Ya, Anda dapat mengatur durasi setiap pengulangan sesuai kebutuhan Anda dengan mengubah parameter dalam kode.

### Q2: Apakah mungkin untuk mengatur kalender berbeda untuk tugas berbeda dalam proyek yang sama?

A2: Tentu saja, Aspose.Tasks memungkinkan Anda menetapkan kalender tertentu untuk masing-masing tugas, menawarkan fleksibilitas dalam penjadwalan.

### Q3: Apakah Aspose.Tasks mendukung pola pengulangan lain selain harian?

A3: Ya, Aspose.Tasks menyediakan berbagai pola pengulangan seperti mingguan, bulanan, tahunan, dll., yang memenuhi beragam kebutuhan proyek.

### Q4: Dapatkah saya memvisualisasikan tugas berulang yang dibuat menggunakan Aspose.Tasks?

A4: Tentu saja, Aspose.Tasks menawarkan opsi visualisasi untuk membantu Anda menganalisis dan melacak tugas berulang secara efektif.

### Q5: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?

 A5: Ya, Anda dapat memanfaatkan uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/) untuk menjelajahi fitur-fiturnya sebelum melakukan pembelian.