---
title: Mengukur Penggunaan Proyek MS dengan Aspose.Tasks untuk .NET
linktitle: Mengukur Penggunaan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memantau dan mengoptimalkan penggunaan Proyek MS Anda secara efektif dengan Aspose.Tasks untuk .NET. Panduan langkah demi langkah untuk manajemen proyek yang efisien.
type: docs
weight: 17
url: /id/net/license-management/metering-usage/
---
## Perkenalan
Apakah Anda ingin mengelola dan memantau penggunaan Proyek MS Anda secara efektif dengan Aspose.Tasks? Dengan kekuatan pengukuran, Anda dapat melacak penggunaan dan mengoptimalkan upaya manajemen proyek Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses pengukuran penggunaan MS Project langkah demi langkah menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mendalami pengukuran penggunaan MS Project, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Unduh Halaman](https://releases.aspose.com/tasks/net/), Ikuti petunjuk instalasi untuk menyiapkan perpustakaan di lingkungan pengembangan Anda.
2.  Kunci Publik dan Pribadi: Dapatkan kunci publik dan pribadi Anda dari Aspose. Kunci-kunci ini penting untuk penggunaan pengukuran. Jika Anda belum memiliki kunci, Anda dapat memintanya dari Aspose melalui[izin sementara](https://purchase.aspose.com/temporary-license/) halaman.

## Impor Namespace
Sebelum melanjutkan, impor namespace yang diperlukan ke proyek Anda:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## Langkah 1: Siapkan Pengukuran
Untuk mulai mengukur penggunaan MS Project, atur lingkungan terukur dengan memberikan kunci publik dan pribadi Anda:
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
 mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen Anda, dan gantikan`<public key>` Dan`<private key>` dengan kunci Anda yang sebenarnya diperoleh dari Aspose.
## Langkah 2: Muat File Proyek MS
Selanjutnya, muat file MS Project Anda menggunakan Aspose.Tasks:
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
Langkah ini memuat file MS Project bernama "Project2.mpp" dari direktori yang ditentukan. Anda dapat mengganti nama file dengan file MS Project Anda sendiri.
## Langkah 3: Bekerja dengan Proyek
Sekarang setelah proyek dimuat, Anda dapat melakukan berbagai operasi sesuai kebutuhan untuk tugas manajemen proyek Anda.
```csharp
// Lakukan tugas manajemen proyek di sini
```
## Langkah 4: Periksa Konsumsi Kredit dan Byte
Anda dapat memeriksa kredit yang dibelanjakan dan byte yang dikonsumsi selama periode penggunaan Anda:
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    // Tangani pengecualian di sini
}
```
Langkah ini mengambil dan menampilkan kredit yang dibelanjakan dan byte yang digunakan oleh operasi Anda. Tangani pengecualian apa pun yang mungkin terjadi selama proses ini.
## Langkah 5: Reset Kunci Terukur
Secara opsional, Anda dapat mengatur ulang kunci terukur untuk berhenti menghitung byte:
```csharp
metered.ResetMeteredKey();
```
Langkah ini menghentikan proses pengukuran dan menyetel ulang kunci terukur.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara mengukur penggunaan MS Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memantau dan mengoptimalkan upaya manajemen proyek Anda secara efektif sekaligus memastikan pemanfaatan sumber daya yang efisien.
### FAQ
### T: Dapatkah saya mengukur penggunaan di beberapa file MS Project?
J: Ya, Anda dapat mengukur penggunaan di beberapa file MS Project dengan memuat setiap file secara terpisah dan memantau penggunaan yang sesuai.
### T: Apakah pengukuran penggunaan MS Project kompatibel dengan semua versi Aspose.Tasks untuk .NET?
J: Ya, pengukuran penggunaan MS Project didukung di semua versi Aspose.Tasks untuk .NET.
### Q: Apakah saya memerlukan koneksi internet untuk penggunaan meteran?
J: Ya, koneksi internet diperlukan untuk berkomunikasi dengan server Aspose untuk pengukuran penggunaan.
### T: Dapatkah saya melacak penggunaan secara real-time?
J: Ya, Anda dapat melacak penggunaan secara real-time dengan memeriksa secara berkala kredit yang dibelanjakan dan byte yang dikonsumsi.
### T: Apakah pengukuran penggunaan MS Project tersedia dalam versi uji coba?
J: Ya, pengukuran penggunaan MS Project tersedia dalam versi uji coba dan berlisensi Aspose.Tasks untuk .NET.