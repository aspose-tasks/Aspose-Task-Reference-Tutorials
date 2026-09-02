---
date: 2026-04-13
description: Pelajari cara menghapus pengecualian kalender di Aspose.Tasks untuk .NET
  dan memeriksa tanggal pengecualian saat mengelola penjadwalan kalender ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Hapus Pengecualian Kalender dengan Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hapus Pengecualian Kalender dengan Aspose.Tasks
url: /id/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hapus Pengecualian Kalender dengan Aspose.Tasks

## Pendahuluan

Dalam tutorial ini, Anda akan belajar cara **menghapus pengecualian kalender** dan mengelola pengecualian kalender lainnya di Aspose.Tasks menggunakan kerangka kerja .NET. Pengecualian kalender memungkinkan Anda memodelkan hari libur, penutupan sementara, atau periode khusus apa pun di mana jadwal kerja normal berubah. Memahami cara menambahkan, menanyakan, dan menghapus pengecualian ini sangat penting untuk penjadwalan proyek yang akurat, terutama saat bekerja dengan skenario **penjadwalan kalender ASP.NET**.

## Jawaban Cepat
- **Apa metode utama untuk menghapus pengecualian?** Gunakan metode `Delete()` pada objek `CalendarException`.  
- **Kelas mana yang memeriksa tanggal terhadap pengecualian?** `CalendarException.CheckException()`—berguna untuk **memeriksa tanggal pengecualian**.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya menambahkan beberapa pengecualian ke satu kalender?** Tentu saja; koleksi `Exceptions` mendukung banyak entri.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu Pengecualian Kalender?

**Pengecualian kalender** mewakili penyimpangan dari kalender kerja reguler—bayangkan sebagai aturan yang menyatakan “pada tanggal-tanggal ini, jam kerja berbeda atau tidak ada sama sekali.” Di Aspose.Tasks, setiap pengecualian dapat memiliki waktu kerja sendiri, pola berulang, dan flag yang menunjukkan apakah hari tersebut merupakan hari kerja.

## Mengapa Mengelola Pengecualian Kalender dalam Penjadwalan Kalender ASP.NET?

- **Garis waktu yang akurat:** Proyek secara otomatis menghormati hari libur dan penutupan khusus, mencegah tenggat waktu yang tidak realistis.  
- **Fleksibilitas:** Anda dapat mendefinisikan pola harian, mingguan, bulanan, atau tahunan, menyesuaikan dengan kalender bisnis dunia nyata.  
- **Otomatisasi:** Memeriksa tanggal pengecualian secara programatik memungkinkan Anda membangun logika penjadwalan dinamis dalam aplikasi ASP.NET.

## Prasyarat

- Pengetahuan dasar pemrograman C#.  
- Visual Studio (versi terbaru apa pun).  
- Perpustakaan Aspose.Tasks untuk .NET ditambahkan ke proyek Anda (melalui NuGet atau referensi manual).  

## Impor Namespace

Pertama, impor namespace yang Anda perlukan:

```csharp
using Aspose.Tasks;
using System;
```

## Langkah 1: Hapus Pengecualian Kalender

Menghapus pengecualian yang tidak diinginkan sangat mudah. Kode berikut memuat proyek, memilih kalender pertama, menampilkan info dasar, menghapus pengecualian pertama, dan kemudian menunjukkan jumlah yang diperbarui.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Pro tip:** Selalu verifikasi bahwa indeks pengecualian ada sebelum memanggil `Delete()` untuk menghindari `IndexOutOfRangeException`.

## Langkah 2: Dapatkan Waktu Kerja dari Pengecualian Kalender

Jika Anda perlu memeriksa jam kerja yang didefinisikan untuk sebuah pengecualian, gunakan `GetWorkingTime()`. Contoh ini juga menunjukkan cara **memeriksa tanggal pengecualian** dengan `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Langkah 3: Definisikan Pengecualian Kalender

Berikut adalah contoh lengkap yang menunjukkan cara **menambah**, **memeriksa**, dan **menghapus** pengecualian kalender. Perhatikan penggunaan `CheckException` untuk **memeriksa tanggal pengecualian** pada momen tertentu.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Masalah Umum & Tips

| Masalah | Alasan | Solusi |
|-------|--------|----------|
| **`IndexOutOfRangeException` saat menghapus** | Mencoba menghapus pengecualian yang tidak ada. | Verifikasi `calendar.Exceptions.Count` > indeks sebelum memanggil `Delete()`. |
| **Waktu kerja tidak tepat** | Tidak mengatur `DayWorking` atau `WorkingTimes` dengan benar. | Gunakan `exception.WorkingTimes.Add(new WorkingTime(...))` untuk mendefinisikan periode eksplisit. |
| **Pengecualian tidak dikenali** | `CheckException` mengembalikan `false` karena tanggal berada di luar rentang yang ditentukan. | Periksa kembali `FromDate`/`ToDate` dan `Type` (Daily, Weekly, dll.). |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menambahkan beberapa pengecualian ke satu kalender?**  
A: Ya, Anda dapat menambahkan sebanyak mungkin pengecualian yang diperlukan untuk mewakili hari libur, jendela pemeliharaan, atau aturan penjadwalan khusus apa pun.

**Q: Bagaimana cara **memeriksa tanggal pengecualian** untuk hari tertentu?**  
A: Gunakan metode `CheckException(DateTime date)` pada instance `CalendarException`. Metode ini mengembalikan `true` jika tanggal yang diberikan berada dalam rentang pengecualian.

**Q: Apakah memungkinkan menghapus pengecualian yang ada dari kalender?**  
A: Tentu saja. Akses koleksi `Exceptions` dan panggil `Remove()` atau gunakan `Delete()` pada objek `CalendarException` tertentu.

**Q: Jenis pengecualian kalender apa yang didukung?**  
A: Aspose.Tasks mendukung tipe pengecualian Daily, Weekly, Monthly, dan Yearly, memberi Anda fleksibilitas untuk memodelkan hampir semua pola berulang.

**Q: Bisakah saya menyesuaikan jam kerja untuk tanggal pengecualian tertentu?**  
A: Ya. Setelah membuat pengecualian, isi koleksi `WorkingTimes`-nya dengan objek `WorkingTime` yang menentukan waktu mulai dan selesai untuk hari tersebut.

## Kesimpulan

Kami telah menelusuri siklus lengkap operasi **menghapus pengecualian kalender**, mulai dari memeriksa pengecualian yang ada hingga menambahkan yang baru dan memeriksa tanggal. Menguasai teknik ini memastikan jadwal proyek Anda menghormati kalender dunia nyata, membuat implementasi penjadwalan kalender ASP.NET Anda menjadi kuat dan dapat diandalkan.

---

**Last Updated:** 2026-04-13  
**Diuji Dengan:** Aspose.Tasks for .NET (latest release)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}