---
date: 2026-08-13
description: Pelajari cara membuat kalender standar MS Project di Java menggunakan
  Aspose.Tasks. Panduan langkah demi langkah ini menunjukkan cara membuat kalender
  standar MS Project, menambahkannya sebagai default, dan menyimpan file.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Buat Kalender Standar di Aspose.Tasks
og_description: Cara membuat kalender di Java dengan Aspose.Tasks. Pelajari cara membuat
  kalender standar MS Project, mengaturnya sebagai default, dan menyimpan file proyek
  dalam hitungan menit.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Cara membuat kalender – buat kalender standar di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Cara membuat kalender – buat kalender standar di Aspose.Tasks
url: /id/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat kalender – membuat kalender standar di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara membuat kalender** objek untuk file Microsoft Project dengan menggunakan pustaka Aspose.Tasks for Java. Kami akan menjelaskan cara membuat kalender standar MS Project, menjadikannya kalender default (standar), dan menyimpan file proyek. Pada akhir panduan Anda akan dapat mengintegrasikan pembuatan kalender ke dalam solusi manajemen proyek berbasis Java apa pun.

## Jawaban Cepat
- **Apa arti “kalender standar”?** Itu adalah definisi waktu kerja default yang diterapkan pada tugas yang tidak memiliki kalender khusus yang ditetapkan.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java – API pure‑Java yang berfungsi tanpa harus menginstal Microsoft Project.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk penerapan produksi.  
- **Format file apa yang dihasilkan?** File Microsoft Project berbasis XML (`.xml`).  
- **Berapa lama waktu implementasinya?** Sekitar 5‑10 menit untuk menyiapkan kalender dasar.

## Apa itu kalender standar di Microsoft Project?
Kalender standar mendefinisikan hari kerja dan jam kerja default untuk sebuah proyek, biasanya Senin hingga Jumat, pukul 8 pagi sampai 5 sore. Ketika Anda menambahkan kalender standar, setiap tugas yang tidak memiliki kalender khusus yang ditetapkan akan mewarisi waktu kerja ini, memastikan penjadwalan yang konsisten di seluruh proyek.

## Mengapa menggunakan Aspose.Tasks untuk membuat kalender?
Aspose.Tasks for Java mendukung **lebih dari 50 format input dan output** dan dapat memproses proyek dengan hingga **10.000 tugas** tanpa harus memuat seluruh file ke dalam memori. Pustaka pure‑Java ini memungkinkan Anda mengotomatisasi pembuatan file Project di server, pipeline CI, atau aplikasi Java apa pun, menghilangkan kebutuhan akan instalasi Microsoft Project berlisensi.

## Prasyarat
Sebelum memulai, pastikan hal‑hal berikut sudah tersedia:

### Instalasi Java Development Kit (JDK)
Instal JDK terbaru dari situs web Oracle atau distribusi OpenJDK.

### Pustaka Aspose.Tasks for Java
Unduh pustaka dari [halaman unduhan](https://releases.aspose.com/tasks/java/). Tambahkan JAR ke classpath proyek Anda.

## Impor paket
Kita hanya membutuhkan satu impor untuk tutorial ini:

```java
import com.aspose.tasks.*;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: siapkan direktori data
Tentukan lokasi dimana file proyek yang dihasilkan akan disimpan.

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan path absolut pada mesin Anda (misalnya, `C:/Projects/Output/`).

### Langkah 2: buat instance proyek
`Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Membuat instance‑nya memberi Anda wadah untuk kalender, tugas, sumber daya, dan data proyek lainnya.

```java
Project project = new Project();
```

### Langkah 3: definisikan dan jadikan kalender standar
`Calendar` adalah kelas yang memodelkan jadwal waktu kerja. Menambahkan kalender baru dengan nama **“My Cal”** dan memanggil `makeStandardCalendar` menjadikannya kalender default untuk seluruh proyek.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Tip pro:** Metode `makeStandardCalendar` secara otomatis menandai kalender yang diberikan sebagai default untuk proyek, yang persis apa yang Anda butuhkan ketika ingin **menambahkan fungsi kalender standar**.

### Langkah 4: simpan proyek
`SaveFileFormat` adalah enumerasi yang menentukan format file yang akan digunakan saat menyimpan proyek.  
Simpan proyek (termasuk kalender baru) ke file XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Anda dapat mengubah nama file atau format (`SaveFileFormat.Pp`) jika menginginkan versi Project yang berbeda.

### Langkah 5: tampilkan pesan selesai
Berikan petunjuk visual bahwa proses selesai tanpa error.

```java
System.out.println("Process completed Successfully");
```

## Masalah umum & solusi

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **File tidak ditemukan** | `dataDir` mengarah ke folder yang tidak ada | Buat folder tersebut atau gunakan path absolut |
| **Pengecualian lisensi** | Menjalankan tanpa lisensi Aspose.Tasks yang valid di produksi | Terapkan file lisensi via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Kalender kosong** | Lupa menambahkan definisi waktu kerja | Gunakan `cal1.getWeekDays().add(WeekDay.DayType.Monday)` dll., jika Anda memerlukan jam khusus |

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?**  
A: Ya, Aspose.Tasks mendukung berbagai versi Microsoft Project, mulai dari 2000 hingga rilis terbaru.

**Q: Bisakah saya menyesuaikan pengaturan kalender lebih lanjut?**  
A: Tentu saja! Anda dapat memodifikasi hari kerja, menambahkan pengecualian, dan mendefinisikan waktu kerja spesifik menggunakan kelas `WeekDay` dan `WorkingTime`.

**Q: Apakah Aspose.Tasks cocok untuk aplikasi tingkat perusahaan?**  
A: Tentu. Pustaka ini dirancang untuk lingkungan berperforma tinggi, skalabel, dan menawarkan dukungan komprehensif untuk file Project yang besar.

**Q: Apakah Aspose.Tasks menyediakan dukungan teknis untuk pengembang?**  
A: Ya, Aspose menyediakan forum khusus, dukungan berbasis tiket, dan dokumentasi lengkap untuk membantu Anda menyelesaikan masalah dengan cepat.

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
A: Ya, Anda dapat mencoba versi percobaan gratis yang tersedia di [situs web](https://purchase.aspose.com/buy), memungkinkan Anda mengevaluasi semua fitur sebelum berkomitmen.

---

**Terakhir Diperbarui:** 2026-08-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Cara Mengatur Kalender Proyek Java dengan Aspose.Tasks](/tasks/java/calendars/properties/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}