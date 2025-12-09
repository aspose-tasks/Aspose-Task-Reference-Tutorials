---
date: 2025-12-05
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

## Pendahuluan
Mengelola kalender proyek adalah bagian inti dari perencanaan proyek yang berhasil. Pada tutorial ini Anda akan **menentukan hari kerja** untuk tugas apa pun dan **mengekstrak jam kerja** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Pada akhir panduan Anda akan dapat **menghitung durasi tugas**, menyesuaikan jam kerja, dan dengan andal **memuat file MPP** untuk mengambil data yang Anda perlukan.

## Jawaban Cepat
- **Apa arti “menentukan hari kerja”?** Artinya mengidentifikasi tanggal kalender mana yang dianggap hari kerja untuk suatu tugas tertentu.  
- **Pustaka mana yang harus saya gunakan?** Asp.Tasks untuk Java menyediakan API lengkap untuk bekerja dengan file MS Project.  
- **Berapa lama implementasinya?** Biasanya 10–15 menit untuk ekstraksi dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan jam kerja?** Ya – Anda dapat memodifikasi kalender, menambahkan hari libur, dan mengatur rentang jam kerja khusus.

## Apa itu “menentukan hari kerja”?
Ketika sebuah tugas dijadwalkan, kalender proyek menentukan hari mana yang merupakan hari kerja dan mana yang bukan (akhir pekan, hari libur). Menentukan hari kerja berarti menanyakan kalender tersebut untuk mengetahui secara tepat kapan pekerjaan dapat dilakukan, yang penting untuk perhitungan **menghitung durasi tugas** yang akurat.

## Mengapa menggunakan Aspose.Tasks untuk mengambil jam kerja?
- **Tidak memerlukan Microsoft Project** – bekerja dengan file .MPP di platform apa pun.  
- **Dukungan kalender lengkap** – mencakup kalender default, sumber daya, dan tugas.  
- **Kinerja tinggi** – memproses proyek besar dengan cepat.  
- **Dokumentasi lengkap** – contoh dan referensi API tersedia dengan mudah.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari [di sini](https://releases.aspose.com/tasks/java/).  
3. Pengetahuan dasar pemrograman Java.  

## Mengimpor Paket
Pertama, impor namespace inti Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Langkah 1: Memuat file MPP
Muat file proyek Anda (langkah **memuat file mpp**) sehingga Anda dapat bekerja dengan kalendernya:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Langkah 2: Mengambil Informasi Tugas dan Kalender
Pilih tugas yang ingin Anda analisis dan dapatkan kalender yang terkait. Di sinilah kita **mengambil jam kerja** untuk tugas tersebut:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Langkah 3: Menentukan Tanggal Mulai dan Selesai
Atur jendela waktu untuk mana Anda ingin **menentukan hari kerja**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Langkah 4: Mengiterasi Tanggal
Loop melalui setiap tanggal dalam durasi tugas. Loop ini akan membantu kita **menyesuaikan jam kerja** nanti jika diperlukan:

```java
java.util.Calendar tempDate = calStartDate;
```

## Langkah 5: Menghitung Durasi
Selama iterasi kami memeriksa apakah setiap hari adalah hari kerja, menjumlahkan jam kerja, dan akhirnya menghitung durasi tugas dalam menit, jam, dan hari:

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

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Tugas mengembalikan `null` untuk kalender** | Pastikan tugas memang memiliki kalender yang ditetapkan; jika tidak, ia akan mewarisi kalender default proyek. |
| **Durasi tidak tepat karena hari libur** | Verifikasi bahwa hari libur didefinisikan di kalender tugas atau di kalender dasar proyek. |
| **Ketidaksesuaian zona waktu** | Gunakan `java.util.TimeZone` untuk menyelaraskan zona waktu kalender dengan sistem Anda jika diperlukan. |

## Pertanyaan yang Sering Diajukan
### Q: Bisakah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
A: Ya, Aspose.Tasks untuk Java menyediakan dukungan komprehensif untuk menangani struktur proyek yang kompleks, termasuk tugas, sumber daya, dan kalender.

### Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?
A: Tentu saja, Aspose.Tasks untuk Java mendukung berbagai versi MS Project, memastikan kompatibilitas di berbagai lingkungan.

### Q: Bisakah saya menyesuaikan jam kerja dan hari libur dalam kalender proyek?
A: Ya, Anda dapat dengan mudah menyesuaikan jam kerja dan hari libur sesuai kebutuhan proyek menggunakan API Aspose.Tasks untuk Java.

### Q: Apakah Aspose.Tasks untuk Java menawarkan dukungan dan dokumentasi?
A: Ya, Aspose.Tasks untuk Java menyediakan dokumentasi yang luas dan forum dukungan khusus untuk membantu pengembang memanfaatkan fiturnya secara efektif.

### Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk Java?
A: Ya, Anda dapat mengakses versi percobaan gratis Aspose.Tasks untuk Java dari [di sini](https://releases.aspose.com/).

## Kesimpulan
Dalam panduan ini kami menunjukkan cara **menentukan hari kerja**, **mengambil jam kerja**, dan **menghitung durasi tugas** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah di atas Anda dapat mengotomatiskan analisis jadwal, menyesuaikan kalender, dan menjaga rencana proyek Anda tetap akurat dan terkini.

---

**Terakhir Diperbarui:** 2025-12-05  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}