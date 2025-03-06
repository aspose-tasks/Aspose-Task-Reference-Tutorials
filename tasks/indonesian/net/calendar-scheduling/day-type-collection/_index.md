---
title: Mengelola Pengumpulan Jenis Hari di Aspose.Tasks
linktitle: Mengelola Pengumpulan Jenis Hari di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola koleksi jenis hari secara efisien di Aspose.Tasks untuk .NET. Buat, ubah, dan manipulasi pengecualian kalender dengan mudah.
type: docs
weight: 28
url: /id/net/calendar-scheduling/day-type-collection/
---
## Perkenalan

 Aspose.Tasks untuk .NET menyediakan fungsionalitas yang kuat untuk mengelola koleksi jenis hari, penting untuk menentukan pengecualian kalender mingguan dalam aplikasi manajemen proyek. Dalam tutorial ini, kita akan mengeksplorasi cara memanfaatkan`DayTypeCollection` kelas secara efisien. 

## Prasyarat

Sebelum kita melanjutkan tutorial, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan konsep kerangka .NET.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda:

```csharp
using Aspose.Tasks;
using System;


```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah:

## Langkah 1: Muat Proyek dan Akses Kalender

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Langkah ini menginisialisasi instance proyek baru dan mengambil kalender berdasarkan UID-nya.

## Langkah 2: Ulangi Pengecualian Kalender

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Di sini, kami mengulangi setiap pengecualian kalender dan mencetak namanya serta jenis hari terkait.

## Langkah 3: Ubah Pengecualian Kalender

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Langkah ini menunjukkan cara mengubah pengecualian kalender dengan menambahkan, menghapus, atau memperbarui jenis hari.

## Langkah 4: Buat dan Manipulasi Pengecualian Kalender Baru

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Pada langkah terakhir ini, kami membuat pengecualian kalender baru dan memanipulasinya dengan menambahkan dan menyalin tipe hari.

## Kesimpulan

 Kesimpulannya, mengelola koleksi tipe hari di Aspose.Tasks untuk .NET sangat penting untuk menentukan dan mengubah pengecualian kalender mingguan dalam aplikasi manajemen proyek. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat memanfaatkannya secara efektif`DayTypeCollection` kelas untuk menangani berbagai operasi kalender.

## FAQ

### Q1: Dapatkah Aspose.Tasks untuk .NET digunakan untuk membuat bagan Gantt secara terprogram?

A1: Ya, Aspose.Tasks untuk .NET menyediakan API untuk membuat dan memanipulasi bagan Gantt di aplikasi .NET.

### Q2: Apakah Aspose.Tasks untuk .NET kompatibel dengan .NET Core dan .NET Framework?

A2: Ya, Aspose.Tasks untuk .NET mendukung .NET Core dan .NET Framework.

### Q3: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

 A3: Anda bisa mendapatkan dukungan dengan mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) tempat Anda dapat mengajukan pertanyaan dan berinteraksi dengan pengguna lain.

### Q4: Apakah Aspose.Tasks untuk .NET menawarkan uji coba gratis?

 A4: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).

### Q5: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk .NET?

 A5: Ya, lisensi sementara tersedia untuk dibeli dari[Asumsikan situs web](https://purchase.aspose.com/temporary-license/).