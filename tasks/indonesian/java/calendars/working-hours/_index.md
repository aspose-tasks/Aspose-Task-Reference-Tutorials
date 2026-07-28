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

## Perkenalan
Mengelola kalender proyek adalah bagian inti dari perencanaan proyek yang berhasil. Dalam tutorial ini Anda akan **menentukan hari kerja** untuk tugas apa pun dan **mengekstrak jam kerja** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Pada akhir panduan Anda akan dapat **menghitung durasi tugas**, menyesuaikan jam kerja, dan secara andal **memuat file MPP** untuk mengambil data yang Anda perlukan. Anda juga akan melihat cara **membaca file MS Project** tanpa harus menginstal Microsoft Project, sehingga otomatisasi dapat dilakukan di platform apa pun.

## Jawaban Cepat
- **Apa arti “menentukan hari kerja”?**Artinya mengidentifikasi tanggal kalender yang dianggap hari kerja untuk suatu tugas tertentu.
- **Perpustakaan mana yang harus saya gunakan?**Aspose.Tasks untuk Java menyediakan API lengkap untuk bekerja dengan file MS Project.
- **Berapa lama implementasinya?**Biasanya 10–15menit untuk ekstraksi dasar.
- **Apakah saya memerlukan lisensi?**Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.
- ** bisakah saya menyesuaikan jam kerja?**Ya – Anda dapat memodifikasi kalender, menambahkan hari libur, dan mengatur rentang waktu kerja khusus.

## Apa yang dimaksud dengan “menentukan hari kerja”?
Ketika sebuah tugas dijadwalkan, kalender proyek menentukan hari mana yang merupakan hari kerja dan mana yang bukan (akhir pekan, hari libur). Menentukan hari kerja berarti menanyakan kalender tersebut untuk mengetahui secara tepat kapan pekerjaan dapat dilakukan, yang penting untuk perhitungan **menghitung durasi tugas** yang akurat.

## Mengapa menggunakan Aspose.Tasks untuk mengambil jam kerja?
- **Tidak memerlukan Microsoft Project** – Anda dapat membaca file MS Project langsung dari kode Java.
- **Dukungan kalender lengkap** – mencakup kalender default, sumber daya, dan tugas.
- **Kinerja tinggi** – memproses proyek besar dengan cepat.
- **Dokumentasi lengkap** – contoh dan referensi API tersedia secara mudah.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari [di sini](https://releases.aspose.com/tasks/java/).
3. Pengetahuan dasar pemrograman Java.

## Impor Paket
Pertama, impor namespace ke Aspose.Tugas:

```java
import com.aspose.tasks.*;
```

## Cara memuat file MPP dengan Aspose.Tasks?
Memuat file proyek adalah langkah pertama untuk analisis kalender apa pun. API memungkinkan Anda **memuat file MPP** dalam satu baris kode, tanpa memerlukan UI MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Mengambil Informasi Tugas dan Kalender
Pilih tugas yang ingin Anda analisis dan dapatkan kalender yang terkait. Di sinilah kita **mengambil jam kerja** untuk tugas tersebut:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Menentukan Tanggal Mulai dan Akhir
Atur jendela waktu untuk **menentukan hari kerja** yang Anda inginkan. Menggunakan tanggal mulai dan selesai tugas memastikan Anda hanya mengevaluasi periode yang relevan.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Mengulang Tanggal
Loop melalui setiap tanggal dalam durasi tugas. Loop ini akan membantu kita **menyesuaikan jam kerja** nanti jika diperlukan:

```java
java.util.Calendar tempDate = calStartDate;
```

## Menghitung Durasi
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

## Cara menyesuaikan jam kerja dan hari libur
Aspose.Tasks memungkinkan Anda memodifikasi rentang waktu kerja kalender dan menambahkannya seperti hari libur. Anda dapat memanggil `taskCalendar.addWorkingTime()` atau `taskCalendar.addException()` untuk menyesuaikan jadwal sesuai kebijakan organisasi Anda. Ini berguna ketika jadwal default 9‑5 tidak mencerminkan kenyataan.

## Masalah Umum dan Solusinya
| Edisi | Solusi |
|-------|----------|
| **Tugas mengembalikan `null` untuk kalender** | Pastikan tugas benar‑benar memiliki kalender yang ditetapkan; jika tidak, ia akan mewarisi proyek default kalender. |
| **Durasi salah karena hari libur** | Verifikasi bahwa hari libur ditentukan di kalender tugas atau di kalender dasar proyek. |
| **Ketidakcocokan zona waktu** | Gunakan `java.util.TimeZone` untuk menyelaraskan zona waktu kalender dengan sistem Anda jika diperlukan. |

## Pertanyaan yang Sering Diajukan
### T: Dapatkah Aspose.Tasks for Java menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks for Java menyediakan dukungan komprehensif untuk menangani struktur proyek yang kompleks, termasuk tugas, sumber daya, dan kalender.

### T: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi MS Project?
J: Tentu saja, Aspose.Tasks for Java mendukung berbagai versi MS Project, memastikan kompatibilitas di berbagai lingkungan.

### T: Dapatkah saya menyesuaikan jam kerja dan hari libur di kalender proyek?
J: Ya, Anda dapat dengan mudah menyesuaikan jam kerja dan hari libur sesuai dengan kebutuhan proyek Anda menggunakan API Aspose.Tasks for Java.

### T: Apakah Aspose.Tasks for Java menawarkan dukungan dan dokumentasi?
J: Ya, Aspose.Tasks for Java menyediakan dokumentasi yang ekstensif dan forum dukungan khusus untuk membantu pengembang dalam memanfaatkan fitur-fiturnya secara efektif.

### T: Apakah tersedia versi uji coba untuk Aspose.Tasks for Java?

J: Ya, Anda dapat mengakses Aspose.Tasks versi uji coba gratis untuk Java dari [di sini](https://releases.aspose.com/).

## Kesimpulan
Dalam panduan ini kami menunjukkan cara **menentukan hari kerja**, **mengambil jam kerja**, dan **menghitung durasi tugas** dari kalender MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah di atas Anda dapat mengotomatisasi analisis jadwal, menyesuaikan kalender, dan menjaga rencana proyek tetap akurat serta terkini. Sekarang Anda memiliki alat untuk **membaca data MS Project**, **memuat file MPP**, dan melakukan perhitungan durasi yang tepat tanpa memerlukan Microsoft Project.

---

**Terakhir Diperbarui:** 05-02-2026
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru pada saat penulisan)
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}