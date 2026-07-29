---
date: 2026-07-29
description: Pelajari cara menjadwalkan hari tidak kerja dengan membuat kalender proyek
  menggunakan Aspose.Tasks for Java, mendefinisikan pengecualian hari kerja, dan mengelola
  jadwal liburan.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Jadwalkan Hari Tidak Kerja – Buat Kalender Proyek Aspose
og_description: Jadwalkan hari tidak kerja menggunakan Aspose.Tasks for Java. Pelajari
  cara mendefinisikan hari kerja, menambahkan pengecualian kalender, dan mengelola
  jadwal liburan secara efisien.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Jadwalkan Hari Tidak Kerja – Buat Kalender Proyek Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Jadwalkan Hari Tidak Kerja – Buat Kalender Proyek Aspose
url: /id/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jadwalkan Hari Tidak Kerja – Buat Kalender Proyek Aspose

### Pendahuluan
Ketika Anda perlu **menjadwalkan hari tidak kerja** untuk sebuah proyek, Anda harus dapat memodelkan liburan, shift khusus, atau penutupan sementara langsung dalam rencana proyek. Aspose.Tasks for Java memberi Anda kontrol penuh atas definisi kalender, memungkinkan Anda menambahkan pengecualian yang mencerminkan jadwal dunia nyata. Dalam tutorial ini kami akan memandu langkah‑langkah tepat untuk mendefinisikan hari kerja untuk pengecualian kalender, sehingga timeline proyek Anda tetap akurat dan dapat diandalkan. Pada akhir tutorial Anda juga akan melihat bagaimana hal ini masuk ke dalam strategi **jadwal hari tidak kerja** yang lebih luas untuk proyek perusahaan mana pun.

## Jawaban Cepat
- **Apa arti “menjadwalkan hari tidak kerja”?**  
  Itu berarti menggunakan Aspose.Tasks untuk membuat kalender yang menandai tanggal tertentu sebagai tidak‑kerja, memengaruhi tanggal tugas secara otomatis.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?**  
  Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **IDE mana yang didukung?**  
  IntelliJ IDEA, Eclipse, NetBeans, atau IDE apa pun yang mendukung Java 8+.  
- **Bisakah saya menambahkan beberapa pengecualian ke kalender yang sama?**  
  Ya – Anda dapat menambahkan sebanyak yang diperlukan objek `CalendarException`.  
- **Format file apa yang dapat saya simpan proyek?**  
  XML, MPP, dan beberapa format lain yang didukung oleh Aspose.Tasks.  

## Apa itu Kalender Proyek di Aspose.Tasks?
**project calendar** adalah objek tingkat‑atas Aspose.Tasks yang mendefinisikan hari kerja dan jam kerja untuk sebuah proyek. Ia secara langsung memengaruhi tanggal mulai/selesai tugas, alokasi sumber daya, dan perhitungan jadwal keseluruhan. Dengan menyesuaikan kalender, Anda memastikan jadwal menghormati kendala dunia nyata seperti libur perusahaan atau kebijakan kerja akhir pekan.

## Mengapa mendefinisikan hari kerja untuk pengecualian kalender?
Mendefinisikan pengecualian hari kerja memastikan bahwa mesin proyek memperlakukan hari‑hari tersebut sebagai tidak‑kerja, mencegah tugas dijadwalkan secara otomatis pada hari‑hari itu dan menjaga timeline selaras dengan kendala dunia nyata seperti liburan, jendela pemeliharaan, atau pola shift khusus di seluruh organisasi.

- **Timeline akurat:** Tugas tidak akan ditempatkan pada liburan atau periode pemadaman.  
- **Perencanaan sumber daya:** Sumber daya dialokasikan hanya pada hari kerja yang sah, mencegah kelebihan alokasi.  
- **Kepatuhan:** Jadwal secara otomatis mengikuti kebijakan organisasi atau kalender libur resmi.  

