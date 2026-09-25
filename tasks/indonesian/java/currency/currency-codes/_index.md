---
date: 2026-09-25
description: Pelajari cara mengambil kode mata uang dari file MS Project menggunakan
  Aspose.Tasks untuk Java – cara cepat mendapatkan kode mata uang yang dibutuhkan
  pengembang Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Kelola Kode Mata Uang di Aspose.Tasks
og_description: Mengambil kode mata uang Java dari file MS Project menggunakan Aspose.Tasks.
  Panduan ini menunjukkan cara membaca proyek, mengekstrak identifier mata uang ISO,
  dan menerapkannya dalam aplikasi Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Mengambil kode mata uang Java dari MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Mengambil kode mata uang Java dari MS Project dengan Aspose.Tasks
url: /id/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengambil kode mata uang java dari MS Project dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengambil kode mata uang java** dari file MS Project dengan menggunakan Aspose.Tasks Java API. Apakah Anda perlu menghasilkan laporan keuangan multi‑mata uang, mengkonsolidasikan proyek di berbagai wilayah, atau sekadar menampilkan simbol mata uang yang benar dalam sistem hilir, langkah-langkah di bawah ini akan membawa Anda dari penyiapan lingkungan hingga pemanggilan satu baris yang mengembalikan pengenal mata uang ISO. Pada akhir panduan Anda akan nyaman memuat format file Project yang didukung apa pun dan mengekstrak kode mata uang tiga huruf seperti `USD`, `EUR`, atau `GBP`.

## Jawaban Cepat
- **Apa yang dilakukan API?** Ia membaca file MS Project dan menampilkan properti seperti kode mata uang.  
- **Bahasa apa yang digunakan?** Java, melalui pustaka Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengambil kode dalam satu baris?** Ya—`prj.get(Prj.CURRENCY_CODE)` mengembalikan string kode mata uang secara instan.  
- **Apakah kompatibel dengan semua versi Project?** Aspose.Tasks mendukung lebih dari 20 format input, termasuk MPP lama, XML, dan file XER.

## Apa itu file MS Project yang dibaca?
Membaca file MS Project berarti secara programatik membuka sebuah *.mpp* (atau format lain yang didukung seperti XML atau XER) dan mengakses struktur data internalnya. Struktur tersebut mencakup tugas, sumber daya, kalender, tabel biaya, dan pengaturan keuangan. Dengan mem-parsing file, Anda dapat mengekstrak informasi tanpa meluncurkan Microsoft Project, memungkinkan alur kerja pelaporan otomatis, migrasi, dan integrasi.

## Mengapa menggunakan Aspose.Tasks untuk membaca file msproject?
Aspose.Tasks menawarkan solusi murni‑Java yang menghilangkan kebutuhan akan interop COM atau instalasi Microsoft Project lokal. Ia mendukung lebih dari 20 format file, dapat menangani proyek dengan ribuan tugas sambil menggunakan kurang dari 100 MB memori, dan menyediakan model objek yang kaya. Akses langsung ke konstanta seperti `Prj.CURRENCY_CODE` memungkinkan Anda mengambil informasi mata uang secara instan dan dapat diandalkan.

## Prasyarat
Sebelum kita menyelam ke kode, pastikan Anda memiliki hal berikut:

### Kit Pengembangan Java (JDK) terpasang
JDK terbaru (11 atau lebih) diperlukan. Unduh dari situs resmi Oracle: [di sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Pustaka Aspose.Tasks untuk Java
Dapatkan binari Aspose.Tasks untuk Java terbaru dan tambahkan ke classpath proyek Anda. Dokumentasi lengkap dan tautan unduhan tersedia [di sini](https://reference.aspose.com/tasks/java/).

## Mengimpor paket
Kelas `Project` dan konstanta `Prj` berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file sumber Java Anda:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Panduan langkah demi langkah

### Langkah 1: siapkan direktori data
Tentukan folder yang berisi file *.mpp* Anda. Sesuaikan path agar cocok dengan lingkungan Anda sehingga runtime dapat menemukan file proyek.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: muat file proyek
Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file MS Project dalam memori. Membuat sebuah instance membaca file dan membangun model dalam memori yang dapat Anda query.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Langkah 3: ambil kode mata uang
Konstanta `Prj.CURRENCY_CODE` mengidentifikasi properti yang menyimpan pengenal mata uang ISO. Memanggil `prj.get(Prj.CURRENCY_CODE)` mengembalikan kode tiga huruf dalam satu operasi.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Outputnya akan berupa kode mata uang ISO tiga huruf (mis., `USD`, `EUR`, `GBP`) yang dikonfigurasi untuk digunakan oleh proyek.

### Langkah 4: cara mengambil kode mata uang di Java (konteks tambahan)
Muat proyek Anda, panggil `prj.get(Prj.CURRENCY_CODE)`, dan simpan hasilnya dalam sebuah `String`. Anda kemudian dapat mengirim nilai ini ke layanan keuangan apa pun, mesin pelaporan, atau komponen UI yang memerlukan pengenal mata uang.

### Langkah 5: (opsional) gunakan kode mata uang
Skenario hilir tipikal meliputi:

- **Pembuatan laporan** – tambahkan kode di depan kolom biaya (`USD 1,200`).  
- **Integrasi API** – kirim kode ISO ke gateway pembayaran yang memerlukan parameter mata uang.  
- **Konsolidasi data** – kelompokkan beberapa proyek berdasarkan mata uang untuk analisis tingkat portofolio.

## Masalah umum dan solusi
| Issue | Reason | Fix |
|-------|--------|-----|
| **Output null** | File proyek tidak mendefinisikan mata uang (default kosong). | Atur mata uang di Microsoft Project atau tetapkan melalui `prj.set(Prj.CURRENCY_CODE, "USD");` sebelum membaca. |
| **File tidak ditemukan** | Path `dataDir` tidak tepat. | Verifikasi path dan pastikan nama file cocok persis, termasuk sensitivitas huruf. |
| **Versi file tidak didukung** | File *.mpp* sangat lama atau rusak. | Upgrade ke versi Aspose.Tasks terbaru atau konversi file ke format yang lebih baru di Microsoft Project terlebih dahulu. |

## Pertanyaan yang sering diajukan

**Q: Bisakah Aspose.Tasks menangani struktur proyek yang kompleks?**  
A: Ya, API membaca hierarki tugas multi‑level, kumpulan sumber daya, bidang khusus, dan kalender tanpa batasan.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file MS Project?**  
A: Tentu saja. Ia mendukung MPP, XML, XER, dan format lain dari Project 98 hingga rilis Office terbaru.

**Q: Apakah Aspose.Tasks menyediakan dokumentasi dan dukungan?**  
A: Referensi API yang komprehensif, contoh kode, dan dukungan teknis khusus tersedia di situs web Aspose.

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
A: Versi percobaan gratis ditawarkan sehingga Anda dapat mengevaluasi semua fitur, termasuk ekstraksi kode mata uang.

**Q: Di mana saya dapat memperoleh lisensi sementara untuk evaluasi?**  
A: Lisensi sementara tersedia di [situs web](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-09-25  
**Diuji dengan:** Aspose.Tasks for Java (latest version)  
**Penulis:** Aspose

## Tutorial Terkait

- [Properti Proyek Java – Baca Metadata dengan Aspose.Tasks](/tasks/java/project-properties/)
- [Cara Membaca Informasi Proyek dari Microsoft Project dengan Aspose.Tasks untuk Java](/tasks/java/project-properties/read-project-info/)
- [Mengambil Kode Outline MS Project di Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}