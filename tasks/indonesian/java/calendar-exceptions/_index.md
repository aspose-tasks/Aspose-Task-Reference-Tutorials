---
date: 2026-11-06
description: Dengan mudah membuat custom calendar exceptions, mengintegrasikan MS
  Project calendar, dan mengelola, mendefinisikan, menangani & mengambil calendar
  exceptions dalam Java projects dengan Aspose.Tasks. Menyederhanakan project workflows
  untuk efisien project management.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Calendar Exceptions
og_description: Pelajari cara membuat calendar exceptions dalam Java menggunakan Aspose.Tasks.
  Kelola project calendars, atur nonworking days, dan modifikasi MS Project calendars
  secara efisien.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Buat calendar exceptions dengan Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Cara membuat calendar exceptions dengan Aspose.Tasks untuk Java
url: /id/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat pengecualian kalender dengan Aspose.Tasks untuk Java

## Pendahuluan

`Aspose.Tasks` adalah perpustakaan Java yang memungkinkan pembuatan, manipulasi, dan konversi file Microsoft Project secara programatik. Dalam tutorial ini Anda akan belajar cara **membuat pengecualian kalender**—periode non‑kerja khusus yang menggantikan kalender default proyek. Kontrol yang tepat atas hari kerja dan non‑kerja sangat penting untuk peramalan jadwal yang akurat, alokasi sumber daya, dan kepatuhan terhadap hari libur regional. Pada akhir panduan ini Anda juga akan mengetahui cara **mengintegrasikan kalender MS Project** ke dalam aplikasi Java Anda serta mengambil atau memodifikasi pengecualian tersebut.

## Jawaban Cepat
- **Apa yang dapat saya capai?** Buat, modifikasi, dan ambil pengecualian kalender khusus dalam proyek Java.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java (rilis stabil terbaru).  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya bekerja dengan file MS Project?** Tentu – Anda dapat mengimpor, mengedit, dan mengekspor data kalender MS Project.  
- **Apakah ada pengaturan khusus yang diperlukan?** Cukup tambahkan JAR Aspose.Tasks ke classpath Anda dan impor kelas yang relevan.

## Cara membuat pengecualian kalender khusus di Aspose.Tasks untuk Java?

Untuk membuat pengecualian kalender khusus di Aspose.Tasks untuk Java, muat Project target, ambil Calendar-nya, tentukan tanggal mulai dan akhir pengecualian dengan waktu kerja yang diinginkan, opsional atur pola berulang, lalu simpan proyek. Urutan ini menambahkan pengecualian secara instan dan menyimpannya ke file .mpp.

`Project` class adalah objek utama Aspose.Tasks yang memodelkan seluruh file Microsoft Project. Kelas `Project` mewakili file Microsoft Project dan menyediakan akses ke isinya. Objek `Calendar` mendefinisikan waktu kerja dan non‑kerja untuk proyek. Kelas `Calendar` adalah wadah untuk semua aturan waktu kerja, termasuk pengecualian. Metode `addException()` menambahkan pengecualian kalender baru ke kalender. `addException()` adalah API panggilan tunggal yang mendaftarkan periode non‑kerja untuk rentang tanggal yang ditentukan.

Muat proyek target dengan `Project project = new Project("example.mpp")`, dapatkan objek `Calendar`-nya, dan panggil `addException()` dengan rentang tanggal dan pengaturan waktu kerja yang diinginkan. Pola dua langkah ini membuat pengecualian baru secara instan dan menyimpannya saat Anda menyimpan proyek. Untuk liburan berulang, konfigurasikan `RecurrencePattern` pada pengecualian sebelum menyimpan.

Membuat pengecualian kalender dengan cara ini memungkinkan Anda **mengatur hari non‑kerja** secara tepat, baik itu penutupan satu kali maupun liburan tahunan. Setelah pengecualian ditambahkan, Anda dapat memanggil `project.save("updated.mpp")` untuk menulis perubahan kembali ke disk.

