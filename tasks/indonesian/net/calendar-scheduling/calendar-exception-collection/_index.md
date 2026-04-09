---
date: 2026-04-09
description: Pelajari cara mengatur kalender standar dan mengelola hari libur proyek
  dalam proyek .NET Anda menggunakan Aspose.Tasks untuk penjadwalan yang akurat.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Atur Kalender Standar dan Tangani Pengecualian di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Atur Kalender Standar dan Tangani Pengecualian di Aspose.Tasks
url: /id/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Setel Kalender Standar dan Tangani Pengecualian di Aspose.Tasks

## Pendahuluan

Penjadwalan yang akurat adalah tulang punggung setiap proyek yang berhasil, dan rencana dunia nyata sering harus menyimpang dari kalender kerja default karena hari libur, acara khusus, atau penghentian tak terduga. Aspose.Tasks untuk .NET memudahkan untuk **set standard calendar** settings dan kemudian menambahkan pengecualian khusus di atasnya. Dalam tutorial ini Anda akan belajar cara memuat kalender proyek, menyetel kalender standar, dan mengelola hari libur proyek melalui fitur Calendar Exception Collection.

## Jawaban Cepat
- **Apa yang dilakukan “set standard calendar”?** Ini mengatur ulang kalender ke waktu kerja default (09.00‑17.00, Senin‑Jumat) sebelum Anda menambahkan pengecualian khusus.  
- **Metode mana yang menghapus pengecualian yang ada?** `Calendar.Exceptions.Clear()` menghapus semua pengecualian yang sebelumnya didefinisikan.  
- **Bagaimana cara menambahkan hari libur?** Buat `CalendarException` dengan `DayWorking = false` dan tambahkan ke koleksi.  
- **Apakah saya perlu memuat ulang proyek setelah perubahan?** Tidak, perubahan diterapkan langsung ke objek `Project` dalam memori.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk .NET (versi .NET yang didukung) dan namespace `System`.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

1. **Aspose.Tasks for .NET** – unduh di [here](https://releases.aspose.com/tasks/net/).  
2. Pengetahuan dasar tentang **C#** – Anda akan menulis beberapa potongan kode singkat.  
3. Lingkungan pengembangan seperti **Visual Studio** atau **JetBrains Rider**.

## Impor Namespace

Direktif `using` ini memberi Anda akses ke kelas yang diperlukan untuk manipulasi kalender.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Apa itu Pengecualian Kalender?

*Pengecualian kalender* mewakili periode di mana jadwal kerja normal diubah – misalnya, libur perusahaan atau jadwal lembur sementara. Dengan menambahkan pengecualian ke kalender, Anda dapat memodelkan kendala dunia nyata tanpa mengubah kalender dasar.

## Cara Menyetel Kalender Standar di Aspose.Tasks

Langkah pertama adalah memuat file proyek Anda dan mengambil kalender yang ingin Anda gunakan.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Langkah 1: Hapus Pengecualian yang Ada dan Atur Ulang ke Kalender Standar

Sebelum menambahkan aturan baru, sebaiknya hapus semua pengecualian lama dan **set standard calendar** settings. Ini memastikan baseline yang bersih.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Langkah 2: Definisikan Pengecualian Waktu Kerja

Kadang‑kadang Anda perlu membuat jadwal sementara (misalnya, jam kerja tambahan untuk peluncuran produk). Potongan kode berikut mendefinisikan pengecualian waktu kerja yang mencakup beberapa hari dan dua periode kerja harian.

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

### Langkah 3: Tambahkan Pengecualian Waktu Non‑Kerja (Hari Libur)

Untuk **manage project holidays**, buat pengecualian di mana `DayWorking` bernilai `false`. Contoh di bawah menambahkan blok libur selama dua hari.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Langkah 4: Tampilkan Pengecualian Kalender (Verifikasi)

Setelah menambahkan pengecualian, Anda sering ingin memverifikasi bahwa mereka tercatat dengan benar. Loop berikut mencetak detail setiap pengecualian ke konsol.

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

### Langkah 5: Hapus Semua Pengecualian (Pembersihan)

Jika Anda perlu mengembalikan kalender ke keadaan semula, Anda dapat menghapus setiap pengecualian secara programatik.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Masalah Umum dan Solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Pengecualian tidak muncul setelah menyimpan | Proyek tidak disimpan setelah modifikasi | Panggil `project.Save("output.mpp")` setelah melakukan perubahan. |
| Pengecualian yang tumpang tindih menyebabkan jam kerja yang tidak terduga | Aspose.Tasks menggunakan pengecualian yang ditambahkan terakhir untuk periode yang tumpang tindih | Urutkan pemanggilan `Add` Anda dengan hati-hati atau sesuaikan prioritas secara manual. |
| `MakeStandardCalendar` mengatur ulang waktu kerja khusus | Ini memang menghapus waktu khusus; tambahkan kembali setelah pemanggilan jika diperlukan. | Tambahkan objek `WorkingTime` khusus Anda setelah memanggil `MakeStandardCalendar`. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menambahkan beberapa pengecualian ke satu kalender?**  
A: Ya, Anda dapat menambahkan beberapa pengecualian ke kalender menggunakan metode `AddRange`.

**Q: Bagaimana cara menangani pengecualian berulang, seperti libur mingguan?**  
A: Anda dapat menghitung pengecualian berulang secara programatik dan menambahkannya ke kalender menggunakan logika khusus.

**Q: Apakah memungkinkan mengimpor pengecualian kalender dari sumber eksternal?**  
A: Ya, Anda dapat membaca pengecualian kalender dari sumber eksternal seperti basis data atau file CSV dan mengintegrasikannya ke dalam proyek Anda.

**Q: Apa yang terjadi jika ada pengecualian yang tumpang tindih dalam kalender?**  
A: Aspose.Tasks untuk .NET memungkinkan Anda menangani pengecualian yang tumpang tindih dengan mendefinisikan prioritas atau menyelesaikan konflik berdasarkan kebutuhan proyek Anda.

**Q: Bisakah saya menyesuaikan waktu kerja untuk setiap hari dalam sebuah pengecualian?**  
A: Ya, Anda dapat menentukan waktu kerja khusus untuk hari-hari tertentu dalam sebuah pengecualian guna memenuhi kebutuhan penjadwalan spesifik.

## Kesimpulan

Dengan **set standard calendar** terlebih dahulu dan kemudian menambahkan pengecualian khusus, Anda mendapatkan kontrol penuh atas penjadwalan proyek, memudahkan **manage project holidays** dan timeline khusus lainnya. Koleksi Pengecualian Kalender di Aspose.Tasks menyediakan cara yang bersih dan programatik untuk memodelkan kalender dunia nyata langsung dalam aplikasi .NET Anda.

---

**Terakhir Diperbarui:** 2026-04-09  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}