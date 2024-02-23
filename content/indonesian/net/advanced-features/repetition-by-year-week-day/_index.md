---
title: Pengulangan berdasarkan Tahun Minggu Hari di Aspose.Tugas
linktitle: Pengulangan berdasarkan Tahun Minggu Hari di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Jelajahi kekuatan Aspose.Tasks untuk .NET dalam mengelola tugas berulang secara efisien. Panduan langkah demi langkah untuk menerapkan fitur Pengulangan berdasarkan Tahun, Hari Minggu.
type: docs
weight: 28
url: /id/net/advanced-features/repetition-by-year-week-day/
---
## Perkenalan

Dalam bidang manajemen proyek, efisiensi dan presisi adalah hal yang terpenting. Aspose.Tasks untuk .NET muncul sebagai alat yang ampuh, menawarkan banyak fitur untuk menyederhanakan penanganan proyek. Di antara persenjataannya adalah kemampuan untuk mengelola tugas berulang dengan fleksibilitas luar biasa. Salah satu fitur tersebut adalah fungsi "Pengulangan berdasarkan Tahun, Hari Minggu", yang memungkinkan pengguna mengatur tugas yang berulang pada hari tertentu dalam seminggu, dalam bulan yang ditentukan, dan dalam beberapa tahun.

## Prasyarat

Sebelum mendalami seluk-beluk penggunaan fitur "Pengulangan menurut Tahun Hari Minggu" di Aspose.Tasks untuk .NET, pastikan Anda memiliki prasyarat berikut:

### 1. Pengetahuan tentang .NET Framework

Biasakan diri Anda dengan dasar-dasar .NET Framework, termasuk konsep pemrograman berorientasi objek dan sintaksis C#.

### 2. Instalasi Aspose.Tasks untuk .NET

 Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/)Ikuti petunjuk instalasi yang diberikan untuk mengintegrasikan perpustakaan ke dalam lingkungan pengembangan Anda.

### 3. Akses terhadap Dokumentasi

 Mengacu kepada[dokumentasi](https://reference.aspose.com/tasks/net/) untuk panduan komprehensif tentang Aspose.Tasks untuk .NET, termasuk penjelasan mendetail tentang kelas, metode, dan contoh penggunaan.

## 4. Pengaturan Lingkungan Pengembangan

Pastikan Anda memiliki konfigurasi lingkungan pengembangan yang sesuai, seperti Visual Studio atau IDE apa pun yang kompatibel untuk pengembangan .NET.

Sekarang setelah Anda memiliki prasyaratnya, mari pelajari panduan langkah demi langkah dalam menerapkan "Pengulangan berdasarkan Tahun, Hari Minggu" di Aspose.Tasks untuk .NET.


## Mengimpor Namespace yang Diperlukan

Untuk memulai, impor namespace yang diperlukan untuk mengakses kelas dan fungsi Aspose.Tasks dalam aplikasi .NET Anda.

Dalam file kode C# Anda, sertakan deklarasi namespace berikut:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Namespace ini menyediakan akses ke perpustakaan Aspose.Tasks dan kelas yang diperlukan untuk bekerja dengan tugas dan file proyek.

Sekarang, mari kita uraikan proses pengaturan tugas berulang menggunakan fitur "Pengulangan berdasarkan Tahun, Hari Minggu" di Aspose.Tasks untuk .NET menjadi langkah-langkah yang dapat dikelola.

## Langkah 1: Inisialisasi Parameter Proyek dan Tugas

Pertama, inisialisasi proyek dan tentukan parameter untuk tugas berulang.

```csharp
// Jalur ke direktori dokumen.
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

Segmen kode ini menginisialisasi proyek baru dan menentukan parameter untuk tugas berulang. Ini menetapkan nama tugas, durasi, dan menentukan pola pengulangan.

## Langkah 2: Tambahkan Parameter ke Proyek

Selanjutnya, tambahkan parameter yang ditentukan ke proyek.

```csharp
project.RootTask.Children.Add(parameters);
```

Baris ini menambahkan parameter tugas ke tugas utama proyek, menggabungkan konfigurasi tugas berulang.

## Langkah 3: Simpan File Proyek

Terakhir, simpan file proyek dengan tugas berulang yang dikonfigurasi.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Cuplikan ini menyimpan file proyek dengan konfigurasi tugas berulang yang ditentukan ke direktori keluaran yang ditentukan.

## Kesimpulan

Kesimpulannya, menguasai fitur "Pengulangan berdasarkan Tahun, Hari Minggu" di Aspose.Tasks untuk .NET memberdayakan manajer proyek dan pengembang untuk menangani tugas berulang secara efisien dengan presisi dan fleksibilitas. Dengan mengikuti panduan langkah demi langkah yang diuraikan dalam artikel ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam alur kerja manajemen proyek Anda, sehingga meningkatkan produktivitas dan organisasi.

## FAQ

### Q1: Dapatkah saya menyesuaikan pola pengulangan lebih jauh dari contoh yang diberikan?

J: Ya, Aspose.Tasks untuk .NET menawarkan opsi penyesuaian ekstensif untuk tugas berulang, memungkinkan Anda menyesuaikan pola pengulangan dengan kebutuhan spesifik Anda.

### Q2: Apakah Aspose.Tasks untuk .NET kompatibel dengan perangkat lunak manajemen proyek lainnya?

J: Aspose.Tasks untuk .NET mendukung interoperabilitas dengan berbagai format manajemen proyek, memungkinkan integrasi tanpa hambatan dengan rangkaian perangkat lunak populer.

### Q3: Bagaimana cara menangani pengecualian atau modifikasi pada tugas berulang?

J: Aspose.Tasks untuk .NET menyediakan API untuk menangani pengecualian dan modifikasi pada tugas berulang, memastikan fleksibilitas dalam mengelola persyaratan proyek yang terus berkembang.

### Q4: Apakah Aspose.Tasks untuk .NET menawarkan dukungan untuk solusi manajemen proyek berbasis cloud?

J: Ya, Aspose.Tasks untuk .NET menawarkan dukungan untuk solusi manajemen proyek berbasis cloud, memfasilitasi kolaborasi dan aksesibilitas di berbagai platform.

### Q5: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?

 J: Ya, Anda dapat mengakses uji coba gratis Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/), memungkinkan Anda menjelajahi fitur-fiturnya sebelum membuat keputusan pembelian.