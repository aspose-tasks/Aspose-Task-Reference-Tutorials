---
title: Menguasai Waktu Kerja di Aspose.Tugas
linktitle: Pengumpulan Waktu Kerja di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Jelajahi kekuatan Aspose.Tasks untuk .NET dalam mengelola jadwal proyek secara efisien. Sesuaikan kalender, atur waktu kerja, dan sederhanakan proyek Anda dengan mudah.
type: docs
weight: 14
url: /id/net/time-recurrence-configuration/working-time-collection/
---
## Perkenalan
Apakah Anda ingin menguasai seni mengatur waktu kerja di Aspose.Tasks untuk .NET? Tidak perlu mencari lagi! Dalam panduan langkah demi langkah ini, kami akan mempelajari seluk-beluk pengumpulan waktu kerja menggunakan Aspose.Tasks, sehingga memberdayakan Anda untuk menangani kalender khusus secara efisien dan menyederhanakan jadwal proyek Anda.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Halaman rilis Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Lingkungan Kerja: Siapkan lingkungan pengembangan yang sesuai, sebaiknya menggunakan IDE yang kompatibel dengan .NET.
## Impor Namespace
Dalam proyek Anda, impor namespace yang diperlukan untuk mengakses fungsi Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Sekarang, mari kita bagi tutorial menjadi beberapa langkah, untuk memastikan pengalaman belajar yang lancar.
## Langkah 1: Buat Kalender Khusus
Mulailah dengan membuat proyek baru dan menambahkan kalender khusus ke dalamnya:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Langkah 2: Tentukan Hari Kerja
Atur hari kerja default dari Senin hingga Jumat:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Langkah 3: Konfigurasikan Waktu Kerja Sabtu
Tentukan waktu kerja untuk hari Sabtu:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Langkah 4: Cetak Masa Kerja Sabtu
Cetak waktu kerja yang dikonfigurasi untuk hari Sabtu:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Langkah 5: Konfigurasikan Waktu Kerja Minggu
Tentukan waktu kerja untuk hari Minggu:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Langkah 6: Cetak Masa Kerja Minggu
Cetak waktu kerja yang dikonfigurasi untuk hari Minggu:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Langkah 7: Tambahkan Hari Khusus ke Kalender
Sertakan hari Sabtu dan Minggu yang dikonfigurasi di kalender:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Langkah 8: Melintasi Waktu Kerja
Telusuri waktu kerja dan tampilkan untuk setiap hari di kalender:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Kini setelah Anda berhasil menavigasi langkah-langkahnya, Anda diperlengkapi untuk memanfaatkan kekuatan Aspose.Tasks untuk .NET dalam mengelola waktu kerja secara efektif.
## Kesimpulan
Menguasai pengumpulan waktu kerja di Aspose.Tasks memberdayakan Anda untuk menyesuaikan kalender proyek, memastikan penjadwalan yang tepat dan pemanfaatan sumber daya yang efisien. Selami proyek Anda dengan percaya diri, berbekal pengetahuan yang diperoleh dari panduan komprehensif ini.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks cocok untuk manajemen proyek skala besar?
Ya, Aspose.Tasks dirancang untuk menangani proyek dengan berbagai ukuran, menyediakan fitur canggih untuk manajemen proyek yang efisien.
### Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan .NET lainnya?
Tentu! Aspose.Tasks terintegrasi secara mulus dengan pustaka .NET lainnya, meningkatkan keserbagunaan dan kompatibilitasnya.
### Seberapa sering Aspose.Tasks diperbarui?
 Aspose.Tasks diperbarui secara berkala untuk memasukkan fitur baru, penyempurnaan, dan peningkatan kompatibilitas. Periksalah[halaman rilis](https://releases.aspose.com/tasks/net/) untuk pembaruan terkini.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat menjelajahi Aspose.Tasks dengan uji coba gratis dengan mengunjungi[Link ini](https://releases.aspose.com/).
### Di mana saya dapat mencari dukungan untuk Aspose.Tasks?
 Untuk pertanyaan atau bantuan apa pun, kunjungi[Forum dukungan Aspose.Tasks](https://forum.aspose.com/c/tasks/15).