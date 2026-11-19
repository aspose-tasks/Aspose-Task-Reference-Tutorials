---
date: 2026-11-19
description: Pelajari cara membuat kalender khusus Java menggunakan Aspose.Tasks.
  Panduan ini menunjukkan cara mendefinisikan hari kerja, mengatur jam kerja, dan
  memodifikasi kalender MS Project secara programatis.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Kalender
og_description: Pelajari cara membuat kalender khusus Java dengan Aspose.Tasks. Kuasai
  mendefinisikan hari kerja, mengatur jam kerja, dan memodifikasi kalender MS Project
  secara efisien.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Cara membuat kalender khusus Java dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
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
title: Cara membuat kalender khusus Java dengan Aspose.Tasks
url: /id/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender

## Pendahuluan

Jika Anda seorang pengembang Java yang ingin **create custom calendar Java** solusi, Anda berada di tempat yang tepat. Pusat ini mengumpulkan semua tutorial Aspose.Tasks for Java yang menunjukkan cara **define working days MS Project**, **set working hours MS Project**, dan menyesuaikan pengaturan kalender secara programatik. Baik Anda membangun mesin penjadwalan baru atau memperluas rencana yang ada, menguasai API ini memberi Anda kontrol tepat atas pola hari kerja, liburan, dan shift khusus—tanpa pernah membuka UI MS Project.

## Jawaban Cepat
- **Apa tujuan utama mendefinisikan hari kerja?**  
  Untuk memberi tahu MS Project hari mana yang merupakan hari kerja dan jam kerja apa yang berlaku.  
- **Perpustakaan mana yang menangani definisi hari kerja di Java?**  
  Aspose.Tasks for Java menyediakan API yang fluens untuk manipulasi kalender.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mendefinisikan beberapa kalender untuk tim yang berbeda?**  
  Ya – setiap proyek dapat berisi beberapa kalender, masing‑masing dengan pengaturan hari kerja mereka sendiri.  
- **Apakah ada contoh proyek untuk memulai?**  
  Tutorial “Define Weekdays in Calendar” yang ditautkan di bawah ini menyertakan contoh yang siap dijalankan.

## Cara membuat kalender khusus Java?

Muat proyek, buat atau ambil kalender, tambahkan definisi hari kerja, dan simpan file—semua dalam beberapa panggilan API. Pendekatan ini menghilangkan langkah UI manual, memungkinkan Anda mengotomatisasi pembuatan kalender di puluhan proyek, dan memastikan pola hari kerja yang konsisten di seluruh organisasi Anda.

## Apa itu kelas Project?

Kelas `Project` adalah objek pusat untuk memuat, mengedit, dan menyimpan file MS Project. Ia menyimpan koleksi tugas, sumber daya, dan kalender, serta mengekspos metode yang memungkinkan Anda membaca dan memodifikasi setiap aspek proyek secara programatik. Dengan kelas ini, Anda dapat mengakses koleksi kalender proyek, menyesuaikan waktu kerja, dan menyimpan perubahan kembali ke file MPP atau XML.

## Bagaimana cara mendefinisikan hari kerja dalam kalender MS Project?

