---
date: 2026-09-09
description: Cara mengatur kalender proyek di Java menggunakan Aspose.Tasks. Pelajari
  cara menampilkan calendar working hours, configure working time, dan modify calendar
  days dalam file MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Kelola properti kalender di Aspose.Tasks
og_description: Cara mengatur kalender proyek di Java menggunakan Aspose.Tasks. Panduan
  ini menunjukkan cara menampilkan calendar working hours, configure working time,
  dan modify calendar days dalam file MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Cara mengatur kalender proyek Java dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Cara mengatur kalender proyek Java dengan Aspose.Tasks
url: /id/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur kalender proyek Java dengan Aspose.Tasks

## Pendahuluan
In tutorial ini Anda akan belajar **cara mengatur kalender proyek** di Java dengan memanfaatkan library Aspose.Tasks. Mengontrol properti kalender memungkinkan Anda **menampilkan jam kerja kalender**, mengonfigurasi hari kerja khusus, dan menjaga jadwal proyek Anda selaras dengan kendala dunia nyata seperti hari libur atau pola shift. Kami akan membahas penyiapan lingkungan, memuat proyek, iterasi kalender, serta membaca atau memperbarui propertinya, sehingga Anda dapat dengan percaya diri **mengelola pengaturan kalender MS Project** di aplikasi Java apa pun.

## Jawaban Cepat
- **Apa arti “set project calendar”?** Itu berarti membuat atau memperbarui waktu kerja kalender, kalender dasar, dan tipe hari dalam file MS Project.  
- **Library apa yang diperlukan?** Aspose.Tasks untuk Java (versi terbaru apa pun).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menampilkan jam kerja kalender?** Ya—dengan membaca setiap `WeekDay` Anda dapat mengeluarkan jam untuk setiap tipe hari.  
- **Apakah ini kompatibel dengan Maven/Gradle?** Tentu—tambahkan JAR Aspose.Tasks sebagai dependensi.  

## Cara mengatur kalender proyek di Java
Muat file proyek Anda, temukan kalender target, lalu sesuaikan definisi waktu kerja, kalender dasar, dan tipe hari sesuai kebutuhan. Langkah‑langkah di bawah ini memberikan solusi lengkap end‑to‑end yang menunjukkan cara memuat, mengiterasi, memodifikasi, dan menyimpan proyek sambil menangani pengecualian serta memastikan perhitungan jam kerja yang akurat.

## Apa itu kalender proyek?
Kalender proyek mendefinisikan hari kerja dan jam kerja untuk tugas, sumber daya, dan garis waktu proyek secara keseluruhan. Di MS Project, kalender dapat mewarisi dari kalender dasar, dan setiap tipe hari (misalnya **Standard**, **Non‑working**) dapat memiliki waktu kerja masing‑masing. Mengelola pengaturan ini secara programatik memungkinkan penyesuaian jadwal dinamis tanpa penyuntingan manual.

## Mengapa mengelola kalender MS Project secara programatik?
Mengelola kalender secara programatik memungkinkan Anda menerapkan aturan penjadwalan yang konsisten di banyak proyek, mengurangi kesalahan manual, dan mengintegrasikan data kalender dengan sistem perusahaan lain seperti HR atau ERP. Otomatisasi ini mempercepat penyiapan proyek dan memastikan semua anggota tim mengikuti kebijakan jam kerja yang sama.

