---
date: 2026-03-08
description: Pelajari cara membuat tugas berulang bulanan di Aspose.Tasks untuk .NET
  dengan tutorial langkah demi langkah ini.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Membuat Tugas Berulang Bulanan di Aspose.Tasks
url: /id/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Tugas Berulang Bulanan Menggunakan Aspose.Tasks

## Pendahuluan

Aspose.Tasks untuk .NET memungkinkan Anda memanipulasi file Microsoft Project secara programatis, dan salah satu kebutuhan dunia nyata yang paling umum adalah **membuat jadwal tugas berulang bulanan**. Baik Anda sedang membangun alat pelacakan proyek, mengotomatiskan alokasi sumber daya, atau menghasilkan item pekerjaan pemeliharaan berulang, tutorial ini akan memandu Anda langkah demi langkah untuk menambahkan pola berulang bulanan ke sebuah tugas.

Pada bagian berikut Anda akan melihat cara menyiapkan proyek, mendefinisikan parameter berulang, dan akhirnya menyimpan file yang telah diperbarui—semua dengan penjelasan yang jelas dan tips praktis.

## Jawaban Cepat
- **Apa arti “tugas berulang bulanan”?** Tugas yang berulang pada pola hari‑atau‑minggu yang ditentukan setiap bulan.  
- **Kelas API mana yang menangani berulang?** `RecurringTaskParameters` bersama dengan `MonthlyRecurrencePattern`.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis cukup untuk evaluasi; lisensi diperlukan untuk produksi.  
- **Bisakah saya mengubah intervalnya?** Ya – atur `RepetitionInterval` ke jumlah bulan antar kejadian.  
- **Format file apa yang didukung?** Baik file Project `.mpp` maupun `.xml` dapat dimuat dan disimpan.

## Apa Itu Pola Berulang Bulanan?

Pola berulang bulanan memberi tahu Microsoft Project (dan Aspose.Tasks) seberapa sering sebuah tugas harus berulang setiap bulan. Anda dapat menentukan hari tetap dalam bulan (misalnya, tanggal 1) atau posisi relatif (misalnya, Jumat terakhir). API menerjemahkan aturan ini ke dalam struktur file Project yang mendasarinya.

## Mengapa Menggunakan Aspose.Tasks untuk Ini?

- **Kontrol penuh** – Tanpa batasan UI; Anda mendefinisikan setiap aspek pola dalam kode.  
- **Lintas‑platform** – Berfungsi pada .NET Framework, .NET Core, dan .NET 5/6+.  
- **Tidak memerlukan Microsoft Project** – Menghasilkan atau memodifikasi file di server atau pipeline CI.  

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- .NET 6 (atau .NET 5/Framework 4.7+) terpasang.  
- Paket NuGet Aspose.Tasks untuk .NET sudah ditambahkan ke proyek Anda.  
- File Project contoh (`Project1.mpp`) ditempatkan di folder yang diketahui (`DataDir`).  

## Impor Namespace

Pertama, impor namespace yang diperlukan untuk bekerja dengan tugas dan menyimpan proyek:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Langkah 1: Inisialisasi Proyek

Buat instance `Project` yang menunjuk ke file `.mpp` Anda yang sudah ada. Ini akan memuat file ke memori sehingga Anda dapat memodifikasinya.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Tips pro:** Jika file tidak ada, Aspose.Tasks akan secara otomatis membuat proyek kosong baru.

## Langkah 2: Atur Parameter Tugas Berulang

Definisikan detail tugas berulang, termasuk nama, durasi, dan pola bulanan yang ingin Anda terapkan.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` berarti tugas terjadi pada **hari pertama** bulan tersebut.  
- `RepetitionInterval = 2` membuat tugas berulang **setiap dua bulan**.  
- `Start` dan `Finish` menentukan jendela keseluruhan di mana berulang aktif.

## Langkah 3: Tambahkan Parameter ke Proyek

Lampirkan objek `RecurringTaskParameters` ke koleksi anak tugas akar. Ini secara efektif membuat tugas berulang dalam hierarki proyek.

```csharp
project.RootTask.Children.Add(parameters);
```

## Langkah 4: Simpan Proyek

Persist perubahan dengan menyimpan proyek ke file baru. Anda dapat memilih format apa pun yang didukung; di sini kami menggunakan format native `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Setelah menjalankan kode, buka file yang dihasilkan di Microsoft Project untuk melihat tugas berulang bulanan yang baru saja Anda buat.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| Tugas tidak muncul setelah disimpan | Proyek tidak disegarkan di UI | Buka kembali file atau panggil `project.UpdateTaskLinks()` sebelum menyimpan. |
| Tanggal mulai salah | `Start` diatur pada akhir pekan | Gunakan `DateTime` yang jatuh pada hari kerja atau sesuaikan kalender. |
| Interval berulang diabaikan | Menggunakan `ByMonthDayRepetition` dengan `DayPosition` = 0 | Pastikan `DayPosition` berada di antara 1‑31. |

## Kesimpulan

Dengan mengikuti langkah‑langkah ini, Anda kini tahu cara **membuat jadwal tugas berulang bulanan** menggunakan Aspose.Tasks untuk .NET. API memberikan kontrol granular atas interval berulang, rentang mulai/selesai, dan pola hari spesifik, memungkinkan Anda mengotomatiskan skenario perencanaan proyek yang kompleks.

## FAQ

### Q1: Apakah Aspose.Tasks kompatibel dengan semua versi file Microsoft Project?

A1: Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk MPP, MPT, XML, dan MPX.

### Q2: Bisakah saya menyesuaikan pola berulang lebih lanjut?

A2: Ya, Aspose.Tasks menyediakan opsi luas untuk menyesuaikan pola berulang, termasuk harian, mingguan, bulanan, dan tahunan.

### Q3: Apakah tersedia percobaan gratis untuk Aspose.Tasks?

A3: Ya, Anda dapat memperoleh percobaan gratis Aspose.Tasks dari situs web [di sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks?

A4: Anda dapat mencari bantuan dan berpartisipasi dalam diskusi di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Di mana saya dapat membeli lisensi untuk Aspose.Tasks?

A5: Anda dapat membeli lisensi Aspose.Tasks dari situs web [di sini](https://purchase.aspose.com/buy).

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan kode ini dalam aplikasi .NET Core?**  
J: Tentu saja. Aspose.Tasks untuk .NET sepenuhnya mendukung .NET Core 3.1 dan versi selanjutnya.

**T: Bagaimana cara mengubah berulang menjadi “hari kerja terakhir bulan ini”?**  
J: Gunakan `ByMonthDayRepetition` dengan `DayPosition = -1` (nilai negatif menghitung dari akhir bulan) dan atur `WeekDay` sesuai.

**T: Apa yang terjadi jika rentang berulang melebihi kalender proyek?**  
J: API menghormati kalender proyek; kejadian yang jatuh pada hari non‑kerja akan dilewati atau dipindahkan berdasarkan pengaturan kalender.

**T: Apakah memungkinkan menghapus kejadian tertentu dari tugas berulang?**  
J: Ya. Setelah menambahkan tugas berulang, Anda dapat mengambil kejadian individual melalui `Task.GetOccurrences()` dan menghapus yang tidak diperlukan.

**T: Apakah Aspose.Tasks menangani perbedaan zona waktu secara otomatis?**  
J: Perpustakaan menyimpan tanggal dalam UTC; Anda dapat mengonversinya ke waktu lokal menggunakan metode .NET `DateTime` standar bila diperlukan.

---

**Terakhir Diperbarui:** 2026-03-08  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}