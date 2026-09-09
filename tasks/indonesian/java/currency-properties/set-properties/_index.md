---
date: 2026-09-09
description: Pelajari cara mengubah simbol mata uang dalam proyek Aspose.Tasks Java,
  mengatur kode mata uang, menyesuaikan simbol, dan menerapkan format khusus untuk
  file Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Atur Properti Mata Uang dalam Proyek Aspose.Tasks
og_description: Cara mengubah simbol mata uang dalam Aspose.Tasks menggunakan Java.
  Temukan panduan langkah demi langkah, prasyarat, dan tips untuk menyesuaikan format
  biaya proyek.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Cara mengubah simbol mata uang dalam Aspose.Tasks – panduan Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Cara mengubah simbol mata uang dalam proyek Aspose.Tasks – panduan Java
url: /id/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengubah simbol mata uang di Aspose.Tasks – Panduan Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengubah simbol mata uang** untuk file Microsoft Project menggunakan Aspose.Tasks Java API. Baik Anda menyiapkan laporan untuk klien luar negeri, mengkonsolidasikan anggaran di beberapa wilayah, atau sekadar perlu menyesuaikan standar akuntansi perusahaan Anda, mengatur simbol mata uang memastikan setiap bidang yang terkait biaya menampilkan tanda moneter yang tepat. Panduan ini menjelaskan setiap langkah, mulai dari menyiapkan lingkungan pengembangan hingga menyimpan perubahan dalam file proyek baru atau yang sudah ada.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java.  
- **Apakah saya dapat mengubah simbol mata uang?** Ya – set `Prj.CURRENCY_SYMBOL` dan pilih `CurrencySymbolPositionType`.  
- **Format file apa yang didukung?** XML, MPP, dan banyak lainnya melalui `SaveFileFormat`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk pengaturan dasar.

## Cara mengubah simbol mata uang di Aspose.Tasks menggunakan Java?
Muat proyek target (atau buat yang baru), atur properti mata uang yang diinginkan, dan simpan file. Seluruh operasi terdiri dari tiga panggilan API: membuat atau memuat objek `Project`, menetapkan kode mata uang, simbol, dan posisi, lalu memanggil `project.save`. Pendekatan ini bekerja untuk proyek baru maupun file yang sudah ada tanpa memerlukan Microsoft Project terinstal.

## Mengapa menggunakan Aspose.Tasks untuk mengubah mata uang?
Aspose.Tasks menyediakan **cakupan API penuh untuk lebih dari 30 properti terkait mata uang**, memungkinkan Anda mendefinisikan kode, simbol, digit desimal, dan posisi dalam satu tempat. Perpustakaan ini memproses file Project berukuran ratusan halaman dalam kurang dari satu detik pada perangkat keras server tipikal, dan berfungsi di Windows, Linux, serta macOS tanpa ketergantungan tambahan.

## Prasyarat
1. **Java Development Kit (JDK) 8 atau lebih tinggi** – API memerlukan setidaknya JDK 8.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau editor apa pun yang mendukung Java.  
4. **Folder yang dapat ditulisi** – tempat file proyek yang dihasilkan akan disimpan.

## Mengimpor paket
Kelas-kelas berikut memberi Anda akses ke properti proyek, penanganan file, dan pengaturan mata uang.  

`Project` – mewakili file Microsoft Project dalam memori.  
`Prj` – berisi konstanta untuk semua properti tingkat proyek, termasuk bidang mata uang.  
`CurrencySymbolPositionType` – mengenumerasi posisi kemungkinan untuk simbol mata uang (sebelum atau sesudah jumlah).  

Impor ini diperlukan sebelum kode apa pun dapat memanipulasi proyek.

## Panduan langkah‑demi‑langkah

### Langkah 1: Tentukan direktori data
Pilih folder yang menyimpan file sumber Anda dan tempat output akan ditulis. Pastikan direktori tersebut ada dan proses Java Anda memiliki izin menulis.

### Langkah 2: Buat instance proyek baru
Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Project dalam memori. Menginstansiasinya membuat proyek kosong yang siap dikonfigurasi.

### Langkah 3: Atur properti mata uang
Di sini Anda mengatur kode mata uang, jumlah digit desimal, simbol itu sendiri, dan posisi simbol.  

