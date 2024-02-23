---
title: Ekstrak Informasi Header dan Footer dengan Aspose.Tasks
linktitle: Informasi Header dan Footer di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengekstrak info header & footer dari file MS Project menggunakan Aspose.Tasks untuk .NET. Solusi yang mudah, efisien, dan ramah pengembang.
type: docs
weight: 29
url: /id/net/tasks-project-management/header-footer-information/
---
## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project dengan mudah. Dalam tutorial ini, kita akan mempelajari cara mengambil informasi header dan footer dari file MS Project menggunakan Aspose.Tasks.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Visual Studio: Instal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C#.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Ini akan memungkinkan Anda untuk mengakses kelas dan metode yang disediakan oleh perpustakaan Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Langkah 1: Inisialisasi Objek Proyek
 Untuk memulai, Anda perlu menginisialisasi a`Project` objek dengan memuat file MS Project yang ada.
```csharp
// Jalur ke direktori dokumen.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Langkah 2: Ambil Informasi Header dan Footer
 Setelah Anda memuat file proyek, Anda dapat mengambil informasi header dan footer menggunakan`PageInfo` Properti.
```csharp
var info = project.DefaultView.PageInfo;
// Informasi Tajuk
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informasi Catatan Kaki
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah mengambil informasi header dan footer dari file MS Project menggunakan Aspose.Tasks untuk .NET.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara mengekstrak informasi header dan footer dari file MS Project menggunakan Aspose.Tasks untuk .NET. Pustaka yang kuat ini menyederhanakan tugas bekerja dengan file Proyek dalam aplikasi C#, menyediakan alat manipulasi yang canggih bagi pengembang.
### FAQ
### Bisakah saya mengubah informasi header dan footer menggunakan Aspose.Tasks?
Ya, Anda dapat mengubah informasi header dan footer secara terprogram menggunakan Aspose.Tasks untuk .NET.
### Apakah Aspose.Tasks mendukung format file proyek lain selain MS Project?
Ya, Aspose.Tasks mendukung berbagai format file proyek, termasuk MPP, XML, dan MPX.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat mengunduh uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks?
 Anda dapat menemukan dokumentasi untuk Aspose.Tasks[Di Sini](https://reference.aspose.com/tasks/net/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 Anda bisa mendapatkan dukungan untuk Aspose.Tasks dengan mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).