---
date: 2026-02-05
description: Pelajari cara menentukan hari kerja dan menghitung durasi tugas dengan
  mengekstrak jam kerja dari kalender MS Project menggunakan Aspose.Tasks untuk Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Menentukan Hari Kerja & Jam Kerja dengan Aspose.Tasks
url: /id/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menentukan Hari Kerja & Jam Kerja dengan Aspose.Tasks

## Introduction
Mengelola kalender proyek adalah bagian inti dari perencanaan proyek yang berhasil. Dalam tutorial ini Anda akan **menentukan hari kerja** untuk tugas apa pun dan **mengekstrak jam kerja** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Pada akhir panduan Anda akan dapat **menghitung durasi tugas**, menyesuaikan jam kerja, dan secara andal **memuat file MPP** untuk mengambil data yang Anda perlukan. Anda juga akan melihat cara **membaca file MS Project** tanpa harus menginstal Microsoft Project, sehingga otomatisasi dapat dilakukan di platform apa pun.

## Quick Answers
- **Apa arti “menentukan hari kerja”?** Artinya mengidentifikasi tanggal kalender yang dianggap hari kerja untuk suatu tugas tertentu.  
- **Perpustakaan mana yang harus saya gunakan?** Aspose.Tasks untuk Java menyediakan API lengkap untuk bekerja dengan file MS Project.  
- **Berapa lama implementasinya?** Biasanya 10–15 menit untuk ekstraksi dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan jam kerja?** Ya – Anda dapat memodifikasi kalender, menambahkan hari libur, dan mengatur rentang waktu kerja khusus.  

## What is “determine working days”?
Ketika sebuah tugas dijadwalkan, kalender proyek menentukan hari mana yang merupakan hari kerja dan mana yang bukan (akhir pekan, hari libur). Menentukan hari kerja berarti menanyakan kalender tersebut untuk mengetahui secara tepat kapan pekerjaan dapat dilakukan, yang penting untuk perhitungan **calculate task duration** yang akurat.

## Why use Aspose.Tasks to retrieve working hours?
- **Tidak memerlukan Microsoft Project** – Anda dapat membaca file MS Project langsung dari kode Java.  
- **Dukungan kalender lengkap** – mencakup kalender default, sumber daya, dan tugas.  
- **Kinerja tinggi** – memproses proyek besar dengan cepat.  
- **Dokumentasi lengkap** – contoh dan referensi API tersedia secara mudah.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari [here](https://releases.aspose.com/tasks/java/).  
3. Pengetahuan dasar pemrograman Java.  

## Import Packages
Pertama, impor namespace inti Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## How to load an MPP file with Aspose.Tasks?
Memuat file proyek adalah langkah pertama untuk analisis kalender apa pun. API memungkinkan Anda **memuat file MPP** dalam satu baris kode, tanpa memerlukan UI MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Retrieve Task and Calendar Information
Pilih tugas yang ingin Anda analisis dan dapatkan kalender yang terkait. Di sinilah kita **mengambil jam kerja** untuk tugas tersebut:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Define Start and End Dates
Atur jendela waktu untuk **menentukan hari kerja** yang Anda inginkan. Menggunakan tanggal mulai dan selesai tugas memastikan Anda hanya mengevaluasi periode yang relevan.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterate Through Dates
Loop melalui setiap tanggal dalam durasi tugas. Loop ini akan membantu kita **menyesuaikan jam kerja** nanti jika diperlukan:

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculate Duration
Selama iterasi kami memeriksa apakah setiap hari adalah hari kerja, menjumlahkan jam kerja, dan akhirnya menghitung durasi tugas dalam menit, jam, dan hari. Langkah ini menunjukkan cara **menghitung hari kerja** dan **menghitung durasi tugas** secara programatik.

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

## How to customize working hours and holidays
Aspose.Tasks memungkinkan Anda memodifikasi rentang waktu kerja kalender dan menambahkan pengecualian seperti hari libur. Anda dapat memanggil `taskCalendar.addWorkingTime()` atau `taskCalendar.addException()` untuk menyesuaikan jadwal sesuai kebijakan organisasi Anda. Ini berguna ketika jadwal default 9‑5 tidak mencerminkan realitas.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Task returns `null` for calendar** | Pastikan tugas benar‑benar memiliki kalender yang ditetapkan; jika tidak, ia akan mewarisi kalender default proyek. |
| **Incorrect duration because of holidays** | Verifikasi bahwa hari libur didefinisikan di kalender tugas atau di kalender dasar proyek. |
| **Time zone mismatch** | Gunakan `java.util.TimeZone` untuk menyelaraskan zona waktu kalender dengan sistem Anda jika diperlukan. |

## Frequently Asked Questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

## Conclusion
Dalam panduan ini kami menunjukkan cara **menentukan hari kerja**, **mengambil jam kerja**, dan **menghitung durasi tugas** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah di atas Anda dapat mengotomatisasi analisis jadwal, menyesuaikan kalender, dan menjaga rencana proyek tetap akurat serta up‑to‑date. Sekarang Anda memiliki alat untuk **membaca data MS Project**, **memuat file MPP**, dan melakukan perhitungan durasi yang tepat tanpa memerlukan Microsoft Project.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}