---
title: Menangani Pengecualian Kalender di Aspose.Tasks
linktitle: Menangani Pengecualian Kalender di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola pengecualian kalender di Aspose.Tasks untuk .NET dengan tutorial langkah demi langkah dan contoh.
type: docs
weight: 12
url: /id/net/calendar-scheduling/calendar-exceptions/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara mengelola pengecualian kalender di Aspose.Tasks menggunakan kerangka .NET. Pengecualian kalender memungkinkan kami menentukan tanggal atau periode khusus dalam kalender proyek di mana jadwal kerja reguler diubah, seperti hari libur atau penutupan sementara. Kami akan membahas berbagai metode untuk menangani pengecualian kalender langkah demi langkah, menggunakan Aspose.Tasks untuk .NET.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar bahasa pemrograman C#.
- Visual Studio diinstal pada sistem Anda.
- Aspose.Tasks untuk perpustakaan .NET ditambahkan ke proyek Anda.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk proyek kita:

```csharp
using Aspose.Tasks;
using System;


```

## Langkah 1: Menghapus Pengecualian Kalender

Untuk menghapus pengecualian kalender, ikuti langkah-langkah berikut:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Menampilkan informasi kalender
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Hapus pengecualian pertama
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Langkah 2: Mendapatkan Waktu Kerja dari Pengecualian Kalender

Untuk mengambil waktu kerja pengecualian kalender, ikuti langkah-langkah berikut:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Menampilkan informasi kalender dan pengecualian
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Dapatkan waktu kerja dan tampilkan detail
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Langkah 3: Menentukan Pengecualian Kalender

Untuk menambah atau menghapus pengecualian kalender, ikuti langkah-langkah berikut:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Buat pengecualian kalender baru
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Tetapkan detail pengecualian
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Periksa apakah suatu tanggal merupakan pengecualian
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Tambahkan pengecualian ke kalender
    calendar.Exceptions.Add(exception);

    // Hapus pengecualian jika ada
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Tambahkan pengecualian baru
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Pengecualian pencetakan
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Kesimpulan

Dalam artikel ini, kami telah membahas berbagai aspek penanganan pengecualian kalender di Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat secara efektif mengelola pengecualian dalam jadwal proyek Anda, memastikan representasi jam kerja dan acara khusus yang akurat.

## FAQ

### Q1: Bisakah saya menambahkan beberapa pengecualian ke satu kalender?

A1: Ya, Anda dapat menambahkan beberapa pengecualian ke kalender untuk mengakomodasi berbagai tanggal atau periode khusus.

### Q2: Bagaimana cara memeriksa apakah tanggal tertentu merupakan pengecualian?

 A2: Anda dapat menggunakan`CheckException()` metode untuk memverifikasi apakah tanggal tertentu termasuk dalam pengecualian.

### Q3: Apakah mungkin untuk menghapus pengecualian yang ada dari kalender?

 A3: Ya, Anda dapat menghapus pengecualian dengan mengakses`Exceptions` koleksi kalender dan menggunakan`Remove()` metode.

### Q4: Jenis pengecualian kalender apa yang didukung?

A4: Aspose.Tasks mendukung berbagai jenis pengecualian, termasuk pengecualian harian, mingguan, bulanan, dan tahunan, memberikan fleksibilitas dalam menentukan aturan pengecualian.

### Q5: Dapatkah saya menyesuaikan jam kerja untuk tanggal pengecualian tertentu?

A5: Ya, Anda dapat menentukan waktu kerja khusus untuk masing-masing tanggal pengecualian menggunakan metode yang sesuai yang disediakan oleh Aspose.Tasks.