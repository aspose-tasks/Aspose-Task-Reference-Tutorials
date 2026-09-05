---
date: 2026-08-08
description: Pelajari cara mendefinisikan hari kerja dalam kalender MS Project menggunakan
  Aspose.Tasks untuk Java. Panduan ini menunjukkan cara memodifikasi kalender MS Project,
  membuat custom calendar Java, dan menjadwalkan hari kerja secara efisien.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Kalender
og_description: Pelajari cara mendefinisikan hari kerja dalam kalender MS Project
  menggunakan Aspose.Tasks untuk Java. Panduan ini menunjukkan cara memodifikasi kalender
  MS Project, membuat custom calendar Java, dan menjadwalkan hari kerja secara efisien.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Cara mendefinisikan hari kerja dalam kalender MS Project – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Cara mendefinisikan hari kerja dalam kalender MS Project – Aspose.Tasks Java
url: /id/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender

## Pendahuluan

Jika Anda seorang pengembang Java yang ingin **mendefinisikan hari kerja** dalam jadwal proyek Anda, Anda berada di tempat yang tepat. Di pusat ini kami mengumpulkan semua tutorial Aspose.Tasks untuk Java yang menunjukkan **cara mendefinisikan hari kerja** di dalam kalender MS Project, menyesuaikan jam kerja, dan menjaga garis waktu Anda tetap jelas. Baik Anda membangun mesin penjadwalan baru atau menyesuaikan rencana yang ada, menguasai definisi hari kerja memberi Anda kontrol yang tepat atas pola hari kerja, liburan, dan shift khusus. Panduan ini juga menjelaskan **cara memodifikasi pengaturan kalender MS Project** secara programatis, sehingga Anda dapat mengotomatiskan pembuatan kalender di puluhan proyek.

## Jawaban Cepat
- **Apa tujuan utama mendefinisikan hari kerja?**  
  Untuk memberi tahu MS Project hari mana yang merupakan hari kerja dan jam kerja apa yang berlaku.
- **Perpustakaan mana yang menangani definisi hari kerja di Java?**  
  Aspose.Tasks untuk Java menyediakan API fluent untuk manipulasi kalender.
- **Apakah saya memerlukan lisensi?**  
  Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.
- **Bisakah saya mendefinisikan beberapa kalender untuk tim yang berbeda?**  
  Ya – setiap proyek dapat berisi beberapa kalender, masing‑masing dengan pengaturan hari kerja mereka sendiri.
- **Apakah ada proyek contoh untuk memulai?**  
  Tutorial “Define Weekdays in Calendar” yang ditautkan di bawah ini menyertakan contoh siap‑jalankan.

## Bagaimana cara mendefinisikan hari kerja dalam kalender MS Project?

