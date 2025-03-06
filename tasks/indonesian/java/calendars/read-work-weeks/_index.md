---
title: Baca Minggu Kerja dari Kalender Proyek MS dengan Aspose.Tasks
linktitle: Baca Minggu Kerja dari Kalender dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membaca minggu kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dapatkan petunjuk langkah demi langkah dalam tutorial komprehensif ini.
weight: 15
url: /id/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Minggu Kerja dari Kalender Proyek MS dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Tasks untuk Java untuk membaca informasi minggu kerja dari kalender Microsoft Project. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan Anda memanipulasi dan mengelola dokumen Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tasks untuk perpustakaan Java diunduh dan diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Pertama, mari impor paket yang diperlukan untuk memulai kode kita:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Langkah 1: Siapkan Direktori Data Anda
Siapkan jalur direktori tempat file MS Project Anda berada:
```java
String dataDir = "Your Data Directory";
```
## Langkah 2: Buat Instans Proyek dan Akses Kalender
Buat instance baru dari kelas Project dan akses koleksi kalender dan minggu kerja:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Langkah 3: Ulangi Melalui Minggu Kerja
Ulangi kumpulan minggu kerja dan tampilkan informasinya:
```java
for (WorkWeek workWeek : collection) {
    // Tampilkan nama minggu kerja, dari dan sampai tanggal
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Akses hari minggu dan waktu kerja
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Proses lebih lanjut waktu kerja jika diperlukan
    }
}
```
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membaca informasi minggu kerja dari kalender Microsoft Project menggunakan Aspose.Tasks untuk Java. Pustaka yang kuat ini memungkinkan manipulasi file Proyek dengan lancar, memungkinkan pengembang mengotomatiskan berbagai tugas secara efisien.
## FAQ
### Bisakah saya mengubah informasi minggu kerja menggunakan Aspose.Tasks untuk Java?
Ya, Aspose.Tasks menyediakan API untuk mengubah, menambah, atau menghapus minggu kerja dan informasi terkaitnya.
### Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk format MPP dan XML.
### Bisakah saya mengintegrasikan Aspose.Tasks dengan kerangka Java lainnya?
Tentu saja, Aspose.Tasks dapat diintegrasikan secara mulus dengan kerangka kerja dan pustaka Java lainnya untuk meningkatkan fungsionalitas.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?
Anda dapat menemukan dukungan dan bantuan di forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
