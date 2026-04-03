---
date: 2026-04-03
description: Pelajari penjadwalan tugas manajemen proyek dan cara menambahkan tugas
  berulang menggunakan Aspose.Tasks untuk .NET, termasuk menyimpan proyek sebagai
  MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Pengulangan berdasarkan Hari Tahun di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Penjadwalan Tugas Manajemen Proyek dengan Pengulangan Hari Tahunan di Aspose.Tasks
url: /id/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Penjadwalan Tugas Manajemen Proyek dengan Pengulangan Hari Tahun di Aspose.Tasks

## Pendahuluan

Penjadwalan **tugas manajemen proyek** yang efektif adalah tulang punggung dari setiap proyek yang sukses. Ketika tugas berulang setiap tahun—seperti audit tahunan, jendela pemeliharaan, atau tinjauan musiman—menangani pengulangan tersebut secara manual dapat menjadi rawan kesalahan dan memakan waktu. Aspose.Tasks untuk .NET menyederhanakan hal ini dengan memungkinkan Anda mendefinisikan pola hari‑tahun secara programatis, sehingga Anda dapat fokus pada hal yang paling penting: memberikan nilai. Dalam tutorial ini Anda akan belajar **cara menambahkan logika tugas berulang** berdasarkan hari tertentu dalam setahun dan melihat secara tepat **cara menyimpan proyek sebagai MPP** untuk integrasi mulus dengan Microsoft Project.

## Jawaban Cepat
- **Apa arti “pengulangan hari tahun”?** Ini menjadwalkan tugas pada hari tertentu dari bulan tertentu setiap tahun.  
- **Kelas API mana yang membuat pengulangan?** `YearlyRecurrencePattern` dikombinasikan dengan `ByYearDayRepetition`.  
- **Apakah saya dapat mengatur tanggal mulai dan selesai?** Ya, menggunakan `EndByRecurrenceRange`.  
- **Format file apa yang dihasilkan?** Proyek disimpan sebagai file MPP (`SaveFileFormat.Mpp`).  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan non‑evaluasi.

## Prasyarat

Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Tasks for .NET Library: Unduh dan instal pustaka Aspose.Tasks untuk .NET dari [situs web](https://releases.aspose.com/tasks/net/).  
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai dengan Visual Studio atau IDE pilihan lain untuk pengembangan .NET.  
3. Pengetahuan Dasar C#: Kenali dasar-dasar bahasa pemrograman C# untuk mengikuti contoh kode.  
4. Konsep Manajemen Proyek: Memahami konsep manajemen proyek dan penjadwalan tugas akan membantu dalam memahami konsep tutorial secara efektif.

## Impor Namespace

Sebelum kita mulai menulis kode, mari impor namespace yang diperlukan untuk memfasilitasi manipulasi tugas kami menggunakan Aspose.Tasks untuk .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah dan jelaskan setiap langkah secara detail.

## Cara Menambahkan Tugas Berulang dengan Pola Hari Tahun

### Langkah 1: Muat File Proyek

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Di sini, kami menginisialisasi objek `Project` baru dan memuat file proyek yang sudah ada bernama **Project1.mpp**.

### Langkah 2: Tentukan Parameter Tugas Berulang

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Pada langkah ini, kami menentukan parameter untuk tugas berulang kami. Kami menentukan nama tugas, durasi, dan pola pengulangan. Untuk pengulangan tahunan, kami menggunakan `YearlyRecurrencePattern` dan mengatur pengulangan terjadi pada **hari pertama Juli** menggunakan `ByYearDayRepetition`. Selain itu, kami mendefinisikan rentang pengulangan dari 1 Juli 2018 hingga 1 Juli 2019.

### Langkah 3: Tambahkan Tugas ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

Di sini, kami menambahkan parameter tugas berulang yang telah didefinisikan ke tugas akar proyek.

### Langkah 4: Simpan Proyek sebagai MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Akhirnya, kami **menyimpan proyek sebagai file MPP**, sehingga siap dibuka di Microsoft Project atau penampil kompatibel lainnya.

## Mengapa Ini Penting

- **Otomatisasi** – Menghilangkan entri manual tugas tahunan, mengurangi kesalahan manusia.  
- **Konsistensi** – Menjamin pola hari‑bulan yang sama diterapkan di beberapa tahun.  
- **Integrasi** – File MPP yang dihasilkan dapat dibagikan kepada pemangku kepentingan yang bergantung pada Microsoft Project.  

## Kesalahan Umum & Tips

- **Presisi DateTime** – Pastikan waktu mulai sesuai dengan kalender proyek Anda; jika tidak, tugas mungkin muncul teroffset.  
- **Zona waktu** – API bekerja dengan objek `DateTime`; pertimbangkan konversi ke UTC jika aplikasi Anda mencakup beberapa wilayah.  
- **Penegakan lisensi** – Dalam mode evaluasi, MPP yang disimpan mungkin berisi watermark; gunakan lisensi yang valid untuk produksi.

## Pertanyaan yang Sering Diajukan

**Q: Dapatkah Aspose.Tasks menangani pola pengulangan yang kompleks?**  
**A:** Ya, Aspose.Tasks menyediakan dukungan komprehensif untuk berbagai pola pengulangan, termasuk tahunan, bulanan, mingguan, dan harian.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai format file proyek?**  
**A:** Tentu saja, Aspose.Tasks mendukung format file proyek populer seperti MPP, XML, dan CSV, memastikan kompatibilitas di berbagai alat manajemen proyek.

**Q: Apakah Aspose.Tasks menyediakan dokumentasi dan dukungan untuk pengembang?**  
**A:** Ya, pengembang dapat mengakses dokumentasi yang luas dan mencari bantuan di forum komunitas Aspose.Tasks untuk pertanyaan atau masalah yang mereka temui.

**Q: Dapatkah saya menyesuaikan properti tugas seperti durasi dan tanggal mulai menggunakan Aspose.Tasks?**  
**A:** Tentu, Aspose.Tasks menyediakan API yang kuat untuk memanipulasi properti tugas secara dinamis, memungkinkan pengembang menyesuaikan durasi, tanggal mulai, ketergantungan, dan lainnya.

**Q: Apakah Aspose.Tasks cocok untuk proyek skala kecil maupun tingkat perusahaan?**  
**A:** Memang, Aspose.Tasks dirancang untuk memenuhi kebutuhan pengembang yang bekerja pada proyek dengan segala skala, dari tugas individu hingga proyek perusahaan berskala besar.

---

**Terakhir Diperbarui:** 2026-04-03  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}