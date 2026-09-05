---
date: 2026-08-08
description: Pelajari cara mengatur kalender ms project, mengatur jam kerja harian,
  dan menambahkan hari kerja akhir pekan menggunakan Aspose.Tasks for Java. Simpan
  proyek sebagai XML dalam beberapa baris kode.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Cara mengatur kalender ms project dan menentukan hari kerja
og_description: Atur kalender ms project, tentukan hari kerja, dan tambahkan hari
  kerja akhir pekan menggunakan Aspose.Tasks for Java. Ikuti tutorial langkah demi
  langkah ini dan simpan sebagai XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Atur kalender ms project dengan Aspose.Tasks – Panduan Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Cara mengatur kalender ms project dan menentukan hari kerja
url: /id/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur kalender ms project dan menentukan hari kerja

Dalam tutorial ini Anda akan belajar **cara mengatur kalender ms project** secara programatis, menentukan hari kerja, dan mengonfigurasi hari kerja khusus menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda membangun mesin penjadwalan, mengintegrasikan dengan sistem ERP, atau hanya perlu menghasilkan rencana proyek tanpa membuka Microsoft Project, langkah‑langkah di bawah ini menunjukkan cara membuat kalender, mengatur jam kerja harian, dan menambahkan hari kerja akhir pekan dalam beberapa baris kode.

## Jawaban Cepat
- **Library apa yang dibutuhkan?** Aspose.Tasks for Java.  
- **Bisakah saya menambahkan hari kerja akhir pekan?** Ya – cukup tandai Sabtu dan Minggu sebagai hari kerja.  
- **Bagaimana cara menyimpan proyek?** Panggil `prj.save(..., SaveFileFormat.Xml)`.  
- **Apakah lisensi diperlukan?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk penggunaan produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi.

## Apa itu set calendar ms project?
Mengatur kalender di MS Project menentukan hari mana yang dianggap hari kerja, jumlah jam kerja setiap hari, dan pengecualian khusus seperti libur atau penutupan perusahaan secara menyeluruh. Informasi ini mengarahkan penjadwalan tugas, alokasi sumber daya, dan keseluruhan jadwal proyek, memastikan perhitungan menghormati pola kerja sebenarnya di organisasi.

## Mengapa menggunakan Aspose.Tasks untuk manipulasi kalender?
Aspose.Tasks memberi Anda kontrol programatis atas kalender tanpa meluncurkan UI Microsoft Project. Ia berjalan di sistem operasi apa pun yang mendukung Java, mendukung lebih dari 50 format input dan output, serta dapat memproses proyek ratusan halaman tanpa memuat seluruh file ke memori, menjadikannya ideal untuk otomasi sisi server.

## Prasyarat
- **Java Development Kit (JDK) 8+** – unduh dari [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – dapatkan JAR terbaru dari [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- Sebuah IDE atau alat build (Maven/Gradle) untuk menambahkan JAR Aspose.Tasks ke classpath Anda.

## Impor paket
Impor kelas-kelas yang menyediakan akses ke proyek, kalender, dan objek waktu kerja.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: buat instance proyek
Instansiasi objek `Project`, yang mewakili file MS Project yang akan Anda manipulasi.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Langkah 2: definisikan kalender baru
`Calendar` mewakili sekumpulan waktu kerja, pengecualian, dan libur untuk sebuah proyek.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Langkah 3: tambahkan hari kerja standar (Senin‑Kamis)
`WeekDay` mendefinisikan waktu kerja untuk hari tertentu dalam seminggu.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Langkah 4: tambahkan hari kerja akhir pekan
Jika proyek Anda berjalan pada akhir pekan, tambahkan Sabtu dan Minggu sebagai hari kerja reguler. Ini menunjukkan **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Langkah 5: atur hari kerja pendek khusus (Jumat)
Konfigurasikan Jumat dengan shift pagi (09.00‑12.00) dan shift sore (13.00‑16.00) untuk menggambarkan **set daily working hours** dan hari kerja pendek khusus.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Langkah 6: simpan proyek sebagai XML
`SaveFileFormat` menenumerasikan format file yang didukung saat menyimpan proyek, seperti XML atau MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Masalah umum & solusi
| Masalah | Solusi |
|-------|----------|
| **Waktu kerja tidak diterapkan** | Pastikan `setDayWorking(true)` dipanggil pada setiap `WeekDay` khusus. |
| **File tidak ditemukan saat menyimpan** | Verifikasi bahwa `dataDir` mengarah ke folder yang ada dan aplikasi memiliki izin menulis. |
| **Kalender tidak tercermin dalam tugas** | Tetapkan kalender yang baru dibuat ke sumber daya atau tugas menggunakan `task.setCalendar(cal)`. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya mendefinisikan hari non‑kerja khusus menggunakan Aspose.Tasks untuk Java?**  
A: Ya. Atur properti `DayWorking` menjadi `false` untuk setiap `WeekDay` yang ingin Anda perlakukan sebagai hari non‑kerja.

**Q: Bagaimana cara menambahkan libur atau pengecualian perusahaan secara menyeluruh?**  
A: Buat objek `CalendarException`, tentukan tanggal pengecualian, dan tambahkan ke `cal.getExceptions()`.

**Q: Apakah pustaka ini kompatibel dengan versi MS Project yang lebih lama?**  
A: Tentu saja. Aspose.Tasks mendukung format MPP, MPT, dan XML di berbagai versi Project.

**Q: Bisakah saya memodifikasi kalender yang ada dalam proyek yang diimpor?**  
A: Muat proyek dengan `new Project("existing.mpp")`, ambil kalender yang diinginkan, lakukan perubahan, dan simpan.

**Q: Apakah Aspose.Tasks juga menangani tugas berulang?**  
A: Ya, Anda dapat membuat dan mengedit tugas berulang menggunakan kelas `RecurringTask`.

## Kesimpulan
Anda sekarang tahu **cara mengatur kalender ms project**, menentukan hari kerja, menambahkan hari kerja akhir pekan, dan mengonfigurasi jadwal Jumat pendek — semuanya dengan Aspose.Tasks untuk Java. Simpan hasilnya sebagai XML dan integrasikan logika kalender ke dalam solusi manajemen proyek berbasis Java apa pun.

---

**Terakhir Diperbarui:** 2026-08-08  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/calendars/create/)
- [Tentukan Hari Kerja & Jam Kerja dengan Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Tambahkan Libur ke Kalender dan Simpan sebagai MPP dengan Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}