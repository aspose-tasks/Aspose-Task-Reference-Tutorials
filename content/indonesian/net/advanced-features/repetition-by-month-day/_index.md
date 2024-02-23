---
title: Pengulangan berdasarkan Hari Bulan di Aspose.Tugas
linktitle: Pengulangan berdasarkan Hari Bulan di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola tugas berulang di proyek .NET dengan Aspose.Tasks. Panduan langkah demi langkah untuk menangani pengulangan berdasarkan hari bulan.
type: docs
weight: 25
url: /id/net/advanced-features/repetition-by-month-day/
---
## Perkenalan

Di bidang pengembangan .NET, Aspose.Tasks berdiri sebagai alat yang ampuh untuk mengelola tugas dan jadwal proyek. Ini menawarkan banyak fungsi untuk menyederhanakan alur kerja manajemen proyek, termasuk menangani tugas-tugas berulang. Pengulangan berdasarkan hari bulan merupakan persyaratan umum dalam penjadwalan proyek, dan Aspose.Tasks memberikan dukungan kuat untuk skenario ini.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk memahami konsep yang dibahas dalam tutorial ini.
2. Pemasangan Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Lingkungan Pengembangan Terpadu (IDE): Miliki IDE seperti Visual Studio yang terinstal di sistem Anda untuk kenyamanan pengkodean.

## Impor Namespace

Dalam proyek C# Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Mari kita uraikan contoh kode yang diberikan ke dalam format panduan langkah demi langkah:

## Langkah 1: Muat File Proyek

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Baris kode ini menginisialisasi instance baru dari`Project` kelas, memuat file proyek bernama "Project1.mpp".

## Langkah 2: Tentukan Parameter Tugas Berulang

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

Bagian ini mendefinisikan parameter untuk tugas berulang, termasuk nama, durasi, pola pengulangan, dan rentang pengulangan.

## Langkah 3: Tambahkan Tugas ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

Di sini, kami menambahkan parameter tugas berulang ke proyek.

## Langkah 4: Simpan File Proyek

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Terakhir, proyek yang dimodifikasi disimpan dengan tugas berulang yang ditambahkan.

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara menangani pengulangan berdasarkan hari bulan di Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengelola tugas berulang secara efisien dalam jadwal proyek Anda.

## FAQ

### Q1: Apakah Aspose.Tasks kompatibel dengan semua versi .NET?

A1: Aspose.Tasks mendukung berbagai versi kerangka .NET, memastikan kompatibilitas di berbagai lingkungan.

### Q2: Dapatkah saya menyesuaikan pola pengulangan lebih lanjut?

A2: Ya, Aspose.Tasks menawarkan opsi penyesuaian yang luas untuk menentukan pola pengulangan sesuai dengan kebutuhan proyek tertentu.

### Q3: Apakah Aspose.Tasks memberikan dukungan untuk fungsi manajemen proyek lainnya?

A3: Tentu saja, Aspose.Tasks menawarkan berbagai fitur untuk manajemen proyek, termasuk pelacakan tugas, alokasi sumber daya, dan pembuatan diagram Gantt.

### Q4: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?

 A4: Ya, Anda dapat memanfaatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/) untuk mengeksplorasi kemampuan Aspose.Tasks sebelum membuat keputusan pembelian.

### Q5: Di mana saya bisa mencari bantuan jika saya menemui masalah atau memiliki pertanyaan?

 A5: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk mencari dukungan dari komunitas atau tim Aspose.