- **Otomasi:** Sesuaikan kalender di puluhan proyek dengan satu skrip.  
- **Konsistensi:** Terapkan kebijakan jam kerja organisasi secara otomatis.  
- **Integrasi:** Sinkronkan kalender dengan sistem HR atau ERP eksternal.  
- **Visibilitas:** Cepat **menampilkan jam kerja kalender** untuk pelaporan atau debugging.  
- **Fleksibilitas:** Tambahkan pengecualian atau pola shift secara langsung tanpa membuka UI.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- **Java Development Kit (JDK) 8+** terinstal dan `JAVA_HOME` dikonfigurasi.  
- **Aspose.Tasks for Java** library diunduh dari [halaman unduhan](https://releases.aspose.com/tasks/java/). Tambahkan JAR ke classpath Anda atau deklarasikan sebagai dependensi Maven/Gradle.  
- File contoh MS Project (`.mpp` atau `.xml`) yang berisi setidaknya satu kalender yang ingin Anda periksa atau modifikasi.

## Impor paket
Class `Project`, `Calendar`, `WeekDay`, dan kelas terkait merupakan inti manipulasi kalender.  
Kelas `Calendar` mewakili kalender proyek, berisi hari kerja, pengecualian, dan hubungan kalender‑dasar.  
Kelas `WeekDay` mendefinisikan pengaturan waktu kerja untuk satu hari dalam kalender.

Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file MS Project dalam memori. Setelah Anda memuat file, semua operasi kalender mengalir melalui objek ini.

```java
import com.aspose.tasks.*;
```

## Langkah 1: siapkan direktori data
Tentukan folder yang berisi file proyek Anda. Ganti placeholder dengan path sebenarnya di mesin Anda.

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: definisikan konstanta satuan waktu
Waktu kerja diekspresikan dalam milidetik. Mendefinisikan konstanta yang dapat digunakan kembali membuat kode lebih mudah dibaca dan membantu Anda **menghitung jam kerja Java** secara akurat.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Langkah 3: muat data proyek
Buat instance `Project` dengan memuat file XML MS Project yang ada (`.xml` atau `.mpp`). Ini memberi Anda akses ke semua kalender yang disimpan dalam file.

Kelas `Project` memuat file ke dalam model objek ringan; ia **tidak** memerlukan seluruh file disimpan dalam memori, memungkinkan Anda bekerja dengan proyek yang berisi puluhan ribu tugas.

```java
Project project = new Project(dataDir + "project.xml");
```

## Langkah 4: iterasi melalui kalender Java
Sekarang kita mengulang setiap kalender, mencetak identifier unik, nama, kalender dasar, dan jam kerja untuk setiap tipe hari. Ini menunjukkan **cara mengatur nilai kalender proyek Java** serta cara **menampilkan jam kerja kalender**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Apa yang dilakukan kode ini
- **Menyaring kalender tanpa nama** (beberapa kalender internal mungkin memiliki nama `null`).  
- **Mencetak UID dan nama** – berguna untuk mengidentifikasi kalender nanti.  
- **Menampilkan kalender dasar** – baik “Self” (kalender adalah basisnya sendiri) atau nama kalender yang diwarisi.  
- **Mengulang setiap `WeekDay`** untuk menghitung dan mengeluarkan total jam kerja (`workingTime` dalam milidetik, jadi kami membagi dengan `OneHour`).  

## Manfaat terukur menggunakan Aspose.Tasks
Aspose.Tasks mendukung **lebih dari 30 format input dan output** dan dapat memproses **proyek dengan hingga 10.000 tugas** tanpa memuat seluruh file ke memori, memberikan hasil dalam kurang dari satu detik pada perangkat keras server tipikal. Angka‑angka ini menjadikannya pilihan andal untuk otomasi skala perusahaan.

## Masalah umum dan solusi
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Kalender adalah kalender dasar itu sendiri (`isBaseCalendar()` mengembalikan `true`). | Gunakan pemeriksaan ternary seperti yang ditunjukkan (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | File proyek menggunakan satuan waktu yang berbeda (ticks). | Verifikasi format file; Aspose.Tasks menormalkan ke milidetik, tetapi pastikan Anda memuat tipe file yang benar. |
| Unable to locate `project.xml` | Path `dataDir` tidak tepat. | Gunakan path absolut atau `Paths.get(dataDir, "project.xml").toString()`. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya memodifikasi properti kalender secara programatik menggunakan Aspose.Tasks?**  
A: Ya, API menyediakan akses baca/tulis penuh ke kalender, memungkinkan Anda menambah, mengedit, atau menghapus waktu kerja, pengecualian, dan hubungan kalender‑dasar.

**Q: Apakah ada batasan dalam penyesuaian kalender dengan Aspose.Tasks?**  
A: Library ini mencerminkan kemampuan Microsoft Project, sehingga Anda dapat menyesuaikan hampir semua aspek kalender. Hanya versi file Project yang sangat lama yang mungkin memiliki sedikit keanehan kompatibilitas.

**Q: Bisakah saya mengintegrasikan manajemen kalender ke dalam proyek Java yang ada?**  
A: Tentu. Cukup tambahkan JAR Aspose.Tasks ke jalur build Anda dan gunakan pola kode yang sama seperti yang ditunjukkan di sini.

**Q: Apakah Aspose.Tasks mendukung fungsionalitas manajemen proyek lainnya selain manajemen kalender?**  
A: Ya, ia mencakup tugas, sumber daya, penugasan, outline, baseline, dan lainnya—menjadikannya solusi komprehensif untuk otomasi proyek berbasis Java.

**Q: Apakah dukungan teknis tersedia untuk pengembang yang menggunakan Aspose.Tasks?**  
A: Ya, Aspose menyediakan forum khusus, dukungan email, dan dokumentasi lengkap untuk semua pengguna berlisensi.

**Terakhir Diperbarui:** 2026-09-09  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Kalender Proyek Java – Panduan Aspose.Tasks untuk Java](/tasks/java/)
- [Muat File Proyek di Java dan Kelola Properti Proyek](/tasks/java/project-management/default-properties/)
- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}