### Ikhtisar Langkah
1. Muat file proyek.  
2. Ambil atau buat instance `Calendar`.  
3. Tentukan rentang tanggal dan waktu kerja pengecualian.  
4. (Opsional) Konfigurasikan pengulangan untuk liburan tahunan.  
5. Simpan proyek.

## Kelola pengecualian kalender di Aspose.Tasks
[Pelajari cara menambah dan menghapus pengecualian kalender di Aspose.Tasks untuk Java secara efisien](./add-remove/). Ketika berbicara tentang manajemen proyek, fleksibilitas adalah kunci. Aspose.Tasks memberi Anda kemampuan untuk mengelola pengecualian kalender dengan mudah, memungkinkan penyesuaian dinamis pada jadwal proyek. Tutorial ini menyediakan panduan langkah demi langkah, memastikan Anda memahami proses dengan efisien. Temukan cara meningkatkan alur kerja manajemen proyek Anda dengan mudah.

## Tentukan hari kerja untuk pengecualian kalender dengan Aspose.Tasks
[Kuasi seni menentukan hari kerja untuk pengecualian kalender dalam proyek Java](./define-weekdays/) menggunakan Aspose.Tasks. Penjadwalan proyek yang akurat memerlukan perhatian detail yang teliti. Dengan Aspose.Tasks, Anda dapat secara tepat menentukan hari kerja untuk pengecualian kalender, memastikan proyek Anda selaras dengan timeline tertentu secara mulus. Tutorial ini membekali Anda dengan pengetahuan untuk mengoptimalkan penjadwalan, memberi Anda kontrol atas timeline proyek.

## Tangani kejadian dalam pengecualian kalender menggunakan Aspose.Tasks
[Tangani pengecualian kalender secara efektif dalam proyek Java](./handle-occurrences/) dengan Aspose.Tasks untuk Java. Manajemen proyek adalah proses dinamis, sering memerlukan penyesuaian untuk mengatasi kejadian tak terduga. Aspose.Tasks memberi Anda kemampuan untuk menangani pengecualian kalender secara efektif, menyediakan pendekatan yang terstruktur untuk manajemen proyek. Pelajari seni mengelola ketidakpastian proyek dengan mudah melalui tutorial terperinci ini.

## Ambil pengecualian kalender dengan Aspose.Tasks
[Pelajari cara mengambil pengecualian kalender dari MS Project menggunakan Aspose.Tasks untuk Java](./retrieve/). Integrasikan pengecualian kalender secara mulus ke dalam proses manajemen proyek Anda dengan Aspose.Tasks. Tutorial ini memandu Anda melalui proses langkah demi langkah untuk mengambil pengecualian kalender, memastikan integrasi yang lancar dan efisien ke dalam proyek Anda. Manfaatkan kekuatan Aspose.Tasks untuk meningkatkan kemampuan manajemen proyek Anda.

## Cara mengintegrasikan kalender MS Project dengan Aspose.Tasks?

Mengintegrasikan kalender MS Project dengan Aspose.Tasks melibatkan pemuatan file .mpp sumber menggunakan kelas Project, mengakses objek Calendar default atau khususnya, memodifikasi atau menggabungkan pengecualian sesuai kebutuhan, lalu menyimpan proyek yang diperbarui. Ini memungkinkan Anda bekerja secara programatik dengan kalender MS Project tanpa interaksi UI manual.

`Project` class adalah objek utama Aspose.Tasks yang memodelkan seluruh file Microsoft Project. Impor file MS Project yang ada menggunakan `new Project("source.mpp")`; perpustakaan secara otomatis memuat kalender default dan semua pengecualian khusus. Anda kemudian dapat membaca, memodifikasi, atau menggabungkan pengecualian tersebut sebelum menyimpan proyek kembali ke disk. Pendekatan ini memungkinkan Anda **memodifikasi data kalender MS Project** secara programatik tanpa penyuntingan manual di UI MS Project.

