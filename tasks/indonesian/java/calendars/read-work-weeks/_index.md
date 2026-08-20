---
date: 2026-08-13
description: Pelajari cara membaca minggu kerja dari kalender MS Project menggunakan
  Aspose.Tasks untuk Java. Ikuti panduan langkah demi langkah dengan contoh kode dan
  tips pemecahan masalah.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Baca Minggu Kerja dari Kalender dengan Aspose.Tasks
og_description: Cara membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks
  untuk Java. Ikuti tutorial singkat dengan langkah pemasangan, potongan kode, dan
  tips pemecahan masalah.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Cara membaca minggu kerja dari kalender MS dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Cara membaca minggu kerja dari kalender MS dengan Aspose.Tasks
url: /id/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Workweeks dari Kalender MS dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan **belajar cara membaca workweeks** dari kalender Microsoft Project menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda sedang membangun dasbor pelaporan, menyinkronkan jadwal dengan sistem ERP, atau mengotomatisasi ekstraksi data untuk analitik, akses programatik ke definisi work‑week menghemat banyak jam kerja manual. Aspose.Tasks mendukung **lebih dari 50 format input dan output** dan dapat memproses file proyek berisi ratusan halaman tanpa memuat seluruh file ke memori, memberikan fleksibilitas dan kinerja.

## Jawaban Cepat
- **Apa arti “read workweeks”?** Ini merujuk pada mengekstrak definisi work‑week (tanggal dan aturan jam kerja harian) dari file Project melalui kode Java.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java (tersedia trial gratis).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Trial dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk penerapan produksi.  
- **Format file apa yang didukung?** Baik file *.mpp* maupun Project XML didukung, serta lebih dari 50 format lain untuk impor/ekspor.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit setelah pustaka diatur.

## Apa itu work week di MS Project?
Work week mendefinisikan aturan kalender yang menentukan kapan sumber daya tersedia selama periode tertentu. Ini mencakup tanggal mulai, tanggal berakhir, dan interval jam kerja harian (misalnya, 9 am–5 pm). Di MS Project, setiap kalender dapat berisi beberapa work week, memungkinkan Anda memodelkan hari libur, pola shift, atau jadwal musiman.

## Bagaimana Aspose.Tasks membaca work weeks dari kalender?
Aspose.Tasks mengekspos `WorkWeekCollection` dari objek `Calendar`. Dengan membuat instance `Project`, memilih kalender yang diinginkan (berdasarkan UID atau nama), dan mengiterasi `WorkWeekCollection`‑nya, Anda dapat mengambil label setiap work‑week, rentang tanggal efektif, serta slot jam kerja harian yang terperinci. API menangani semua konversi tanggal‑waktu dan secara otomatis menghormati pengaturan zona waktu proyek.

## Mengapa membaca workweeks Java dari kalender Microsoft Project?
Membaca work weeks secara programatik menghilangkan penyalinan manual, memastikan bahwa sistem hilir (ERP, HR, pelaporan) menggunakan aturan penjadwalan yang sama persis, serta menjamin konsistensi di seluruh proyek. Otomatisasi juga mengurangi kesalahan manusia dan mempercepat alur integrasi, terutama ketika Anda perlu memproses puluhan file proyek setiap malam.

## Prasyarat
Sebelum masuk ke kode, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru terpasang.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari situs resmi: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. File **Project contoh** (`ReadWorkWeeksInformation.mpp`) ditempatkan di folder yang diketahui pada mesin Anda.

## Impor paket
Pertama, impor kelas‑kelas yang diperlukan untuk berinteraksi dengan kalender dan work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Langkah 1: siapkan direktori data Anda
Tentukan folder yang berisi file `.mpp`. Ganti placeholder dengan jalur aktual pada mesin Anda:

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: buat instance Project dan akses kalender
Kelas `Project` mewakili file Microsoft Project dan menyediakan akses ke struktur datanya, termasuk kalender, tugas, dan sumber daya.  
Instansiasi objek `Project`, pilih kalender yang Anda inginkan (berdasarkan UID), dan peroleh `WorkWeekCollection`‑nya:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Tip Pro:** Jika Anda tidak yakin tentang UID kalender, iterasi melalui `project.getCalendars()` dan cetak nama serta UID setiap kalender terlebih dahulu.

## Langkah 3: iterasi melalui work weeks
Kelas `WorkWeek` mengenkapsulasi definisi work‑week, berisi tanggal mulai/berakhir dan pengaturan jam kerja harian.  
Loop melalui setiap `WorkWeek` untuk menampilkan nama, tanggal mulai/berakhir, dan jam kerja harian:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Apa yang akan Anda lihat:** Konsol mencetak label setiap work‑week (misalnya, “Standard”), rentang tanggal efektifnya, dan Anda dapat menelusuri jam kerja tepat untuk setiap hari.

## Masalah umum dan solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `NullPointerException` saat mengakses `calendar` | UID salah atau kalender tidak ada | Verifikasi UID dengan `project.getCalendars().size()` dan daftar kalender yang tersedia terlebih dahulu. |
| Tidak ada output untuk work weeks | Kalender yang dipilih tidak memiliki work weeks khusus (menggunakan default) | Gunakan kalender default (`project.getDefaultCalendar()`) atau buat work week secara programatik. |
| Format tanggal terlihat aneh | `System.out.println` menggunakan format default `java.util.Date` | Terapkan `SimpleDateFormat` untuk memformat tanggal sesuai kebutuhan. |

## Pertanyaan yang Sering Diajukan
**T: Bisakah saya memodifikasi informasi work weeks menggunakan Aspose.Tasks untuk Java?**  
J: Ya. API menyediakan `addWorkWeek()`, `removeWorkWeek()`, dan setter properti untuk mengubah nama, tanggal, dan jam kerja.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
J: Tentu saja. Ia mendukung file MPP dari Project 98 hingga rilis terbaru, serta file Project XML.

**T: Bisakah saya mengintegrasikan Aspose.Tasks dengan kerangka kerja Java lain?**  
J: Ya. Pustaka ini murni Java, sehingga dapat digunakan bersama Spring, Jakarta EE, atau kerangka kerja lainnya.

**T: Apakah ada versi trial yang tersedia untuk Aspose.Tasks?**  
J: Ya, Anda dapat mengunduh trial gratis 30 hari dari situs resmi: [Aspose.Tasks trial](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?**  
J: Forum komunitas Aspose adalah tempat terbaik: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-08-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/calendars/create/)
- [Ambil Pengecualian Kalender dengan Aspose.Tasks – tutorial java asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Cara Mengatur Kalender dan Menentukan Hari Kerja di MS Project dengan Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}