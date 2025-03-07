---
title: Dapatkan Jam Kerja dari Kalender menggunakan Aspose.Tasks
linktitle: Dapatkan Jam Kerja dari Kalender menggunakan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Ekstrak jam kerja dari kalender MS Project dengan mudah menggunakan Aspose.Tasks untuk Java. Sederhanakan tugas manajemen proyek.
weight: 13
url: /id/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Jam Kerja dari Kalender menggunakan Aspose.Tasks

## Perkenalan
Mengelola kalender proyek dan menentukan jam kerja sangat penting untuk manajemen proyek yang efektif. Aspose.Tasks untuk Java menyediakan fungsionalitas yang kuat untuk mengambil jam kerja dari kalender MS Project dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Pemahaman dasar bahasa pemrograman Java.
## Paket Impor
Pertama, impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks untuk Java:
```java
import com.aspose.tasks.*;
```
## Langkah 1: Muat File Proyek
Mulailah dengan memuat file MS Project Anda:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Langkah 2: Ambil Informasi Tugas dan Kalender
Ekstrak detail tugas dan kalender dari proyek:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Langkah 3: Tentukan Tanggal Mulai dan Berakhir
Tetapkan tanggal mulai dan berakhir untuk tugas:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Langkah 4: Ulangi Tanggal
Ulangi tanggal dalam durasi tugas:
```java
java.util.Calendar tempDate = calStartDate;
```
## Langkah 5: Hitung Durasi
Hitung durasi dalam menit, jam, dan hari:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Kesimpulan
Dalam tutorial ini, kami telah membahas cara mengambil jam kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola jadwal proyek secara efisien dan menghitung durasi tugas dengan mudah.
## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks untuk Java memberikan dukungan komprehensif untuk menangani struktur proyek yang kompleks, termasuk tugas, sumber daya, dan kalender.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan versi MS Project yang berbeda?
J: Tentu saja, Aspose.Tasks untuk Java mendukung berbagai versi MS Project, memastikan kompatibilitas di berbagai lingkungan.
### T: Dapatkah saya menyesuaikan jam kerja dan hari libur di kalender proyek?
J: Ya, Anda dapat dengan mudah menyesuaikan jam kerja dan hari libur sesuai dengan kebutuhan proyek Anda menggunakan Aspose.Tasks untuk Java API.
### T: Apakah Aspose.Tasks untuk Java menawarkan dukungan dan dokumentasi?
J: Ya, Aspose.Tasks untuk Java menyediakan dokumentasi ekstensif dan forum dukungan khusus untuk membantu pengembang dalam memanfaatkan fitur-fiturnya secara efektif.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengakses Aspose.Tasks versi uji coba gratis untuk Java dari[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
