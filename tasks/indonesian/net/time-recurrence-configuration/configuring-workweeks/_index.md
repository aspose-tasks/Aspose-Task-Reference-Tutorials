---
title: Menguasai Konfigurasi Minggu Kerja di Aspose.Tasks
linktitle: Mengonfigurasi Minggu Kerja di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi minggu kerja dengan mudah di Aspose.Tasks untuk .NET. Tingkatkan penjadwalan proyek dan manajemen sumber daya dengan panduan langkah demi langkah kami.
weight: 16
url: /id/net/time-recurrence-configuration/configuring-workweeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Konfigurasi Minggu Kerja di Aspose.Tasks

## Perkenalan
Selamat datang di panduan komprehensif kami tentang mengonfigurasi minggu kerja di Aspose.Tasks untuk .NET. Mengelola minggu kerja secara efisien sangat penting untuk perencanaan dan penjadwalan proyek. Aspose.Tasks menyederhanakan proses ini, memungkinkan Anda menyesuaikan minggu kerja sesuai dengan kebutuhan proyek Anda. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengonfigurasi minggu kerja dengan lancar.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Perpustakaan Aspose.Tasks: Pastikan Anda telah menginstal perpustakaan Aspose.Tasks di proyek .NET Anda. Anda dapat mengunduhnya dari[Situs web Aspose.Tasks](https://releases.aspose.com/tasks/net/).
2. Lingkungan .NET: Pastikan Anda bekerja di lingkungan .NET, dan Anda memiliki pemahaman dasar tentang pemrograman C#.
## Impor Namespace
Untuk memulai, sertakan namespace yang diperlukan dalam proyek Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Siapkan proyek Anda
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project();
```
## Langkah 2: Buat kalender standar
```csharp
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Langkah 3: Tentukan minggu kerja khusus
```csharp
var item = new WorkWeek();
item.Name = "My Work Week";
item.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
item.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Langkah 4: Tentukan hari kerja
```csharp
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
item.WeekDays.Add(new WeekDay(DayType.Saturday));
item.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(item);
```
## Langkah 5: Tampilkan detail minggu kerja
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    // Tampilkan detail minggu kerja
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    Console.WriteLine();
    // Tampilkan waktu kerja khusus untuk setiap hari
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        // Tampilkan waktu kerja
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengonfigurasi minggu kerja di Aspose.Tasks, sehingga meningkatkan kemampuan manajemen proyek Anda.
## Kesimpulan
Kesimpulannya, mengelola minggu kerja adalah aspek mendasar dari perencanaan proyek, dan Aspose.Tasks menyederhanakan proses ini dengan fitur-fitur canggihnya. Dengan menyesuaikan minggu kerja sesuai dengan kebutuhan proyek, Anda dapat memastikan pemanfaatan sumber daya yang efisien dan penjadwalan proyek yang lebih baik.
## FAQ
### Bisakah saya mengonfigurasi beberapa minggu kerja dalam satu proyek?
Ya, Anda dapat mengonfigurasi beberapa minggu kerja dalam proyek yang sama menggunakan Aspose.Tasks.
### Apakah mungkin untuk menetapkan jam kerja yang berbeda untuk hari tertentu?
Sangat. Aspose.Tasks memungkinkan Anda menentukan waktu kerja unik untuk setiap hari dalam satu minggu kerja.
### Bisakah saya mengimpor/mengekspor minggu kerja antar proyek?
Meskipun Aspose.Tasks memberikan kemampuan impor/ekspor yang kuat, minggu kerja biasanya spesifik untuk proyek dan mungkin tidak dapat ditransfer secara langsung.
### Apakah ada batasan jumlah minggu kerja yang dapat saya buat dalam sebuah proyek?
Pada versi saat ini, tidak ada batasan yang ditentukan sebelumnya mengenai jumlah minggu kerja yang dapat Anda konfigurasi dalam sebuah proyek.
### Apakah ada templat bawaan untuk minggu kerja umum?
Ya, Aspose.Tasks menyertakan templat kalender standar yang dapat Anda gunakan sebagai titik awal untuk proyek Anda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
