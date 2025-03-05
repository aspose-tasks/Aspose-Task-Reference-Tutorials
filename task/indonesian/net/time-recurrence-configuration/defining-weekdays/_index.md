---
title: Menguasai Hari Kerja di Aspose.Tasks untuk .NET
linktitle: Mendefinisikan Hari Kerja di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi kekuatan menentukan hari kerja di Aspose.Tasks .NET. Ikuti tutorial mendetail kami untuk mengelola kalender proyek secara efisien, menyesuaikan waktu kerja, dan banyak lagi.
type: docs
weight: 10
url: /id/net/time-recurrence-configuration/defining-weekdays/
---
## Perkenalan
Jika Anda mendalami dunia manajemen proyek menggunakan Aspose.Tasks untuk .NET, memahami dan memanipulasi hari kerja adalah aspek yang penting. Mengelola dan menyesuaikan hari kerja secara efisien dalam kalender proyek Anda dapat berdampak signifikan pada jadwal proyek. Dalam tutorial ini, kami akan memandu Anda melalui proses menentukan hari kerja menggunakan Aspose.Tasks, memberikan petunjuk langkah demi langkah dan contoh untuk kejelasan yang lebih baik.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar bahasa pemrograman C#.
-  Aspose.Tasks untuk perpustakaan .NET diinstal. Jika tidak, unduh dari[Di Sini](https://releases.aspose.com/tasks/net/).
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek Anda:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Periksa Kesetaraan Hari Kerja
```csharp
// Direktori dokumen Anda
String DataDir = "Your Document Directory";
// Muat file proyek
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Akses hari kerja
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Periksa kesetaraan berdasarkan berbagai properti
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Mengkloning Hari Kerja
```csharp
// Muat file proyek
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Buat salinan mendalam tentang hari kerja
var weekDay2 = weekDay1.Clone();
// Properti keluaran dari kedua hari kerja
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Dapatkan Kode Hash Hari Kerja
```csharp
// Muat file proyek
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Properti keluaran dari kedua hari kerja
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Buat Kalender Baru dengan Hari Kerja yang Ditentukan
```csharp
// Buat proyek baru
var project = new Project();
// Tentukan kalender
var calendar = project.Calendars.Add("Calendar1");
// Tambahkan hari kerja dan hari pengecualian
// Tambahkan pernyataan keluaran serupa untuk FromDate dan ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Tetapkan waktu kerja untuk hari Jumat
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Tetapkan Waktu Kerja Default untuk Sehari
```csharp
// Buat proyek baru
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Tambahkan waktu kerja default untuk Senin hingga Jumat
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Ulangi untuk Selasa, Rabu, Kamis, dan Jumat
// Tetapkan hari non-kerja untuk hari Sabtu dan Minggu
// Tambahkan pernyataan keluaran serupa untuk DayWorking, FromDate, ToDate, dan WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Kesimpulan
Dalam tutorial ini, kami telah membahas aspek penting dalam menentukan hari kerja di Aspose.Tasks untuk .NET. Memanipulasi hari kerja adalah keterampilan kunci untuk manajemen proyek yang efektif. Bereksperimenlah dengan contoh yang diberikan, sesuaikan dengan kebutuhan proyek Anda, dan buka potensi penuh Aspose.Tasks.
## FAQ
### Bisakah saya menentukan waktu kerja khusus untuk setiap hari?
Ya, Anda dapat mengatur waktu kerja khusus untuk hari kerja tertentu menggunakan contoh yang diberikan.
### Apakah mungkin menambahkan beberapa hari pengecualian ke kalender?
Sangat. Ubah kode pada contoh keempat untuk menyertakan hari pengecualian tambahan.
### Bagaimana cara menghapus hari kerja tertentu dari kalender?
Manfaatkan metode yang sesuai yang disediakan oleh perpustakaan Aspose.Tasks untuk menghapus hari kerja sesuai kebutuhan.
### Apakah perubahan yang dilakukan pada hari kerja tetap ada di file proyek?
Ya, setiap modifikasi pada hari kerja akan tercermin dalam file proyek saat disimpan.
### Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
Aspose.Tasks mendukung berbagai bahasa pemrograman, namun contoh di sini khusus untuk .NET.