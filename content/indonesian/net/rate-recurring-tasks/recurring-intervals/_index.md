---
title: Interval Berulang Proyek MS yang Mudah di Aspose.Tasks
linktitle: Mengelola Interval Berulang di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Temukan cara mengelola interval berulang dengan mudah di MS Project menggunakan Aspose.Tasks untuk .NET.
type: docs
weight: 12
url: /id/net/rate-recurring-tasks/recurring-intervals/
---
## Perkenalan
Apakah Anda ingin mengelola interval berulang secara efisien dalam file Microsoft Project menggunakan Aspose.Tasks untuk .NET? Tutorial komprehensif ini akan memandu Anda melalui proses langkah demi langkah, memastikan Anda dapat dengan mudah menangani interval berulang dalam proyek Anda. Sebelum masuk ke tutorial, mari kita bahas beberapa prasyarat untuk memastikan Anda siap untuk memulai.
## Prasyarat
Sebelum melanjutkan tutorial ini, pastikan Anda memiliki hal berikut:
1. Pengetahuan tentang Pemrograman C#: Diperlukan pemahaman dasar tentang bahasa pemrograman C# dan sintaksisnya.
2. Visual Studio Terpasang: Pastikan Anda telah menginstal Visual Studio di sistem Anda untuk mengkode dan mengkompilasi aplikasi .NET.
3. Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/tasks/net/).

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh perpustakaan Aspose.Tasks untuk .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah dan menjelaskannya secara detail.
## Langkah 1: Inisialisasi Objek Proyek:
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
Di sini, kami menginisialisasi instance baru dari`Project` kelas dengan menyediakan jalur ke file Microsoft Project.
## Langkah 2: Tetapkan Tanggal Status:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Langkah ini menetapkan tanggal status proyek ke tanggal mulainya.
## Langkah 3: Akses Tampilan Gantt Chart:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Kami mengakses tampilan Gantt Chart dari proyek tersebut.
## Langkah 4: Baca Jalur Kemajuan:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Langkah ini mengambil interval berulang untuk garis kemajuan dari tampilan Gantt Chart.
## Langkah 5: Tampilkan Informasi Interval:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Di sini, kami menampilkan informasi tentang interval, jumlah minggu mingguan, dan hari mingguan.
## Langkah 6: Definisikan Ulang Interval Berulang:
```csharp
var newInterval = new RecurringInterval();
```
 Kami membuat contoh baru`RecurringInterval` untuk mendefinisikan ulang interval berulang.
## Langkah 7: Tetapkan Garis Kemajuan Bulanan:
```csharp
// Tetapkan garis kemajuan bulanan berdasarkan hari.
interval.MonthlyDay = true;
// Tetapkan jumlah hari garis kemajuan bulanan.
interval.MonthlyDayDayNumber = 1;
// Tetapkan jumlah bulan dari garis kemajuan bulanan.
interval.MonthlyDayMonthNumber = 1;
// Tetapkan garis kemajuan berdasarkan hari pertama atau terakhir yang telah ditentukan.
interval.MonthlyFirstLast = true;
// Tetapkan jenis garis kemajuan bulanan hari pertama atau terakhir.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Tetapkan jumlah bulan garis kemajuan.
interval.MonthlyFirstLastMonthNumber = 1;
```
Langkah-langkah ini mengonfigurasi jalur kemajuan bulanan sesuai dengan parameter yang ditentukan.
## Langkah 8: Perbarui Garis Kemajuan:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Kami memperbarui garis kemajuan dalam tampilan Gantt Chart dengan interval berulang yang baru ditentukan.
## Langkah 9: Simpan Proyek sebagai PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Terakhir, kami menyimpan proyek dengan interval berulang yang diperbarui sebagai file PDF.

## Kesimpulan
Kesimpulannya, pengelolaan interval berulang dalam file Microsoft Project menggunakan Aspose.Tasks untuk .NET menjadi sederhana dengan fungsionalitas komprehensif yang disediakan oleh perpustakaan. Dengan mengikuti panduan langkah demi langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien menangani interval berulang dalam proyek Anda, sehingga meningkatkan produktivitas dan organisasi.
### FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan bahasa pemrograman lain?
Ya, Aspose.Tasks untuk .NET dapat digunakan dengan bahasa apa pun yang didukung .NET seperti C# dan VB.NET.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?
 Anda bisa mendapatkan dukungan dari forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk .NET?
 Ya, Anda dapat membeli lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi lengkap Aspose.Tasks untuk .NET?
 Dokumentasi lengkap dapat ditemukan[Di Sini](https://reference.aspose.com/tasks/net/).