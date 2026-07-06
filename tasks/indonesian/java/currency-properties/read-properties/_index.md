---
date: 2026-02-07
description: Pelajari cara membaca properti mata uang Java dan mengekstrak simbol
  mata uang Java dari file MS Project menggunakan Aspose.Tasks for Java. Ikuti panduan
  langkah demi langkah ini untuk mengekstrak kode mata uang, simbol, digit, dan posisi
  secara programatis.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Baca Properti Mata Uang Java dengan Proyek Aspose.Tasks
url: /id/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Properti Mata Uang Java dengan Proyek Aspose.Tasks

## Introduction
Dalam tutorial ini Anda akan **read currency properties java** dari file Microsoft Project menggunakan API Aspose.Tasks untuk Java. Aspose.Tasks memungkinkan Anda bekerja dengan file .mpp tanpa harus menginstal Microsoft Project, menjadikannya ideal untuk pelaporan otomatis, migrasi data, atau integrasi ke dalam aplikasi perusahaan berbasis Java. Pada akhir panduan ini, Anda akan dapat mengekstrak kode mata uang, simbol, jumlah digit desimal, dan posisi simbol langsung dari file proyek.

## Quick Answers
- **Apa arti “read currency properties java”?** Itu merujuk pada pengambilan metadata terkait mata uang (kode, simbol, digit, posisi) dari file MS Project menggunakan kode Java.  
- **Apakah saya memerlukan lisensi untuk mencoba ini?** Versi percobaan gratis Aspose.Tasks tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi JDK mana yang diperlukan?** Java 8 atau yang lebih baru.  
- **Bisakah saya mengubah pengaturan mata uang setelah membacanya?** Ya, Aspose.Tasks memungkinkan operasi baca dan tulis pada properti mata uang.  
- **Apakah ini kompatibel dengan semua versi .mpp?** API mendukung file yang dibuat dengan Microsoft Project 2003‑2021.

## What is read currency properties java?
Membaca properti mata uang dalam Java berarti mengakses pengaturan tingkat proyek yang menentukan bagaimana nilai moneter ditampilkan dalam file Microsoft Project. Pengaturan ini mencakup kode mata uang ISO (misalnya **USD**), simbol (**$**), jumlah digit desimal, dan apakah simbol muncul sebelum atau sesudah jumlah.

