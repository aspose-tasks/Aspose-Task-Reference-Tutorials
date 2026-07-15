---
date: 2026-02-10
description: Pelajari cara membaca properti mata uang java dan mengatur nilai mata
  uang dalam file MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah
  demi langkah untuk mengekstrak kode mata uang java dan menyesuaikan format mata
  uang java.
linktitle: How to Read Currency
second_title: Aspose.Tasks Java API
title: Baca Properti Mata Uang Java dengan Aspose.Tasks
url: /id/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Properti Mata Uang Java dengan Aspose.Tasks

## Introduction
Siap meningkatkan keahlian Anda dalam Aspose.Tasks untuk Java? Dalam tutorial ini Anda akan menemukan **cara membaca properti mata uang java** dari file Microsoft Project dan juga belajar **cara mengatur nilai mata uang** bila diperlukan. Menguasai properti ini membantu Anda menjaga konsistensi data keuangan di seluruh proyek internasional, menghindari kesalahan konversi, dan menyajikan laporan biaya yang jelas kepada pemangku kepentingan.

## Quick Answers
- **Apa arti “read currency”?** Mengekstrak kode mata uang, simbol, dan format yang disimpan dalam file Project.  
- **Mengapa mengatur pengaturan mata uang?** Untuk menyesuaikan format regional anggaran proyek Anda atau mematuhi persyaratan klien.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks untuk Java yang valid diperlukan untuk penggunaan produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi Project mana yang didukung?** Baik format .mpp (Microsoft Project 2007‑2024) maupun .xml sepenuhnya didukung.  
- **Apakah ada pengaturan tambahan yang diperlukan?** Cukup tambahkan JAR Aspose.Tasks untuk Java ke classpath Anda dan impor kelas yang relevan.

## Read Currency Properties Java in Aspose.Tasks Projects
Dalam dunia manajemen proyek yang dinamis, mengekstrak detail mata uang sangat penting untuk analisis biaya yang akurat. Panduan khusus kami **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** memandu Anda melalui setiap langkah—dari membuka file proyek hingga mengambil kode mata uang, simbol, dan formatnya. Dengan mengikuti tutorial ini Anda akan dapat:

* Mengambil kode mata uang (misalnya USD, EUR) yang digunakan di seluruh proyek.  
* Mengakses simbol mata uang dan pengaturan format angka.  
* Menggunakan informasi ini untuk menghasilkan laporan biaya yang terlokalisasi atau mengisi dasbor keuangan.

Memahami cara membaca mata uang memastikan Anda dapat mengaudit anggaran proyek, membandingkan biaya antar wilayah, dan menjaga kepatuhan terhadap standar akuntansi.

## How to Extract Currency Code Java with Aspose.Tasks
Jika Anda hanya memerlukan identifier ISO‑4217, API menyediakan properti yang sederhana:

* `project.getCurrencyCode()` mengembalikan kode tiga huruf seperti **USD** atau **EUR**.  
* Nilai ini dapat disimpan, dicatat, atau diteruskan ke layanan keuangan eksternal untuk konversi.

Mengekstrak kode mata uang secara programatik sangat berguna ketika Anda mengintegrasikan data proyek dengan sistem ERP yang mengharapkan kode standar.

## How to Adjust Currency Format Java with Aspose.Tasks
Locale yang berbeda memerlukan format angka yang berbeda (pemisah desimal, pemisah ribuan, dll.). Gunakan properti berikut untuk menyesuaikan tampilan:

* `project.setCurrencySymbol("€")` – menetapkan simbol visual.  
* `project.setCurrencyDecimalSeparator(",")` – menentukan pemisah desimal.  
* `project.setCurrencyThousandsSeparator(".")` – menentukan pemisah ribuan.  

Menyesuaikan format mata uang memastikan setiap pemangku kepentingan melihat angka dalam gaya yang familiar, mengurangi kesalahpahaman.

