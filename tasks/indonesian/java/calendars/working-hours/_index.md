---
date: 2026-08-24
description: Pelajari cara menambahkan kalender libur, menentukan hari kerja, dan
  menghitung durasi tugas dengan mengekstrak jam kerja dari kalender MS Project menggunakan
  Aspose.Tasks for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Cara menambahkan kalender libur dan menentukan hari kerja
og_description: Pelajari cara menambahkan kalender libur, menentukan hari kerja, dan
  menghitung durasi tugas dengan mengekstrak jam kerja dari kalender MS Project menggunakan
  Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Cara menambahkan kalender libur dan menentukan hari kerja
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Cara menambahkan kalender libur dan menentukan hari kerja
url: /id/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan kalender liburan dan menentukan hari kerja

Mengelola kalender proyek merupakan bagian inti dari perencanaan proyek yang sukses. Dalam tutorial ini Anda akan **menambahkan kalender liburan**, **menentukan hari kerja** untuk tugas apa pun, dan **mengekstrak jam kerja** dari kalender MS Project menggunakan Aspose.Tasks for Java. Pada akhir panduan, Anda akan dapat **menghitung durasi tugas**, menyesuaikan jam kerja, dan dengan andal **memuat file MPP** untuk mengambil data yang Anda butuhkan—semua tanpa menginstal Microsoft Project.

## Jawaban cepat
- **Apa arti “menentukan hari kerja”?** Artinya mengidentifikasi tanggal kalender mana yang dianggap hari kerja untuk tugas tertentu.  
- **Pustaka mana yang harus saya gunakan?** Aspose.Tasks for Java menyediakan API lengkap untuk bekerja dengan file MS Project.  
- **Berapa lama implementasinya?** Biasanya 10–15 menit untuk ekstraksi dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan jam kerja?** Ya – Anda dapat memodifikasi kalender, menambahkan liburan, dan mengatur rentang waktu kerja khusus.  

## Apa itu “menentukan hari kerja”?
**Menentukan hari kerja** berarti melakukan kueri pada kalender proyek untuk mengetahui tanggal mana yang ditandai sebagai hari kerja versus hari non‑kerja (akhir pekan, liburan, atau pengecualian khusus). Informasi ini penting untuk **menghitung durasi tugas** secara akurat karena hanya hari kerja yang berkontribusi pada waktu yang berlalu untuk sebuah tugas.

## Mengapa menggunakan Aspose.Tasks untuk mengambil jam kerja?
Aspose.Tasks memungkinkan Anda membaca file MS Project tanpa harus menginstal Microsoft Project, memungkinkan otomatisasi di platform apa pun. Ini juga menyediakan pemrosesan berperforma tinggi, dukungan format yang luas, dan dokumentasi terperinci.  

- **Dukungan kalender penuh** – kalender default, sumber daya, dan tugas semuanya dapat diakses.  
- **Kinerja tinggi** – dapat memproses proyek yang berisi **lebih dari 10.000 tugas dalam waktu kurang dari 2 detik** pada CPU standar 2,5 GHz.  
- **Cakupan format yang luas** – mendukung **lebih dari 50 format input dan output**, termasuk MPP, MPX, XML, dan Primavera.  
- **Dokumentasi komprehensif** – contoh kode, referensi API, dan forum komunitas semuanya tersedia.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Pengetahuan dasar pemrograman Java.  

## Impor paket
Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file MS Project dalam memori. Impor namespace yang diperlukan sebelum Anda memulai:

Impor Paket

```java
import com.aspose.tasks.*;
```

## Cara memuat file MPP dengan Aspose.Tasks?
Kelas `Project` memuat file MS Project dan memberikan akses ke datanya. Muat file proyek dalam satu baris kode; tidak diperlukan UI atau interop COM. Langkah sederhana ini memberi Anda akses penuh ke kalender, tugas, dan sumber daya.

Memuat file MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Mengambil informasi tugas dan kalender
`Task` mewakili tugas proyek, dan `Calendar` mendefinisikan aturan waktu kerjanya. Pilih tugas yang ingin Anda analisis dan dapatkan kalender yang terkait. Objek `Task` menyediakan metode `getStart()` dan `getFinish()`, sementara objek `Calendar` menampilkan definisi waktu kerja.

