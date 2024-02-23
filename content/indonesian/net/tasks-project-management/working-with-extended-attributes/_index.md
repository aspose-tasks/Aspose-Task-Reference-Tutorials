---
title: Memanipulasi Atribut Diperluas Proyek MS dengan Aspose.Tasks
linktitle: Bekerja dengan Atribut yang Diperluas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara bekerja dengan atribut yang diperluas MS Project menggunakan Aspose.Tasks untuk .NET. Memanipulasi data tugas secara terprogram dengan mudah.
type: docs
weight: 11
url: /id/net/tasks-project-management/working-with-extended-attributes/
---
## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Salah satu fitur utama perpustakaan ini adalah kemampuannya untuk bekerja dengan atribut tambahan MS Project. Atribut yang diperluas memberikan penyesuaian dan metadata tambahan pada tugas dalam proyek, memungkinkan pengguna menyimpan dan mengelola informasi spesifik di luar properti tugas standar.
Dalam tutorial ini, kita akan menjelajahi cara bekerja dengan atribut yang diperluas MS Project menggunakan Aspose.Tasks untuk .NET. Kami akan membahas prasyarat, mengimpor namespace, dan membagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah. Di akhir tutorial ini, Anda akan memiliki pemahaman yang kuat tentang cara memanfaatkan atribut yang diperluas dalam aplikasi .NET Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
### 1. Visual Studio Terpasang
Pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda dapat mendownloadnya dari situs web jika Anda belum melakukannya.
### 2. Aspose.Tasks untuk Perpustakaan .NET
 Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).

## Impor Namespace
Untuk mulai bekerja dengan Aspose.Tasks untuk .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah ini:
### Langkah 1: Buka Visual Studio
Luncurkan Visual Studio di sistem Anda.
### Langkah 2: Buat Proyek Baru
Buat proyek baru atau buka proyek yang sudah ada di mana Anda ingin menggunakan Aspose.Tasks.
### Langkah 3: Impor Namespace
Tambahkan namespace berikut di awal file C# Anda:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

Sekarang setelah kita menyiapkan lingkungan, mari selami cara bekerja dengan atribut tambahan MS Project menggunakan Aspose.Tasks untuk .NET.
## Langkah 1: Tentukan Direktori Data
Tentukan jalur ke direktori tempat file MS Project Anda berada:
```csharp
String DataDir = "Your Document Directory";
```
 mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.
## Langkah 2: Muat File Proyek
 Muat file MS Project menggunakan`Project` kelas:
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
 Kode ini menginisialisasi instance baru dari`Project` kelas, memuat file MS Project yang ditentukan.
## Langkah 3: Baca Atribut yang Diperluas untuk Tugas
Ulangi tugas dan atributnya yang diperluas untuk membaca informasi:
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        // Baca informasi umum tentang atribut yang diperluas
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
Cuplikan kode ini menelusuri setiap tugas dan atribut yang diperluas, mencetak informasinya ke konsol.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara bekerja dengan atribut yang diperluas MS Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat mengelola dan memanipulasi data atribut yang diperluas secara efisien di aplikasi .NET Anda.
## FAQ
### Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi Microsoft Project?
Ya, Aspose.Tasks untuk .NET mendukung berbagai versi Microsoft Project, termasuk 2003, 2007, 2010, 2013, 2016, dan 2019.
### Bisakah saya menggunakan Aspose.Tasks untuk .NET untuk membuat file MS Project baru?
Sangat! Aspose.Tasks untuk .NET memungkinkan Anda membuat, memodifikasi, dan memanipulasi file MS Project secara terprogram.
### Apakah Aspose.Tasks untuk .NET memerlukan lisensi untuk penggunaan komersial?
Ya, Anda perlu membeli lisensi untuk penggunaan komersial Aspose.Tasks untuk .NET. Namun, Anda juga dapat memanfaatkan uji coba gratis untuk mengevaluasi kemampuannya.
### Bisakah saya menyesuaikan atribut yang diperluas sesuai dengan kebutuhan proyek saya?
Ya, Aspose.Tasks untuk .NET menyediakan kemampuan ekstensif untuk menyesuaikan atribut yang diperluas agar sesuai dengan kebutuhan spesifik proyek Anda.
### Di mana saya bisa mendapatkan dukungan jika saya mengalami masalah apa pun saat menggunakan Aspose.Tasks untuk .NET?
 Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).