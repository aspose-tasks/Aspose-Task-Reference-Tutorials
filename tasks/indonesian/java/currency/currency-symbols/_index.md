---
date: 2026-09-20
description: Pelajari cara mengekstrak simbol mata uang mpp dan memperbarui properti
  proyek menggunakan Aspose.Tasks untuk Java. Ubah dan ambil simbol tersebut dalam
  hanya beberapa baris kode.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Ekstrak simbol mata uang mpp menggunakan Aspose.Tasks untuk Java
og_description: Pelajari cara mengekstrak simbol mata uang mpp dan memperbarui properti
  proyek menggunakan Aspose.Tasks untuk Java. Cepat, andal, dan siap untuk produksi.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Cara mengekstrak simbol mata uang mpp dengan Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Cara mengekstrak simbol mata uang mpp dengan Aspose.Tasks Java
url: /id/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak simbol mata uang mpp menggunakan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara bekerja dengan **java project properties**—khususnya cara **mengekstrak simbol mata uang mpp** dari file Microsoft Project (MPP) dan cara **mengubah simbol mata uang java** atau **mengambil simbol mata uang java** menggunakan pustaka Aspose.Tasks. Baik Anda sedang membangun alat pelaporan keuangan, mengintegrasikan data Project ke dalam sistem ERP, atau sekadar perlu menampilkan simbol mata uang yang benar di UI Anda, menguasai tugas kecil namun penting ini akan membuat aplikasi Java Anda lebih kuat dan ramah pengguna.

## Jawaban Cepat
- **Apa arti “extract currency symbol mpp”?** Itu berarti membaca simbol mata uang yang disimpan dalam file MPP (Microsoft Project).  
- **Pustaka mana yang menangani ini?** Aspose.Tasks untuk Java menyediakan API sederhana untuk pekerjaan ini.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama waktu yang dibutuhkan?** Dengan kode di bawah, Anda dapat mendapatkan simbol dalam waktu kurang dari satu menit.  
- **Apakah saya juga dapat mengubah simbolnya?** Ya – Anda dapat menetapkan nilai baru menggunakan properti `Prj.CURRENCY_SYMBOL` yang sama.

## Apa itu “extract currency symbol mpp”?
Mengekstrak simbol mata uang dari file MPP berarti membaca string satu karakter yang disimpan Microsoft Project di header file untuk mewakili unit moneter proyek. Operasi ini memungkinkan Anda menampilkan simbol yang tepat (seperti $, €, £) dalam aplikasi Anda tanpa harus mengkodekan nilai secara manual.

## Mengapa memperbarui simbol mata uang dalam properti proyek java?
Memperbarui simbol mata uang memungkinkan Anda melokalisasi laporan, faktur, dan dasbor secara dinamis. Perusahaan yang menjalankan proyek di beberapa wilayah dapat mengganti simbol dalam satu langkah, menghindari kebutuhan menduplikasi seluruh file proyek. Aspose.Tasks dapat memodifikasi properti di memori dan menyimpan kembali file, mendukung proyek dengan hingga 2.000 tugas tanpa penurunan kinerja yang signifikan.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. File **project.mpp** yang valid ditempatkan di folder yang dapat Anda referensikan dari kode Anda.

## Impor paket
Pertama, impor kelas yang diperlukan untuk bekerja dengan file Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Langkah 1: definisikan direktori data
Beritahu aplikasi di mana file *.mpp* Anda berada.

```java
String dataDir = "Your Data Directory";
```

> **Tip Pro:** Gunakan `System.getProperty("user.dir")` untuk membangun path absolut yang berfungsi di mesin mana pun.

## Langkah 2: muat file MS Project
`Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Membuat objek ini memuat struktur file tanpa memerlukan Microsoft Project terinstal.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Langkah 3: ambil (dan opsional ubah) simbol mata uang
`Prj.CURRENCY_SYMBOL` adalah kunci properti yang menyimpan simbol mata uang. Membacanya mengembalikan simbol saat ini; menetapkan string baru memperbarui definisi mata uang proyek.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Pemanggilan `System.out.println` mencetak simbol (mis., `$`) ke konsol, mengonfirmasi bahwa ekstraksi berhasil.

## Masalah umum & cara memperbaikinya
| Gejala | Penyebab kemungkinan | Solusi |
|---------|----------------------|--------|
| `NullPointerException` pada `project.get(...)` | Path file salah atau file tidak ditemukan | Verifikasi `dataDir` dan nama file; gunakan `new File(dataDir).exists()` untuk debug |
| Simbol tidak terduga (mis., `?`) | Proyek dibuat dengan locale non‑standar | Pastikan file MPP sumber memang mendefinisikan simbol mata uang; Anda dapat menetapkannya secara programatik seperti contoh di atas |
| Kesalahan lisensi | Menggunakan versi percobaan tanpa file lisensi yang valid | Muat lisensi Anda dengan `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` sebelum membuat objek `Project` |

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat memanipulasi atribut proyek lain selain simbol mata uang menggunakan Aspose.Tasks?**  
J: Ya, Aspose.Tasks memungkinkan Anda mengedit tugas, sumber daya, penugasan, kalender, dan banyak properti proyek lainnya.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file MS Project?**  
J: Tentu saja. Ia mendukung format MPP, MPT, dan XML dari Project 98 hingga rilis terbaru.

**T: Apakah Aspose.Tasks menyediakan dokumentasi dan dukungan untuk pengembang?**  
J: Dokumentasi API lengkap, contoh kode, dan forum dukungan khusus tersedia di situs web Aspose.Tasks.

**T: Bisakah saya mencoba Aspose.Tasks sebelum membelinya?**  
J: Ya – percobaan gratis yang berfungsi penuh dapat diunduh dari [situs Aspose](https://purchase.aspose.com/buy).

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?**  
J: Lisensi sementara disediakan di [halaman lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.

---

**Last Updated:** 2026-09-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Properti Proyek Java – Baca Metadata dengan Aspose.Tasks](/tasks/java/project-properties/)
- [Cara Mengambil Mata Uang dari MS Project dengan Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}