---
title: Kumpulan Pengecualian Kalender di Aspose.Tasks
linktitle: Kumpulan Pengecualian Kalender di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani pengecualian kalender secara efisien di proyek .NET Anda menggunakan Aspose.Tasks, memastikan penjadwalan dan manajemen sumber daya yang akurat.
weight: 13
url: /id/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kumpulan Pengecualian Kalender di Aspose.Tasks

## Perkenalan

Dalam manajemen proyek, penjadwalan yang tepat sangat penting untuk kesuksesan. Namun, skenario dunia nyata sering kali memerlukan penyimpangan dari jadwal standar karena hari libur, acara khusus, atau faktor lainnya. Aspose.Tasks untuk .NET memberikan solusi tangguh untuk mengelola pengecualian tersebut melalui fitur Koleksi Pengecualian Kalender. Tutorial ini akan memandu Anda melalui proses pemanfaatan fungsi ini langkah demi langkah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal perpustakaan. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
2. Pengetahuan dasar C#: Keakraban dengan bahasa pemrograman C# akan membantu dalam memahami contoh-contoh.
3. Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda, seperti Visual Studio atau JetBrains Rider.

## Impor Namespace

Sebelum Anda mulai bekerja dengan Aspose.Tasks untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Langkah ini memungkinkan Anda mengakses kelas dan metode yang diperlukan untuk mengelola pengecualian kalender.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah:

## Langkah 1: Muat Proyek dan Ambil Kalender

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Pada langkah ini, kami memuat file proyek dan mengambil kalender yang diinginkan berdasarkan UID-nya.

## Langkah 2: Hapus Pengecualian yang Ada dan Tetapkan Kalender Standar

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Langkah ini menghapus semua pengecualian yang ada dari kalender dan menetapkannya ke konfigurasi standar.

## Langkah 3: Tentukan dan Tambahkan Pengecualian Waktu Kerja

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Langkah ini menentukan pengecualian waktu kerja dengan tanggal mulai dan akhir tertentu, beserta waktu kerja dalam tanggal tersebut, dan menambahkannya ke kalender.

## Langkah 4: Tentukan dan Tambahkan Pengecualian Waktu Non-Kerja

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Tambahkan lebih banyak pengecualian jika diperlukan

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Langkah ini menentukan pengecualian waktu non-kerja, seperti hari libur, dan menambahkannya ke kalender.

## Langkah 5: Tampilkan Pengecualian Kalender

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Langkah ini menampilkan pengecualian kalender yang ditambahkan beserta detailnya.

## Langkah 6: Hapus Semua Pengecualian

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Terakhir, langkah ini menghapus semua pengecualian dari kalender.

## Kesimpulan

Mengelola pengecualian kalender sangat penting untuk penjadwalan proyek yang akurat. Aspose.Tasks untuk .NET menyederhanakan tugas ini dengan menyediakan serangkaian fitur lengkap, termasuk Koleksi Pengecualian Kalender. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menangani berbagai skenario penjadwalan dalam proyek Anda secara efisien.

## FAQ

### Q1: Bisakah saya menambahkan beberapa pengecualian ke satu kalender?

 A1: Ya, Anda dapat menambahkan beberapa pengecualian ke kalender menggunakan`AddRange` metode.

### Q2: Bagaimana cara menangani pengecualian berulang, seperti hari libur mingguan?

A2: Anda dapat menghitung pengecualian berulang secara terprogram dan menambahkannya ke kalender menggunakan logika khusus.

### Q3: Apakah mungkin mengimpor pengecualian kalender dari sumber eksternal?

A3: Ya, Anda dapat membaca pengecualian kalender dari sumber eksternal seperti database atau file CSV dan mengintegrasikannya ke dalam proyek Anda.

### Q4: Apa yang terjadi jika ada pengecualian yang tumpang tindih di kalender?

A4: Aspose.Tasks untuk .NET memungkinkan Anda menangani pengecualian yang tumpang tindih dengan menentukan prioritas atau menyelesaikan konflik berdasarkan kebutuhan proyek Anda.

### Q5: Dapatkah saya menyesuaikan waktu kerja untuk setiap hari dalam pengecualian?

A5: Ya, Anda dapat menentukan waktu kerja khusus untuk setiap hari dalam pengecualian untuk mengakomodasi kebutuhan penjadwalan tertentu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