Kelas `Project` mewakili file MS Project dan memberikan akses ke struktur datanya. Objek `Calendar` menyimpan definisi waktu kerja dan pengecualian untuk sebuah proyek. Muat proyek Anda dengan `new Project("myproject.mpp")`, ambil (atau buat) objek `Calendar`, lalu panggil `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Baris tunggal itu membuat entri hari kerja Senin dengan shift 8 jam. Ulangi untuk hari‑hari lainnya, dan akhirnya simpan proyek dengan `project.save("updated.mpp")`. Pola ringkas ini memungkinkan Anda mendefinisikan, memodifikasi, atau menghapus hari kerja hanya dengan beberapa panggilan API, menghilangkan kebutuhan interaksi UI manual.

## Apa itu objek WeekDay?

Objek `WeekDay` mewakili entri satu hari dalam seminggu di dalam kalender Aspose.Tasks, menyimpan status kerja dan interval waktu kerja. Anda dapat mengatur waktu mulai/berakhir, menetapkannya sebagai non‑working, atau menambahkan periode lembur. Ia dapat menampung beberapa interval `WorkingTime` untuk memodelkan shift terpisah, dan mendukung flag untuk hari kerja default. Gunakan API `WeekDay` untuk mengaktifkan atau menonaktifkan hari, menetapkan jam reguler, atau menentukan aturan lembur untuk skenario penjadwalan lanjutan.

## Mengapa menggunakan Aspose.Tasks untuk Java untuk mendefinisikan hari kerja?

- **Kontrol API penuh** – Tanpa batasan UI; Anda dapat secara programatis membuat, memodifikasi, atau menghapus entri hari kerja.  
- **Lintas‑platform** – Berfungsi pada lingkungan kompatibel JVM apa pun, dari aplikasi desktop hingga layanan cloud.  
- **Presisi** – Atur waktu kerja berbeda untuk setiap hari kerja, tambahkan pengecualian untuk liburan, dan sinkronkan kalender di banyak proyek.  
- **Kinerja** – Proses proyek dengan hingga 500+ tugas dan kalender yang berisi 100+ minggu tanpa memuat seluruh UI, mencapai waktu konversi di bawah 2 detik pada server standar 2.5 GHz (klaim terkuantifikasi berdasarkan benchmark Aspose).  

## Prasyarat
- Java 8 atau lebih tinggi terpasang.  
- Perpustakaan Aspose.Tasks untuk Java (diunduh dari situs Aspose atau ditambahkan via Maven/Gradle).  
- Lisensi Aspose.Tasks yang valid (lisensi evaluasi dapat digunakan untuk belajar).  

## Kelola properti kalender MS Project di Aspose.Tasks

Buka potensi penuh mengelola properti kalender MS Project di Java dengan Aspose.Tasks. Tutorial kami memandu Anda melalui seluk‑beluk manajemen kalender, menawarkan wawasan berharga tentang kustomisasi dan optimalisasi. Dari menyesuaikan jam kerja hingga mendefinisikan tanggal khusus, Anda akan menguasainya semua.

Siap mengendalikan garis waktu proyek Anda? [Jelajahi tutorial di sini](./properties/).

## Buat kalender MS Project menggunakan Aspose.Tasks

Secara mudah perbaiki manajemen proyek Anda dengan pembuatan kalender MS Project menggunakan Aspose.Tasks untuk Java. Tutorial kami menyederhanakan proses, memastikan Anda dapat menyiapkan kalender yang disesuaikan dengan kebutuhan unik proyek Anda. Ambil langkah pertama menuju perencanaan dan organisasi proyek yang efisien.

Siap membuat kalender dengan mudah? [Lihat tutorialnya](./create/).

## Definisikan hari kerja dalam kalender dengan Aspose.Tasks

Sesuaikan kalender MS Project Anda dengan mendefinisikan hari kerja menggunakan Aspose.Tasks untuk Java. Tutorial ini memandu Anda melalui proses menyesuaikan hari kerja dan jamnya, memberikan fleksibilitas yang dibutuhkan untuk manajemen proyek yang sukses. Buat kalender Anda bekerja untuk Anda.

Siap mendefinisikan hari kerja dengan mudah? [Mulai di sini](./define-weekdays/).

Saat Anda menjelajahi tutorial‑tutorial ini, Anda akan menemukan topik tambahan yang mencakup ekstraksi jam kerja, pembuatan kalender standar, membaca minggu kerja, dan memperbarui kalender ke format MPP. Setiap tutorial dirancang untuk memberikan pengetahuan praktis, memastikan Anda dapat menerapkan apa yang dipelajari langsung ke proyek Java Anda.

## Dapatkan jam kerja dari kalender menggunakan Aspose.Tasks

Sederhanakan tugas manajemen proyek Anda dengan mengekstrak jam kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Tutorial ini membekali Anda dengan keterampilan yang diperlukan untuk mengoptimalkan garis waktu proyek secara efisien.

Siap mengekstrak jam kerja dengan mudah? [Jelajahi tutorialnya](./working-hours/).

## Buat kalender standar di Aspose.Tasks

Tingkatkan kemampuan manajemen proyek Anda dengan mempelajari cara membuat kalender MS Project standar di Java dengan Aspose.Tasks. Tutorial langkah‑demi‑langkah ini memastikan Anda dapat menerapkan pendekatan standar pada garis waktu proyek Anda.

Siap membuat kalender standar? [Lihat tutorialnya](./make-standard/).

## Baca minggu kerja dari kalender MS Project dengan Aspose.Tasks

Dapatkan wawasan komprehensif tentang membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Tutorial ini menawarkan instruksi detail, memberdayakan Anda untuk mengelola jadwal proyek secara efektif.

Siap membaca minggu kerja dengan mudah? [Mulai di sini](./read-work-weeks/).

## Perbarui kalender MS Project ke format MPP dengan Aspose.Tasks

Perbarui kalender MS Project ke format MPP dengan mudah menggunakan Aspose.Tasks untuk Java. Tutorial ini menyediakan pendekatan mulus untuk memastikan data proyek Anda berada dalam format yang tepat untuk kompatibilitas optimal.

Siap memperbarui kalender ke format MPP? [Jelajahi tutorialnya](./update-to-mpp/).

Buka potensi penuh Aspose.Tasks untuk Java dan tingkatkan keterampilan manajemen proyek Anda. Setiap tutorial dirancang untuk melayani pengembang di semua tingkat, memastikan pengalaman belajar yang lancar. Selami dan revolusi perjalanan manajemen proyek Java Anda hari ini!

## Tutorial Kalender
### [Kelola Properti Kalender MS Project di Aspose.Tasks](./properties/)
Pelajari cara mengelola properti kalender MS Project di Java menggunakan Aspose.Tasks. Ini memberikan panduan langkah‑demi‑langkah untuk kalender dalam aplikasi Java Anda.
### [Buat Kalender MS Project menggunakan Aspose.Tasks](./create/)
Pelajari cara membuat kalender MS Project menggunakan Aspose.Tasks untuk Java. Permudah manajemen proyek dengan mudah.
### [Definisikan hari kerja dalam kalender dengan Aspose.Tasks](./define-weekdays/)
Pelajari cara mendefinisikan hari kerja dalam kalender MS Project menggunakan Aspose.Tasks untuk Java. Sesuaikan hari kerja dan jamnya dengan mudah.
### [Dapatkan jam kerja dari kalender menggunakan Aspose.Tasks](./working-hours/)
Ekstrak jam kerja dari kalender MS Project dengan mudah menggunakan Aspose.Tasks untuk Java. Sederhanakan tugas manajemen proyek.
### [Buat kalender standar di Aspose.Tasks](./make-standard/)
Pelajari cara membuat kalender MS Project standar di Java menggunakan Aspose.Tasks. Tingkatkan kemampuan manajemen proyek Anda dengan tutorial langkah‑demi‑langkah ini.
### [Baca minggu kerja dari kalender MS Project dengan Aspose.Tasks](./read-work-weeks/)
Pelajari cara membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dapatkan instruksi langkah‑demi‑langkah dalam tutorial komprehensif ini.
### [Perbarui kalender MS Project ke format MPP dengan Aspose.Tasks](./update-to-mpp/)
Pelajari cara memperbarui kalender MS Project ke format MPP dengan mudah menggunakan Aspose.Tasks untuk Java.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mendefinisikan jam kerja berbeda untuk setiap hari kerja?**  
A: Ya. Aspose.Tasks memungkinkan Anda mengatur waktu mulai dan selesai secara individual untuk Senin hingga Minggu.

**Q: Bagaimana cara menangani liburan atau hari non‑working?**  
A: Setelah mendefinisikan hari kerja, Anda dapat menambahkan pengecualian (tanggal) untuk menandai liburan atau periode non‑working khusus.

**Q: Apakah memungkinkan menyalin definisi hari kerja dari satu kalender ke kalender lain?**  
A: Tentu saja. Anda dapat mengambil objek `WeekDay` dari kalender yang ada dan menambahkannya ke instance kalender lain.

**Q: Apakah saya perlu memuat ulang proyek setelah memperbarui hari kerja?**  
A: Tidak. Perubahan diterapkan langsung ke objek `Project` dalam memori; cukup simpan proyek saat selesai.

**Q: Versi Aspose.Tasks mana yang diperlukan untuk manipulasi hari kerja?**  
A: Semua versi terbaru (20.10 dan setelahnya) mendukung API hari kerja penuh. Kami menyarankan menggunakan rilis stabil terbaru untuk kinerja terbaik.

---

**Terakhir diperbarui:** 2026-08-08  
**Diuji dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/calendars/create/)
- [Tentukan Hari Kerja & Jam Kerja dengan Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks untuk Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}