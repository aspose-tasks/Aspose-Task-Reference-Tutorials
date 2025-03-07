---
title: Mengonfigurasi Waktu Kerja di Aspose.Tasks
linktitle: Mengonfigurasi Waktu Kerja di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Tingkatkan penjadwalan proyek di .NET dengan Aspose.Tasks. Konfigurasikan waktu kerja dengan mudah untuk pengelolaan sumber daya yang tepat. Unduh perpustakaannya sekarang!
weight: 13
url: /id/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonfigurasi Waktu Kerja di Aspose.Tasks

## Perkenalan
Dalam manajemen proyek, pengendalian waktu kerja yang tepat sangat penting untuk penjadwalan dan alokasi sumber daya yang akurat. Aspose.Tasks untuk .NET memberikan solusi ampuh untuk menangani informasi waktu kerja dalam proyek Anda. Tutorial ini akan memandu Anda melalui proses konfigurasi waktu kerja menggunakan Aspose.Tasks di lingkungan .NET.
## Prasyarat
Sebelum mendalami tutorial, pastikan Anda memiliki hal berikut:
- Pemahaman dasar bahasa pemrograman C#.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Visual Studio atau pengaturan lingkungan pengembangan C# pilihan apa pun.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Langkah 1: Buat Kalender
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Di sini, kami memulai proyek baru dan membuat kalender bernama "MyCalendar" berdasarkan kalender standar. Kalender ini akan digunakan untuk menentukan waktu kerja tertentu.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Langkah 2: Tampilkan Informasi Minggu Kerja
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Langkah ini mencetak jumlah hari kerja dalam kalender yang ditentukan.
## Langkah 3: Detail Waktu Kerja
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
Di bagian ini, kami mengulangi setiap hari dalam seminggu, mencetak jenis hari dan waktu kerja terkait. Anda dapat menyesuaikan waktu kerja untuk setiap hari kerja sesuai dengan kebutuhan proyek Anda.
## Kesimpulan
Mengonfigurasi waktu kerja secara efektif di Aspose.Tasks untuk .NET memastikan perencanaan proyek dan manajemen sumber daya yang akurat. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengintegrasikan penyesuaian waktu kerja ke dalam alur kerja proyek Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks cocok untuk manajemen proyek skala besar?
Ya, Aspose.Tasks dirancang untuk menangani proyek dengan berbagai ukuran, menawarkan fitur canggih untuk manajemen proyek yang efisien.
### Bisakah saya menetapkan waktu kerja yang berbeda untuk anggota tim yang berbeda?
Sangat. Anda dapat menyesuaikan waktu kerja berdasarkan sumber daya, memungkinkan jadwal individual.
### Apakah Aspose.Tasks mendukung integrasi dengan alat manajemen proyek lainnya?
Ya, Aspose.Tasks memfasilitasi integrasi dengan berbagai alat manajemen proyek, sehingga meningkatkan interoperabilitas.
### Apakah mungkin untuk mengimpor/mengekspor data proyek dalam format berbeda?
Aspose.Tasks mendukung berbagai format file, memungkinkan operasi impor/ekspor yang lancar untuk data proyek.
### Seberapa sering pembaruan Aspose.Tasks dirilis?
Pembaruan dirilis secara berkala untuk memastikan kompatibilitas dengan teknologi terbaru dan menanggapi masukan pengguna.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
