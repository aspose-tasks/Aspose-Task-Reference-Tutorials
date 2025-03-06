---
title: Pengulangan berdasarkan Hari Tahun di Aspose.Tugas
linktitle: Pengulangan berdasarkan Hari Tahun di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani pengulangan hari tahun di Aspose.Tasks untuk .NET guna menyederhanakan manajemen tugas berulang secara efisien.
weight: 27
url: /id/net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengulangan berdasarkan Hari Tahun di Aspose.Tugas

## Perkenalan

Dalam bidang manajemen proyek, penjadwalan dan pengulangan tugas yang efisien memainkan peran penting dalam memastikan pelaksanaan tepat waktu dan kelancaran alur kerja. Aspose.Tasks untuk .NET menawarkan solusi tangguh bagi pengembang untuk menangani tugas berulang dengan mudah dalam aplikasi mereka. Dalam tutorial ini, kami mempelajari seluk-beluk bekerja dengan pengulangan hari tahun menggunakan Aspose.Tasks, memberikan panduan komprehensif untuk membuat tugas berulang berdasarkan pola tahunan.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
   
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai dengan Visual Studio atau IDE pilihan lainnya untuk pengembangan .NET.

3. Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C# untuk mengikuti contoh kode.

4. Konsep Manajemen Proyek: Pemahaman konsep manajemen proyek dan penjadwalan tugas akan membantu dalam memahami konsep tutorial secara efektif.

## Impor Namespace

Sebelum kita memulai pengkodean, mari impor namespace yang diperlukan untuk memfasilitasi manipulasi tugas kita menggunakan Aspose.Tasks untuk .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah dan jelaskan setiap langkah secara mendetail.

## Langkah 1: Muat File Proyek

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Di sini, kami menginisialisasi yang baru`Project` objek dan memuat file proyek yang ada bernama "Project1.mpp".

## Langkah 2: Tentukan Parameter Tugas Berulang

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

 Pada langkah ini, kami menentukan parameter untuk tugas berulang kami. Kami menentukan nama tugas, durasi, dan pola pengulangan. Untuk pengulangan tahunan, kami menggunakan`YearlyRecurrencePattern` dan atur pengulangan agar terjadi pada hari 1 Juli menggunakan`ByYearDayRepetition`. Selain itu, kami menentukan rentang pengulangan dari 1 Juli 2018 hingga 1 Juli 2019.

## Langkah 3: Tambahkan Tugas ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

Di sini, kami menambahkan parameter tugas berulang yang ditentukan ke tugas utama proyek.

## Langkah 4: Simpan Proyek

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Terakhir, kami menyimpan file proyek yang dimodifikasi dengan tugas berulang yang ditambahkan.

## Kesimpulan

Dalam tutorial ini, kami telah menjelajahi proses bekerja dengan pengulangan hari tahun di Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, pengembang dapat dengan mudah mengintegrasikan fungsionalitas tugas berulang ke dalam aplikasi mereka, sehingga meningkatkan kemampuan manajemen proyek.

## FAQ

### Q1: Dapatkah Aspose.Tasks menangani pola pengulangan yang kompleks?

A1: Ya, Aspose.Tasks memberikan dukungan komprehensif untuk berbagai pola pengulangan, termasuk pola kompleks seperti pengulangan tahunan, bulanan, mingguan, dan harian.

### Q2: Apakah Aspose.Tasks kompatibel dengan format file proyek yang berbeda?

A2: Tentu saja, Aspose.Tasks mendukung format file proyek populer seperti MPP, XML, dan CSV, memastikan kompatibilitas di berbagai alat manajemen proyek.

### Q3: Apakah Aspose.Tasks menawarkan dokumentasi dan dukungan untuk pengembang?

A3: Ya, pengembang dapat mengakses dokumentasi ekstensif dan mencari bantuan dari forum komunitas Aspose.Tasks untuk pertanyaan atau masalah apa pun yang mereka temui.

### Q4: Dapatkah saya menyesuaikan properti tugas seperti durasi dan tanggal mulai menggunakan Aspose.Tasks?

A4: Tentu saja, Aspose.Tasks menyediakan API yang kuat untuk memanipulasi properti tugas secara dinamis, memungkinkan pengembang menyesuaikan durasi, tanggal mulai, dependensi, dan banyak lagi.

### Q5: Apakah Aspose.Tasks cocok untuk proyek skala kecil dan tingkat perusahaan?

A5: Memang benar, Aspose.Tasks dirancang untuk memenuhi kebutuhan pengembang yang mengerjakan proyek dari semua skala, mulai dari tugas individu hingga proyek perusahaan skala besar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
