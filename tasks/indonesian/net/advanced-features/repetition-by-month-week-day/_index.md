---
date: 2026-04-01
description: Pelajari cara mengatur pengulangan di Aspose.Tasks untuk .NET, menambahkan
  tugas berulang, dan mengotomatiskan tugas berulang berdasarkan bulan, minggu, dan
  hari.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Pengulangan berdasarkan Bulan, Minggu, Hari di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Mengatur Pengulangan di Aspose.Tasks (Bulan, Minggu, Hari)
url: /id/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Pengulangan di Aspose.Tasks (Bulan, Minggu, Hari)

## Pendahuluan

Jika Anda perlu **cara mengatur pengulangan** untuk tugas dalam sebuah proyek, Aspose.Tasks untuk .NET memberikan cara yang bersih dan programatis untuk menambahkan definisi tugas berulang yang dijalankan per bulan, minggu, atau hari. Dalam tutorial ini kami akan membahas contoh dunia nyata yang menunjukkan cara **menambahkan tugas berulang**, **mengotomatiskan tugas berulang**, dan mengelolanya langsung dari kode C#. Pada akhir tutorial, Anda akan siap mengintegrasikan kemampuan ini ke dalam solusi penjadwalan atau manajemen proyek apa pun.

## Jawaban Cepat
- **Apa arti “recurrence” dalam Aspose.Tasks?** Ini mendefinisikan pola (harian, mingguan, bulanan) yang secara otomatis membuat instance tugas selama rentang tanggal.  
- **Metode utama mana yang membuat pengulangan?** `RecurringTaskParameters` digabungkan dengan `RecurrencePattern` tertentu.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode ini?** Versi percobaan dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menjadwalkan tugas mingguan alih-alih bulanan?** Ya – ganti `MonthlyRecurrencePattern` dengan `WeeklyRecurrencePattern`.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 and later.

## Apa Itu Pengulangan di Aspose.Tasks?

Pengulangan adalah sekumpulan aturan yang memberi tahu Aspose.Tasks untuk menghasilkan instance tugas pada interval reguler—harian, mingguan, atau bulanan—tanpa menyalin secara manual. Fitur ini penting untuk proyek yang berisi aktivitas rutin seperti rapat status, inspeksi, atau pekerjaan pemeliharaan.

## Mengapa Menggunakan Fitur Pengulangan?

- **Hemat waktu:** Tidak perlu menyalin‑tempel tugas secara manual.  
- **Kurangi kesalahan:** Perpustakaan menjamin tanggal dan durasi yang konsisten.  
- **Fleksibilitas:** Gabungkan pola (misalnya, “Minggu pertama setiap 2 bulan”).  
- **Otomatisasi:** Sangat cocok untuk menghasilkan jadwal dalam pipeline CI atau alat pelaporan.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **Pemahaman Dasar tentang C#** – Anda akan menulis beberapa baris kode C#.  
2. **Aspose.Tasks untuk .NET terpasang** – dapatkan dari [halaman unduhan](https://releases.aspose.com/tasks/net/).  
3. **File proyek .mpp** – kami akan menggunakan `Project1.mpp` sebagai file sumber.

## Impor Namespace

Untuk memulai, impor namespace Aspose.Tasks yang diperlukan:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Langkah 1: Muat File Proyek

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Kami membuat instance `Project` yang menunjuk ke file Microsoft Project yang ada.

### Langkah 2: Definisikan Parameter Tugas Berulang

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Di sini kami **membuat parameter tugas berulang**:

- **TaskName** – nama tugas yang dihasilkan.  
- **Duration** – berapa lama setiap kejadian berlangsung.  
- **RecurrencePattern** – pola bulanan yang berulang setiap 2 bulan pada Minggu pertama.  
- **RecurrenceRange** – tanggal mulai dan selesai yang membatasi jadwal.

### Langkah 3: Tambahkan Tugas Berulang ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

Baris ini **menambahkan tugas berulang** ke akar hierarki proyek.

### Langkah 4: Simpan Proyek yang Diperbarui

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Proyek disimpan sebagai file `.mpp` baru yang kini berisi jadwal otomatis.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Tugas tidak muncul** | Rentang pengulangan berada di luar tanggal proyek. | Verifikasi nilai `Start` dan `Finish` berada dalam kalender proyek. |
| **Hari minggu salah** | `WeekDay` enum tidak cocok. | Gunakan `DayOfWeek.Monday` … `DayOfWeek.Sunday` sesuai kebutuhan. |
| **Pengecualian lisensi** | Menjalankan tanpa lisensi yang valid di produksi. | Terapkan lisensi sementara atau penuh sebelum menyimpan. |

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menyesuaikan pola pengulangan di luar contoh yang diberikan?

A1: Ya, Aspose.Tasks untuk .NET menawarkan opsi penyesuaian yang luas untuk pola pengulangan, memungkinkan Anda menyesuaikannya dengan kebutuhan spesifik Anda.

### Q2: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk .NET?

A2: Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Tasks untuk .NET dari [halaman rilis](https://releases.aspose.com/).

### Q3: Bagaimana saya dapat memperoleh dukungan untuk Aspose.Tasks untuk .NET?

A3: Anda dapat mencari bantuan dan berinteraksi dengan komunitas di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q4: Apakah lisensi sementara tersedia untuk Aspose.Tasks untuk .NET?

A4: Ya, Anda dapat memperoleh lisensi sementara dari [halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

### Q5: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Tasks untuk .NET?

A5: Anda dapat merujuk ke [dokumentasi](https://reference.aspose.com/tasks/net/) terperinci yang tersedia di situs web Aspose untuk panduan mendalam tentang penggunaan perpustakaan.

---

**Terakhir Diperbarui:** 2026-04-01  
**Diuji Dengan:** Aspose.Tasks 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}