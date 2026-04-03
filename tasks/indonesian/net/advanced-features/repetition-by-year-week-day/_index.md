---
date: 2026-04-03
description: Pelajari cara menggunakan Aspose.Tasks untuk menambahkan tugas berulang
  ke proyek dan menyimpan proyek sebagai MPP. Panduan ini menunjukkan fitur Pengulangan
  berdasarkan Tahun, Minggu, dan Hari langkah demi langkah.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Pengulangan berdasarkan Tahun, Minggu, Hari di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Menggunakan Aspose.Tasks – Pengulangan Berdasarkan Tahun, Minggu, Hari
url: /id/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengulangan berdasarkan Tahun Minggu Hari dalam Aspose.Tasks

## Pendahuluan

Ketika Anda perlu **how to use Aspose.Tasks** untuk menangani jadwal berulang yang kompleks, perpustakaan ini memberi Anda kontrol yang halus atas pola tahunan. Dalam tutorial ini kami akan menjelaskan cara membuat tugas yang berulang pada hari kerja tertentu dalam bulan tertentu, meliputi beberapa tahun. Pada akhir tutorial Anda akan dapat **add recurring task project** entri dan **save project as MPP** dengan hanya beberapa baris kode C#.

## Jawaban Cepat
- **What does “Repetition by Year Week Day” mean?** Itu mengulangi sebuah tugas pada hari kerja yang dipilih (misalnya, Minggu pertama) dari bulan tertentu setiap tahun.  
- **Which .NET versions are supported?** Semua versi .NET Framework dan .NET Core/5/6 modern.  
- **Do I need a license to run the code?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Can I change the recurrence range?** Ya – Anda dapat mengatur tanggal mulai, tanggal selesai, atau jumlah kejadian tetap.  
- **Is the output an MPP file?** Tentu – proyek disimpan sebagai file MPP yang siap untuk Microsoft Project.

## Apa itu fitur “Repetition by Year Week Day”?

Fitur ini memungkinkan Anda mendefinisikan pengulangan tahunan yang menargetkan **day of the week** tertentu (misalnya, Sunday) dan **position** dalam bulan (pertama, kedua, terakhir, dll.). Ini ideal untuk tugas seperti tinjauan kuartalan, audit tahunan, atau acara apa pun yang mengikuti irama berbasis kalender.

## Mengapa menggunakan Aspose.Tasks untuk tugas berulang?

- **Precision** – Kontrol penuh atas bulan, hari kerja, dan posisi ordinal.  
- **Compatibility** – Menghasilkan file MPP native yang dapat dibuka tanpa masalah di Microsoft Project.  
- **No COM interop** – API .NET murni, tidak memerlukan instalasi Office.  
- **Scalability** – Berfungsi untuk proyek kecil maupun jadwal tingkat perusahaan.

## Prasyarat

Sebelum menyelami kode, pastikan Anda memiliki:

1. **Basic .NET knowledge** – Familiaritas dengan C# dan konsep berorientasi objek.  
2. **Aspose.Tasks for .NET** – Unduh dari [tautan unduhan](https://releases.aspose.com/tasks/net/) dan tambahkan DLL ke proyek Anda.  
3. **Access to the official docs** – [dokumentasi](https://reference.aspose.com/tasks/net/) berisi detail lengkap tentang semua kelas.  
4. **A development IDE** – Visual Studio, Rider, atau editor .NET kompatibel lainnya.

Sekarang Anda siap, mari lihat implementasinya.

## Cara Menggunakan Aspose.Tasks untuk Tugas Berulang

### Mengimpor Namespace yang Diperlukan

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup sehingga Anda dapat bekerja dengan proyek, tugas, dan opsi penyimpanan.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Langkah 1: Inisialisasi Proyek dan Parameter Tugas

Buat instance `Project` baru, kemudian definisikan objek `RecurringTaskParameters` yang menggambarkan pola pengulangan.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Sesuaikan `Month`, `WeekDay`, dan `Position` agar sesuai dengan jadwal dunia nyata Anda.

### Langkah 2: Tambahkan Parameter ke Proyek

Sisipkan definisi tugas berulang ke dalam root proyek.

```csharp
project.RootTask.Children.Add(parameters);
```

### Langkah 3: Simpan Proyek sebagai MPP

Akhirnya, simpan proyek ke file MPP sehingga dapat dibuka di Microsoft Project atau penampil kompatibel lainnya.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Ini menunjukkan **save project as mpp** dalam satu baris kode.

## Masalah Umum dan Solusinya

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| Tidak ada tugas yang muncul setelah membuka file MPP | Tanggal rentang pengulangan berada di luar kalender proyek | Verifikasi tanggal `Start` dan `Finish` berada dalam waktu kerja proyek |
| Exception `ArgumentNullException` pada `Add` | `parameters` bernilai null atau tidak terinisialisasi sepenuhnya | Pastikan semua properti yang diperlukan (TaskName, Duration, RecurrencePattern) telah diatur |
| Hari kerja yang dipilih salah | Nilai enum `WeekDay` tidak cocok | Gunakan `DayOfWeek.Monday` … `DayOfWeek.Sunday` sesuai kebutuhan |

## Pertanyaan yang Sering Diajukan

**Q: Can I customize the recurrence pattern beyond the provided example?**  
A: Ya, Aspose.Tasks memungkinkan Anda menggabungkan objek `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, atau bahkan `RecurrenceRange` kustom untuk menyesuaikan jadwal apa pun.

**Q: Is Aspose.Tasks for .NET compatible with other project management software?**  
A: Tentu – perpustakaan ini dapat membaca dan menulis format MPP, XML, dan Primavera, memungkinkan pertukaran data yang lancar.

**Q: How can I handle exceptions or modifications to recurring tasks?**  
A: Gunakan kelas `ExceptionTask` untuk membuat penimpaan pada kejadian tertentu, atau edit `RecurringTaskParameters` dan simpan kembali proyek.

**Q: Does Aspose.Tasks support cloud‑based solutions?**  
A: Ya, Anda dapat menjalankan API di Azure Functions, AWS Lambda, atau layanan cloud apa pun yang kompatibel dengan .NET.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.Tasks untuk .NET dari [situs web](https://releases.aspose.com/), memungkinkan Anda menjelajahi fiturnya sebelum membuat keputusan pembelian.

**Q: How do I add a recurring task to an existing project without overwriting other data?**  
A: Muat proyek yang ada dengan `new Project("Existing.mpp")`, tambahkan `RecurringTaskParameters` ke `RootTask.Children`, lalu `Save` file tersebut.

## Kesimpulan

Dengan menguasai **how to use Aspose.Tasks** untuk skenario **Repetition by Year Week Day**, Anda memperoleh kemampuan untuk **add recurring task project** entri yang selaras sempurna dengan kalender dunia nyata dan **save project as MPP** untuk kolaborasi tanpa hambatan. Gabungkan potongan kode ini ke dalam solusi Anda sendiri untuk meningkatkan akurasi penjadwalan dan mengurangi upaya manual.

---

**Terakhir Diperbarui:** 2026-04-03  
**Diuji Dengan:** Aspose.Tasks 24.12 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}