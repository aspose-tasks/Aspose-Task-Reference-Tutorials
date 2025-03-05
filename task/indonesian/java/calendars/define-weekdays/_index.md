---
title: Tentukan Hari Kerja di Kalender dengan Aspose.Tasks
linktitle: Tentukan Hari Kerja di Kalender dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menentukan hari kerja di MS Project Calendar menggunakan Aspose.Tasks untuk Java. Sesuaikan hari dan waktu kerja dengan mudah.
type: docs
weight: 12
url: /id/java/calendars/define-weekdays/
---
## Perkenalan
Dalam tutorial ini, kita akan memandu proses menentukan hari kerja di Kalender Proyek MS menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah perpustakaan Java yang kuat yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[situs web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) jika Anda belum melakukannya.
2.  Aspose.Tasks for Java Library: Unduh dan instal perpustakaan Aspose.Tasks for Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/). Ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

## Paket Impor
Untuk memulai, impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks di proyek Java Anda:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Langkah 1: Buat Instans Proyek
Buat instance objek Project, yang mewakili file MS Project yang akan Anda gunakan:
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Langkah 2: Tentukan Kalender
Buat instance kalender baru dan tambahkan ke proyek:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Langkah 3: Tambahkan Hari Kerja
Tentukan hari kerja dengan menambahkan Senin hingga Kamis dengan waktu default:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Langkah 4: Tetapkan Hari Kerja Khusus
Tentukan hari Sabtu dan Minggu sebagai hari kerja:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Langkah 5: Tetapkan Hari Kerja yang Singkat
Tetapkan hari Jumat sebagai hari kerja singkat dengan waktu kerja khusus:
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
## Langkah 6: Simpan Proyek
Simpan proyek yang dimodifikasi ke file XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Kesimpulan
Selamat! Anda telah berhasil menentukan hari kerja di Kalender Proyek MS menggunakan Aspose.Tasks untuk Java. Anda sekarang dapat mengintegrasikan fungsi ini ke dalam aplikasi Java Anda untuk memanipulasi file MS Project secara terprogram.
## FAQ
### Q1: Dapatkah saya menentukan hari non-kerja khusus menggunakan Aspose.Tasks untuk Java?
 J: Ya, Anda dapat menentukan hari non-kerja khusus dengan mengatur`DayWorking` properti ke`false` untuk hari kerja masing-masing.
### Q2: Bagaimana cara menambahkan hari libur ke kalender?
 J: Anda dapat menambahkan hari libur dengan membuat instance`CalendarExceptions`dan menentukan tanggal tidak bekerja.
### Q3: Apakah Aspose.Tasks kompatibel dengan versi file MS Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi file MS Project, termasuk format MPP, MPT, dan XML.
### Q4: Bisakah saya mengubah kalender yang ada di file MS Project?
J: Ya, Anda dapat memuat proyek yang ada dengan kalender, membuat modifikasi, lalu menyimpan perubahan kembali ke file aslinya.
### Q5: Apakah Aspose.Tasks memberikan dukungan untuk tugas berulang?
J: Ya, Aspose.Tasks memungkinkan Anda bekerja dengan tugas berulang, termasuk menentukan pola dan durasi pengulangannya.