Kelas `Project` mewakili file MS Project dan memberikan akses ke struktur datanya. Objek `Calendar` menyimpan definisi waktu kerja dan pengecualian untuk sebuah proyek. Muat proyek Anda dengan `new Project("myproject.mpp")`, ambil (atau buat) objek `Calendar`, lalu panggil `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Baris tunggal itu membuat entri hari kerja Senin dengan shift 8 jam. Ulangi untuk hari lain, dan akhirnya simpan proyek dengan `project.save("updated.mpp")`. Pola ringkas ini memungkinkan Anda mendefinisikan, memodifikasi, atau menghapus hari kerja hanya dengan beberapa panggilan API, menghilangkan kebutuhan interaksi UI manual.

## Apa itu objek WeekDay?

Objek `WeekDay` mewakili satu entri hari dalam seminggu di dalam kalender. Ia menyimpan apakah hari tersebut bekerja, interval waktu kerja untuk hari itu, dan flag untuk perilaku default. Anda dapat melampirkan satu atau lebih interval `WorkingTime` untuk memodelkan shift terpisah, menetapkan hari sebagai non‑working, atau mewarisi default dari kalender induk.

## Cara mendefinisikan hari kerja MS Project?

Anda mendefinisikan hari kerja dengan menambahkan objek `WeekDay` ke koleksi `WeekDays` kalender. Setiap `WeekDay` menentukan apakah hari tersebut bekerja dan rentang waktu yang dianggap sebagai waktu kerja. Misalnya, untuk menjadikan Sabtu setengah hari, tambahkan `WeekDay` dengan satu `WorkingTime` dari 10:00 hingga 14:00. API secara otomatis memperbarui perhitungan jadwal proyek.

## Cara mengatur jam kerja MS Project?

Atur jam kerja dengan membuat satu atau lebih interval `WorkingTime` untuk setiap `WeekDay`. `WorkingTime` menerima nilai jam‑mulai, menit‑mulai, jam‑selesai, dan menit‑selesai. Anda dapat menetapkan beberapa interval ke satu hari untuk memodelkan shift terpisah (misalnya, 08:00‑12:00 dan 13:00‑17:00). Setelah mengonfigurasi semua hari kerja, panggil `project.save(...)` untuk menyimpan perubahan.

## Mengapa menggunakan Aspose.Tasks for Java untuk mendefinisikan hari kerja?

- **Kontrol API penuh** – Tanpa batasan UI; Anda dapat secara programatis membuat, memodifikasi, atau menghapus entri hari kerja.  
- **Cross‑platform** – Berfungsi di lingkungan yang kompatibel dengan JVM apa pun, mulai dari aplikasi desktop hingga layanan cloud.  
- **Presisi** – Atur waktu kerja yang berbeda untuk setiap hari kerja, tambahkan pengecualian untuk hari libur, dan sinkronkan kalender di banyak proyek.  
- **Kinerja** – Memproses proyek dengan lebih dari 500 tugas dan kalender yang berisi lebih dari 100 minggu tanpa memuat seluruh UI, mencapai waktu konversi di bawah 2 detik pada server standar 2,5 GHz (klaim terkuantifikasi berdasarkan benchmark Aspose).  
- **Dukungan format luas** – Aspose.Tasks mendukung lebih dari 30 API terkait kalender dan dapat mengimpor/mengekspor ke lebih dari 20 format file, memungkinkan integrasi mulus dengan alur data proyek yang ada.

## Prasyarat
- Java 8 atau lebih tinggi terpasang.  
- Perpustakaan Aspose.Tasks for Java (diunduh dari situs Aspose atau ditambahkan melalui Maven/Gradle).  
- Lisensi Aspose.Tasks yang valid (lisensi evaluasi dapat digunakan untuk belajar).  

## Kelola properti kalender MS Project di Aspose.Tasks

Buka potensi penuh mengelola properti kalender MS Project dalam Java dengan Aspose.Tasks. Tutorial kami membimbing Anda melalui seluk‑beluk manajemen kalender, menawarkan wawasan berharga tentang kustomisasi dan optimisasi. Dari menyesuaikan jam kerja hingga mendefinisikan tanggal khusus, Anda akan menguasainya semua.

Siap mengendalikan jadwal proyek Anda? [Jelajahi tutorial di sini](./properties/).

## Buat kalender MS Project menggunakan Aspose.Tasks

Dengan mudah menyederhanakan manajemen proyek Anda melalui pembuatan kalender MS Project menggunakan Aspose.Tasks for Java. Tutorial kami mempermudah proses, memastikan Anda dapat menyiapkan kalender yang disesuaikan dengan kebutuhan unik proyek Anda. Ambil langkah pertama menuju perencanaan dan organisasi proyek yang efisien.

Siap membuat kalender dengan mudah? [Lihat tutorialnya](./create/).

## Definisikan hari kerja dalam kalender dengan Aspose.Tasks

Sesuaikan kalender MS Project Anda dengan mendefinisikan hari kerja menggunakan Aspose.Tasks for Java. Tutorial ini memandu Anda melalui proses menyesuaikan hari kerja dan jam, memberi fleksibilitas yang diperlukan untuk manajemen proyek yang sukses. Buat kalender Anda bekerja untuk Anda.

Siap mendefinisikan hari kerja tanpa kesulitan? [Mulai di sini](./define-weekdays/).

Saat Anda menelusuri tutorial ini, Anda akan menemukan topik tambahan yang mencakup ekstraksi jam kerja, pembuatan kalender standar, membaca minggu kerja, dan memperbarui kalender ke format MPP. Setiap tutorial dirancang untuk memberi Anda pengetahuan praktis, memastikan Anda dapat menerapkan apa yang dipelajari langsung ke proyek Java Anda.

## Dapatkan jam kerja dari kalender menggunakan Aspose.Tasks

Permudah tugas manajemen proyek Anda dengan mengekstrak jam kerja dari kalender MS Project menggunakan Aspose.Tasks for Java. Tutorial ini membekali Anda dengan keterampilan yang diperlukan untuk mengoptimalkan jadwal proyek secara efisien.

Siap mengekstrak jam kerja tanpa kesulitan? [Jelajahi tutorial](./working-hours/).

## Buat kalender standar di Aspose.Tasks

Tingkatkan kemampuan manajemen proyek Anda dengan mempelajari cara membuat kalender standar MS Project dalam Java dengan Aspose.Tasks. Tutorial langkah‑demi‑langkah ini memastikan Anda dapat menerapkan pendekatan standar pada jadwal proyek Anda.

Siap membuat kalender standar? [Lihat tutorialnya](./make-standard/).

## Baca minggu kerja dari kalender MS Project dengan Aspose.Tasks

Dapatkan wawasan komprehensif tentang cara membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks for Java. Tutorial ini menawarkan instruksi terperinci, memberdayakan Anda untuk mengelola jadwal proyek secara efektif.

Siap membaca minggu kerja tanpa kesulitan? [Mulai di sini](./read-work-weeks/).

## Perbarui kalender MS Project ke format MPP dengan Aspose.Tasks

Perbarui kalender MS Project ke format MPP dengan mudah menggunakan Aspose.Tasks for Java. Tutorial ini menyediakan pendekatan mulus untuk memastikan data proyek Anda berada dalam format yang tepat untuk kompatibilitas optimal.

Siap memperbarui kalender ke format MPP? [Jelajahi tutorial](./update-to-mpp/).

Buka potensi penuh Aspose.Tasks for Java dan tingkatkan keterampilan manajemen proyek Anda. Setiap tutorial dirancang untuk melayani pengembang dari semua tingkat, memastikan pengalaman belajar yang lancar. Selami dan revolusionerkan perjalanan manajemen proyek Java Anda hari ini!

## Tutorial Kalender
### [Kelola Properti Kalender MS Project di Aspose.Tasks](./properties/)
Pelajari cara mengelola properti kalender MS Project dalam Java menggunakan Aspose.Tasks. Ini memberikan panduan langkah‑demi‑langkah untuk kalender dalam aplikasi Java Anda.
### [Buat Kalender MS Project menggunakan Aspose.Tasks](./create/)
Pelajari cara membuat kalender MS Project menggunakan Aspose.Tasks for Java. Sederhanakan manajemen proyek dengan mudah.
### [Definisikan hari kerja dalam kalender dengan Aspose.Tasks](./define-weekdays/)
Pelajari cara mendefinisikan hari kerja dalam kalender MS Project menggunakan Aspose.Tasks for Java. Sesuaikan hari kerja dan jam dengan mudah.
### [Dapatkan jam kerja dari kalender menggunakan Aspose.Tasks](./working-hours/)
Ekstrak jam kerja dari kalender MS Project dengan mudah menggunakan Aspose.Tasks for Java. Permudah tugas manajemen proyek.
### [Buat kalender standar di Aspose.Tasks](./make-standard/)
Pelajari cara membuat kalender standar MS Project dalam Java menggunakan Aspose.Tasks. Tingkatkan kemampuan manajemen proyek Anda dengan tutorial langkah‑demi‑langkah ini.
### [Baca minggu kerja dari kalender MS Project dengan Aspose.Tasks](./read-work-weeks/)
Pelajari cara membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks for Java. Dapatkan instruksi langkah‑demi‑langkah dalam tutorial komprehensif ini.
### [Perbarui kalender MS Project ke format MPP dengan mudah menggunakan Aspose.Tasks for Java](./update-to-mpp/)
Pelajari cara memperbarui kalender MS Project ke format MPP dengan mudah menggunakan Aspose.Tasks for Java.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mendefinisikan jam kerja yang berbeda untuk setiap hari kerja?**  
A: Ya. Aspose.Tasks memungkinkan Anda mengatur waktu mulai dan selesai secara terpisah untuk Senin hingga Minggu.

**Q: Bagaimana saya menangani hari libur atau hari non‑kerja?**  
A: Setelah mendefinisikan hari kerja, Anda dapat menambahkan pengecualian (tanggal) untuk menandai hari libur atau periode non‑kerja khusus.

**Q: Apakah memungkinkan menyalin definisi hari kerja dari satu kalender ke kalender lain?**  
A: Tentu saja. Anda dapat mengambil objek `WeekDay` dari kalender yang ada dan menambahkannya ke instance kalender lain.

**Q: Apakah saya perlu memuat ulang proyek setelah memperbarui hari kerja?**  
A: Tidak. Perubahan diterapkan langsung ke objek `Project` dalam memori; cukup simpan proyek saat selesai.

**Q: Versi Aspose.Tasks mana yang diperlukan untuk manipulasi hari kerja?**  
A: Semua versi terbaru (20.10 ke atas) mendukung API hari kerja lengkap. Kami merekomendasikan menggunakan rilis stabil terbaru untuk kinerja terbaik.

**Terakhir Diperbarui:** 2026-11-19  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Tentukan Hari Kerja & Jam Kerja dengan Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}