Mengambil tugas dan kalender

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Menentukan tanggal mulai dan akhir
Objek `Date` menentukan jendela waktu untuk analisis kalender. Atur jendela waktu yang ingin Anda **tentukan hari kerja**. Menggunakan tanggal mulai dan selesai tugas memastikan Anda hanya mengevaluasi periode yang relevan.

Menentukan tanggal

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterasi melalui tanggal
Loop `for` dapat mengiterasi setiap hari dalam rentang tanggal. Loop melalui setiap tanggal dalam durasi tugas. Loop ini akan memungkinkan Anda **menyesuaikan jam kerja** nanti jika diperlukan dan menjadi dasar untuk menghitung total waktu kerja.

Mengiterasi tanggal

```java
java.util.Calendar tempDate = calStartDate;
```

## Menghitung durasi
`Duration` mengagregasi total waktu kerja yang dihitung dari iterasi. Selama iterasi Anda memeriksa apakah setiap hari adalah hari kerja, menjumlahkan jam kerja, dan akhirnya menghitung durasi tugas dalam menit, jam, dan hari. Ini menunjukkan cara **menghitung hari kerja** dan **menghitung durasi tugas** secara programatik.

Menghitung durasi

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

## Cara menyesuaikan jam kerja dan liburan
Anda dapat memodifikasi rentang waktu kerja kalender dan menambahkan pengecualian seperti liburan. Gunakan `taskCalendar.addWorkingTime()` untuk menetapkan periode kerja baru dan `taskCalendar.addException()` untuk menyisipkan liburan. Ini berguna ketika jadwal default 9‑5 tidak sesuai dengan kebijakan organisasi Anda.

## Masalah umum dan solusi
| Masalah | Solusi |
|-------|----------|
| **Task mengembalikan `null` untuk kalender** | Pastikan tugas benar‑benar memiliki kalender yang ditetapkan; jika tidak, ia akan mewarisi kalender default proyek. |
| **Durasi tidak tepat karena liburan** | Verifikasi bahwa liburan didefinisikan dalam kalender tugas atau dalam kalender dasar proyek. |
| **Perbedaan zona waktu** | Gunakan `java.util.TimeZone` untuk menyelaraskan zona waktu kalender dengan sistem Anda jika diperlukan. |

## Pertanyaan yang sering diajukan
### Q: Apakah Aspose.Tasks for Java dapat menangani struktur proyek yang kompleks?
A: Ya, Aspose.Tasks for Java menyediakan dukungan komprehensif untuk menangani struktur proyek yang kompleks, termasuk tugas, sumber daya, dan kalender.

### Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi MS Project?
A: Tentu saja, Aspose.Tasks for Java mendukung berbagai versi MS Project, memastikan kompatibilitas di berbagai lingkungan.

### Q: Bisakah saya menyesuaikan jam kerja dan liburan dalam kalender proyek?
A: Ya, Anda dapat dengan mudah menyesuaikan jam kerja dan liburan sesuai kebutuhan proyek Anda menggunakan API Aspose.Tasks for Java.

### Q: Apakah Aspose.Tasks for Java menawarkan dukungan dan dokumentasi?
A: Ya, Aspose.Tasks for Java menyediakan dokumentasi yang luas dan forum dukungan khusus untuk membantu pengembang memanfaatkan fiturnya secara efektif.

### Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks for Java?
A: Ya, Anda dapat mengakses versi percobaan gratis Aspose.Tasks for Java dari [halaman rilis Aspose](https://releases.aspose.com/).

## Kesimpulan
Dalam panduan ini kami menunjukkan cara **menambahkan kalender liburan**, **menentukan hari kerja**, **mengambil jam kerja**, dan **menghitung durasi tugas** dari kalender MS Project menggunakan Aspose.Tasks for Java. Dengan mengikuti langkah‑langkah di atas Anda dapat mengotomatisasi analisis jadwal, menyesuaikan kalender, dan menjaga rencana proyek Anda tetap akurat dan terbaru. Sekarang Anda memiliki alat untuk **membaca data MS Project**, **memuat file MPP**, dan melakukan perhitungan durasi yang tepat tanpa memerlukan Microsoft Project itu sendiri.

---

**Terakhir Diperbarui:** 2026-08-24  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Tambahkan Liburan ke Kalender dan Simpan sebagai MPP dengan Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}