---
title: Menangani Tarif Proyek MS dengan Aspose.Tasks untuk .NET
linktitle: Menangani Tarif di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Kuasai pengelolaan Tarif Proyek MS dengan mudah menggunakan Aspose.Tasks untuk .NET. Otomatiskan tugas secara efisien untuk alur kerja proyek yang lebih lancar.
type: docs
weight: 10
url: /id/net/rate-recurring-tasks/handling-rates/
---
## Perkenalan
Selamat datang di tutorial kami tentang menangani Tarif Proyek MS menggunakan Aspose.Tasks untuk .NET! Dalam panduan ini, kami akan memandu Anda melalui proses langkah demi langkah, memastikan Anda dapat mengelola tarif secara efisien dalam dokumen Proyek MS Anda. Aspose.Tasks untuk .NET menyediakan fitur canggih untuk memanipulasi file MS Project secara terprogram, memungkinkan Anda menyederhanakan tugas manajemen proyek dengan mudah.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
1. Visual Studio Terpasang: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.
## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Namespace ini akan memberikan akses ke kelas dan metode yang diperlukan untuk menangani Tarif Proyek MS.
## Langkah 1: Impor Namespace Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah dan pahami setiap langkah secara menyeluruh.
## Langkah 1: Muat File Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Pada langkah ini, kita memuat file MS Project yang sudah ada bernama "Project1.mpp" menggunakan`Project` kelas yang disediakan oleh Aspose.Tasks.
## Langkah 2: Tambahkan Sumber Daya dan Tetapkan Pekerjaan
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Di sini, kami menambahkan sumber daya baru bernama "Sumber Daya 1" ke proyek dan menetapkan jenisnya sebagai "Pekerjaan". Kami juga menentukan durasi kerja untuk sumber daya ini.
## Langkah 3: Tetapkan Tarif Standar
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Pada langkah ini, kami menetapkan tarif standar untuk sumber daya menjadi $20 per jam.
## Langkah 4: Tentukan Periode Tarif
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Di sini, kami menentukan periode tarif untuk sumber daya. Tarif1 ditetapkan mulai 1 Januari 2019 hingga 11 November 2019, dengan tarif standar dan lembur yang ditentukan.
## Langkah 5: Tambahkan Periode Tarif Lain
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Pada langkah terakhir ini, kami menambahkan periode tarif lain mulai dari 12 November 2019 hingga 31 Desember 2019, dengan tarif standar dan biaya per penggunaan yang berbeda.
Selamat! Anda telah berhasil menangani Tarif Proyek MS menggunakan Aspose.Tasks untuk .NET.
## Kesimpulan
Mengelola Tarif Proyek MS secara terprogram dapat meningkatkan alur kerja manajemen proyek Anda secara signifikan. Dengan Aspose.Tasks untuk .NET, Anda memiliki kekuatan untuk mengotomatiskan tugas penanganan laju secara efisien, menghemat waktu dan sumber daya.
## FAQ
### T: Dapatkah Aspose.Tasks menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks menyediakan fitur tangguh untuk menangani struktur proyek yang kompleks dengan mudah.
### T: Apakah Aspose.Tasks kompatibel dengan semua versi file MS Project?
J: Aspose.Tasks mendukung berbagai versi file MS Project, memastikan kompatibilitas di berbagai platform.
### T: Bisakah saya mengubah tarif yang ada di file MS Project menggunakan Aspose.Tasks?
J: Tentu saja! Aspose.Tasks memungkinkan Anda mengubah tarif yang ada, menambahkan tarif baru, dan mengelolanya secara dinamis.
### T: Apakah Aspose.Tasks menawarkan dukungan untuk penghitungan tarif khusus?
J: Ya, Anda dapat menerapkan penghitungan tarif khusus menggunakan Aspose.Tasks untuk memenuhi persyaratan proyek tertentu.
### T: Apakah ada forum komunitas atau dukungan yang tersedia untuk pengguna Aspose.Tasks?
 A: Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15)untuk mencari bantuan dan berinteraksi dengan pengguna lain.