## Kasus penggunaan umum
- **Penjadwalan liburan** – Tentukan hari libur nasional sebagai hari non‑kerja di seluruh proyek.  
- **Kerja shift** – Atur minggu kerja khusus untuk tim yang beroperasi dengan jadwal non‑standar.  
- **Pengaturan fase proyek** – Blokir periode di mana tidak ada pekerjaan yang harus dijadwalkan, seperti jendela pemeliharaan.  
- **Migrasi warisan** – Impor kalender dari file MS Project lama dan sesuaikan secara programatik.

## Tips & praktik terbaik
- **Tips pro:** Selalu ambil kalender yang ada sebelum menambahkan pengecualian baru untuk menghindari duplikat.  
- **Peringatan:** Mengubah kalender yang sudah ditetapkan ke tugas dapat menggeser tanggal tugas; hitung ulang jadwal setelah modifikasi.  
- **Kinerja:** Kelompokkan beberapa pembaruan pengecualian dalam satu transaksi untuk mengurangi beban I/O file. Aspose.Tasks memproses file hingga 1 GB sambil menjaga penggunaan memori di bawah 200 MB, dan dapat menangani lebih dari 30 panggilan API terkait kalender per detik pada perangkat keras server tipikal.

## Tutorial pengecualian kalender
### [Kelola Pengecualian Kalender di Aspose.Tasks](./add-remove/)
Pelajari cara menambah dan menghapus pengecualian kalender di Aspose.Tasks untuk Java secara efisien. Tingkatkan alur kerja manajemen proyek dengan mudah.
### [Tentukan Hari Kerja untuk Pengecualian Kalender dengan Aspose.Tasks](./define-weekdays/)
Pelajari cara menentukan hari kerja untuk pengecualian kalender dalam proyek Java menggunakan Aspose.Tasks untuk penjadwalan proyek yang akurat.
### [Tangani Kejadian dalam Pengecualian Kalender menggunakan Aspose.Tasks](./handle-occurrences/)
Pelajari cara menangani pengecualian kalender secara efektif dalam proyek Java dengan Aspose.Tasks untuk Java. Sederhanakan proses manajemen proyek Anda sekarang.
### [Ambil Pengecualian Kalender dengan Aspose.Tasks](./retrieve/)
Pelajari cara mengambil pengecualian kalender dari MS Project menggunakan Aspose.Tasks untuk Java. Tutorial langkah demi langkah untuk integrasi yang mulus.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya memodifikasi pengecualian kalender setelah proyek sudah dipublikasikan?**  
A: Ya. Gunakan API add‑remove dan define‑weekdays untuk memperbarui kalender, lalu simpan kembali file proyek.

**Q: Apakah Aspose.Tasks mendukung pengecualian berulang (mis., setiap Senin pertama tiap bulan)?**  
A: Tentu saja. Tutorial “handle occurrences” menjelaskan cara mengatur pola berulang.

**Q: Bagaimana saya memastikan kalender khusus saya digunakan oleh semua tugas dalam proyek?**  
A: Tetapkan kalender ke kalender default proyek atau secara eksplisit atur pada properti `Calendar` setiap tugas.

**Q: Apakah memungkinkan menggabungkan kalender dari beberapa file MS Project?**  
A: Ya. Ambil setiap kalender, gabungkan pengecualian mereka secara programatik, lalu tetapkan kalender yang digabungkan ke proyek target.

**Q: Versi Aspose.Tasks apa yang diperlukan untuk fitur-fitur ini?**  
A: Semua fitur tersedia dalam rilis stabil terbaru Aspose.Tasks untuk Java (2025.x).

## Tutorial Terkait

- [Buat Kalender Proyek Aspose – Tentukan Hari Kerja untuk Pengecualian Kalender](/tasks/java/calendar-exceptions/define-weekdays/)
- [Ambil Pengecualian Kalender dengan Aspose.Tasks – tutorial java asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Buat Pengecualian Kalender Aspose untuk Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Terakhir Diperbarui:** 2026-11-06  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}