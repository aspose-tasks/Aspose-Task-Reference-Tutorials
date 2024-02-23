---
title: Pengulangan berdasarkan Bulan Minggu Hari di Aspose.Tugas
linktitle: Pengulangan berdasarkan Bulan Minggu Hari di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengatur pengulangan berdasarkan bulan, minggu, dan hari di Aspose.Tasks untuk .NET untuk mengotomatiskan tugas berulang secara efisien.
type: docs
weight: 26
url: /id/net/advanced-features/repetition-by-month-week-day/
---
## Perkenalan

Dalam bidang pengembangan perangkat lunak, khususnya dalam aplikasi manajemen proyek, kemampuan untuk menangani tugas berulang secara efisien adalah hal yang terpenting. Aspose.Tasks untuk .NET adalah perpustakaan canggih yang dirancang untuk menyederhanakan pembuatan dan pengelolaan tugas proyek, termasuk tugas berulang. Salah satu fungsi yang disediakan oleh Aspose.Tasks adalah kemampuan untuk mengatur pengulangan berdasarkan bulan, minggu, dan hari, memastikan bahwa tugas dilaksanakan sesuai jadwal tanpa intervensi manual.

## Prasyarat

Sebelum mendalami seluk-beluk pengaturan pengulangan berdasarkan bulan, minggu, dan hari menggunakan Aspose.Tasks untuk .NET, pastikan Anda memiliki prasyarat berikut:

1. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# sangat penting untuk memahami dan mengimplementasikan contoh kode yang diberikan.
   
2.  Instalasi Aspose.Tasks untuk .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.Tasks untuk .NET. Anda dapat memperoleh perpustakaan dari[Unduh Halaman](https://releases.aspose.com/tasks/net/).

3. Akses ke File Proyek .mpp: Siapkan file Microsoft Project (.mpp), karena kami akan menggunakannya untuk mendemonstrasikan penerapan pengulangan berdasarkan bulan, minggu, dan hari.

## Impor Namespace

Untuk mulai menggunakan Aspose.Tasks untuk .NET di aplikasi C# Anda, Anda perlu mengimpor namespace yang diperlukan. Inilah cara Anda melakukannya:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Mari kita bagi cuplikan kode yang diberikan menjadi beberapa langkah untuk memahami setiap bagian secara menyeluruh.

## Langkah 1: Muat File Proyek

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Langkah ini melibatkan pembuatan instance baru dari`Project` kelas dan memuat file Microsoft Project yang ada (`Project1.mpp`) dari direktori yang ditentukan.

## Langkah 2: Tentukan Parameter Tugas Berulang

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

Pada langkah ini, kami menentukan parameter untuk tugas berulang. Kami menentukan nama tugas, durasi, pola pengulangan (bulanan), dan rentang pengulangan (berakhir pada tanggal tertentu).

## Langkah 3: Tambahkan Tugas Berulang ke Proyek

```csharp
project.RootTask.Children.Add(parameters);
```

Di sini, kami menambahkan parameter tugas berulang yang ditentukan ke tugas utama proyek.

## Langkah 4: Simpan File Proyek

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Terakhir, kami menyimpan file proyek yang dimodifikasi dengan tugas berulang yang ditambahkan.

## Kesimpulan

Kesimpulannya, menyiapkan pengulangan berdasarkan bulan, minggu, dan hari di Aspose.Tasks untuk .NET adalah proses langsung yang memberdayakan pengembang untuk mengotomatiskan pengelolaan tugas berulang dalam proyek mereka secara efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi C# Anda, menghemat waktu dan tenaga dalam manajemen proyek.

## FAQ

###Q1: Bisakah saya menyesuaikan pola pengulangan di luar contoh yang diberikan?

A1: Ya, Aspose.Tasks untuk .NET menawarkan opsi penyesuaian ekstensif untuk pola pengulangan, memungkinkan Anda menyesuaikannya dengan kebutuhan spesifik Anda.

###Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?

 A2: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET dari[halaman rilis](https://releases.aspose.com/).

###Q3: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

 A3: Anda dapat mencari bantuan dan terlibat dengan komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

###Q4: Apakah lisensi sementara tersedia untuk Aspose.Tasks untuk .NET?

 A4: Ya, Anda dapat memperoleh lisensi sementara dari[halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

###Q5: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks untuk .NET?

 A5: Anda dapat merujuk ke detailnya[dokumentasi](https://reference.aspose.com/tasks/net/) tersedia di situs web Aspose untuk panduan mendalam tentang pemanfaatan perpustakaan.