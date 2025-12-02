---
date: 2025-12-02
description: Pelajari cara mengatur kalender, mendefinisikan hari kerja MS Project,
  dan mengatur hari kerja khusus menggunakan Aspose.Tasks untuk Java. Simpan proyek
  sebagai XML dengan hanya beberapa baris kode.
language: id
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengatur Kalender dan Menentukan Hari Kerja di MS Project dengan Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Kalender dan Menentukan Hari Kerja di MS Project dengan Aspose.Tasks

## Introduction
Dalam tutorial ini Anda akan menemukan **cara mengatur kalender** secara programatis dan menentukan hari kerja dalam file Microsoft Project menggunakan pustaka Aspose.Tasks untuk Java. Apakah Anda perlu membuat minggu kerja standar, menambahkan hari kerja akhir pekan, atau mengonfigurasi jadwal Jumat singkat, panduan ini akan memandu Anda melalui setiap langkah—dari pembuatan proyek hingga menyimpan file sebagai XML.

## Quick Answers
- **Library apa yang dibutuhkan?** Aspose.Tasks for Java  
- **Bisakah saya menambahkan hari kerja akhir pekan?** Ya – cukup tambahkan Sabtu dan Minggu sebagai hari kerja.  
- **Bagaimana cara menyimpan proyek?** Gunakan `prj.save(..., SaveFileFormat.Xml)`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang dibutuhkan?** Java 8 atau lebih tinggi.

## What is “how to set calendar” in the context of MS Project?
Mengatur kalender di MS Project berarti menentukan hari mana yang merupakan hari kerja, jam kerja harian, dan pengecualian apa pun seperti hari libur. Kalender ini mengendalikan penjadwalan tugas, alokasi sumber daya, dan keseluruhan jadwal proyek.

## Why use Aspose.Tasks for calendar manipulation?
- **Kontrol penuh** – membuat, memodifikasi, atau menghapus kalender secara programatis tanpa membuka UI.  
- **Cross‑platform** – bekerja pada sistem operasi apa pun yang mendukung Java.  
- **Mendukung semua format file** – MPP, MPT, dan XML, sehingga Anda dapat *menyimpan proyek sebagai XML* untuk integrasi mudah dengan sistem lain.  
- **Tanpa ketergantungan COM** – tidak seperti pustaka Microsoft Project Interop.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK) 8+** – unduh dari [situs Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – dapatkan JAR terbaru dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Sebuah IDE atau alat build (Maven/Gradle) untuk menambahkan JAR Aspose.Tasks ke classpath proyek Anda.

## Import Packages
Pertama, impor kelas yang Anda perlukan. Impor ini memberi Anda akses ke objek proyek, kalender, dan waktu kerja.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Project Instance
Buat sebuah objek `Project` baru. Objek ini mewakili file MS Project yang akan Anda edit.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: Define a New Calendar
Tambahkan kalender baru ke proyek. Memberi nama yang jelas membantu ketika Anda memiliki banyak kalender.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: Add Standard Working Days (Monday‑Thursday)
Gunakan pembantu bawaan `WeekDay.createDefaultWorkingDay` untuk mengatur jadwal default 9 am‑5 pm untuk minggu kerja inti.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: Add Weekend Working Days
Jika proyek Anda berjalan pada akhir pekan, cukup tambahkan Sabtu dan Minggu sebagai hari kerja reguler. Ini menunjukkan **menambahkan hari kerja akhir pekan**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: Set a Custom Short Working Day (Friday)
Di sini kami **mengatur hari kerja khusus** untuk Jumat: shift pagi (9 am‑12 pm) dan shift sore (1 pm‑4 pm).

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

### Step 6: Save the Project as XML
Akhirnya, simpan perubahan. Opsi `SaveFileFormat.Xml` memungkinkan Anda **menyimpan proyek sebagai XML**, yang berguna untuk integrasi dengan alat lain.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues & Solutions
| Masalah | Solusi |
|-------|----------|
| **Waktu kerja tidak diterapkan** | Pastikan `setDayWorking(true)` dipanggil pada `WeekDay` khusus. |
| **File tidak ditemukan saat menyimpan** | Verifikasi bahwa `dataDir` mengarah ke folder yang ada dan aplikasi Anda memiliki izin menulis. |
| **Kalender tidak tercermin pada tugas** | Tetapkan kalender yang baru dibuat ke sumber daya atau tugas menggunakan `task.setCalendar(cal)`. |

## Frequently Asked Questions

**Q: Bisakah saya mendefinisikan hari non‑kerja khusus menggunakan Aspose.Tasks untuk Java?**  
A: Ya. Atur properti `DayWorking` menjadi `false` untuk setiap `WeekDay` yang ingin Anda perlakukan sebagai hari non‑kerja.

**Q: Bagaimana cara menambahkan hari libur atau pengecualian perusahaan?**  
A: Buat objek `CalendarException`, tentukan tanggal pengecualian, dan tambahkan ke `cal.getExceptions()`.

**Q: Apakah pustaka ini kompatibel dengan versi MS Project yang lebih lama?**  
A: Tentu saja. Aspose.Tasks mendukung format MPP, MPT, dan XML pada berbagai versi Project.

**Q: Bisakah saya memodifikasi kalender yang sudah ada dalam proyek yang diimpor?**  
A: Muat proyek dengan `new Project("existing.mpp")`, ambil kalender yang diinginkan, lakukan perubahan, dan simpan.

**Q: Apakah Aspose.Tasks juga menangani tugas berulang?**  
A: Ya, Anda dapat membuat dan mengedit tugas berulang menggunakan kelas `RecurringTask`.

## Conclusion
Anda sekarang mengetahui **cara mengatur kalender**, **menentukan hari kerja MS Project**, menambahkan hari kerja akhir pekan, dan membuat jadwal Jumat singkat—semua dengan Aspose.Tasks untuk Java. Simpan hasilnya sebagai XML dan integrasikan logika kalender ke dalam solusi manajemen proyek berbasis Java apa pun.

---

**Terakhir Diperbarui:** 2025-12-02  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}