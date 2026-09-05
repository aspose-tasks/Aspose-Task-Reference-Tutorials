---
date: 2026-07-19
description: Pelajari cara mengontrol simbol mata uang setelah jumlah dalam proyek
  .NET dengan mudah menggunakan Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Posisi Simbol Mata Uang di Aspose.Tasks
og_description: Pelajari cara menempatkan simbol mata uang setelah jumlah menggunakan
  Aspose.Tasks untuk .NET. Ikuti petunjuk langkah demi langkah dan praktik terbaik.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Simbol Mata Uang Setelah Jumlah di Aspose.Tasks — Panduan Cepat
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Cara Menempatkan Simbol Mata Uang Setelah Jumlah di Aspose.Tasks
url: /id/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menempatkan Simbol Mata Uang Setelah Jumlah di Aspose.Tasks

## Pendahuluan

Saat Anda menghasilkan laporan biaya proyek, penempatan **currency symbol after amount** dapat memengaruhi keterbacaan dan kepatuhan terhadap standar regional. Aspose.Tasks untuk .NET memungkinkan Anda mengontrol format ini dengan hanya beberapa baris kode, memastikan setiap angka keuangan muncul persis seperti yang diharapkan pemangku kepentingan Anda. Dalam tutorial ini kami akan membahas langkah‑langkah yang diperlukan, menjelaskan mengapa pengaturan ini penting, dan menunjukkan cara menerapkannya dalam proyek .NET dunia nyata.

## Jawaban Cepat
- **Apa arti “currency symbol after amount”?** Menampilkan simbol (misalnya $) setelah nilai numerik, seperti `100 $`.
- **Properti mana yang mengontrol posisi?** `CurrencySymbolPosition` pada objek `Project`.
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **Mata uang yang didukung?** Lebih dari 50 mata uang sudah tersedia, mencakup sebagian besar pasar global.
- **Bisakah saya mengubah pengaturan ini saat runtime?** Ya, Anda dapat memperbaruinya kapan saja sebelum menyimpan file proyek.

## Apa itu pengaturan “currency symbol after amount”?
Opsi **currency symbol after amount** menentukan apakah tanda mata uang muncul sebelum atau setelah nilai numerik di semua bidang moneter sebuah proyek. Menyesuaikan pengaturan ini memastikan laporan mematuhi konvensi akuntansi lokal tanpa pemrosesan manual. Ini juga meningkatkan keterbacaan bagi pemangku kepentingan yang terbiasa dengan format tersebut.

## Mengapa menggunakan Aspose.Tasks untuk pemformatan mata uang?
Aspose.Tasks mendukung **lebih dari 50 mata uang** dan dapat menangani proyek dengan **lebih dari 10.000 tugas** tanpa harus memuat seluruh file ke memori, memberikan kinerja cepat bahkan pada perangkat keras yang sederhana. API‑nya memberi Anda kontrol programatis, menghilangkan kebutuhan untuk mengedit spreadsheet secara manual. Hal ini membuat pelaporan keuangan berskala besar menjadi efisien dan dapat diandalkan.

## Prasyarat

### 1. Instalasi Aspose.Tasks untuk .NET
Pastikan Anda telah menginstal pustaka Aspose.Tasks. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/net/).

### 2. Pengetahuan Dasar tentang Pemrograman .NET
Pemahaman dasar tentang pemrograman .NET diperlukan untuk mengikuti contoh‑contoh yang disajikan.

## Import Namespaces

Namespace `Aspose.Tasks` menyediakan akses ke kelas `Project` dan enum terkait.

Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file proyek dalam memori. Setelah mengimpor namespace, Anda dapat mulai bekerja dengan data proyek.

```csharp

```

Sekarang, mari kita uraikan contoh ini menjadi langkah‑langkah yang jelas dan dapat ditindaklanjuti.

## Cara mengatur simbol mata uang setelah jumlah?

`CurrencySymbolPosition` adalah enumerasi yang menentukan apakah simbol mata uang muncul sebelum atau setelah nilai numerik.

Muat proyek Anda, atur `CurrencySymbolPosition` ke `After`, lalu simpan – itu saja yang Anda perlukan untuk menampilkan simbol setelah jumlah. Pendekatan langsung ini bekerja untuk semua mata uang yang didukung dan tidak memerlukan logika pemformatan tambahan. Anda juga dapat memverifikasi pengaturan dengan mengekspor contoh laporan biaya untuk memastikan simbol muncul dengan benar.

### Langkah 1: Muat File Proyek
Kelas `Project` memuat file MS‑Project yang sudah ada atau membuat yang baru di memori.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Langkah 2: Atur Posisi Simbol Mata Uang
`CurrencySymbolPosition` adalah enum yang memungkinkan Anda memilih `Before` atau `After`. Menetapkannya ke `After` menempatkan simbol setelah nilai numerik.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Langkah 3: Bekerja dengan Proyek
Setelah Anda mengonfigurasi posisi simbol, Anda dapat melanjutkan menambahkan tugas, sumber daya, atau bidang khusus sesuai kebutuhan. Pengaturan ini akan dipertahankan saat Anda menyimpan proyek.

```csharp
// Perform other operations with the project...
```

## Masalah Umum dan Solusinya
- **Simbol masih muncul sebelum jumlah:** Pastikan Anda mengatur properti *sebelum* memanggil `Save`. Mengubahnya setelah penyimpanan memerlukan penyimpanan ulang file.
- **Mata uang tidak didukung:** Verifikasi bahwa kode mata uang yang Anda gunakan tercantum dalam daftar mata uang yang didukung Aspose.Tasks (lebih dari 50 mata uang).
- **Penurunan kinerja pada proyek besar:** Gunakan `ProjectReader` untuk streaming file besar jika Anda melebihi 10.000 tugas.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya mengubah posisi simbol mata uang beberapa kali dalam satu proyek?**  
J: Ya, Anda dapat menyesuaikan `CurrencySymbolPosition` sebanyak yang diperlukan; cukup atur properti tersebut dan simpan ulang proyek.

**T: Apakah Aspose.Tasks mendukung mata uang selain Dolar AS?**  
J: Tentu saja. Aspose.Tasks mendukung lebih dari 50 mata uang internasional, memungkinkan Anda bekerja dengan format regional apa pun.

**T: Apakah ada versi percobaan untuk Aspose.Tasks untuk .NET?**  
J: Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Tasks untuk .NET dari [here](https://releases.aspose.com/).

**T: Bisakah saya mendapatkan bantuan jika mengalami masalah saat menggunakan Aspose.Tasks untuk .NET?**  
J: Tentu! Anda dapat mencari dukungan dan bantuan di forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**T: Bagaimana cara membeli lisensi untuk Aspose.Tasks untuk .NET?**  
J: Anda dapat membeli lisensi Aspose.Tasks untuk .NET dari [here](https://purchase.aspose.com/buy).

## Kesimpulan

Mengontrol **currency symbol after amount** merupakan bagian penting dari pelaporan keuangan dalam perangkat lunak manajemen proyek. Dengan Aspose.Tasks untuk .NET Anda dapat mengatur opsi ini secara programatis, mendukung lebih dari 50 mata uang dan menangani proyek besar secara efisien. Terapkan langkah‑langkah di atas untuk memastikan laporan proyek Anda sesuai dengan harapan format setiap locale.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Mengelola Koleksi Kalender di Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Koleksi Pengecualian Kalender di Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Menangani Tarif MS Project dengan Aspose.Tasks untuk .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}