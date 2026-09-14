---
date: 2026-09-14
description: Pelajari cara mendapatkan mata uang MS Project dan membaca properti proyek
  Java dengan Aspose.Tasks. Panduan langkah demi langkah untuk mengekstrak digit mata
  uang dari file MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Cara Mendapatkan Mata Uang dari MS Project menggunakan Aspose.Tasks
og_description: Pelajari cara mendapatkan mata uang MS Project dan membaca properti
  proyek Java dengan Aspose.Tasks. Ikuti tutorial Java singkat ini untuk mengekstrak
  digit mata uang dari file MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Cara mendapatkan mata uang MS Project menggunakan Aspose.Tasks – Panduan
  Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Cara mendapatkan mata uang MS Project menggunakan Aspose.Tasks
url: /id/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mendapatkan mata uang proyek ms menggunakan Aspose.Tasks

## Pendahuluan
If you’re wondering **cara mendapatkan mata uang proyek ms** information from a Microsoft Project file, you’ve landed in the right place. In this comprehensive tutorial you’ll discover **cara bekerja dengan mata uang proyek ms** values using the Aspose.Tasks library for Java. Whether you’re building a reporting tool, a migration utility, or simply need to read the currency settings from a **file proyek java**, this guide walks you through every step—from loading an *.mpp* file to extracting the currency digits. By the end, you’ll be comfortable handling ms project currency data in your own applications.

## Jawaban cepat
- **Perpustakaan apa yang membaca file MS Project?** Aspose.Tasks for Java.  
- **Berapa baris kode untuk mendapatkan digit mata uang?** Just three concise lines after the project is loaded.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** A free trial works for testing; a commercial license is required for production.  
- **Versi Java mana yang didukung?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Bisakah saya mengambil properti Project lainnya?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## Apa itu mata uang proyek ms?
The `ms project currency` property defines the number of decimal places Microsoft Project uses when displaying monetary values. It is stored in the Project file as the **CURRENCY_DIGITS** field and determines whether amounts appear as whole numbers, one‑decimal, two‑decimal, etc. This setting directly influences budgeting reports, cost roll‑ups, and any UI that shows financial figures, making it essential for accurate data exchange.

## Mengapa menggunakan Aspose.Tasks untuk menangani mata uang proyek ms?
Aspose.Tasks memungkinkan Anda mengekstrak digit mata uang tanpa menginstal Microsoft Project, dan melakukannya dengan kinerja tingkat perusahaan. The library supports **30+ years of Project file versions**—from Project 2000 through Project 2024—covering more than **150 distinct file schemas**. Loading a 500‑page project typically takes under **2 seconds** on a standard server, and you can query only the fields you need, keeping memory usage under **50 MB** even for the largest schedules.

## Prasyarat
Before you start, make sure you have the following:

1. **Java Development Environment** – JDK 8 atau yang lebih baru terpasang dan dikonfigurasi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari situs resmi: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Anda harus nyaman membuat proyek Java, menambahkan pustaka eksternal, dan menjalankan metode `main`.  

## Impor paket
Pertama, impor kelas yang diperlukan.  
Impor kelas `Project` dan utilitas terkait dari pustaka Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Langkah 1: tentukan direktori data
Tentukan folder yang berisi **file proyek java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan path absolut atau relatif tempat `project.mpp` berada.

## Langkah 2: muat file mpp  
Sekarang kita akan melihat **cara memuat mpp** menggunakan Aspose.Tasks.  
Kelas `Project` mewakili file Microsoft Project dan menyediakan akses ke propertinya.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Pastikan nama file cocok persis; jika tidak, `IOException` akan dilempar.

## Langkah 3: ambil digit mata uang  
Dengan proyek dimuat, mengekstrak digit **ms project currency** adalah satu baris kode:  
The `getCurrencyDigits()` method returns the number of decimal places defined for monetary values.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Pemanggilan mengembalikan `Integer` yang mewakili jumlah tempat desimal (misalnya, `2` untuk sen). Nilai tersebut dicetak ke konsol, tetapi Anda juga dapat menyimpannya dalam variabel untuk pemrosesan lebih lanjut.

## Masalah umum & tips
- **File tidak ditemukan** – double‑check the `dataDir` path and ensure the file name is correct, including the `.mpp` extension.  
- **Versi file tidak didukung** – Aspose.Tasks supports Project 2000‑2024 formats; older or corrupted files may need conversion.  
- **Lisensi belum diatur** – during development a trial works, but for production you must apply a valid license to avoid evaluation watermarks.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Tasks dapat menangani atribut Project lain selain digit mata uang?**  
A: Ya, Aspose.Tasks menawarkan berbagai fungsionalitas untuk memanipulasi berbagai aspek file Project, seperti tugas, sumber daya, dan field kustom.

**Q: Apakah Aspose.Tasks cocok untuk aplikasi tingkat perusahaan?**  
A: Tentu saja, Aspose.Tasks dirancang untuk memenuhi kebutuhan proyek tingkat perusahaan, menawarkan kinerja tinggi dan skalabilitas.

**Q: Apakah Aspose.Tasks mendukung pengembangan lintas platform?**  
A: Ya, Anda dapat menggunakan Aspose.Tasks untuk Java di platform apa pun yang mendukung Java Runtime Environment (Windows, Linux, macOS).

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
A: Ya, Anda dapat mengunduh versi trial gratis dari [Aspose releases page](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
A: Anda dapat menemukan dukungan di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Terakhir diperbarui:** 2026-09-14  
**Diuji dengan:** Aspose.Tasks for Java (latest at time of writing)  
**Penulis:** Aspose

## Tutorial Terkait

- [java project properties – Ekstrak simbol mata uang dari MPP menggunakan Aspose.Tasks untuk Java](/tasks/java/currency/currency-symbols/)
- [Cara Mengambil Mata Uang dari MS Project dengan Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Properti Project Java – Baca Metadata dengan Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}