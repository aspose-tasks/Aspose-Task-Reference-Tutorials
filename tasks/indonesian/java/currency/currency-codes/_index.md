---
date: 2026-02-10
description: Pelajari cara mengambil kode mata uang dari file MS Project menggunakan
  Aspose.Tasks untuk Java – cara cepat mendapatkan kode mata uang yang dibutuhkan
  pengembang Java.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengambil Mata Uang dari MS Project dengan Aspose.Tasks
url: /id/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengambil Mata Uang dari MS Project dengan Aspise.Tasks

## Pendahuluan
Selamat datang! Dalam tutorial ini Anda akan menemukan **cara mengambil kode mata uang** dari file MS Project menggunakan Aspose.Tasks Java API. Baik Anda membuat laporan keuangan multi‑mata uang, mengkonsolidasikan proyek dari berbagai wilayah, atau hanya membutuhkan simbol moneter yang tepat untuk pemrosesan lanjutan, panduan ini akan memandu Anda melalui setiap langkah—dari menyiapkan lingkungan hingga mengekstrak kode mata uang secara programatis. Pada akhirnya, Anda akan merasa nyaman membaca file MS Project dan menggunakan panggilan **get currency code java** untuk memperoleh identifier mata uang ISO.

## Jawaban Cepat
- **Apa yang dilakukan API?** API membaca file MS Project dan menampilkan properti seperti kode mata uang.  
- **Bahasa apa yang digunakan?** Java, melalui pustaka Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengambil kode dalam satu baris?** Ya—`prj.get(Prj.CURRENCY_CODE)` mengembalikan string kode mata uang.  
- **Apakah kompatibel dengan semua versi Project?** Aspose.Tasks mendukung format lama (MPP) dan baru (XML, XER).

## Apa itu **read ms project file**?
Membaca file MS Project berarti secara programatis membuka dokumen proyek *.mpp* (atau format lain yang didukung) dan mengakses struktur data‑nya—tugas, sumber daya, kalender, dan pengaturan keuangan—tanpa interaksi manual dengan Microsoft Project itu sendiri.

## Mengapa menggunakan Aspose.Tasks untuk **read msproject** file?
- **Dukungan format lengkap** – bekerja dengan file dari Project 98 hingga rilis Office terbaru.  
- **Tidak memerlukan instalasi COM atau Office** – murni Java, sempurna untuk otomatisasi sisi server.  
- **API kaya** – memberikan akses langsung ke properti seperti `Prj.CURRENCY_CODE`, memungkinkan Anda **how to retrieve currency** informasi secara instan.  
- **Kinerja** – parsing ringan, ideal untuk pemrosesan batch banyak proyek.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki hal‑hal berikut:

### Java Development Kit (JDK) Terpasang
Pastikan JDK terbaru tersedia di mesin Anda. Anda dapat mengunduh dan menginstal versi JDK terbaru dari [sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Pustaka Aspose.Tasks untuk Java
Unduh dan siapkan pustaka Aspose.Tasks untuk Java. Dokumentasi terperinci serta binary terbaru tersedia [di sini](https://reference.aspose.com/tasks/java/).

## Mengimpor Paket
Untuk memulai, mari impor paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Panduan Langkah‑demi‑langkah

### Langkah 1: Siapkan Direktori Data
Tentukan folder yang berisi file *.mpp* Anda. Sesuaikan path agar cocok dengan lingkungan Anda.
```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Muat File Proyek
Buat instance `Project` dengan memuat file MS Project. Ini adalah titik di mana Anda **read msproject** data ke dalam memori.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Langkah 3: Ambil Kode Mata Uang
Setelah proyek dimuat, Anda dapat **how to retrieve currency** informasi dengan satu panggilan. Ini menunjukkan penggunaan **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Output akan berupa kode mata uang ISO tiga huruf (mis., `USD`, `EUR`, `GBP`) yang dikonfigurasi pada proyek.

### Langkah 4: Cara Mengambil Kode Mata Uang di Java (Konteks Tambahan)
Jika Anda perlu menyimpan nilai untuk penggunaan selanjutnya, cukup tetapkan ke sebuah variabel:

*Tidak diperlukan blok kode tambahan* – cukup gunakan string yang dikembalikan oleh `prj.get(Prj.CURRENCY_CODE)` dan kirimkan ke layanan keuangan apa pun, mesin pelaporan, atau komponen UI.

### Langkah 5: (Opsional) Gunakan Kode Mata Uang
Anda mungkin ingin menerapkan kode yang diambil di tempat lain—seperti memformat nilai biaya dalam laporan khusus atau mengirimkannya ke API keuangan. Skenario umum meliputi:

- **Pembuatan laporan** – tambahkan kode di depan kolom biaya (`USD 1,200`).  
- **Integrasi API** – kirim kode ISO ke gateway pembayaran yang memerlukan identifier mata uang.  
- **Konsolidasi data** – kelompokkan beberapa proyek berdasarkan mata uang untuk analisis portofolio.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Output null** | File proyek tidak menentukan mata uang (default kosong). | Atur mata uang di Microsoft Project atau tetapkan melalui `prj.set(Prj.CURRENCY_CODE, "USD");` sebelum membaca. |
| **File tidak ditemukan** | Path `dataDir` tidak tepat. | Verifikasi path dan pastikan nama file cocok persis, termasuk sensitivitas huruf. |
| **Versi file tidak didukung** | File *.mpp* sangat lama atau rusak. | Gunakan versi Aspose.Tasks terbaru atau konversi file ke format yang lebih baru di Microsoft Project terlebih dahulu. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah Aspose.Tasks menangani struktur proyek yang kompleks?**  
J: Ya, API dapat membaca dan memanipulasi hierarki tugas multi‑level, pool sumber daya, dan bidang khusus tanpa masalah.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file MS Project?**  
J: Tentu saja. Ia mendukung MPP, XML, XER, dan format lain di banyak rilis Microsoft Project.

**T: Apakah Aspose.Tasks menyediakan dokumentasi dan dukungan?**  
J: Dokumentasi lengkap, contoh kode, dan dukungan khusus tersedia di situs web Aspose.

**T: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
J: Versi percobaan gratis disediakan sehingga Anda dapat mengevaluasi semua fitur, termasuk membaca kode mata uang.

**T: Di mana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks?**  
J: Lisensi sementara dapat diperoleh dari [situs web](https://purchase.aspose.com/temporary-license/) untuk evaluasi jangka pendek.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks untuk Java (versi terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}