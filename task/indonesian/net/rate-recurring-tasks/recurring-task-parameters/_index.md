---
title: Mengatur Parameter Tugas Berulang di Aspose.Tasks
linktitle: Mengatur Parameter Tugas Berulang di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengatur parameter tugas berulang di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Tutorial komprehensif dengan panduan langkah demi langkah.
type: docs
weight: 14
url: /id/net/rate-recurring-tasks/recurring-task-parameters/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses pengaturan parameter tugas berulang Microsoft Project menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Pemahaman dasar bahasa pemrograman C#.
2. Menginstal Visual Studio atau C# IDE lainnya.
3. Aspose.Tasks untuk perpustakaan .NET diinstal dan direferensikan dalam proyek Anda.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan dalam kode C# Anda:
```csharp
using Aspose.Tasks;
using System;

```
## Langkah 1: Tentukan Direktori Dokumen
```csharp
String DataDir = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen Anda.
## Langkah 2: Muat File Proyek
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Baris kode ini memuat file Microsoft Project ke dalam`project` variabel.
## Langkah 3: Tentukan Parameter Tugas Berulang
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Di sini, Anda menentukan parameter untuk tugas berulang seperti nama tugas, durasi, pola pengulangan, rentang pengulangan, dan apakah akan mengabaikan kalender sumber daya.
## Langkah 4: Atur Kalender untuk Tugas Berulang
```csharp
parameters.SetCalendar(project, "Standard");
```
Langkah ini mengatur kalender untuk tugas berulang. Dalam contoh ini, ini menyetel kalender ke "Standar".
## Langkah 5: Tambahkan Parameter ke Proyek
```csharp
project.RootTask.Children.Add(parameters);
```
Terakhir, tambahkan parameter ke tugas utama proyek.

## Kesimpulan
Dalam tutorial ini, kami telah menunjukkan cara mengatur parameter tugas berulang Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola tugas berulang di proyek Anda secara efisien.
## FAQ
### Bisakah saya menyesuaikan pola pengulangan lebih lanjut?
Ya, Aspose.Tasks menyediakan berbagai pola pengulangan dan opsi untuk disesuaikan sesuai dengan kebutuhan proyek Anda.
### Apakah ada versi uji coba yang tersedia sebelum membeli?
 Ya, Anda dapat mengunduh uji coba gratis dari Aspose.Tasks[situs web](https://purchase.aspose.com/buy) untuk mengevaluasi fitur perpustakaan.
### Apakah Aspose.Tasks mendukung format file proyek lainnya?
Ya, Aspose.Tasks mendukung berbagai format file proyek termasuk MPP, XML, XLSX, dan banyak lagi.
### Bisakah saya mendapatkan dukungan jika saya menemui masalah selama penerapan?
Ya, Anda dapat mengunjungi forum Aspose.Tasks untuk mendapatkan bantuan dari komunitas atau menghubungi dukungan untuk bantuan langsung.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks?
 Anda dapat memperoleh lisensi sementara dari[situs web](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.