- **Kode mata uang** – kode tiga huruf ISO 4217 seperti `AUD` atau `USD`.  
- **Digit desimal** – biasanya 2 untuk kebanyakan mata uang.  
- **Simbol mata uang** – karakter atau string yang ditampilkan bersama jumlah, misalnya `$` atau `€`.  
- **Posisi simbol** – `CurrencySymbolPositionType.Before` menempatkan simbol sebelum angka; `After` menempatkannya setelah.  

Pengaturan ini memengaruhi setiap bidang yang terkait biaya (tarif sumber daya, anggaran tugas, dll.) dalam proyek.

> **Tip profesional:** Jika Anda perlu mengubah mata uang untuk file yang sudah ada, muat dengan `new Project("file.mpp")` sebelum menerapkan pengaturan di atas.

### Langkah 4: Simpan proyek yang diperbarui
Tuliskan proyek kembali ke disk menggunakan format yang diinginkan. Format XML dapat dibaca manusia, sementara `SaveFileFormat.MPP` mempertahankan kompatibilitas penuh dengan Microsoft Project.

### Langkah 5: Konfirmasi keberhasilan
Cetak pesan singkat atau entri log sehingga Anda tahu operasi selesai tanpa error. Ini sangat berguna dalam pipeline otomatis.

## Masalah umum & solusi
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **`NullPointerException` pada `project.save`** | `dataDir` bukan path yang valid atau tidak memiliki izin menulis. | Pastikan direktori ada dan proses Java Anda memiliki akses menulis. |
| **Simbol mata uang tidak muncul** | Posisi simbol diatur tidak tepat untuk locale Anda. | Gunakan `CurrencySymbolPositionType.Before` jika simbol harus berada sebelum jumlah. |
| **File proyek tidak dapat dibuka di MS Project** | Menyimpan dalam format lama dengan pengaturan yang tidak kompatibel. | Simpan menggunakan `SaveFileFormat.MPP` untuk kompatibilitas penuh dengan versi MS Project terbaru. |

## Pertanyaan yang sering diajukan

**T: Apakah saya dapat menetapkan beberapa mata uang dalam satu proyek menggunakan Aspose.Tasks?**  
J: Ya, Anda dapat menetapkan pengaturan mata uang yang berbeda untuk masing-masing sumber daya atau tugas dengan memodifikasi bidang biaya masing-masing setelah mata uang tingkat proyek ditetapkan.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
J: Tentu saja. Perpustakaan ini mendukung file MPP dari Project 2000 hingga rilis terbaru, serta XML dan format pertukaran lainnya.

**T: Apakah Aspose.Tasks menyediakan dukungan untuk format mata uang khusus?**  
J: Ya, Anda dapat mendefinisikan simbol khusus, digit desimal, dan posisi untuk memenuhi kebutuhan regional apa pun, dan pengaturan ini disimpan dalam file yang disimpan.

**T: Apakah saya dapat mengintegrasikan Aspose.Tasks dengan kerangka kerja Java lainnya?**  
J: Tentu. API ini murni Java, sehingga bekerja mulus dengan Spring, Hibernate, Maven, Gradle, dan ekosistem lainnya.

**T: Di mana saya dapat menemukan bantuan atau contoh tambahan?**  
J: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas, atau lihat dokumentasi resmi untuk referensi API yang detail.

## Kesimpulan
Anda kini tahu **cara mengubah simbol mata uang** dalam proyek Aspose.Tasks menggunakan Java, cara mengatur kode mata uang, menyesuaikan digit desimal, dan menerapkan simbol khusus. Kemampuan ini memungkinkan Anda menghasilkan laporan biaya yang spesifik locale, menyelaraskan anggaran proyek dengan standar akuntansi regional, dan menjaga konsistensi file Microsoft Project di seluruh tim global.

---

**Terakhir Diperbarui:** 2026-09-09  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Tutorial Terkait

- [properti proyek java – Ekstrak simbol mata uang dari MPP menggunakan Aspose.Tasks untuk Java](/tasks/java/currency/currency-symbols/)
- [Baca Properti Mata Uang Java dengan Proyek Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Kelola Kode Mata Uang Java dengan Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}