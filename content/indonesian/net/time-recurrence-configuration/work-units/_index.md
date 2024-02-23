---
title: Menguasai Penanganan Satuan Kerja di Aspose.Tugas
linktitle: Menangani Satuan Kerja di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Jelajahi Aspose.Tasks untuk .NET, perpustakaan canggih untuk manajemen proyek yang efisien. Tangani unit kerja dengan presisi untuk pemanfaatan sumber daya yang optimal.
type: docs
weight: 15
url: /id/net/time-recurrence-configuration/work-units/
---
## Perkenalan
Dalam dunia manajemen proyek yang dinamis, menangani unit kerja secara efisien sangat penting untuk keberhasilan penyelesaian proyek. Aspose.Tasks untuk .NET menyediakan perangkat canggih untuk menavigasi informasi unit kerja, memastikan kontrol yang tepat atas jadwal proyek dan alokasi sumber daya.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET yang berfungsi.
3. Direktori Dokumen: Buat direktori untuk menyimpan dokumen proyek Anda.
## Impor Namespace
Dalam kode C# Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Langkah 1: Inisialisasi Proyek
Mulailah dengan menginisialisasi proyek Aspose.Tasks menggunakan kode yang disediakan:
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## Langkah 2: Akses Informasi Kalender
Ambil kalender proyek dan simpan dalam variabel:
```csharp
var calendar = project.Calendars.GetByUid(1);
```
## Langkah 3: Dapatkan Jam Kerja
Tentukan rentang tanggal dan ambil jam kerja menggunakan kode berikut:
```csharp
var workUnit = calendar.GetWorkingHours(new DateTime(2020, 4, 8, 8, 0, 0), new DateTime(2020, 4, 9, 17, 0, 0));
```
## Langkah 4: Tampilkan Hasil
Cetak informasi yang diambil untuk dianalisis:
```csharp
Console.WriteLine("From: " + workUnit.From);
Console.WriteLine("To: " + workUnit.To);
Console.WriteLine("Working hours: " + workUnit.WorkingHours);
```
Ulangi langkah-langkah ini sesuai kebutuhan proyek spesifik Anda.
## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET memberdayakan pengembang untuk menangani unit kerja dalam manajemen proyek dengan lancar, memfasilitasi manajemen waktu dan pemanfaatan sumber daya yang efektif. Mengintegrasikan perpustakaan ini ke dalam aplikasi .NET Anda meningkatkan kemampuan Anda untuk mengontrol jadwal proyek dan mengoptimalkan produktivitas tim.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan semua format file manajemen proyek?
 Aspose.Tasks mendukung berbagai format file proyek, termasuk MPP, XML, dan lainnya. Mengacu kepada[dokumentasi](https://reference.aspose.com/tasks/net/) untuk daftar lengkap.
### Bisakah saya mencoba Aspose.Tasks sebelum membeli?
Ya, Anda dapat menjelajahi Aspose.Tasks dengan uji coba gratis. Unduh dari[halaman rilis](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks?
 mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 Dapatkan lisensi sementara untuk Aspose.Tasks dengan mengunjungi[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
### Apa manfaat yang ditawarkan Aspose.Tasks untuk menangani unit kerja?
Aspose.Tasks menyediakan serangkaian fungsi yang kuat untuk bekerja dengan unit kerja, memungkinkan kontrol yang tepat atas jadwal proyek, alokasi sumber daya, dan manajemen proyek secara keseluruhan.