---
date: 2026-09-14
description: Pelajari cara mengubah currency format dan membaca currency properties
  di Java menggunakan Aspose.Tasks. Ekstrak currency code, ambil currency symbol,
  dan perbarui project currency dalam file MS Project.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Cara mengubah currency format
og_description: Pelajari cara mengubah currency format dan membaca currency properties
  di Java menggunakan Aspose.Tasks. Panduan langkah demi langkah untuk mengekstrak
  currency code dan memperbarui project currency.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Cara mengubah currency format di Java dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Cara mengubah currency format di Java dengan Aspose.Tasks
url: /id/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca properti mata uang Java dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **mengubah format mata uang** dan membaca properti mata uang dalam proyek Java yang menggunakan Aspose.Tasks. Data keuangan yang akurat sangat penting untuk tim multinasional, dan menguasai API ini memungkinkan Anda mengekstrak kode ISO‑4217, mengambil simbol mata uang, dan memperbarui pengaturan moneter proyek tanpa mengedit spreadsheet secara manual.

## Jawaban Cepat
- **Apa arti “read currency”?** Itu berarti mengekstrak kode mata uang, simbol, dan pengaturan format‑angka yang disimpan di dalam file Project.  
- **Mengapa menyesuaikan pengaturan mata uang?** Untuk menyelaraskan laporan biaya dengan konvensi regional dan menghindari kesalahan konversi.  
- **Apakah saya memerlukan lisensi?** Ya – lisensi Aspose.Tasks untuk Java yang valid diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi Project mana yang didukung?** Baik format *.mpp* (Project 2007‑2024) maupun *.xml* didukung sepenuhnya, mencakup lebih dari 20 tahun versi file.  
- **Apakah ada penyiapan tambahan yang diperlukan?** Cukup tambahkan JAR Aspose.Tasks untuk Java ke classpath Anda dan impor kelas yang relevan.

## Baca properti mata uang Java dalam proyek Aspose.Tasks
Dalam bidang manajemen proyek yang dinamis, mengekstrak detail mata uang sangat penting untuk analisis biaya yang akurat. Panduan khusus kami **[Membaca Properti Mata Uang dalam Proyek Aspose.Tasks](./read-properties/)** memandu Anda melalui setiap langkah—dari membuka file proyek hingga mengambil kode mata uang, simbol, dan format. Dengan mengikuti tutorial ini Anda akan dapat:
* Tarik kode mata uang (mis., USD, EUR) yang digunakan di seluruh proyek.  
* Akses simbol mata uang dan pengaturan format‑angka.  
* Gunakan informasi ini untuk menghasilkan laporan biaya yang dilokalkan atau mengisi dasbor keuangan.  

Memahami cara membaca mata uang memastikan Anda dapat mengaudit anggaran proyek, membandingkan biaya antar wilayah, dan menjaga kepatuhan terhadap standar akuntansi.

## Cara mengekstrak kode mata uang java dengan Aspose.Tasks
Metode `Project.getCurrencyCode()` mengembalikan pengenal tiga‑huruf ISO‑4217 untuk unit moneter proyek.  

**Jawaban langsung:** Panggil `project.getCurrencyCode()` untuk memperoleh kode mata uang seperti **USD** atau **EUR**; Anda kemudian dapat menyimpan, mencatat, atau mengirim nilai ini ke layanan keuangan eksternal untuk konversi. Panggilan satu baris ini memberi Anda pengenal yang dapat diandalkan dan berbasis standar yang berfungsi di semua versi Project yang didukung.  

Metode ini menyediakan cara cepat untuk menyinkronkan data proyek dengan sistem ERP yang mengharapkan kode standar.

## Cara menyesuaikan format mata uang java dengan Aspose.Tasks
Mengubah representasi visual nilai moneter dilakukan melalui tiga properti sederhana.

`project.setCurrencySymbol(String)` menetapkan simbol mata uang yang ditampilkan untuk nilai moneter.  
`project.setCurrencyDecimalSeparator(char)` menentukan karakter yang digunakan untuk memisahkan bagian bilangan bulat dari bagian pecahan.  
`project.setCurrencyThousandsSeparator(char)` menentukan karakter yang digunakan untuk memisahkan kelompok ribuan.  

**Jawaban langsung:** Gunakan `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")`, dan `project.setCurrencyThousandsSeparator(".")` untuk mendefinisikan simbol, pemisah desimal, dan pemisah ribuan masing‑masing—ini sepenuhnya mengubah format mata uang dalam satu langkah. Menyesuaikan pengaturan ini menjamin setiap pemangku kepentingan melihat angka dalam gaya yang familiar, mengurangi kesalahpahaman.  

* `project.setCurrencySymbol("€")` – menetapkan simbol visual.  
* `project.setCurrencyDecimalSeparator(",")` – menentukan pemisah desimal.  
* `project.setCurrencyThousandsSeparator(".")` – menentukan pemisah ribuan.  

## Cara mengatur properti mata uang dalam proyek Aspose.Tasks
Ketika sebuah proyek berpindah ke pasar baru atau klien meminta format moneter yang berbeda, Anda perlu memperbarui mata uang secara programatis.  

`project.setCurrencyCode(String)` mendefinisikan kode mata uang ISO‑4217 untuk proyek.  