## Why read currency properties java with Aspose.Tasks?
- **Tidak memerlukan instalasi Microsoft Project** – API ini bekerja pada platform apa pun yang mendukung Java.  
- **Ekstraksi cepat dalam proses** – ideal untuk pemrosesan batch sejumlah besar file proyek.  
- **Kontrol penuh** – Anda dapat menggabungkan nilai yang diambil dengan pelaporan khusus atau mengintegrasikannya ke dalam sistem ERP.  
- **Dukungan lintas versi** – bekerja dengan file .mpp dari Project 2003 hingga rilis terbaru 2021.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – Java 8 atau yang lebih baru terinstal dan dikonfigurasi di `PATH` Anda.  
2. **Aspose.Tasks for Java JAR** – unduh pustaka terbaru dari [here](https://releases.aspose.com/tasks/java/) dan tambahkan ke classpath proyek Anda.  

## Import Packages
Mulailah dengan mengimpor namespace Aspose.Tasks yang diperlukan untuk manipulasi proyek:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Tentukan folder yang berisi file `.mpp` yang ingin Anda analisis. Menyimpan path dalam variabel membuat kode dapat digunakan kembali:

```java
String dataDir = "Your Data Directory";
```

*Ganti `"Your Data Directory"` dengan path absolut atau relatif ke folder tempat `project.mpp` berada.*

## Step 2: Create a Project Reader Instance
Muat file Microsoft Project ke dalam objek `Project`. Objek ini memberi Anda akses ke semua properti proyek, termasuk pengaturan mata uang:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Jika file Anda memiliki nama yang berbeda, ubah `"project.mpp"` sesuai kebutuhan.*

## Step 3: Display Currency Properties
Sekarang ambil setiap atribut mata uang menggunakan enumerasi `Prj` dan cetak hasilnya ke konsol. API mengembalikan objek yang dapat Anda konversi ke string untuk ditampilkan:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Apa yang akan Anda lihat:**  
- **Currency Code** – kode ISO‑4217 seperti `USD`, `EUR`, `JPY`.  
- **Currency Digits** – biasanya `2` untuk kebanyakan mata uang, `0` untuk Yen Jepang.  
- **Currency Symbol** – karakter yang ditampilkan dalam laporan (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` untuk **sebelum** jumlah, `1` untuk **sesudah**.

## How to extract currency symbol java?
Jika yang Anda butuhkan hanya simbolnya saja, Anda dapat fokus pada properti `Prj.CURRENCY_SYMBOL`. Pemanggilan `project.get(...)` yang sama mengembalikan simbol, yang dapat Anda simpan, log, atau kirim ke layanan lain untuk pemrosesan lebih lanjut. Ini sangat berguna ketika Anda perlu **extract currency symbol java** untuk dasbor keuangan atau komponen UI yang terlokalisasi.

## Step 4: Process Completion
Berikan sinyal bahwa ekstraksi telah selesai dengan sukses. Pesan sederhana ini berguna ketika kode dijalankan sebagai bagian dari pekerjaan batch yang lebih besar:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | Path `dataDir` tidak tepat atau nama file salah ketik. | Verifikasi string direktori dan pastikan file `.mpp` ada di lokasi yang ditentukan. |
| **NullPointerException on `project.get(...)`** | File proyek tidak berisi informasi mata uang (jarang) atau kunci properti salah. | Gunakan `project.contains(Prj.CURRENCY_CODE)` untuk memeriksa keberadaan sebelum membaca. |
| **LicenseException** | Menjalankan tanpa lisensi Aspose.Tasks yang valid di lingkungan produksi. | Terapkan file lisensi menggunakan `License license = new License(); license.setLicense("Aspose.Tasks.lic");` sebelum membuat objek `Project`. |

## Frequently Asked Questions

**Q: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?**  
A: Aspose.Tasks mendukung file .mpp yang dihasilkan oleh Microsoft Project 2003‑2021, mencakup format lama maupun yang terbaru.

**Q: Bisakah saya mengubah properti mata uang menggunakan Aspose.Tasks?**  
A: Ya, Anda dapat membaca maupun menulis pengaturan mata uang. Gunakan `project.set(Prj.CURRENCY_CODE, "EUR");` lalu simpan proyek.

**Q: Apakah Aspose.Tasks cocok untuk penggunaan komersial?**  
A: Tentu saja. Ini adalah pustaka komersial; Anda dapat membeli lisensi [here](https://purchase.aspose.com/buy).

**Q: Apakah Aspose.Tasks menawarkan percobaan gratis?**  
A: Ya, percobaan penuh fungsi tersedia dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.Tasks?**  
A: Forum resmi Aspose.Tasks adalah tempat terbaik untuk mendapatkan bantuan – kunjungi [here](https://forum.aspose.com/c/tasks/15).

## Additional FAQ (AI‑Optimized)

**Q: Bagaimana cara mengekstrak hanya simbol mata uang secara programatis di Java?**  
A: Panggil `project.get(Prj.CURRENCY_SYMBOL)` dan cast hasilnya ke `String`. Ini mengembalikan simbol tepat yang digunakan dalam file proyek.

**Q: Bisakah saya membaca properti mata uang dari file .mpp yang dilindungi kata sandi?**  
A: Ya. Muat file dengan overload yang tepat dari konstruktor `Project` yang menerima kata sandi, lalu baca properti seperti yang ditunjukkan.

**Q: Kinerja seperti apa yang dapat saya harapkan saat memproses banyak file proyek?**  
A: Aspose.Tasks beroperasi dalam proses dan biasanya membaca file .mpp standar dalam beberapa milidetik. Untuk operasi bulk, pertimbangkan untuk menggunakan kembali instance `Project` yang sama bila memungkinkan.

## Conclusion
Anda kini telah mempelajari cara **read currency properties java** dan **extract currency symbol java** dari file MS Project menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda menggabungkan metadata mata uang ke dalam laporan khusus, analisis keuangan, atau pipeline integrasi tanpa bergantung pada Microsoft Project itu sendiri. Jangan ragu untuk bereksperimen dengan memodifikasi properti atau menggabungkan data ini dengan atribut proyek lain untuk membangun solusi yang lebih kaya.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}