## Jadwal Hari Tidak Kerja dengan Pengecualian Kalender
Ketika Anda memelihara **jadwal hari tidak kerja**, biasanya Anda memiliki daftar utama liburan, jendela pemeliharaan, atau periode pemadaman lainnya. Menambahkan tanggal‑tanggal tersebut sebagai objek `CalendarException` menjamin setiap perhitungan—baik analisis jalur kritis maupun leveling sumber daya—secara otomatis menghormati kendala tersebut. Pendekatan ini menghilangkan penyesuaian tanggal manual dan mengurangi risiko penyimpangan jadwal.

## Prasyarat
1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.  
2. **Aspose.Tasks for Java** – unduh dari halaman resmi [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, atau editor kompatibel Java apa pun.  

## Cara menjadwalkan hari tidak kerja menggunakan pengecualian kalender
Muat proyek Anda, buat kalender khusus, dan tambahkan objek `CalendarException` yang menandai hari kerja yang diinginkan sebagai tidak‑kerja. Seluruh proses ini dapat diselesaikan dalam beberapa langkah sederhana, dan kalender yang dihasilkan akan secara otomatis memengaruhi semua logika penjadwalan tugas.

### Panduan Langkah‑per‑Langkah

### Langkah 1: Impor Paket yang Diperlukan
We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for date handling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Langkah 2: Tentukan Direktori Data
Specify where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

### Langkah 3: Buat Instance Proyek
`Project` is the main object that holds all project data, including tasks, resources, and calendars.

```java
Project project = new Project();
```

### Langkah 4: Definisikan Kalender
`Calendar` represents a schedule of working and non‑working times within a project.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Langkah 5: Definisikan Pengecualian Hari Kerja
`CalendarException` represents a period that is marked as non‑working in a calendar.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Langkah 6: Simpan Proyek
Persist the project, including the custom calendar and its exception, to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Tanggal pengecualian tidak diterapkan** | Pastikan `setEnteredByOccurrences(false)` dan nilai `FromDate/ToDate` yang benar. |
| **File yang disimpan kosong** | Verifikasi `dataDir` mengarah ke folder yang dapat ditulisi dan nama file berakhiran `.xml`. |
| **Kalender tidak tercermin dalam penjadwalan tugas** | Tetapkan kalender ke tugas atau sumber daya menggunakan `task.setCalendar(cal)` atau `resource.setCalendar(cal)`. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah saya dapat mendefinisikan beberapa pengecualian untuk hari kerja yang berbeda dalam kalender yang sama?**  
A: Ya. Tambahkan objek `CalendarException` tambahan ke `cal.getExceptions()` untuk setiap periode atau aturan yang berbeda.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai IDE Java?**  
A: Tentu saja. Perpustakaan ini bekerja dengan IntelliJ IDEA, Eclipse, NetBeans, dan IDE apa pun yang mendukung proyek Java standar.

**Q: Bisakah saya menyesuaikan tipe pengecualian selain pengecualian harian?**  
A: Ya. Gunakan `CalendarExceptionType.Weekly`, `Monthly`, atau `Yearly` sesuai kebutuhan penjadwalan Anda.

**Q: Bagaimana cara menangani pengecualian secara dinamis berdasarkan kebutuhan proyek?**  
A: Bangun objek pengecualian secara programatik—misalnya, baca tanggal libur dari basis data atau file konfigurasi dan buat instance `CalendarException` dalam loop.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **menjadwalkan hari tidak kerja** dengan membuat kalender proyek dan mendefinisikan pengecualian hari kerja yang secara akurat mencerminkan liburan atau periode tidak‑kerja khusus. Konfigurasi kalender yang tepat sangat penting untuk jadwal realistis, alokasi sumber daya, dan keberhasilan proyek secara keseluruhan. Jelajahi lebih lanjut dengan melampirkan kalender khusus ke tugas atau sumber daya serta bereksperimen dengan tipe pengecualian lain untuk membangun **jadwal hari tidak kerja** yang komprehensif bagi proyek apa pun.

---

**Last Updated:** 2026-07-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Buat Pengecualian Kalender Aspose untuk Java](/tasks/java/calendar-exceptions/add-remove/)
- [Cara Mengatur Kalender dan Mendefinisikan Hari Kerja di MS Project dengan Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}