## How to Set Currency Properties in Aspose.Tasks Projects
Ketika sebuah proyek berpindah ke pasar baru atau klien meminta format moneter yang berbeda, Anda perlu **mengatur mata uang** secara programatik. Panduan langkah‑demi‑langkah kami **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** menjelaskan cara:

* Menetapkan kode mata uang dan simbol baru untuk seluruh proyek.  
* Menyesuaikan format angka (jumlah desimal, pemisah ribuan) agar sesuai dengan konvensi lokal.  
* Menyimpan file proyek yang telah diperbarui tanpa kehilangan data yang ada.

Dengan menguasai cara mengatur mata uang, Anda mendapatkan kontrol penuh atas representasi keuangan jadwal Anda, memudahkan pergantian antara USD, GBP, JPY, atau mata uang lain yang didukung secara dinamis.

## Why Master Currency Handling in Aspose.Tasks?
* **Kolaborasi Global:** Tim di berbagai negara dapat melihat biaya dalam format native mereka.  
* **Pelaporan Akurat:** Mencegah kesalahan pembulatan atau konversi yang dapat memengaruhi anggaran.  
* **Kepatuhan:** Menyesuaikan dengan standar akuntansi regional dan spesifikasi klien.  
* **Otomatisasi:** Mengurangi penyuntingan manual dengan menerapkan pengaturan mata uang secara programatik selama pembuatan proyek.

## Real‑World Use Cases
* **Proyek Multinasional:** Firma konstruksi yang mengelola situs di Eropa dan Amerika Utara perlu menyajikan anggaran dalam EUR dan USD.  
* **Audit Keuangan:** Auditor memerlukan tampilan jelas tentang konteks mata uang untuk setiap entri biaya.  
* **Model Penetapan Harga Dinamis:** Penyedia SaaS menyesuaikan biaya langganan berdasarkan mata uang lokal pelanggan.

## Common Pitfalls & Tips
* **Pitfall:** Lupa memperbarui simbol mata uang setelah mengubah kode.  
  **Tip:** Selalu atur kode dan simbol secara bersamaan untuk menghindari tampilan yang tidak cocok.  
* **Pitfall:** Mengandalkan locale default mesin yang menjalankan kode.  
  **Tip:** Secara eksplisit tentukan format mata uang yang diinginkan dalam kode Aspose.Tasks Anda untuk memastikan konsistensi di semua lingkungan.  

## Currency Properties Tutorials
### [Read Currency Properties in Aspose.Tasks Projects](./read-properties/)
Pelajari cara mengekstrak informasi mata uang dari file MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah‑demi‑langkah disediakan.

### [Set Currency Properties in Aspose.Tasks Projects](./set-properties/)
Pelajari cara mengatur properti mata uang dalam proyek Aspose.Tasks menggunakan Java. Manipulasi file Microsoft Project menjadi mudah.

## Frequently Asked Questions

**Q: Can I change the currency after the project is already saved?**  
A: Ya. Gunakan `Project.setCurrencyCode()` dan metode terkait, lalu simpan proyek kembali.

**Q: Does changing the currency affect existing cost values?**  
A: Nilai numerik tetap tidak berubah; hanya format tampilan (simbol, pemisah desimal) yang diperbarui. Anda harus menghitung ulang biaya jika memerlukan konversi antar mata uang.

**Q: Are there any limits on the number of currencies I can define?**  
A: Aspose.Tasks mendukung semua kode mata uang ISO‑4217, sehingga secara efektif tidak ada batasan.

**Q: What happens if I open a project with an unsupported currency code?**  
A: Perpustakaan akan kembali ke mata uang default (USD) dan mencatat peringatan; Anda dapat menimpa ini dengan mengatur mata uang yang diinginkan secara manual.

**Q: Is it possible to read/write currency properties in a Project XML file?**  
A: Tentu saja. API yang sama bekerja untuk format .mpp dan .xml.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}