**Jawaban langsung:** Panggil `project.setCurrencyCode("GBP")` bersama dengan `project.setCurrencySymbol("£")` dan pemisah yang sesuai, lalu simpan proyek; perpustakaan akan memperbarui semua pengaturan tampilan sambil mempertahankan data biaya yang ada. Pendekatan ini memberi Anda kontrol penuh atas representasi keuangan jadwal Anda.  

Panduan langkah‑demi‑langkah kami **[Mengatur Properti Mata Uang dalam Proyek Aspose.Tasks](./set-properties/)** menjelaskan cara:
* Mendefinisikan kode mata uang dan simbol baru untuk seluruh proyek.  
* Menyesuaikan format angka (tempat desimal, pemisah ribuan) agar sesuai dengan konvensi lokal.  
* Menyimpan file proyek yang diperbarui tanpa kehilangan data yang ada.  

Dengan menguasai cara mengatur mata uang, Anda dapat beralih antara USD, GBP, JPY, atau mata uang lain yang didukung secara cepat.

## Mengapa menguasai penanganan mata uang dalam Aspose.Tasks?
Penanganan mata uang yang tepat menghilangkan kesalahpahaman yang mahal dan memperlancar kolaborasi global.  

**Jawaban langsung:** Menguasai penanganan mata uang memungkinkan Anda menyajikan biaya dalam format asli masing‑masing tim, memastikan pelaporan yang akurat, mematuhi standar akuntansi regional, dan memungkinkan alur kerja keuangan otomatis—menghemat jam kerja manual per proyek.  

* **Kolaborasi global:** Tim di berbagai negara dapat melihat biaya dalam format asli mereka.  
* **Pelaporan akurat:** Mencegah kesalahan pembulatan atau konversi yang dapat memengaruhi anggaran.  
* **Kepatuhan:** Menyesuaikan dengan standar akuntansi regional dan spesifikasi klien.  
* **Otomatisasi:** Mengurangi penyuntingan manual dengan menerapkan pengaturan mata uang secara programatis selama pembuatan proyek.  

## Kasus penggunaan dunia nyata
* **Proyek multi‑nasional:** Perusahaan konstruksi yang mengelola situs di Eropa dan Amerika Utara perlu menyajikan anggaran dalam EUR dan USD.  
* **Audit keuangan:** Auditor memerlukan tampilan jelas tentang konteks mata uang untuk setiap entri biaya.  
* **Model penetapan harga dinamis:** Penyedia SaaS menyesuaikan biaya langganan berdasarkan mata uang lokal pelanggan.  

## Jebakan umum & tips
* **Jebakan:** Lupa memperbarui simbol mata uang setelah mengubah kode.  
  **Tip:** Selalu atur kode dan simbol secara bersamaan untuk menghindari tampilan yang tidak cocok.  
* **Jebakan:** Mengandalkan locale default mesin yang menjalankan kode.  
  **Tip:** Secara eksplisit tentukan format mata uang yang diinginkan dalam kode Aspose.Tasks Anda untuk memastikan konsistensi di semua lingkungan.  

## Tutorial properti mata uang
### [Baca Properti Mata Uang dalam Proyek Aspose.Tasks](./read-properties/)
Pelajari cara mengekstrak informasi mata uang dari file MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah‑demi‑langkah disediakan.  

### [Atur Properti Mata Uang dalam Proyek Aspose.Tasks](./set-properties/)
Pelajari cara mengatur properti mata uang dalam proyek Aspose.Tasks menggunakan Java. Memanipulasi file Microsoft Project dengan mudah.  

## Pertanyaan yang sering diajukan
**Q: Bisakah saya mengubah mata uang setelah proyek sudah disimpan?**  
A: Ya. Gunakan `Project.setCurrencyCode()` dan metode terkait, lalu simpan proyek lagi.  

**Q: Apakah mengubah mata uang memengaruhi nilai biaya yang ada?**  
A: Nilai numerik tetap tidak berubah; hanya format tampilan (simbol, pemisah desimal) yang diperbarui. Anda harus menghitung ulang biaya jika memerlukan konversi antar mata uang.  

**Q: Apakah ada batasan jumlah mata uang yang dapat saya definisikan?**  
A: Aspose.Tasks mendukung semua kode mata uang ISO‑4217, sehingga pada dasarnya tidak ada batasan.  

**Q: Apa yang terjadi jika saya membuka proyek dengan kode mata uang yang tidak didukung?**  
A: Perpustakaan akan kembali ke mata uang default (USD) dan mencatat peringatan; Anda dapat menggantinya dengan mengatur mata uang yang diinginkan secara manual.  

**Q: Apakah memungkinkan untuk membaca/menulis properti mata uang dalam file Project XML?**  
A: Tentu saja. API yang sama bekerja untuk format *.mpp* dan *.xml*.  

**Terakhir Diperbarui:** 2026-09-14  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

## Tutorial Terkait
- [properti proyek java – Ekstrak simbol mata uang dari MPP menggunakan Aspose.Tasks untuk Java](/tasks/java/currency/currency-symbols/)
- [Cara Mengambil Mata Uang dari MS Project dengan Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Properti Proyek Java – Baca Metadata dengan Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}