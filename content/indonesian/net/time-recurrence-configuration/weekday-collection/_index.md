---
title: Menguasai Hari Kerja di Aspose.Tugas
linktitle: Kumpulan Hari Kerja di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Temukan kekuatan Aspose.Tasks untuk .NET dalam mengelola hari kerja dengan mudah. Sesuaikan hari kerja, hapus akhir pekan, dan buat kalender khusus dengan mudah.
type: docs
weight: 11
url: /id/net/time-recurrence-configuration/weekday-collection/
---
## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memfasilitasi manipulasi data manajemen proyek secara efisien. Dalam tutorial ini, kita akan menjelajahi kumpulan hari kerja di Aspose.Tasks, memungkinkan Anda menyesuaikan hari kerja, menghapus akhir pekan, dan membuat kalender khusus untuk memenuhi kebutuhan proyek Anda. Baik Anda pengembang berpengalaman atau pendatang baru, panduan langkah demi langkah ini akan memandu Anda melalui proses bekerja dengan hari kerja di Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
-  Instal perpustakaan Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Aspose.Tasks untuk halaman unduh .NET](https://releases.aspose.com/tasks/net/).
- Familiar dengan bahasa pemrograman C#.
- Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke proyek C# Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Buat Instans Proyek
Inisialisasi proyek Aspose.Tasks baru:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Langkah 2: Akses Kalender
Ambil kalender proyek:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Langkah 3: Sesuaikan Hari Kerja
Hapus hari kerja yang ada dan tetapkan hari kerja default:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Tambahkan hari kerja lainnya dengan cara yang sama...
```
## Langkah 4: Tambahkan Waktu Kerja
Tambahkan waktu kerja untuk hari kerja tertentu:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Langkah 5: Tampilkan Informasi Kalender
Keluarkan detail kalender ke konsol:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Tampilkan setiap hari kerja dan waktu kerja...
```
## Langkah 6: Hapus Akhir Pekan
Hapus hari Sabtu dan Minggu dari hari kerja:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Langkah 7: Tampilkan Waktu Kerja yang Diperbarui
Output waktu kerja yang diperbarui setelah menghapus akhir pekan:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Tampilkan setiap hari kerja dan waktu kerja yang diperbarui...
```
## Langkah 8: Buat Kalender 24 Jam
Buat kalender 24 jam dan salin hari kerja:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Kesimpulan
Dalam tutorial ini, kami menjelajahi kemampuan hebat Aspose.Tasks untuk .NET dalam mengelola hari kerja dalam kalender proyek. Dari menyesuaikan hari kerja hingga membuat kalender 24 jam khusus, Aspose.Tasks menyederhanakan proses, menawarkan fleksibilitas dan kontrol dalam manajemen proyek.
## Pertanyaan yang Sering Diajukan
### T: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan bahasa pemrograman lain?
J: Aspose.Tasks terutama mendukung bahasa .NET, namun juga menawarkan versi untuk Java.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Halaman rilis Aspose.Tasks](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk .NET?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas atau pertimbangkan untuk membeli paket dukungan.
### T: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks untuk .NET?
 J: Lihat[Aspose.Tasks untuk dokumentasi .NET](https://reference.aspose.com/tasks/net/) untuk informasi rinci.
### T: Bagaimana cara mendapatkan lisensi sementara Aspose.Tasks untuk .NET?
 J: Anda dapat memperoleh lisensi sementara dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).