---
title: Sesuaikan Minggu Kerja di Aspose.Tasks
linktitle: Kumpulan Minggu Kerja di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyesuaikan minggu kerja di Aspose.Tasks untuk .NET. Panduan langkah demi langkah untuk membuat kalender proyek yang dipersonalisasi. Unduh sekarang!
type: docs
weight: 17
url: /id/net/time-recurrence-configuration/workweek-collection/
---
## Perkenalan
Selamat datang di tutorial kami tentang cara membuat minggu kerja khusus menggunakan Aspose.Tasks untuk .NET! Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menentukan minggu kerja yang dipersonalisasi untuk kalender di proyek Anda. Aspose.Tasks adalah perpustakaan canggih yang memberdayakan pengembang untuk bekerja secara efisien dengan dokumen Microsoft Project di aplikasi .NET mereka.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di mesin Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.
## Impor Namespace
Dalam proyek C# Anda, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Buat Proyek dan Kalender
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Langkah 2: Tentukan Minggu Kerja Kustom
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Langkah 3: Tetapkan Hari Kerja
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Langkah 4: Tampilkan Informasi Minggu Kerja
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Panduan komprehensif ini memberdayakan Anda untuk secara efisien membuat dan mengelola minggu kerja khusus menggunakan Aspose.Tasks untuk .NET.
## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET memberikan solusi tangguh untuk menangani kalender proyek dengan minggu kerja khusus. Dengan mengikuti tutorial ini, Anda telah mempelajari cara membuat dan menampilkan informasi tentang minggu kerja khusus di proyek Anda.
## FAQ
### Bisakah saya memiliki beberapa minggu kerja khusus dalam satu proyek?
Ya, Anda dapat menambahkan beberapa minggu kerja khusus ke kalender proyek.
### Bagaimana cara mengubah minggu kerja yang ada?
 Gunakan yang disediakan`WorkWeek` properti dan metode untuk mengubah minggu kerja yang ada.
### Apakah Aspose.Tasks kompatibel dengan .NET Core?
Ya, Aspose.Tasks mendukung .NET Core.
### Bisakah saya mengekspor proyek dengan minggu kerja khusus ke format file Microsoft Project?
Tentu saja, Aspose.Tasks memungkinkan Anda menyimpan proyek Anda dalam berbagai format, termasuk Microsoft Project.
### Di mana saya dapat mencari dukungan untuk pertanyaan terkait Aspose.Tasks?
 mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan atau bantuan apa pun.