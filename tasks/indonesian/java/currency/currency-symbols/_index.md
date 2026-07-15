---
date: 2026-02-10
description: Pelajari cara mengekstrak dan memperbarui properti proyek Java seperti
  simbol mata uang menggunakan Aspose.Tasks untuk Java. Ubah mata uang proyek dan
  dapatkan simbol mata uang dengan mudah.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Properti Proyek Java – Ekstrak Simbol Mata Uang dari MPP Menggunakan Aspose.Tasks
  untuk Java
url: /id/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak simbol mata uang mpp menggunakan Aspose.Tasks untuk Java

## Introduction
Pada tutorial ini Anda akan belajar cara bekerja dengan **java project properties**—khususnya cara mengekstrak simbol mata uang dari file Microsoft Project (MPP) dan cara **change currency symbol java** atau **retrieve currency symbol java** menggunakan pustaka Aspose.Tasks. Baik Anda sedang membangun alat pelaporan, mengintegrasikan data Project ke dalam sistem keuangan, atau sekadar perlu menampilkan simbol mata uang yang tepat di UI Anda, menguasai tugas kecil namun penting ini akan membuat aplikasi Java Anda lebih kuat dan ramah pengguna.

## Quick Answers
- **Apa arti “extract currency symbol mpp”?** Artinya membaca simbol mata uang yang disimpan dalam file MPP (Microsoft Project).  
- **Library mana yang menangani ini?** Aspose.Tasks for Java menyediakan API sederhana untuk tugas ini.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama waktu yang dibutuhkan?** Dengan kode di bawah ini, Anda dapat memperoleh simbol dalam waktu kurang dari satu menit.  
- **Apakah saya juga dapat mengubah simbol?** Ya – Anda dapat menetapkan nilai baru menggunakan properti `Prj.CURRENCY_SYMBOL` yang sama.

## What is “extract currency symbol mpp”?
Microsoft Project menyimpan simbol mata uang (mis., $, €, £) di header file proyek. Operasi **extract currency symbol mpp** membaca nilai tersebut sehingga Anda dapat menampilkan atau memanipulasinya secara programatik.

## Why update currency symbol in java project properties?
Proyek sering melibatkan banyak wilayah. Kemampuan untuk **change project currency** atau **update currency symbol** pada waktu berjalan memungkinkan Anda menyesuaikan laporan, faktur, atau dasbor ke pasar lokal tanpa harus membuat ulang seluruh file proyek. Fleksibilitas ini merupakan bagian inti dari pengelolaan java project properties secara efektif.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. File **project.mpp** yang valid ditempatkan di folder yang dapat Anda referensikan dari kode Anda.

## Import Packages
First, import the classes we’ll need to work with Project files.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Define the Data Directory
Tell the application where your *.mpp* file lives.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Gunakan `System.getProperty("user.dir")` untuk membangun path absolut yang berfungsi di mesin mana pun.

## Step 2: Load the MS Project File
Create a `Project` object that represents the MPP file in memory.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Step 3: Retrieve (and optionally change) the Currency Symbol
Now we **retrieve currency symbol java** by reading the `Prj.CURRENCY_SYMBOL` property. You can also **change currency symbol java** (or **change project currency**) by assigning a new string to the same property.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Pemanggilan `System.out.println` mencetak simbol (mis., `$`) ke konsol, mengonfirmasi bahwa ekstraksi berhasil.

## Common Issues & How to Fix Them
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|----------|
| `NullPointerException` on `project.get(...)` | Path file salah atau file tidak ditemukan | Verifikasi `dataDir` dan nama file; gunakan `new File(dataDir).exists()` untuk debug |
| Simbol tidak terduga (mis., `?`) | Proyek dibuat dengan locale non‑standar | Pastikan file MPP sumber memang mendefinisikan simbol mata uang; Anda dapat menetapkannya secara programatik seperti yang ditunjukkan di atas |
| Kesalahan lisensi | Menggunakan versi percobaan tanpa file lisensi yang valid | Muat lisensi Anda dengan `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` sebelum membuat objek `Project` |

## Frequently Asked Questions

**Q: Bisakah saya memanipulasi atribut proyek lain selain simbol mata uang menggunakan Aspose.Tasks?**  
A: Ya, Aspose.Tasks memungkinkan Anda mengedit tugas, sumber daya, penugasan, kalender, dan banyak properti proyek lainnya.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file MS Project?**  
A: Tentu saja. Ia mendukung format MPP, MPT, dan XML dari Project 98 hingga rilis terbaru.

**Q: Apakah Aspose.Tasks menyediakan dokumentasi dan dukungan untuk pengembang?**  
A: Dokumentasi API lengkap, contoh kode, dan forum dukungan khusus tersedia di situs web Aspose.Tasks.

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membelinya?**  
A: Ya – percobaan gratis yang berfungsi penuh dapat diunduh dari [Aspose website](https://purchase.aspose.com/buy).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?**  
A: Lisensi sementara disediakan pada [halaman lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.

---

**Terakhir Diperbarui:** 2026-02-10  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}